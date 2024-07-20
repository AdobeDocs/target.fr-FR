---
keywords: A4T;Adobe Analytics;activité basée sur Analytics;suite de rapports Analytics;suite de rapports;intégration d’Analytics Target;configurer une suite de rapports;at.js;atjs;sdk web adobe experience platform;sdk web aep;sdk web platform
description: Suivez les étapes requises pour mettre en oeuvre Analytics for [!DNL Target] (A4T) dans vos solutions Adobe [!DNL Target]  et Adobe Analytics.
title: Comment mettre en oeuvre Analytics for [!DNL Target] (A4T) ?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 17%

---

# Implémentation d’Analytics pour [!DNL Target]

Plusieurs étapes sont requises lors de l’implémentation de [!DNL Adobe Analytics] en tant que source des rapports pour [!DNL Adobe Target] (A4T). Le processus varie selon que vous implémentez A4T avec l’élément [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) ou at.js.

## ![Badge du SDK Web Adobe Experience Platform](/help/main/assets/platform.png) Étapes de mise en oeuvre pour une mise en oeuvre du SDK Web Adobe Experience Platform {#platform}

Les sections suivantes décrivent les étapes nécessaires au déploiement de cette intégration sur votre site si vous envisagez d’utiliser le SDK Web Platform :

### Étape 1 : demande d’approvisionnement pour [!DNL Analytics] et [!DNL Target]

