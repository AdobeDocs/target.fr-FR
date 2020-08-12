---
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
description: Notes de mise à jour relatives aux API côté serveur Adobe Target.
title: Notes de mise à jour relatives aux API côté serveur Adobe Target.
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 2%

---


# Notes de mise à jour - API côté serveur de Target

Notes de mise à jour relatives aux API [côté serveur](https://developers.adobetarget.com/api/delivery-api/)Adobe Target.

## V1/diffusion (9 octobre 2019)

Un point de terminaison API de diffusion entièrement nouveau a été publié.

* Une nouvelle [documentation](https://developers.adobetarget.com/api/delivery-api/) est disponible.
* Un point de terminaison pour récupérer des expériences pour une ou plusieurs mbox.
* Récupérez des activités créées par le compositeur d’expérience visuelle via l’API.

   La réponse qui contient des activités créées par le compositeur d’expérience visuelle comporte des sélecteurs qui peuvent être utilisés pour masquer au préalable uniquement les parties de votre page qui doivent être personnalisées. Cela permet d’optimiser la mesure [](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Première peinture de contenu de votre page, qui est un indicateur clé de performance clé important pour votre entreprise afin d’obtenir un score élevé dans le système [Google PageRank](https://en.wikipedia.org/wiki/PageRank) .

* Prise en charge d’un objet entièrement nouveau appelé Vues qui est utilisé pour les applications [](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) monopages (SPA) et les applications [](/help/c-target-mobile-app/target-mobile-app.md)mobiles.
* Prise en charge de la prérécupération des vues et des mbox pour optimiser les performances par le biais de la mise en cache.
* Prise en charge de l’envoi de notifications pour les vues et mbox prérécupérées.

>[!IMPORTANT]
>
>La documentation [héritée de l’API](https://developers.adobetarget.com/api/legacy-api/index.html) /v1/mbox et /v2/batchmbox est toujours accessible. Cependant, de nouvelles fonctionnalités seront développées dans la nouvelle API de diffusion et ne seront pas renvoyées aux API héritées.
