---
title: Extension Flags pour le guide d’intégration d’iOS
description: Découvrez comment intégrer l’extension Flags à Adobe Experience Platform Mobile SDK sur iOS.
badge: label="Version bêta" type="Informative"
hide: true
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 5%

---

# Extension Flags pour iOS {#ios-extension-integration-guide}

Ce guide décrit comment intégrer l’extension Flags à Adobe Experience Platform Mobile SDK sur iOS.

## Conditions préalables {#prerequisites}

Avant d’implémenter l’extension Flags, vérifiez que vous disposez des éléments suivants :

* Propriété mobile configurée dans la collecte de données Adobe Experience Platform [&#128279;](https://experience.adobe.com/#/data-collection)
* Extension Flags installée et configurée dans votre propriété mobile
* Un identifiant d’organisation Adobe Experience Cloud
* Cible de déploiement minimale : iOS 12.0

## Dépendances d’extension {#extension-dependencies}

L’extension Flags nécessite les extensions Adobe Experience Platform suivantes :

| Extension | Description | Requis |
|---|---|---|
| Mobile Core | Fournit des fonctionnalités de base, notamment la configuration et le traitement des événements | Oui |
| Cycle de vie | Collecte les données de session et de cycle de vie des applications pour Mobile SDK | Oui |
| Edge Network | Permet la communication avec Adobe Experience Platform Edge Network. | Oui |
| Identité Edge | Active la gestion des identités à partir d’une application mobile lors de l’utilisation de l’extension Edge Network | Oui |

Assurez-vous que ces extensions sont installées dans votre propriété mobile de collecte de données et incluses dans vos dépendances d’application.

## Configurer l’extension Flags dans la collecte de données {#configure}

### Installation de l’extension {#install-extension}

1. Connectez-vous à [Collecte de données &#x200B;](https://experience.adobe.com/#/data-collection).
1. Sélectionnez l’onglet **Balises** et choisissez votre propriété mobile.
1. Accédez à **Extensions** > **Catalogue**.
1. Recherchez **Extension Flags** et sélectionnez **Installer**.
1. Configurez les paramètres d’extension :

   | Paramètre | Description |
   |---|---|
   | ID d’application | Identifiant unique de votre application dans Flags |

1. Sélectionnez **Enregistrer**.
1. Suivez le [processus de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview) pour mettre à jour votre configuration.

### Obtention de l’identifiant du fichier d’environnement {#environment-file-id}

1. Dans votre propriété mobile, accédez à **Environnements**.
1. Sélectionnez l’icône en forme de boîte sous la colonne **Installer** pour votre environnement.
1. Dans la boîte de dialogue **Instructions d’installation mobile**, copiez le **ID du fichier d’environnement**.

## Ajouter l’extension Flags à votre application {#add-to-app}

### Ajouter des dépendances {#add-dependencies}

Ajoutez les dépendances Mobile SDK à votre projet. L’extension Flags nécessite Mobile Core et les extensions associées à Edge répertoriées ci-dessous.

#### Utilisation Du Gestionnaire De Packages Swift {#swift-package-manager}

Dans Xcode, sélectionnez **Fichier** > **Ajouter des packages** et ajoutez les URL de package Adobe Experience Platform Mobile SDK suivantes :

| Package | URL |
|---|---|
| AEPCore | `https://github.com/adobe/aepsdk-core-ios.git` |
| AEPEdge | `https://github.com/adobe/aepsdk-edge-ios.git` |
| AEPdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios.git` |

Lorsque vous y êtes invité, sélectionnez les bibliothèques suivantes à ajouter à votre cible :

* `AEPCore`, `AEPLifecycle` (à partir de `aepsdk-core-ios`)
* `AEPEdge` (de `aepsdk-edge-ios`)
* `AEPEdgeIdentity` (de `aepsdk-edgeidentity-ios`)

Utilisez la version 5.8.0 ou ultérieure d’AEPCore.

>[!NOTE]
>
>Lors de l’ajout d’un package dans Xcode, choisissez une règle de dépendance pour chaque package (par exemple, **Jusqu’à la prochaine version majeure**), qui sélectionne automatiquement les nouvelles versions mineures et de correctifs tout en excluant la version majeure suivante. Pour connaître les dernières versions publiées, consultez la page versions de chaque extension sur GitHub.

### Ajout du package Indicateurs {#add-flags-package}

Utilisez le package Swift ou la méthode d&#39;intégration XCFrframework pour une cible d&#39;application, mais pas les deux.

#### Pour un projet Xcode sans fichier Package.swift {#xcode-project}

1. Dans Xcode, sélectionnez **Fichier** > **Ajouter des packages**.
1. Sélectionnez **Ajouter local**.
1. Sélectionnez le répertoire de `Packages/AEPFlags` fourni qui contient `Package.swift`.
1. Ajoutez la bibliothèque `AEPFlags` à la cible de l’application.

Xcode stocke la référence du package local dans le projet, de sorte que votre application n’a pas besoin de son propre fichier `Package.swift`.

#### Pour un projet avec un fichier Package.swift {#package-swift-project}

Dans votre manifeste existant, ajoutez des `AEPFlags` aux dépendances de la cible de votre application et ajoutez la cible binaire à l’aide de l’URL et de la somme de contrôle du manifeste fourni :

```swift
targets: [
    .target(
        name: "YourApp",
        dependencies: [
            "AEPFlags"
        ]
    ),
    .binaryTarget(
        name: "AEPFlags",
        url: "<AEPFlags binary URL>",
        checksum: "<AEPFlags binary checksum>"
    )
]
```

Le gestionnaire de packages Swift résout la cible binaire pour les versions locales Xcode, CI et d&#39;archive.

#### Ajouter directement le framework XCF {#xcframework}

Vous pouvez également faire glisser le `AEPFlags.xcframework` fourni dans le navigateur de projet Xcode et l’ajouter à la cible de votre application. Sous **Général** > **Frameworks, bibliothèques et contenu incorporé**, définissez le framework sur **Incorporer et signer**.

### Initialiser le SDK {#initialize-sdk}

Enregistrez les extensions Mobile SDK dans votre `AppDelegate` avant d’appeler les API Flags. Enregistrez le `Flag` après Identité, Edge et Cycle de vie, puis configurez le SDK à l’aide de l’identifiant du fichier d’environnement de votre propriété mobile.

#### Enregistrement et configuration des extensions {#register-configure}

>[!IMPORTANT]
>
>Pour les applications de production, utilisez `.error` niveau de journal uniquement ; n’utilisez pas `.debug` ou `.trace` dans les versions.

**Swift**

```swift
// AppDelegate.swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import UIKit

final class AppDelegate: NSObject, UIApplicationDelegate {

    func application(_: UIApplication,
                      didFinishLaunchingWithOptions _: [UIApplication.LaunchOptionsKey: Any]? = nil) -> Bool {
        // Production: use .error only. Do not use .debug or .trace in release builds.
        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions([
            Identity.self,
            Edge.self,
            Lifecycle.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
            MobileCore.lifecycleStart(additionalContextData: nil)
        }

        return true
    }
}
```

**Objectif-C**

```objc
// AppDelegate.m
#import "AppDelegate.h"
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    // Production: use AEPLogLevelError only. Do not use Debug or Trace in release builds.
    [AEPMobileCore setLogLevel:AEPLogLevelError];

    [AEPMobileCore registerExtensions:@[
        AEPMobileEdgeIdentity.class,
        AEPMobileEdge.class,
        AEPMobileLifecycle.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
        [AEPMobileCore lifecycleStart:nil];
    }];

    return YES;
}

@end
```

## Contexte d’évaluation {#evaluation-context}

`FeatureEvaluationContext` inclut les attributs de ciblage (utilisés pour la correspondance des règles d’indicateur).

| Paramètre | Requis | Description |
|---|---|---|
| `attributes` | Non | `[String: [String]]`. Clé est le nom de l’attribut de contexte utilisé par vos règles d’indicateur (par exemple `locale`, `platform`, `appVersion`, `deviceType`). Valeur est la liste des valeurs d’attribut candidates pour cette clé pour l’utilisateur/la session en cours (par exemple `["en_US"]` ou `["phone"]`). |

**Swift**

```swift
import AEPFlags

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Objectif-C**

```objc
@import AEPFlags;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContextBuilder *builder = [AEPFeatureEvaluationContext builder];
AEPFeatureEvaluationContext *ctx = [[builder withAttributes:attrs] build];
```

### Exemples d’attributs de ciblage {#sample-attributes}

| Attribut | Description | Exemples de valeurs |
|---|---|---|
| `locale` | Paramètres régionaux/langue de l’utilisateur | `["en_US"]`, `["fr_FR"]` |
| `platform` | Identifiant de plateforme | `["IOS"]` |
| `appVersion` | Version de l’application | `["3.0.0"]` |
| `deviceType` | Type de périphérique | `["phone"]`, `["tablet"]` |

### Identité personnalisée {#custom-identity}

L’extension Flags utilise l’extension Identity for Edge Network pour la résolution d’identité. Un indicateur de fonctionnalité peut être associé à une identité personnalisée (par exemple, un identifiant CRM ou un identifiant de fidélité) afin que les divisions de variantes et les analyses soient liées à l’identité qui importe pour votre application.

L’espace de noms d’identité personnalisée doit être sélectionné dans l’interface utilisateur des indicateurs lorsque l’indicateur de fonctionnalité est créé. Pour évaluer un indicateur par rapport à cette identité, la même identité doit être présente dans le `identityMap` d’identité Edge sur l’appareil, à l’aide de l’espace de noms correspondant. Fournissez-le au moment de l’exécution avec l’API Identity for Edge Network `updateIdentities`.

#### Ajouter l’identité personnalisée au mappage d’identités {#add-identity}

Ajoutez l’identité sous le même espace de noms configuré sur l’indicateur de fonctionnalité.

**Swift**

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
                 withNamespace: "userCRMId") // must match the namespace configured on the feature flag
Identity.updateIdentities(with: identityMap)
```

**Objectif-C**

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc]
    initWithId:@"1111"
    authenticatedState:AEPAuthenticatedStateAuthenticated
    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

## Référence d’API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` indique si la fonction Indicateurs est activée ou désactivée pour le contexte donné. Transmettez des `featureKey`, une `FeatureEvaluationContext` (attributs de ciblage facultatifs) et une fermeture complète. Voir [&#x200B; Contexte d’évaluation &#x200B;](#evaluation-context).

**Signature**

*Swift*

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objectif-C*

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
               completion:(void (^)(BOOL))completion;
```

**Paramètres**

| Paramètre | Type | Description |
|---|---|---|
| `featureKey` | Chaîne | Clé de fonctionnalité à évaluer dans Flags |
| `evaluationContext` | FeatureEvaluationContext | Incluez les attributs de ciblage selon vos besoins ; utilisez `FeatureEvaluationContext.builder().build()` pour un contexte vide. Voir [&#x200B; Contexte d’évaluation &#x200B;](#evaluation-context). |
| `completion` | `(Bool) -> Void` | Appelé avec `true` si la fonctionnalité est activée, `false` dans le cas contraire. |

**Exemples**

*Swift*

```swift
import AEPFlags

Flag.isFeatureEnabled(
    "new-flag",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}
```

*Objectif-C*

```objc
@import AEPFlags;

[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}];
```

### getFeature {#get-feature}

`getFeature` renvoie la payload de fonction évaluée pour le contexte fourni. Utilisez cette API lorsque vous avez besoin de plus que activés/désactivés et que vous souhaitez obtenir des métadonnées ou des valeurs de fonctionnalités.

**Signature**

*Swift*

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objectif-C*

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion;
```

**Paramètres**

| Paramètre | Type | Description |
|---|---|---|
| `featureKey` | Chaîne | Clé de fonctionnalité à évaluer dans Flags |
| `evaluationContext` | FeatureEvaluationContext | Incluez les attributs de ciblage selon vos besoins ; utilisez `FeatureEvaluationContext.builder().build()` pour un contexte vide. Voir [&#x200B; Contexte d’évaluation &#x200B;](#evaluation-context). |
| `completion` | `(FeatureEvaluationResult?) -> Void` | Appelé avec la payload de la fonctionnalité évaluée ; `nil` lorsque la fonctionnalité est introuvable. |

**Réponse**

*FeatureEvaluationResult*

| Champ | Type | Description |
|---|---|---|
| `id` | Int | Identifiant numérique de la caractéristique |
| `key` | Chaîne | Clé de fonctionnalité |
| `featureGroupKey` | Chaîne ? | Clé du groupe de fonctionnalités si disponible |
| `meta` | Chaîne ? | Métadonnées de fonction opaques, le cas échéant |
| `analyticsParam` | AnalyticsParam ? | Détails Analytics pour la fonctionnalité évaluée |

*AnalyticsParam*

| Champ | Type | Description |
|---|---|---|
| `featureGroupId` | Int | Identifiant numérique du groupe de caractéristiques |
| `featureId` | Int | Identifiant numérique de la caractéristique |
| `variantId` | Chaîne ? | Identifiant de la variante |

**Exemples**

*Swift*

```swift
import AEPFlags

Flag.getFeature(
    "new-flag",
    evaluationContext: ctx
) { feature in
    guard let meta = feature?.meta, !meta.isEmpty else {
        // No metadata available: fall back to the default behavior
        return
    }
    // Feature metadata is available: use it to drive the feature behavior
}
```

*Objectif-C*

```objc
@import AEPFlags;

[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta.length > 0) {
        // Feature metadata is available: use it to drive the feature behavior
    } else {
        // No metadata available: fall back to the default behavior
    }
}];
```

### extensionVersion {#extension-version}

Renvoie la chaîne de version de l’extension Flags.

**Syntaxe**

*Swift*

```swift
static var extensionVersion: String
```

*Objectif-C*

```objc
+ (nonnull NSString *)flagExtensionVersion;
```

**Exemple &#x200B;**

*Swift*

```swift
let version = Flag.extensionVersion
```

*Objectif-C*

```objc
NSString *version = [AEPMobileFlag flagExtensionVersion];
```

## Résumé des API {#api-summary}

| Visiteur | Retours |
|---|---|
| `isFeatureEnabled(_:evaluationContext:completion:)`. `FeatureEvaluationContext` transfère les attributs de ciblage pour les règles. Voir [isFeatureEnabled](#is-feature-enabled). | Booléen via la fermeture d&#39;achèvement |
| `getFeature(_:evaluationContext:completion:)`. Renvoie la payload de fonction évaluée pour le contexte donné. Voir [getFeature](#get-feature). | FeatureEvaluationResult ? fermeture du via |
| `extensionVersion` | Chaîne |

## Voir également {#see-also}

* [Applications mobiles](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)
* [Guide d’intégration de l’extension Android](../android/android-extension-integration-guide.md)

<!-- -->
