---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: Notes de mise à jour relatives au SDK Java Adobe Target.
title: Notes de mise à jour relatives au SDK Java Adobe Target.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 2%

---


# Notes de mise à jour - SDK Target Java

Notes de mise à jour relatives au SDK [Java](https://github.com/adobe/target-java-sdk)Cible.

Le [!DNL Target] SDK Java vous permet de déployer [!DNL Target] côté serveur. Ce SDK Java vous permet de vous intégrer facilement [!DNL Target] à d’autres [!DNL Adobe Experience Cloud] solutions, telles que [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]et [!DNL Adobe Audience Manager].

Le SDK Java introduit les meilleures pratiques et élimine les complexités lors de l’intégration avec [!DNL Target] via notre API de diffusion, de sorte que vos équipes d’ingénieurs puissent se concentrer sur la logique métier.

Pour en savoir plus sur le SDK Java de la Cible, consultez le blog des techniques d&#39;Adobe - Optimisation côté [serveur avec le nouveau SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)Java de la Cible.

## Version 1.1.0 (16 décembre 2019)

La section suivante fournit plus d’informations sur la version 1.1.0 du SDK Java Cible :

### Ajout de la section

* La prise en charge de la configuration du proxy a été ajoutée grâce à une contribution open source de @hisham-hassan.

## Version 1.0.1 (11 novembre 2019)

La section suivante fournit plus d’informations sur la version 1.0.1 du SDK Java Cible :

### Fixe

* Envoyez un ID de données supplémentaire dans une demande de Cible même s’il n’existe aucun cookie API Visiteur.

## Version 1.0.0 (31 octobre 2019)

Les sections suivantes fournissent plus d’informations sur la version 1.0.0 du SDK Java Cible :

### Ajout de la section

* [Prise en charge de l’API](https://developers.adobetarget.com/api/delivery-api/) v1 de la Diffusion de Vue de cible, y compris le chargement de page et la prérécupération de Vue.
   * Prise en charge complète de la diffusion de tous les types d’offres créées dans le compositeur d’expérience visuelle.
* Prise en charge de la prérécupération et des notifications qui permettent d’optimiser les performances en mettant en cache le contenu prérécupéré.
* Prise en charge de l’optimisation des performances dans les [!DNL Target] intégrations hybrides via `serverState`le déploiement [!DNL Target] côté serveur et côté client.
   * Nous introduisons un paramètre appelé `serverState` qui contient des expériences récupérées côté serveur, de sorte qu’at.js v2.2+ ne lancera pas un appel serveur supplémentaire pour récupérer les expériences. Cette approche optimise les performances de chargement de page.
* Open Source sur GitHub en tant que SDK [Java](https://github.com/adobe/target-java-sdk)Cible.
* Validation des arguments de méthode de l’API SDK.
* ajouté README, échantillons et tests unitaires.
* ajouté CoC, lignes directrices sur les contributions, relations publiques et modèles de publication.

