---
keywords: A4T ; Adobe Analytics ; activité basée sur Analytics ; Report Suite Analytics ; Report Suite ; Intégration d’Analytics Cible ; configurer la suite de rapports ; at.js ; atjs ; adobe experience platform web sdk ; aep web sdk ; platform web sdk
description: Suivez les étapes requises pour mettre en oeuvre les solutions Analytics pour  [!DNL Target] (A4T) in your Adobe [!DNL Target] et Adobe Analytics.
title: Comment mettre en oeuvre Analytics pour  [!DNL Target] (A4T) ?
feature: 'Analytics for Target (A4T) '
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: efa796edf3cd4da718fdcb0dbfd3d6f635ebf401
workflow-type: tm+mt
source-wordcount: '1156'
ht-degree: 22%

---

# Analytics pour l’implémentation de [!DNL Target]

Plusieurs étapes sont requises lors de l’implémentation de [!DNL Adobe Analytics] en tant que source de rapports pour [!DNL Adobe Target] (A4T). Le processus varie selon que vous implémentez A4T avec [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) ou avec at.js.

## Procédure d’implémentation d’une implémentation du SDK Web Adobe Experience Platform {#platform}

>[!NOTE]
>
>La prise en charge d’A4T dans une mise en oeuvre [!DNL Adobe Experience Platform Web SDK] décrite dans cet article devrait être disponible avec la version [!DNL Platform Web SDK] 2.5.0 (24 mai 2021).

Les sections suivantes décrivent les étapes requises pour déployer cette intégration sur votre site si vous prévoyez d&#39;utiliser le SDK Web de la plate-forme :

### Étape 1 : Demander l&#39;approvisionnement pour [!DNL Analytics] et [!DNL Target]

Avant d’implémenter A4T, vous devez disposer des privilèges d’accès [!DNL Analytics] et [!DNL Target]. [Pour ce faire, utilisez ce formulaire](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES).

### Étape 2 : configuration des autorisations d’utilisateur

Les exigences du compte utilisateur doivent être satisfaites avant de pouvoir créer une activité basée sur [!DNL Analytics] dans [!DNL Target]. Voir [Exigences d’autorisation utilisateur](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Étape 3 : Création d’une configuration Edge

Créez une configuration Edge à l&#39;aide de [!DNL Adobe Experience Platform Launch] l&#39;outil de configuration Edge. Configurez les paramètres de configuration [[!DNL Analytics] and [!DNL Target] edge](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### Étape 4 : Installation et configuration du SDK Web de la plate-forme

Pour début de fournir [!DNL Target] expériences et d&#39;appliquer [!DNL Analytics] à des fins de suivi et d&#39;analyse, [installez ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) et [configurez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) le SDK Web de la plate-forme sur les pages de votre site.

### Étape 5 : Activation des options d’utilisation d’A4T

Dans l’interface utilisateur [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Compositeur visuel d’expérience]**, puis sélectionnez **[!UICONTROL Sélectionner par activité]** ou **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL L’option Sélection par activité vous permet de choisir entre et lors de la création de chaque activité.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL L’option Adobe  définit Analytics en tant que source des rapports pour toutes les activités que vous créez.]**[!DNL Analytics]

## Procédure d’implémentation d’une implémentation d’at.js{#section_73961BAD5BB4430A95E073DE5C026277}

Les sections suivantes décrivent les étapes requises pour déployer cette intégration sur votre site si vous prévoyez d’utiliser at.js :

### Étape 1 : Demander l’approvisionnement pour Analytics et la Cible

