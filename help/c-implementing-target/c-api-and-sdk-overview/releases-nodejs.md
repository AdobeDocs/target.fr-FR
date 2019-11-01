---
description: Notes de mise à jour relatives au SDK Node.js d’Adobe Target
keywords: at.js;sdk;node.js;release;updates;sdks;server side;server side;server side;server side;nodejs
seo-description: Notes de mise à jour relatives aux API côté serveur d’Adobe Target.
seo-title: Notes de mise à jour relatives au SDK Node.js d’Adobe Target.
solution: Target
title: Notes de mise à jour - SDK de Node.js Target
topic: Standard
translation-type: tm+mt
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# Notes de mise à jour - SDK de Node.js Target

Notes de mise à jour relatives au SDK [Node.js d’](https://github.com/adobe/target-nodejs-sdk)Adobe Target.

Le SDK de Target Node.js vous permet de déployer [!DNL Target] côté serveur.

Ce SDK Node.js vous permet de vous intégrer facilement [!DNL Target] à d’autres [!DNL Adobe Experience Cloud] solutions, telles que [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]et [!DNL Adobe Audience Manager].

Le SDK Node.js présente les meilleures pratiques et élimine les complexités lors de l’intégration avec [!DNL Target] via notre API de diffusion afin que vos équipes d’ingénieurs puissent se concentrer sur la logique métier.

Pour en savoir plus sur le SDK de Target Node.js, consultez le blog technique d’Adobe - [Ouvrir l’approvisionnement du nouveau SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)de Adobe Target Node.js.

## Version 1.0.0 (9 octobre 2019)

Les sections suivantes fournissent plus d’informations sur la version 1.0.0 du kit SDK de Target Node.js :

### Ajout de la section

* Prise en charge de l’API Target View Delivery v1, y compris la prérécupération des pages et des vues.
* Prise en charge complète de la diffusion de tous les types d’offres créées dans le compositeur d’expérience visuelle (VEC).
* Prise en charge de la prérécupération et des notifications pour l’optimisation des performances en mettant en cache le contenu prérécupéré.
* Prise en charge de l’optimisation des performances dans les [!DNL Target] intégrations hybrides via `serverState` [!DNL Target] le déploiement à la fois côté serveur et côté client.

   Nous introduisons un paramètre appelé `serverState` qui contient des expériences récupérées côté serveur, de sorte qu’at.js v2.2+ ne lancera pas un appel serveur supplémentaire pour récupérer les expériences. Cette approche optimise les performances de chargement des pages.

* Ouvrez le fichier source sur GitHub en tant que SDK [Node.js](https://github.com/adobe/target-nodejs-sdk)Target.
* Nouvelle méthode [API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) sendNotifications() pour envoyer des notifications affichées/cliquées [!DNL Target] pour le contenu prérécupéré via [getOffers()](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers).
* Création simplifiée de requêtes d’API de remise des vues, avec remplissage automatique des champs internes avec des valeurs par défaut ( `request.id`, `request.context`, etc.).
* Validation des arguments de méthode de l’API SDK.
* Mise à jour des tests LISEZ-MOI, échantillons et unités.
* Nouveau flux CI configuré à l’aide des actions GitHub.
* Ajout de modèles CoC, de directives sur les contributions, de relations publiques et de problèmes

### La 

* Projet renommé en `target-nodejs-sdk`.
* Principale restructuration, remplacement de l’API Target BatchMbox v2 par l’API Target View Delivery v1.
* [Les arguments de la méthode](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) API create() ont été modifiés, supprimant l’imbrication redondante (voir l’ancienne déclaration de méthode [ici](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [Les arguments de méthode](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) API getOffers() ont été modifiés (voir l’ancienne déclaration de méthode [ici](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* La méthode `getTargetCookieName()` API a été remplacée par `TargetCookieName` un accesseur. Voir Accesseurs [de l’utilitaire](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)TargetClient.
* La méthode `getTargetLocationHintCookieName()` API a été remplacée par `TargetLocationHintCookieName` un accesseur.  Voir Accesseurs [de l’utilitaire](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)TargetClient.

### Supprimée

* Prise en charge de l’API BatchMbox v2 Target.
* La méthode [API](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) getOffer() a été supprimée. Utilisez plutôt la méthode [API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) getOffers().

