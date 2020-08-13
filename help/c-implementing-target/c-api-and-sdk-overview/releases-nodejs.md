---
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
description: Notes de mise à jour relatives aux API côté serveur Adobe Target.
title: Notes de mise à jour relatives au SDK Node.js Adobe Target.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 1%

---


# Notes de mise à jour - SDK Target Node.js

Notes de mise à jour relatives au SDK [Node.js](https://github.com/adobe/target-nodejs-sdk)Adobe Target.

Le SDK de Cible Node.js vous permet de déployer [!DNL Target] côté serveur.

Ce SDK Node.js vous permet de vous intégrer facilement [!DNL Target] à d’autres [!DNL Adobe Experience Cloud] solutions, telles que [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]et [!DNL Adobe Audience Manager].

Le SDK Node.js présente les meilleures pratiques et élimine les complexités lors de l’intégration avec [!DNL Target] via notre API de diffusion, de sorte que vos équipes d’ingénieurs puissent se concentrer sur la logique métier.

Pour en savoir plus sur le SDK Node.js de Cible, consultez le blog Adobe Tech Blog - [Open Sourcing the New Adobe Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc).

## Version 1.0.0 (9 octobre 2019)

Les sections suivantes fournissent des informations supplémentaires sur la version 1.0.0 du SDK Node.js de Cible :

### Ajout de la section

* Prise en charge de l’API v1 de la Diffusion de Vue de cible, notamment Chargement de page et prérécupération de Vue.
* Prise en charge complète de la diffusion de tous les types d’offres créés dans le compositeur d’expérience visuelle (VEC).
* Prise en charge de la prérécupération et des notifications pour l’optimisation des performances en mettant en cache le contenu prérécupéré.
* Prise en charge de l’optimisation des performances des [!DNL Target] intégrations hybrides via `serverState` le déploiement [!DNL Target] côté serveur et côté client.

   Nous introduisons un paramètre appelé `serverState` qui contient des expériences récupérées côté serveur, de sorte qu’at.js v2.2+ ne lancera pas un appel serveur supplémentaire pour récupérer les expériences. Cette approche optimise les performances de chargement de page.

* Open source sur GitHub en tant que SDK [Node.js de](https://github.com/adobe/target-nodejs-sdk)Cible.
* Nouvelle méthode [API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) sendNotifications() pour envoyer des notifications affichées/cliquées [!DNL Target] pour le contenu prérécupéré via [getOffers()](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers).
* Création simplifiée de requêtes d’API de Diffusion de Vue, avec remplissage automatique des champs internes avec des valeurs par défaut (par exemple, `request.id`, `request.context`etc.).
* Validation des arguments de méthode de l’API SDK.
* Mise à jour des tests README, d’exemples et d’unités.
* Nouveau flux de CI configuré à l’aide des actions GitHub.
* CoC Ajouté, lignes directrices sur les contributions, relations publiques et modèles de publication

### La 

* Le projet a été renommé `target-nodejs-sdk`.
* Principale refactorisation, remplacement de l’API BatchMbox v2 Cible par l’API v1 de la Diffusion de Vue de Cible.
* [Les arguments de la méthode](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) API create() ont été modifiés, supprimant l’imbrication redondante (voir l’ancienne déclaration de méthode [ici](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [Les arguments de méthode](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) API getOffers() ont été modifiés (voir l’ancienne déclaration de méthode [ici](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* La méthode `getTargetCookieName()` API a été remplacée par `TargetCookieName` accesseur. Voir Accesseurs [de l’utilitaire](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)TargetClient.
* La méthode `getTargetLocationHintCookieName()` API a été remplacée par `TargetLocationHintCookieName` accesseur.  Voir Accesseurs [de l’utilitaire](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)TargetClient.

### Supprimée

* Prise en charge de l’API BatchMbox v2 cible.
* La méthode [API](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) getOffer() a été supprimée, utilisez plutôt la méthode [API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) getOffers().

