---
keywords: at.js;api;release;updates;apis;sdks;server side;server side;server side;api;delivery api
description: Notes de mise à jour relatives aux API côté serveur d’Adobe Target.
title: Notes de mise à jour relatives aux API côté serveur d’Adobe Target.
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Notes de mise à jour - API côté serveur Target

Notes de mise à jour relatives aux API [côté serveur d’](https://developers.adobetarget.com/api/delivery-api/)Adobe Target.

## V1/livraison (9 octobre 2019)

Un point de fin API de remise entièrement nouveau a été publié.

* Une nouvelle [documentation](https://developers.adobetarget.com/api/delivery-api/) est disponible.
* Un point de fin pour récupérer des expériences pour une ou plusieurs mbox.
* Récupérez les activités créées par le compositeur d’expérience visuelle via l’API.

   La réponse qui contient des activités créées par le compositeur d’expérience visuelle comporte des sélecteurs qui peuvent être utilisés pour masquer au préalable uniquement les parties de votre page qui doivent être personnalisées. Cela permet d’optimiser la mesure [](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Première peinture de contenu de votre page, qui est un indicateur clé de performance clé important pour votre entreprise afin d’obtenir un score élevé dans le système de classement [des pages](https://en.wikipedia.org/wiki/PageRank) Google.

* Prise en charge d’un objet entièrement nouveau appelé Vues, qui est utilisé pour les applications [](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) monopages (SPA) et les applications [](/help/c-target-mobile-app/target-mobile-app.md)mobiles.
* Prise en charge de la prérécupération des vues et des mbox pour optimiser les performances par le biais de la mise en cache.
* Prise en charge de l’envoi de notifications pour les vues prédéfinies et les mbox.

>[!IMPORTANT]
>
>La documentation [héritée de l’API](https://developers.adobetarget.com/api/legacy-api/index.html) /v1/mbox et /v2/batchmbox est toujours accessible. Toutefois, de nouvelles fonctionnalités seront développées dans la nouvelle API de diffusion et ne seront pas reportées vers les API héritées.
