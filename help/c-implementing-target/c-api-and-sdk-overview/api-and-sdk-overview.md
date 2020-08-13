---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Informations sur les API de diffusion côté serveur Adobe Target, le SDK Node.js et les API Cible Recommendations.
title: Informations sur les API de diffusion côté serveur Adobe Target, le SDK Node.js et les API Cible Recommendations.
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 11%

---


# Côté serveur : implémentation de Target{#server-side-implement-target}

Informations sur les API de diffusion côté [!DNL Adobe Target] serveur, le SDK Node.js et les [!DNL Target Recommendations] API.

Le processus suivant se produit dans une implémentation côté serveur de [!DNL Target] :

1. Un périphérique client émet une demande d’expérience via votre serveur.
1. Votre serveur envoie cette demande à [!DNL Target].
1. [!DNL Target] envoie la réponse à votre serveur.
1. Votre serveur décide de l’expérience à diffuser sur le périphérique client à rendre.

Il n’est pas nécessaire que l’expérience s’affiche dans un navigateur. L’expérience peut s’afficher dans un courrier électronique ou un kiosque, par le biais d’un assistant vocal ou d’une autre expérience non visuelle ou d’un périphérique non navigateur. Étant donné que votre serveur se trouve entre le client et [!DNL Target], ce type d’implémentation est également idéal si vous avez besoin de plus de contrôle et de sécurité ou si vous avez des processus complexes de serveur principal, que vous souhaitez exécuter sur votre serveur.

Les sections suivantes fournissent des informations supplémentaires sur les différentes API et le SDK NodeJS :

## API de diffusion côté serveur

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Grâce à l’API de [!DNL Target] Diffusion, vous pouvez :

* Proposez des expériences sur le Web, y compris des applications monopages et des canaux mobiles, ainsi que sur des périphériques IoT non basés sur un navigateur, tels que des téléviseurs connectés, des kiosques ou des écrans numériques en magasin.
* Proposez des expériences à partir de n’importe quelle plate-forme ou application côté serveur pouvant effectuer des appels HTTP/s.
* Proposez des expériences cohérentes et personnalisées à un visiteur quel que soit le ou les canaux utilisés par le visiteur pour interagir avec votre entreprise.
* Mettez en cache des expériences pour un visiteur au cours d’une session sur votre serveur afin d’éviter plusieurs appels d’API, ce qui permet d’obtenir de meilleures performances.
* S’intégrer en toute transparence à [!DNL Adobe Experience Cloud] des produits, tels que [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) et le côté [!DNL Experience Cloud ID Service] serveur.

## SDK Node.js

Lien : [SDK Node.js](https://github.com/adobe/target-nodejs-sdk)

Le SDK Node.js est un kit de développement logiciel sophistiqué qui élimine la complexité de la gestion des cookies, des sessions et de l’intégration à [!DNL Experience Cloud] des produits, tels que [!DNL Analytics], [!DNL Experience Cloud Visitor ID Service]et [!DNL Audience Manager]les produits. En arrière-plan, le SDK Node.js utilise l’ `/rest/v1/delivery` API. Voici quelques fonctions notables prises en charge par le SDK Node.js :

* **Prise en charge de la prérécupération et des notifications qui vous permettent d’optimiser les performances par le biais de la mise en cache :** Vous pouvez utiliser le SDK Node.js pour récupérer des expériences et les mettre en cache localement sur votre serveur Node.js afin de minimiser les appels au serveur [!DNL Target] et d’optimiser les performances de votre application.
* **Possibilité de récupérer les activités créées par le compositeur d’expérience visuelle :** Récupérez les activités créées par le compositeur d’expérience visuelle côté serveur. La réponse qui contient des activités créées par le compositeur d’expérience visuelle comporte des sélecteurs qui peuvent être utilisés pour masquer au préalable uniquement les parties de votre page qui doivent être personnalisées. Cela permet d’optimiser la mesure [](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Première peinture de contenu de votre page, qui est un indicateur clé de performance clé important pour votre entreprise afin d’obtenir un score élevé dans le système [Google PageRank](https://en.wikipedia.org/wiki/PageRank) .

## Cible Java SDK

Lien : [Cible Java SDK](https://github.com/adobe/target-java-sdk)

Le SDK Java est un kit de développement logiciel sophistiqué qui élimine les complexités de la gestion des cookies, des sessions et de l’intégration à [!DNL Adobe Experience Cloud] des solutions, telles que [!DNL Adobe Analytics]le, le [!DNL Experience Cloud Visitor ID Service]et [!DNL Adobe Audience Manager]. En arrière-plan, le SDK Java utilise l’ `/rest/v1/delivery` API. Voici quelques fonctionnalités notables qui sont prises en charge dans le SDK Java :

* **Prise en charge de la prérécupération et des notifications qui vous permettent d’optimiser les performances par le biais de la mise en cache**: Vous pouvez utiliser le JavaSDK pour récupérer des expériences et les mettre en cache localement sur votre serveur Java afin de minimiser les appels au serveur [!DNL Target] et d’optimiser les performances de votre application.
* **Possibilité de récupérer des activités** créées par le compositeur d’expérience visuelle : Récupérez les activités créées par le compositeur d’expérience visuelle côté serveur. La réponse qui contient des activités créées par le compositeur d’expérience visuelle comporte des sélecteurs qui peuvent être utilisés pour masquer au préalable uniquement les parties de votre page qui doivent être personnalisées. Cela permet d’optimiser la mesure [Première peinture](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html) de contenu de votre page, qui est un indicateur clé de performance clé important pour votre entreprise afin d’obtenir un score élevé dans le système [Google PageRank](https://en.wikipedia.org/wiki/PageRank) .

## API de recommandation Target

Lien : [API](https://developers.adobetarget.com/api/recommendations) Recommendations cible et présentation [de l’API](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html)Adobe Recommendations.

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