Après avoir implémenté [!DNL Analytics] en tant que source de rapports pour [!DNL Target], vous devez être configuré pour [!DNL Analytics] et [!DNL Target]. [Pour ce faire, utilisez ce formulaire](http://www.adobe.com/go/audiences).

### Étape 2 : configuration des autorisations d’utilisateur

Les exigences du compte utilisateur doivent être satisfaites pour que vous puissiez créer une activité basée sur [!DNL Analytics] dans [!DNL Target]. Voir [Exigences d’autorisation utilisateur](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Étape 3 : implémentation du service Identification des visiteurs d’Experience Cloud

Le service Identifiant visiteur permet d’identifier les utilisateurs sur l’ensemble des solutions [!DNL Adobe Experience Cloud]. Mettez en oeuvre ou migrez vers la version requise de l’ID de Visiteur Experience Cloud. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Voir [Mise en oeuvre du service d’identification des Experience Cloud pour la Cible](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) dans la documentation *Service d’identification des Visiteurs Experience Cloud*.

### Étape 4 : mise à jour d’AppMeasurement pour JavaScript ou s_code

Implémentez ou migrez vers la version requise du fichier appMeasurement.js. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Pour les nouvelles implémentations, voir [Présentation de l’implémentation JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) dans le *Guide d’implémentation Analytics*.

Pour une migration, voir [Migration vers AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) dans le *Guide de mise en oeuvre d’Analytics*.

### Étape 5 : Téléchargement et mise à jour d’at.js

Implémentez ou migrez vers la version requise d’at.js à l’aide de votre compte de production. Aucune modification du code n’est requise.

Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

### Étape 6 : Hôte at.js

Si vous avez déjà déployé at.js, vous pouvez remplacer votre fichier existant par la version mise à jour. Pour plus d’informations, voir « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Sinon, ce fichier peut être hébergé avec le service Identifiant visiteur et les fichiers AppMeasurement pour JavaScript. Ces fichiers doivent être hébergés sur un serveur web accessible par toutes les pages de votre site. Vous aurez besoin du chemin d’accès à ces fichiers à l’étape suivante.

### Étape 7 : Référence au fichier at.js sur toutes les pages du site {#step7}

Insérez at.js sous VisitorAPI.js en ajoutant la ligne de code suivante dans la balise de chaque page :

Pour at.js :

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Le fichier VisitorAPI.js doit être chargé avant at.js. Si vous mettez à jour un fichier at.js ou mbox.js existant, veillez à vérifier l’ordre de chargement.

Le paramètre par défaut pour l’intégration [!DNL Target] et [!DNL Analytics], du point de vue de l’implémentation, consiste à utiliser le SDID transmis à partir de la page pour assembler automatiquement les requêtes [!DNL Target] et [!DNL Analytics] sur le serveur principal.

Vous pouvez contrôler comment et quand envoyer des données d&#39;analyse liées à [!DNL Target] à [!DNL Analytics] à des fins de rapports. Si vous ne souhaitez pas opt-in aux paramètres par défaut, à savoir que [!DNL Target] et [!DNL Analytics] assemblent automatiquement les données d’analyse via le SDID, définissez **analyticsLogging = client_side** via **window.targetGlobalSettings**. Remarque : Toutes les versions antérieures à 2.1 ne prennent pas en charge cette approche.

Par exemple :

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Cette configuration a un effet global, ce qui signifie que chaque appel effectué par at.js comporte **analyticsLogging: &quot;client_side&quot;** envoyé dans les requêtes [!DNL Target] et une charge utile d’analyse est renvoyée pour chaque requête. Lorsque cette option est configurée, le format de la charge utile renvoyée se présente comme suit :

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La charge utile peut ensuite être transférée à Analytics via l’[API d’insertion de données](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Pour les activités d’affectation automatique et d’Cible automatique, vous devez également transférer l’ID de session. Pour plus d’informations, voir le [rapports Analytics for Cible (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) dans le guide *Adobe Target SDKs*.

Si un paramètre global n’est pas souhaité et qu’une approche plus à la demande est préférable, utilisez la fonction at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) en transmettant **analyticsLogging : &quot;client_side&quot;**. La charge utile d’analyse est renvoyée pour cet appel uniquement et le serveur principal [!DNL Target] ne transmet pas la charge utile à [!DNL Analytics]. En suivant cette approche, chaque requête at.js [!DNL Target] renvoie la charge par défaut, mais uniquement lorsque cela est souhaité et spécifié.

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

La charge utile peut ensuite être transférée à [!DNL Analytics] par l&#39;intermédiaire de l&#39;[API d&#39;insertion de données](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Étape 8 : validation de l’implémentation {#step8}

Chargez vos pages après avoir mis à jour les bibliothèques JavaScript pour vérifier que les valeurs de paramètre `mboxMCSDID` dans les appels [!DNL Target] correspondent à la valeur de paramètre `sdid` dans l&#39;appel de vue de page [!DNL Analytics].

Il est particulièrement important de confirmer que ces valeurs correspondent dans les applications d’une seule page (SPA) où l’ordre des appels n’est pas toujours prévisible.

>[!NOTE]
>
>La correspondance de ces valeurs est requise pour que A4T fonctionne correctement.

### Étape 9 (facultative) : suppression du code d’intégration précédent

Adobe vous recommande de supprimer l’intégration précédente afin de simplifier votre implémentation et d’éliminer la nécessité de résoudre les incohérences entre les systèmes. Vous pouvez supprimer tout code que vous avez déployé pour une intégration SC à T&amp;T précédente, y compris `mboxLoadSCPlugin`.

### Étape 10 : activation des options pour utiliser Analytics en tant que source de création de rapports pour Target

Dans [!DNL Target], cliquez sur **[!UICONTROL Administration > Compositeur visuel d’expérience]** et sélectionnez **[!UICONTROL Sélectionner par activité]** ou **[!UICONTROL Adobe Analytics]** pour activer les options.

* **[!UICONTROL L’option Sélection par activité vous permet de choisir entre et lors de la création de chaque activité.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL L’option Adobe  définit Analytics en tant que source des rapports pour toutes les activités que vous créez.]**[!DNL Analytics]


