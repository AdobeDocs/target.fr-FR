---
keywords: A4T;Adobe Analytics;activité basée sur Analytics;suite de rapports Analytics;suite de rapports;intégration d’Analytics Target;configurer la suite de rapports;at.js;atjs;sdk web adobe experience platform;sdk web aep;sdk web platform
description: Suivez les étapes requises pour implémenter Analytics for [!DNL Target] (A4T) dans vos solutions Adobe [!DNL Target] et Adobe Analytics.
title: Comment mettre en œuvre Analytics for  [!DNL Target] (A4T) ?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 17%

---

# Implémentation d’Analytics for [!DNL Target]

Plusieurs étapes sont nécessaires lors de l’implémentation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T). Le processus varie selon que vous implémentez A4T avec le [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) ou avec at.js.

## ![Badge Adobe Experience Platform Web SDK ](/help/main/assets/platform.png) Étapes d’implémentation pour une implémentation de Adobe Experience Platform Web SDK {#platform}

Les sections suivantes décrivent les étapes requises pour déployer cette intégration sur votre site si vous envisagez d’utiliser le SDK Web Platform :

### Étape 1 : demande d’approvisionnement pour [!DNL Analytics] et [!DNL Target]

Avant de mettre en œuvre A4T, vous devez disposer des privilèges d’accès pour [!DNL Analytics] et [!DNL Target]. [Utilisez ce formulaire pour demander à être approvisionné](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### Étape 2 : configuration des autorisations d’utilisateur

Les exigences du compte utilisateur doivent être remplies avant de pouvoir créer une activité basée sur [!DNL Analytics] dans [!DNL Target]. Voir [Exigences d’autorisation des utilisateurs](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Étape 3 : création d’une configuration Edge

Créez une configuration Edge à l’aide de [!DNL Adobe Experience Platform] à l’aide de l’outil de configuration Edge. Configurez l’[Créer et configurer des flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

### Étape 4 : installer et configurer Platform Web SDK

Pour commencer à diffuser des expériences [!DNL Target] et appliquer des [!DNL Analytics] à des fins de suivi et d’analyse, [Installez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr) et [configurez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) le SDK web Platform sur les pages de votre site.

### Étape 5 : activer les options d’utilisation d’A4T

Dans l’interface utilisateur de [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**, puis choisissez **[!UICONTROL Select per activity]** ou **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Select per activity]** permet de choisir entre [!DNL Target] et [!DNL Analytics] lors de la création de chaque activité.
* **[!UICONTROL Adobe Analytics]** définit [!DNL Analytics] comme source de création de rapports pour toutes les activités que vous créez.

## ![badge at.js](/help/main/assets/atjs.png) Étapes d’implémentation d’at.js{#section_73961BAD5BB4430A95E073DE5C026277}

Les sections suivantes décrivent les étapes requises pour déployer cette intégration sur votre site si vous envisagez d’utiliser at.js :

### Étape 1 : demande d’approvisionnement pour Analytics et Target

Après avoir implémenté [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous devez disposer des privilèges d’accès pour [!DNL Analytics] et [!DNL Target]. [Utilisez ce formulaire pour demander à être approvisionné](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### Étape 2 : configuration des autorisations d’utilisateur

Les exigences du compte d’utilisateur doivent être remplies avant de pouvoir créer une activité basée sur des [!DNL Analytics] dans [!DNL Target]. Voir [Exigences d’autorisation des utilisateurs](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Étape 3 : implémentation du service Identification des visiteurs d’Experience Cloud

Le service d’identification des visiteurs vous permet d’identifier les utilisateurs dans les solutions [!DNL Adobe Experience Cloud]. Implémentez ou migrez vers la version requise de l’identifiant visiteur Experience Cloud. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Voir [Mise en œuvre du service Experience Cloud ID pour Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html?lang=fr) dans la documentation du *Service d’identification des visiteurs Experience Cloud*.

### Étape 4 : mise à jour d’AppMeasurement pour JavaScript ou s_code

Implémentez ou migrez vers la version requise d’appMeasurement.js. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Pour connaître les nouvelles mises en œuvre, consultez la présentation de l’implémentation de JavaScript [&#128279;](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=fr) dans le *Guide d’implémentation d’Analytics*.

Pour une migration, voir [Migration vers AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html?lang=fr) dans le *Guide de mise en œuvre d’Analytics*.

### Étape 5 : télécharger et mettre à jour at.js

Mettez en œuvre ou migrez vers la version requise d’at.js à l’aide de votre compte de production. Aucune modification du code n’est requise.

Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

### Étape 6 : hébergez at.js.

Si vous avez précédemment déployé at.js, vous pouvez remplacer votre fichier existant par la version mise à jour. Pour plus d’informations, voir « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Sinon, ce fichier peut être hébergé avec le service Identifiant visiteur et les fichiers AppMeasurement pour JavaScript. Ces fichiers doivent être hébergés sur un serveur web accessible par toutes les pages de votre site. Vous aurez besoin du chemin d’accès à ces fichiers à l’étape suivante.

### Étape 7 : référencer at.js sur toutes les pages du site {#step7}

Incluez at.js sous VisitorAPI.js en ajoutant la ligne de code suivante dans la balise de chaque page :

Pour at.js :

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js doit être chargé avant at.js. Si vous mettez à jour un fichier at.js existant, veillez à vérifier l’ordre de chargement.

Du point de vue de la mise en œuvre, le paramètre par défaut de l’intégration de [!DNL Target] et [!DNL Analytics] consiste à utiliser le SDID transmis à partir de la page pour regrouper automatiquement les requêtes [!DNL Target] et [!DNL Analytics] sur le serveur principal.

Vous pouvez contrôler comment et quand envoyer les données d’analyse liées aux [!DNL Target] à [!DNL Analytics] à des fins de création de rapports. Si vous ne souhaitez pas activer les paramètres par défaut de [!DNL Target] et [!DNL Analytics] regrouper automatiquement les données d’analyse via le SDID, définissez **analyticsLogging = côté_client** via **window.targetGlobalSettings**. Remarque : Toutes les versions antérieures à 2.1 ne prennent pas en charge cette approche.

Par exemple :

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Cette configuration a un effet global, ce qui signifie que chaque appel effectué par at.js reçoit **analyticsLogging: « client_side »** envoyé dans les requêtes [!DNL Target] et qu’un payload d’analyse est renvoyé pour chaque requête. Lorsque cette option est configurée, le format de la payload renvoyée est le suivant :

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La payload peut ensuite être transmise à Analytics via l’[API Data Insertion](https://helpx.adobe.com/fr/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Pour les activités d’affectation automatique et de ciblage automatique , vous devez également transférer l’ID de session. Pour plus d’informations, consultez [Rapports Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=fr){target=_blank} dans le guide des *SDK Adobe Target*.

Si aucun paramètre global n’est souhaité et qu’une approche plus à la demande est préférable, utilisez la fonction at.js [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html?lang=fr){target=_blank} en transmettant **analyticsLogging: « client_side »**. La payload d’analyse est renvoyée pour cet appel uniquement et le serveur principal [!DNL Target] ne transfère pas la payload vers [!DNL Analytics]. En suivant cette approche, chaque requête de [!DNL Target] at.js renvoie la payload par défaut, mais uniquement lorsque cela est souhaité et spécifié.

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

La payload peut ensuite être transmise à [!DNL Analytics] via l’API [Data Insertion](https://helpx.adobe.com/fr/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Étape 8 : validation de l’implémentation {#step8}

Chargez vos pages après avoir mis à jour les bibliothèques JavaScript pour confirmer que les valeurs de paramètre `mboxMCSDID` dans les appels de [!DNL Target] correspondent à la valeur de paramètre `sdid` dans l’appel de page vue [!DNL Analytics].

Il est particulièrement important de confirmer que ces valeurs correspondent dans les applications monopages (SPA), où l’ordre des appels n’est pas toujours prévisible.

>[!NOTE]
>
>La correspondance de ces valeurs est nécessaire au bon fonctionnement d’A4T.

### Étape 9 (facultative) : suppression du code d’intégration précédent

Adobe vous recommande de supprimer l’intégration précédente pour simplifier votre implémentation et éliminer la nécessité de résoudre les incohérences entre les systèmes. Vous pouvez supprimer tout code que vous avez déployé pour une intégration précédente de SC à T&amp;T, y compris `mboxLoadSCPlugin`.

### Étape 10 : activation des options pour utiliser Analytics en tant que source de création de rapports pour Target

Dans [!DNL Target], cliquez sur **[!UICONTROL Administration > Reporting]** et choisissez **[!UICONTROL Select per activity]** ou **[!UICONTROL Adobe Analytics]** pour activer les options.

* **[!UICONTROL Select per activity]** permet de choisir entre [!DNL Target] et [!DNL Analytics] lors de la création de chaque activité.
* **[!UICONTROL Adobe Analytics]** définit [!DNL Analytics] comme source de création de rapports pour toutes les activités que vous créez.


