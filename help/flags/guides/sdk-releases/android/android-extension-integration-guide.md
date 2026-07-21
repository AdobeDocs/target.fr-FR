---
title: Extension Flags pour le guide d’intégration d’Android
description: Découvrez comment intégrer l’extension Flags à Adobe Experience Platform Mobile SDK sur Android.
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 4%

---

# Extension Flags pour Android {#android-extension-integration-guide}

Ce guide décrit comment intégrer l’extension Flags à Adobe Experience Platform Mobile SDK sur Android.

## Conditions préalables {#prerequisites}

Avant d’implémenter l’extension Flags, vérifiez que vous disposez des éléments suivants :

* Propriété mobile configurée dans la collecte de données Adobe Experience Platform [](https://experience.adobe.com/#/data-collection)
* Extension Flags installée et configurée dans votre propriété mobile
* Un identifiant d’organisation Adobe Experience Cloud
* SDK minimale : API 21 (Android 5.0 Lollipop)

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

1. Connectez-vous à [Collecte de données ](https://experience.adobe.com/#/data-collection).
1. Sélectionnez l’onglet **Balises** et choisissez votre propriété mobile.
1. Accédez à **Extensions** > **Catalogue**.
1. Recherchez **Extension Flags** et sélectionnez **Installer**.
1. Configurez les paramètres d’extension :

   | Paramètre | Description |
   |---|---|
   | ID d’application | Identifiant unique de votre application dans Flags |

1. Sélectionnez **Enregistrer**.
1. Suivez le [processus de publication](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) pour mettre à jour votre configuration.

### Obtention de l’identifiant du fichier d’environnement {#environment-file-id}

1. Dans votre propriété mobile, accédez à **Environnements**.
1. Sélectionnez l’icône en forme de boîte sous la colonne **Installer** pour votre environnement.
1. Dans la boîte de dialogue **Instructions d’installation mobile**, copiez le **ID du fichier d’environnement**.

## Ajouter l’extension Flags à votre application {#add-to-app}

### Ajouter des dépendances {#add-dependencies}

Ajoutez les dépendances Mobile SDK à votre projet. L’extension Flags nécessite Mobile Core et les extensions associées à Edge répertoriées ci-dessous.

#### Utilisation de Gradle avec la nomenclature (recommandé) {#gradle-bom}

Ajoutez les dépendances suivantes au fichier `build.gradle.kts` de votre application :

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdkbom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")
}
```

#### Utilisation de Gradle (Groovy) {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdkbom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'
}
```

>[!IMPORTANT]
>
>Pour les applications de production, Adobe recommande d’utiliser des numéros de version explicites plutôt que des versions dynamiques. Voir [ Gestion des dépendances Gradle ](https://docs.gradle.org/current/userguide/dependency_management.html) pour plus d’informations.

### Ajoutez la dépendance Indicateurs . {#add-flags-dependency}

#### Utilisation du référentiel Maven hébergé (recommandé) {#hosted-maven}

Ajoutez le référentiel Maven Flags au bloc `repositories` dans `settings.gradle.kts` :

```kotlin
maven {
    url = uri("<HTTPS Flags Maven repository URL>")
}
```

Pour un fichier Groovy `settings.gradle` :

```groovy
maven {
    url = uri('<HTTPS Flags Maven repository URL>')
}
```

Remplacez `<HTTPS Flags Maven repository URL>` par l’URL de référentiel sécurisée fournie pour l’extension Flags.

Ajoutez ensuite la dépendance Indicateurs avec version au `build.gradle.kts` de votre application :

```kotlin
implementation("com.adobe.marketing.mobile:flags:<version>")
```

Pour un fichier Groovy `build.gradle` :

```groovy
implementation 'com.adobe.marketing.mobile:flags:<version>'
```

Remplacez `<version>` par la version exacte de l’extension Flags fournie pour votre version.

#### Utilisation du package Distribution des indicateurs {#distribution-package}

Le package de distribution de l’extension Flags comprend :

* `flags-3.x.aar`
* `flags-3.x.module`
* `flags-3.x.pom`

Rendez l’extension disponible pour votre projet Android à l’aide de l’une des méthodes suivantes :

* Publiez tous les fichiers du package de distribution dans un référentiel Maven local ou privé et configurez votre projet pour utiliser ce référentiel.
* Ajoutez des `flags-3.x.aar` directement à votre projet et déclarez les dépendances transitives spécifiées dans `flags-3.x.pom`.

### Ajout d’autorisations {#add-permissions}

Ajoutez les autorisations suivantes à votre fichier `AndroidManifest.xml` :

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Initialiser le SDK {#initialize-sdk}

Initialisez Mobile SDK dans votre classe `Application` avant d’appeler les API d’extension Flags. Utilisez l’identifiant du fichier d’environnement de votre propriété mobile avec `MobileCore.initialize` afin que l’application récupère les paramètres Flags que vous avez publiés dans la collecte de données.

#### Utilisation de MobileCore.initialize {#mobile-core-initialize}

Disponible à partir de la version 3.8.0 de la nomenclature Android, cette API initialise le SDK avec votre fichier d’environnement de collecte de données.

>[!IMPORTANT]
>
>Pour les applications de production, utilisez `LoggingMode.ERROR` uniquement ; n’utilisez ni `DEBUG` ni `VERBOSE` dans les versions.

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### Enregistrer la classe d’application {#register-application}

Enregistrez votre classe `Application` dans `AndroidManifest.xml` :

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## Contexte d’évaluation {#evaluation-context}

`FeatureEvaluationContext` classe inclut les attributs de ciblage (utilisés pour la correspondance des règles d’indicateur).

| Méthode | Requis | Description |
|---|---|---|
| `withAttributes(map)` | Non | `Map<String, List<String>>`. Clé est le nom de l’attribut de contexte utilisé par vos règles d’indicateur (par exemple `locale`, `platform`, `appVersion`, `deviceType`). Valeur est la liste des valeurs d’attribut candidates pour cette clé pour l’utilisateur/la session en cours (par exemple `["en_US"]` ou `["phone"]`). |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID")
)

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withAttributes(attrs)
        .build();
```

### Identité personnalisée {#custom-identity}

L’extension Flags utilise l’extension Identity for Edge Network pour la résolution d’identité. Un indicateur de fonctionnalité peut être associé à une identité personnalisée (par exemple, un identifiant CRM ou un identifiant de fidélité) afin que les divisions de variantes et les analyses soient liées à l’identité qui importe pour votre application.

L’espace de noms d’identité personnalisée doit être sélectionné dans l’interface utilisateur des indicateurs lorsque l’indicateur de fonctionnalité est créé. Pour évaluer un indicateur par rapport à cette identité, la même identité doit être présente dans le `identityMap` d’identité Edge sur l’appareil, à l’aide de l’espace de noms correspondant. Fournissez-le au moment de l’exécution avec l’API Identity for Edge Network `updateIdentities`.

#### Ajouter l’identité personnalisée au mappage d’identités {#add-identity}

Ajoutez l’identité sous le même espace de noms configuré sur l’indicateur de fonctionnalité.

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.edge.identity.IdentityItem
import com.adobe.marketing.mobile.edge.identity.IdentityMap

val identityMap = IdentityMap()
identityMap.addItem(
    IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
    "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(identityMap)
```

**Java**

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

final IdentityItem item = new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true);
final IdentityMap identityMap = new IdentityMap();
identityMap.addItem(item, "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

## Référence d’API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` indique si la fonction Indicateurs est activée ou désactivée pour le contexte donné. Transmettez des `featureKey`, un `FeatureEvaluationContext` (attributs de ciblage facultatifs) et un rappel. Voir [ Contexte d’évaluation ](#evaluation-context).

**Signature**

*Kotlin*

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**Paramètres**

| Paramètre | Type | Description |
|---|---|---|
| `featureKey` | Chaîne | Clé de fonctionnalité à évaluer dans Flags |
| `evaluationContext` | FeatureEvaluationContext | Incluez les attributs de ciblage selon vos besoins ; utilisez `FeatureEvaluationContext.builder().build()` pour un contexte vide. Voir [ Contexte d’évaluation ](#evaluation-context). |
| `callback` | AdobeCallback&lt;Boolean> | Appelée avec `true` si la fonctionnalité est activée, `false` dans le cas contraire. Vous pouvez également transmettre des `AdobeCallbackWithError<Boolean>` pour gérer les `fail(...)`. |

**Exemples**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature` renvoie la payload de fonction évaluée pour le contexte fourni. Utilisez cette API lorsque vous avez besoin de plus que activés/désactivés et que vous souhaitez obtenir des métadonnées ou des valeurs de fonctionnalités.

**Signature**

*Kotlin*

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**Paramètres**

| Paramètre | Type | Description |
|---|---|---|
| `featureKey` | Chaîne | Clé de fonctionnalité à évaluer dans Flags |
| `evaluationContext` | FeatureEvaluationContext | Incluez les attributs de ciblage selon vos besoins ; utilisez `FeatureEvaluationContext.builder().build()` pour un contexte vide. Voir [ Contexte d’évaluation ](#evaluation-context). |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | Appelée avec la payload de la fonctionnalité évaluée ; peut être `null` lorsque la fonctionnalité est introuvable. Vous pouvez également transmettre des `AdobeCallbackWithError<FeatureEvaluationResult>` pour gérer les `fail(...)`. |

**Réponse**

*FeatureEvaluationResult*

| Champ | Type | Description |
|---|---|---|
| `id` | Int | Identifiant numérique de la caractéristique |
| `key` | Chaîne | Clé de fonctionnalité |
| `featureGroupKey` | Chaîne ? | Clé du groupe de fonctionnalités si disponible |
| `meta` | Chaîne ? | Métadonnées sous forme de chaîne JSON, le cas échéant |
| `analyticsParam` | AnalyticsParam ? | Détails Analytics pour la fonctionnalité évaluée |

*AnalyticsParam*

| Champ | Type | Description |
|---|---|---|
| `featureGroupId` | Int | Identifiant numérique du groupe de caractéristiques |
| `featureId` | Int | Identifiant numérique de la caractéristique |
| `variantId` | Chaîne ? | Identifiant de la variante |

**Exemples**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-flag",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-flag",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
);
```

### extensionVersion {#extension-version}

Renvoie la chaîne de version de l’extension Flags.

**Syntaxe**

```kotlin
Flag.extensionVersion(): String
```

**Exemple **

*Kotlin*

```kotlin
val version = Flag.extensionVersion()
```

*Java*

```java
String version = Flag.extensionVersion();
```

## Résumé des API {#api-summary}

| Visiteur | Retours |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext` transfère les attributs de ciblage pour les règles. Voir [Évaluation des fonctionnalités](#is-feature-enabled). | Booléen via le rappel |
| `getFeature(featureKey, evaluationContext, callback)`. Renvoie la payload de fonction évaluée pour le contexte donné. Voir [getFeature](#get-feature). | FeatureEvaluationResult via le rappel |
| `extensionVersion()` | Chaîne |

## Voir également {#see-also}

* [Applications mobiles](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)

<!-- -->
