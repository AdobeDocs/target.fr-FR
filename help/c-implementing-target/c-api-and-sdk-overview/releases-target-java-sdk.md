---
description: Notes de mise à jour relatives au SDK Java d’Adobe Target
keywords: at.js;sdk;release;updates;sdks;server side;server side;server side;java;java sdk
seo-description: Notes de mise à jour relatives au SDK Java d’Adobe Target.
seo-title: Notes de mise à jour relatives au SDK Java d’Adobe Target.
solution: Target
title: Notes de mise à jour - SDK Java Target
topic: Standard
translation-type: tm+mt
source-git-commit: 540367e4c49c712df98dc132bccf4f29b4d6f095

---


# Notes de mise à jour - SDK Java Target

Notes de mise à jour relatives au SDK [Java](https://github.com/adobe/target-java-sdk)Target.

Le [!DNL Target] SDK Java vous permet de déployer [!DNL Target] côté serveur. Ce SDK Java vous permet de vous intégrer facilement [!DNL Target] à d’autres [!DNL Adobe Experience Cloud] solutions, telles que [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]et [!DNL Adobe Audience Manager].

Le SDK Java introduit les meilleures pratiques et élimine les complexités lors de l’intégration avec [!DNL Target] via notre API de diffusion afin que vos équipes d’ingénieurs puissent se concentrer sur la logique métier.

## Version 1.0.0 (31 octobre 2019)

Les sections suivantes fournissent plus d’informations sur la version 1.0.0 du SDK Java Target :

### Ajout de la section

* [Prise en charge de l’API](https://developers.adobetarget.com/api/delivery-api/) Target View Delivery v1, y compris les fonctions de prérécupération des pages et des vues.
   * Prise en charge complète de la diffusion de tous les types d’offres créées dans le compositeur d’expérience visuelle (VEC).
* Prise en charge de la prérécupération et des notifications permettant d’optimiser les performances en mettant en cache le contenu prérécupéré.
* Prise en charge de l’optimisation des performances dans les [!DNL Target] intégrations hybrides via `serverState`, lors [!DNL Target] du déploiement côté serveur et côté client.
   * Nous introduisons un paramètre appelé `serverState` qui contient des expériences récupérées côté serveur, de sorte qu’at.js v2.2+ ne lancera pas un appel serveur supplémentaire pour récupérer les expériences. Cette approche optimise les performances de chargement des pages.
* Open Source sur GitHub en tant que SDK [Java](https://github.com/adobe/target-java-sdk)Target.
* Validation des arguments de méthode de l’API SDK.
* Ajout de tests LISEZ-MOI, d’exemples et d’unités.
* Ajout de modèles de coC, de lignes directrices sur les contributions, de relations publiques et de problèmes.

