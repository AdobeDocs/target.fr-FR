---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: Plusieurs étapes sont requises lors de l’implémentation d’Adobe Analytics en tant que source des rapports pour Target (A4T).
title: Implémentation d’Analytics for Target
feature: a4t implementation
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 47%

---


# Implémentation d’Analytics for Target{#analytics-for-target-implementation}

Several steps are required when implementing [!DNL Adobe Analytics] as the reporting source for [!DNL Target] (A4T).

## Implementation steps {#section_73961BAD5BB4430A95E073DE5C026277}

Les sections suivantes décrivent les étapes requises pour déployer cette intégration sur votre site.

## Étape 1 : Demander l’approvisionnement pour Analytics et la Cible

After you implement [!DNL Analytics] as the reporting source for [!DNL Target], you must be provisioned for [!DNL Analytics] and [!DNL Target]. [Pour ce faire, utilisez ce formulaire](http://www.adobe.com/go/audiences).

## Étape 2 : configuration des autorisations d’utilisateur

User account requirements must be met before you can create an [!DNL Analytics]-based activity in [!DNL Target]. See [User permission requirements](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Étape 3 : implémentation du service Identification des visiteurs d’Experience Cloud

Le service Identifiant visiteur permet d’identifier les utilisateurs sur l’ensemble des solutions [!DNL Adobe Experience Cloud]. Vous devez mettre en œuvre la version requise de l’identifiant visiteur Experience Cloud ou effectuer la migration vers cette dernière. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

See [Implement the Experience Cloud ID Service for Target](https://experienceleague.adobe.com/docs/id-service/using/implementation-guides/setup-target.html) in the *Experience Cloud Visitor ID Service* documentation.

## Étape 4 : mise à jour d’AppMeasurement pour JavaScript ou s_code

Vous devez mettre en œuvre la version requise d’appMeasurement.js ou effectuer la migration vers cette dernière. Pour plus d’informations, voir « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Pour les nouvelles mises en oeuvre, voir Présentation [de la mise en oeuvre de](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) JavaScript dans le Guide *de mise en oeuvre d’* Analytics.

Pour une migration, voir [Migration vers AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) dans le Guide *de mise en oeuvre d’* Analytics.

## Étape 5 : Téléchargement et mise à jour d’at.js

Vous devez implémenter at.js ou effectuer la migration vers la version requise de at.js à l’aide de votre compte de production. Aucune modification du code n’est requise.

Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Étape 6 : Hôte at.js

Si vous avez déjà déployé at.js, vous pouvez remplacer votre fichier existant par la version mise à jour. Pour plus d’informations, voir « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Sinon, ce fichier peut être hébergé avec le service Identifiant visiteur et les fichiers AppMeasurement pour JavaScript. Ces fichiers doivent être hébergés sur un serveur web accessible par toutes les pages de votre site. Vous aurez besoin du chemin d’accès à ces fichiers à l’étape suivante.

## Step 7: Reference at.js on all site pages {#step7}

Insérez at.js sous VisitorAPI.js en ajoutant la ligne de code suivante dans la balise de chaque page :

Pour at.js :

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Il est essentiel que VisitorAPI.js soit chargé avant at.js. Si vous mettez à jour un fichier at.js ou mbox.js existant, veillez à vérifier l’ordre de chargement.

The way the out-of-the-box settings are configured for [!DNL Target] and [!DNL Analytics] integration from an implementation perspective is to use the SDID that is passed from the page to stitch the [!DNL Target] and [!DNL Analytics] request together on the backend automatically for you.

However, if you want more control on how and when to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes, and you do not want to opt-in to the default settings of having [!DNL Target] and [!DNL Analytics] automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. Remarque : Toutes les versions antérieures à 2.1 ne prennent pas en charge cette approche.

Par exemple :

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Cette configuration a un effet global. Cela signifie que chaque appel effectué par at.js aura **analyticsLogging: &quot;client_side&quot;** envoyé dans les requêtes et une charge utile Analytics est renvoyée pour chaque requête. [!DNL Target] Lors de la configuration, le format de la charge utile renvoyé ressemble à ce qui suit :

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La charge utile peut ensuite être transférée à Analytics via l’API [d’insertion de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)données. Notez que, pour les activités d’affectation  automatique et de Cible  automatique, vous devez également transférer le paramètre sessionId. Pour plus d’informations, voir rapports [Analytics pour la Cible (A4T) dans le](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) guide des kits SDK ** Adobe Target.

Si un paramètre global n’est pas souhaité et qu’une approche plus à la demande est préférable, vous pouvez utiliser la fonction at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) pour obtenir ce résultat en transmettant **analyticsLogging: &quot;client_side&quot;**. The analytics payload will be returned for only this call and the [!DNL Target] backend will not forward the payload to [!DNL Analytics]. By pursuing this approach, every at.js [!DNL Target] request will not return the payload by default, but instead only when desired and specified.

Par exemple :

```javascript
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

Cet appel appelle une réponse à partir de laquelle vous pouvez extraire la charge utile Analytics.

La réponse ressemble à ce qui suit :

```javascript
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

La charge utile peut ensuite être transférée vers [!DNL Analytics] via l’API [d’insertion de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)données.

## Étape 8 : validation de l’implémentation {#step8}

Load your pages after you have updated the JavaScript libraries to confirm that the `mboxMCSDID` parameter values in [!DNL Target] calls match the `sdid` parameter value in the [!DNL Analytics] page-view call.

Ceci s’avère particulièrement important dans les applications à une seule page, où l’ordre des appels n’est pas toujours prévisible.

**Remarque :** Ces valeurs doivent correspondre pour qu’A4T fonctionne correctement.

## Étape 9 (facultative) : suppression du code d’intégration précédent

Il est recommandé de supprimer l’intégration précédente afin de simplifier la mise en œuvre et d’éliminer la nécessité d’avoir à résoudre les incohérences entre les systèmes. Vous pouvez supprimer tout code que vous pouvez avoir déployé lors d’une intégration SC à T&amp;T précédente, notamment `mboxLoadSCPlugin`.

## Étape 10 : activation des options pour utiliser Analytics en tant que source de création de rapports pour Target

In [!DNL Target], click **[!UICONTROL Administation > Visual Experience Composer]** and choose either **[!UICONTROL Select per activity]** or **[!UICONTROL Adobe Analytics]** to enable the options.

* **[!UICONTROL L’option Sélection par activité vous permet de choisir entre et lors de la création de chaque activité.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL L’option Adobe  définit Analytics en tant que source des rapports pour toutes les activités que vous créez.]**[!DNL Analytics]