Avant de mettre en oeuvre A4T, vous devez être configuré pour [!DNL Analytics] et [!DNL Target]. [Utilisez ce formulaire pour demander à être configuré](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### Étape 2 : configuration des autorisations d’utilisateur

Les exigences de compte utilisateur doivent être respectées avant de pouvoir créer une activité basée sur [!DNL Analytics] dans [!DNL Target]. Voir [Exigences d’autorisation des utilisateurs](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Étape 3 : création d’une configuration Edge

Créez une configuration Edge à l’aide de [!DNL Adobe Experience Platform] à l’aide de l’outil de configuration Edge. Configurez les [flux de données de création et de configuration](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

### Étape 4 : installation et configuration du SDK Web de Platform

Pour commencer à fournir [!DNL Target] expériences et appliquer [!DNL Analytics] à des fins de suivi et d’analyse, [Installez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) et [configurez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) le SDK Web Platform sur les pages de votre site.

### Étape 5 : activation des options pour l’utilisation d’A4T

Dans l’interface utilisateur de [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**, puis sélectionnez **[!UICONTROL Select per activity]** ou **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Select per activity]** vous permet de choisir entre [!DNL Target] et [!DNL Analytics] lors de la création de chaque activité.
* **[!UICONTROL Adobe Analytics]** définit [!DNL Analytics] comme source de création de rapports pour toutes les activités que vous créez.

## ![Badge at.js](/help/main/assets/atjs.png) Étapes de mise en oeuvre d’une implémentation at.js{#section_73961BAD5BB4430A95E073DE5C026277}

Les sections suivantes décrivent les étapes nécessaires au déploiement de cette intégration sur votre site si vous envisagez d’utiliser at.js :

### Étape 1 : demande d’approvisionnement pour Analytics et Target

Après avoir implémenté [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous devez être configuré pour [!DNL Analytics] et [!DNL Target]. [Utilisez ce formulaire pour demander à être configuré](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### Étape 2 : configuration des autorisations d’utilisateur

Les exigences de compte utilisateur doivent être respectées pour pouvoir créer une activité basée sur [!DNL Analytics] dans [!DNL Target]. Voir [Exigences d’autorisation des utilisateurs](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Étape 3 : implémentation du service Identification des visiteurs d’Experience Cloud

Le service d’identification des visiteurs vous permet d’identifier les utilisateurs sur l’ensemble des [!DNL Adobe Experience Cloud] solutions. Mettez en oeuvre ou migrez vers la version requise de l’identifiant visiteur Experience Cloud. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Voir [Mise en oeuvre du service d’ID Experience Cloud pour Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) dans la documentation *du service d’identification des visiteurs Experience Cloud*.

### Étape 4 : mise à jour d’AppMeasurement pour JavaScript ou s_code

Mettez en oeuvre ou migrez vers la version requise d’appMeasurement.js. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Pour les nouvelles implémentations, consultez la [présentation de l’implémentation de JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) dans le *Guide de l’implémentation d’Analytics*.

Pour une migration, reportez-vous à la section [Migration vers AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) du *Guide de mise en oeuvre d’Analytics*.

### Étape 5 : téléchargement et mise à jour d’at.js

Implémentez ou migrez vers la version requise d’at.js à l’aide de votre compte de production. Aucune modification du code n’est requise.

Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

### Étape 6 : Hébergement d’at.js

Si vous avez déjà déployé at.js, vous pouvez remplacer votre fichier existant par la version mise à jour. Pour plus d’informations, voir « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Sinon, ce fichier peut être hébergé avec le service Identifiant visiteur et les fichiers AppMeasurement pour JavaScript. Ces fichiers doivent être hébergés sur un serveur web accessible par toutes les pages de votre site. Vous aurez besoin du chemin d’accès à ces fichiers à l’étape suivante.

### Étape 7 : référencement d’at.js sur toutes les pages du site {#step7}

Insérez at.js sous VisitorAPI.js en ajoutant la ligne de code suivante dans la balise de chaque page :

Pour at.js :

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Le fichier VisitorAPI.js doit être chargé avant at.js. Si vous mettez à jour un fichier at.js existant, veillez à vérifier l’ordre de chargement.

Le paramètre par défaut pour l’intégration [!DNL Target] et [!DNL Analytics], du point de vue de l’implémentation, consiste à utiliser le SDID transmis à partir de la page pour assembler automatiquement la requête [!DNL Target] et [!DNL Analytics] sur le serveur principal.

Vous pouvez contrôler comment et à quel moment envoyer des données d’analyse liées à [!DNL Target] vers [!DNL Analytics] à des fins de création de rapports. Si vous ne souhaitez pas souscrire aux paramètres par défaut de [!DNL Target] et [!DNL Analytics] assembler automatiquement les données d’analyse par l’intermédiaire du SDID, définissez **analyticsLogging = client_side** via **window.targetGlobalSettings**. Remarque : Toutes les versions antérieures à 2.1 ne prennent pas en charge cette approche.

Par exemple :

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Cette configuration a un effet global, ce qui signifie que chaque appel effectué par at.js comporte **analyticsLogging: &quot;client_side&quot;** envoyé dans les demandes [!DNL Target] et une charge utile d’analyse est renvoyée pour chaque requête. Lorsque cette option est configurée, le format de la payload renvoyé ressemble à ce qui suit :

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La payload peut ensuite être transmise à Analytics via l’ [API d’insertion de données](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Pour les activités d’affectation automatique et de ciblage automatique, vous devez également transférer l’ID de session. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} dans le guide *SDK Adobe Target*.

Si un paramètre global n’est pas souhaité et qu’une approche plus à la demande est préférable, utilisez la fonction at.js [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank} en transmettant **analyticsLogging: &quot;client_side&quot;**. La charge utile Analytics est renvoyée pour cet appel uniquement et le serveur principal [!DNL Target] ne transfère pas la charge utile vers [!DNL Analytics]. En poursuivant cette approche, chaque requête at.js [!DNL Target] renvoie la charge utile par défaut, mais uniquement lorsque cela est souhaité et spécifié.

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

La payload peut ensuite être transmise à [!DNL Analytics] via l’ [API d’insertion de données](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Étape 8 : validation de l’implémentation {#step8}

Chargez vos pages après avoir mis à jour les bibliothèques JavaScript pour confirmer que les valeurs de paramètre `mboxMCSDID` dans les appels [!DNL Target] correspondent à la valeur de paramètre `sdid` dans l’appel de page vue [!DNL Analytics].

Il est particulièrement important de confirmer que ces valeurs correspondent dans les applications d’une seule page (SPA) où l’ordre des appels n’est pas toujours prévisible.

>[!NOTE]
>
>La correspondance de ces valeurs est requise pour que A4T fonctionne correctement.

### Étape 9 (facultative) : suppression du code d’intégration précédent

Adobe recommande de supprimer l’intégration précédente afin de simplifier votre mise en oeuvre et d’éliminer la nécessité de résoudre les incohérences entre les systèmes. Vous pouvez supprimer tout code que vous avez déployé pour une intégration SC à T&amp;T précédente, y compris `mboxLoadSCPlugin`.

### Étape 10 : activation des options pour utiliser Analytics en tant que source de création de rapports pour Target

Dans [!DNL Target], cliquez sur **[!UICONTROL Administration > Reporting]** et sélectionnez **[!UICONTROL Select per activity]** ou **[!UICONTROL Adobe Analytics]** pour activer les options.

* **[!UICONTROL Select per activity]** vous permet de choisir entre [!DNL Target] et [!DNL Analytics] lors de la création de chaque activité.
* **[!UICONTROL Adobe Analytics]** définit [!DNL Analytics] comme source de création de rapports pour toutes les activités que vous créez.


