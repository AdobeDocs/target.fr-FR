---
title: Extension Flags pour le guide d’intégration d’iOS
description: Découvrez comment intégrer l’extension Flags à Adobe Experience Platform Mobile SDK sur iOS.
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 3%
---
# Extension Flags pour iOS {#ios-extension-integration-guide}

Ce guide décrit comment intégrer l’extension Flags à Adobe Experience Platform Mobile SDK sur iOS. Le code source est disponible dans le référentiel [aepsdk-flags-ios](https://github.com/adobe/aepsdk-flags-ios).

## Conditions préalables {#prerequisites}

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* iOS 12.0 ou version ultérieure et Swift 5.7 ou version ultérieure
* Propriété mobile dans la collecte de données [&#128279;](https://experience.adobe.com/#/data-collection)
* Ces extensions sont installées et configurées dans la propriété mobile :

  | Extension | Description | Version minimale de SDK |
  |---|---|---|
  | [&#x200B; Mobile Core &#x200B;](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | Configuration et traitement des événements | AEPCore 5.8.0 |
  | [Cycle de vie](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | Données de cycle de vie de l’application | Identique à AEPCore |
  | [&#128279;](https://developer.adobe.com/client-sdks/edge/edge-network/) | Communication avec Adobe Experience Platform Edge Network. Nécessite un flux de données. | AEPEdge 5.0.2 |
  | [&#x200B; Identité pour Edge Network &#x200B;](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | Identity Management pour Edge Network | AEPEdgeIdentity 5.0.0 |
  | [Indicateurs](https://experienceleague.adobe.com/fr/docs/target/flags/home) | Évaluation de l’indicateur de fonctionnalité | Voir [&#x200B; Installation &#x200B;](#installation) |

## Configurer les indicateurs dans la collecte de données {#configure}

### Installation de l’extension {#install-extension}

1. Connectez-vous à [Collecte de données &#x200B;](https://experience.adobe.com/#/data-collection).

1. Sélectionnez le menu **[!UICONTROL Balises]** et choisissez votre propriété mobile.

1. Accédez à **[!UICONTROL Extensions]** > **[!UICONTROL Catalogue]**.

1. Recherchez **[!DNL Adobe Flags]** et sélectionnez **[!UICONTROL Installer]**.

   ![](../assets/extension-install.png)

1. Configurez les paramètres d’extension :

   * **[!UICONTROL Sandbox]** : sandbox Adobe Experience Platform contenant votre configuration Indicateurs.
   * **[!UICONTROL Identifiant de l’application]** : l’identifiant de votre application dans Flags.

1. Sélectionnez **[!UICONTROL Enregistrer]**.

1. Suivez le [processus de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview) pour mettre à jour votre configuration.

### Obtention de l’identifiant du fichier d’environnement {#environment-file-id}

1. Dans votre propriété mobile, accédez à **[!UICONTROL Environnements]**.

1. Sélectionnez l’icône en forme de boîte dans la colonne **[!UICONTROL Installer]** de l’environnement sélectionné.

   ![](../assets/extension-install-2.png)

1. Dans la boîte de dialogue **[!UICONTROL Instructions d’installation mobile]**, copiez le **[!UICONTROL ID du fichier d’environnement]**.

   ![](../assets/extension-install-3.png)

## Installation {#installation}

Ajoutez l’extension avec le gestionnaire de packages Swift ou un framework XCF. Utilisez une méthode par cible d’application.

### Gestionnaire de packages Swift {#swift-package-manager}

Dans Xcode :

1. Sélectionnez **Fichier** > **Ajouter des dépendances de package**.

1. Saisissez l’URL du package : `https://github.com/adobe/aepsdk-flags-ios.git`

1. Pour la règle de version, sélectionnez **Version exacte** et saisissez la dernière version à partir de la page [&#x200B; versions](https://github.com/adobe/aepsdk-flags-ios/releases).

1. Ajoutez la bibliothèque `AEPFlags` à la cible de l’application.

1. Ajoutez les packages Adobe dont dépend l’extension et ajoutez leurs bibliothèques à la cible de votre application :

   * `https://github.com/adobe/aepsdk-core-ios.git` : `AEPCore`, `AEPLifecycle` et `AEPServices`
   * `https://github.com/adobe/aepsdk-edge-ios.git`: `AEPEdge`
   * `https://github.com/adobe/aepsdk-edgeidentity-ios.git`: `AEPEdgeIdentity`

Si votre projet utilise un fichier `Package.swift`, ajoutez-y les dépendances. Remplacez `<latest-version>` par la dernière version de la page Versions.

```swift
dependencies: [
    .package(url: "https://github.com/adobe/aepsdk-flags-ios.git", exact: "<latest-version>"),
    .package(url: "https://github.com/adobe/aepsdk-core-ios.git", .upToNextMajor(from: "5.8.0")),
    .package(url: "https://github.com/adobe/aepsdk-edge-ios.git", .upToNextMajor(from: "5.0.2")),
    .package(url: "https://github.com/adobe/aepsdk-edgeidentity-ios.git", .upToNextMajor(from: "5.0.0"))
],
targets: [
    .target(
        name: "YourTarget",
        dependencies: [
            .product(name: "AEPFlags", package: "aepsdk-flags-ios"),
            .product(name: "AEPCore", package: "aepsdk-core-ios"),
            .product(name: "AEPLifecycle", package: "aepsdk-core-ios"),
            .product(name: "AEPServices", package: "aepsdk-core-ios"),
            .product(name: "AEPEdge", package: "aepsdk-edge-ios"),
            .product(name: "AEPEdgeIdentity", package: "aepsdk-edgeidentity-ios")
        ]
    )
]
```

### XCFrframework {#xcframework}

1. Dans la [page versions](https://github.com/adobe/aepsdk-flags-ios/releases), téléchargez `AEPFlags-<version>.xcframework.zip` et décompressez-la.

1. Téléchargez les XCFrameworks dont dépend l’extension à partir de la page des versions de chaque référentiel :

   * [versions d’aepsdk-core-ios](https://github.com/adobe/aepsdk-core-ios/releases) : `AEPCore`, `AEPServices`, `AEPLifecycle` et `AEPRulesEngine`
   * [versions d’aepsdk-edge-ios](https://github.com/adobe/aepsdk-edge-ios/releases) : `AEPEdge`
   * [versions aepsdk-edgeidentity-ios](https://github.com/adobe/aepsdk-edgeidentity-ios/releases) : `AEPEdgeIdentity`

1. Dans Xcode, sélectionnez la cible de l’application, puis ouvrez **Général** > **Frameworks, bibliothèques et contenu incorporé**.

1. Ajoutez `AEPFlags.xcframework` et tous les XCFrameworks dépendants.

1. Définissez chaque framework sur **Incorporer et signer**.

## Initialiser le SDK {#initialize-sdk}

Enregistrez l’extension Flags, puis initialisez le SDK avec l’ID de fichier d’environnement de votre propriété mobile. `MobileCore.initialize` n’enregistre pas l’extension Flags pour vous, enregistrez-la d’abord.

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
import AEPCore
import AEPFlags
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([Flag.self])
        MobileCore.initialize(appId: "<your-environment-file-id>")
        return true
    }
}
```

>[!TAB Objectif-C]

```objc
@import AEPCore;
@import AEPFlags;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[AEPMobileFlag.class] completion:nil];
    [AEPMobileCore initializeWithAppId:@"<your-environment-file-id>" completion:nil];
    return YES;
}
```

>[!ENDTABS]

### Enregistrement manuel des extensions {#register-manually}

Si vous enregistrez des extensions vous-même, enregistrez-les toutes. Appelez `MobileCore.lifecycleStart` lorsque l’application entre en premier plan et `MobileCore.lifecyclePause` lorsqu’elle entre en arrière-plan.

Si votre application utilise des scènes, effectuez plutôt ces appels dans `sceneWillEnterForeground(_:)` et `sceneDidEnterBackground(_:)`.

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
import AEPCore
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import AEPLifecycle
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([
            Lifecycle.self,
            Edge.self,
            AEPEdgeIdentity.Identity.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "<your-environment-file-id>")
            DispatchQueue.main.async {
                if application.applicationState != .background {
                    MobileCore.lifecycleStart(additionalContextData: nil)
                }
            }
        }
        return true
    }

    func applicationWillEnterForeground(_ application: UIApplication) {
        MobileCore.lifecycleStart(additionalContextData: nil)
    }

    func applicationDidEnterBackground(_ application: UIApplication) {
        MobileCore.lifecyclePause()
    }
}
```

>[!TAB Objectif-C]

```objc
@import AEPCore;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;
@import AEPLifecycle;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"<your-environment-file-id>"];
        dispatch_async(dispatch_get_main_queue(), ^{
            if (application.applicationState != UIApplicationStateBackground) {
                [AEPMobileCore lifecycleStart:nil];
            }
        });
    }];
    return YES;
}

- (void)applicationWillEnterForeground:(UIApplication *)application {
    [AEPMobileCore lifecycleStart:nil];
}

- (void)applicationDidEnterBackground:(UIApplication *)application {
    [AEPMobileCore lifecyclePause];
}
```

>[!ENDTABS]

## Contexte d’évaluation {#evaluation-context}

Chaque appel d’évaluation prend un `FeatureEvaluationContext`. Il contient les attributs utilisés par les règles de ciblage de vos indicateurs.

| Paramètre | Requis | Description |
|---|---|---|
| `attributes` | Non | `[String: [String]]`. Chaque clé est un nom d’attribut utilisé par vos règles de ciblage des indicateurs. Chaque valeur correspond à la liste des valeurs de l’utilisateur actuel. |

* Utilisez des noms et des valeurs d’attribut correspondant aux règles de ciblage que vous avez définies dans Indicateurs.
* Appelez `withAttributes` au plus une fois par créateur. Un deuxième appel met fin à l’application.
* Pour effectuer une évaluation sans attributs, appelez `build()` sans appeler `withAttributes`.

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
import AEPFlags

let context = FeatureEvaluationContext.builder()
    .withAttributes([
        "locale": ["en_US"],
        "appVersion": ["3.0.0"]
    ])
    .build()
```

>[!TAB Objectif-C]

```objc
@import AEPFlags;

AEPFeatureEvaluationContext *context = [[[AEPFeatureEvaluationContext builder]
    withAttributes:@{
        @"locale": @[@"en_US"],
        @"appVersion": @[@"3.0.0"]
    }]
    build];
```

>[!ENDTABS]

## Identité personnalisée {#custom-identity}

L’extension Flags utilise l’extension Identity for Edge Network pour la résolution d’identité. Un indicateur de fonctionnalité peut être associé à une identité personnalisée (par exemple, un identifiant CRM ou un identifiant de fidélité) afin que les divisions de variantes et les analyses soient liées à l’identité qui importe pour votre application.

L’espace de noms d’identité personnalisée doit être sélectionné dans l’interface utilisateur des indicateurs lorsque l’indicateur de fonctionnalité est créé. Pour évaluer un indicateur par rapport à cette identité, la même identité doit être présente dans le `identityMap` d’identité Edge sur l’appareil, à l’aide de l’espace de noms correspondant. Fournissez-le au moment de l’exécution avec l’API Identity for Edge Network `updateIdentities`.

### Ajouter l’identité personnalisée au mappage d’identités {#add-identity}

Ajoutez l’identité sous le même espace de noms configuré sur l’indicateur de fonctionnalité.

Notez le comportement suivant :

* L’espace de noms doit correspondre exactement à celui configuré sur l’indicateur , y compris les lettres majuscules et minuscules.
* Si l’espace de noms contient plusieurs identités, celle marquée comme principale est utilisée. Si aucun n’est marqué comme principal, le premier est utilisé.
* Si l’identité est manquante, l’appel n’échoue pas. L’utilisateur est affecté à une variante de manière aléatoire pour la session d’application en cours uniquement, et peut être affecté à une autre variante après le redémarrage de l’application. Définissez l’identité avant d’évaluer les indicateurs qui l’utilisent.

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(
    item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
    withNamespace: "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(with: identityMap)
```

>[!TAB Objectif-C]

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc] initWithId:@"1111"
                                         authenticatedState:AEPAuthenticatedStateAuthenticated
                                                    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

>[!ENDTABS]


## Référence d’API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

Vérifie si une fonctionnalité est activée pour l’utilisateur actuel. Le résultat est `true` lorsque la fonctionnalité existe, que l’utilisateur ou l’utilisatrice correspond à ses règles de ciblage et qu’il ou elle ne se trouve pas dans une population témoin. Dans le cas contraire, le résultat est `false`.

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objectif-C]

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
              completion:(void (^)(BOOL))completion
           errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**Paramètres**

| Paramètre | Type | Description |
|---|---|---|
| `featureKey` | Chaîne | Clé de fonctionnalité à évaluer dans Flags |
| `evaluationContext` | FeatureEvaluationContext | Incluez les attributs de ciblage selon vos besoins ; utilisez `FeatureEvaluationContext.builder().build()` pour un contexte vide. Voir [&#x200B; Contexte d’évaluation &#x200B;](#evaluation-context). |
| `completion` | `(Bool) -> Void` | Appelé avec `true` si la fonctionnalité est activée, `false` dans le cas contraire. |
| `errorCallback` | `((AEPError) -> Void)?` | Facultatif. Appelé uniquement en cas d’échecs réels, tels qu’une clé vide, une configuration manquante, une évaluation ayant échoué ou un délai d’expiration. |

**Exemples**

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
Flag.isFeatureEnabled("new-flag", evaluationContext: context) { isEnabled in
    DispatchQueue.main.async {
        if isEnabled {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // Run the default behavior
    }
}
```

>[!TAB Objectif-C]

```objc
[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:context
                     completion:^(BOOL isEnabled) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (isEnabled) {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### getFeature {#get-feature}

>[!IMPORTANT]
>
>Les versions antérieures appelaient le rappel d’erreur avec `AEPError.unexpected` lorsqu’une fonctionnalité n’était pas diffusée. `nil` Si votre application a traité cette erreur comme une « fonctionnalité manquante », gérez-la à la place.

Renvoie les détails d’une fonctionnalité pour l’utilisateur actuel, y compris ses métadonnées et la variante à laquelle l’utilisateur est affecté. Utilisez-le lorsque vous avez besoin de plus que activés ou désactivés.

L’achèvement est appelé avec un résultat uniquement lorsque la fonctionnalité est diffusée à l’utilisateur. Si la fonction n’est pas diffusée, l’achèvement est appelé avec `nil`. Il s’agit d’un résultat normal, pas d’une erreur, et le rappel d’erreur n’est pas appelé. L’achèvement est appelé avec `nil` lorsque :

* Aucune fonctionnalité ne possède cette clé.
* L’utilisateur ne correspond pas aux règles de ciblage.
* L’utilisateur fait partie d’une population témoin.

Le rappel d’erreur est appelé avec `AEPError.unexpected` (ou une autre `AEPError`) uniquement en cas de problème : la clé de la fonctionnalité est vide, une valeur de configuration requise est manquante, l’évaluation échoue, la réponse ne peut pas être lue ou la requête expire.

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objectif-C]

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion
     errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**Paramètres**

| Paramètre | Type | Description |
|---|---|---|
| `featureKey` | Chaîne | Clé de fonctionnalité à évaluer dans Flags |
| `evaluationContext` | FeatureEvaluationContext | Incluez les attributs de ciblage selon vos besoins ; utilisez `FeatureEvaluationContext.builder().build()` pour un contexte vide. Voir [&#x200B; Contexte d’évaluation &#x200B;](#evaluation-context). |
| `completion` | `(FeatureEvaluationResult?) -> Void` | Appelé avec la payload de fonctionnalité évaluée. Appelé avec `nil` lorsque la fonctionnalité n’est pas diffusée à l’utilisateur (clé inconnue, ciblage non correspondant ou population témoin). `nil` n&#39;est pas une erreur. |
| `errorCallback` | `((AEPError) -> Void)?` | Facultatif. Appelé uniquement en cas d’échecs réels, tels qu’une clé vide, une configuration manquante, une évaluation ayant échoué ou un délai d’expiration. Non appelé lorsque la fonctionnalité n’est pas diffusée. |

**Réponse**

*FeatureEvaluationResult*

| Champ | Type | Description |
|---|---|---|
| `id` | Int | Identifiant de la fonctionnalité |
| `key` | Chaîne | La clé de la fonctionnalité |
| `featureGroupKey` | Chaîne ? | Clé du groupe de fonctionnalités contenant la fonctionnalité |
| `meta` | Chaîne ? | Métadonnées configurées pour la fonction, sous forme de texte. Si vos métadonnées sont au format JSON, décodez-les dans votre application. |
| `analyticsParam` | AnalyticsParam ? | Identifiants de la fonctionnalité et de la variante de l’utilisateur |

**Exemples**

>[!BEGINTABS]

>[!TAB  Swift ]

```swift
Flag.getFeature("new-flag", evaluationContext: context) { feature in
    DispatchQueue.main.async {
        guard let meta = feature?.meta, !meta.isEmpty else {
            // The feature is not served to this user (feature is nil), or it has no metadata.
            // Run the default behavior
            return
        }
        // Use the metadata to drive the feature behavior
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // A genuine failure occurred. Run the default behavior
    }
}
```

>[!TAB Objectif-C]

```objc
[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:context
               completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (feature.meta.length > 0) {
            // Use the metadata to drive the feature behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### extensionVersion {#extension-version}

Renvoie la version de l’extension Flags.

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
| `isFeatureEnabled(_:evaluationContext:completion:errorCallback:)` | Passer en revue l’ensemble des éléments |
| `getFeature(_:evaluationContext:completion:errorCallback:)` | FeatureEvaluationResult ? à l’achèvement |
| `extensionVersion` | Chaîne |
