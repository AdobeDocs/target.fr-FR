---
description: Informations sur les API de diffusion côté serveur d’Adobe Target, le SDK Node.js et les API de recommandations Target.
keywords: côté serveur;côté serveur;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
seo-description: Informations sur les API de diffusion côté serveur d’Adobe Target, le SDK Node.js et les API de recommandations Target.
seo-title: Informations sur les API de diffusion côté serveur d’Adobe Target, le SDK Node.js et les API de recommandations Target.
solution: Target
title: Côté serveur implémentation de Target
topic: Recommandations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: afec96b2bec18048ab7132232711d2c14769c46c

---


# Côté serveur : implémentation de Target{#server-side-implement-target}

Informations sur les API de remise côté [!DNL Adobe Target] serveur, le SDK Node.js et [!DNL Target Recommendations] les API.

Le processus suivant se produit dans une implémentation côté serveur de [!DNL Target] :

1. Un périphérique client émet une demande d’expérience via votre serveur.
1. Votre serveur envoie cette demande à [!DNL Target].
1. [!DNL Target] envoie la réponse à votre serveur.
1. Votre serveur décide de l’expérience à diffuser sur le périphérique client pour qu’il effectue le rendu.

Il n’est pas nécessaire que l’expérience s’affiche dans un navigateur. L’expérience peut s’afficher dans un courrier électronique ou un kiosque, par le biais d’un assistant vocal ou d’une autre expérience non visuelle ou d’un périphérique non basé sur un navigateur. Étant donné que votre serveur se trouve entre le client et [!DNL Target], ce type d’implémentation est également idéal si vous avez besoin de plus de contrôle et de sécurité ou si vous avez des processus complexes de serveur principal, que vous souhaitez exécuter sur votre serveur.

Les sections suivantes fournissent plus d’informations sur les différentes API et le SDK NodeJS :

## API de diffusion côté serveur

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Grâce à l’API [!DNL Target] de remise, vous pouvez :

* Proposez des expériences sur le Web, y compris des applications monopages et des canaux mobiles, ainsi que sur des périphériques IoT non basés sur un navigateur, tels que des téléviseurs connectés, des kiosques ou des écrans numériques en magasin.
* Proposez des expériences à partir de n’importe quelle plateforme ou application côté serveur pouvant effectuer des appels HTTP/s.
* Proposez des expériences cohérentes et personnalisées à un visiteur quel que soit le canal ou les périphériques utilisés par le visiteur pour interagir avec votre entreprise.
* Mettez en cache des expériences pour un visiteur au cours d’une session sur votre serveur afin d’éviter plusieurs appels d’API, ce qui améliore les performances.
* S’intégrer en toute transparence à [!DNL Adobe Experience Cloud] des produits, tels que [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) et le côté serveur [!DNL Experience Cloud ID Service] .

## SDK Node.js

Lien : SDK [Node.js](https://github.com/adobe/target-nodejs-sdk)

Le SDK Node.js est un kit de développement logiciel sophistiqué qui élimine la complexité de la gestion des cookies, des sessions et de l’intégration avec [!DNL Experience Cloud] des produits, tels [!DNL Analytics], [!DNL Experience Cloud Visitor ID Service]et [!DNL Audience Manager]. En arrière-plan, le SDK Node.js utilise l’ `/rest/v1/delivery` API. Voici quelques fonctionnalités notables prises en charge par le SDK Node.js :

* **** Prise en charge de la prérécupération et des notifications qui vous permettent d’optimiser les performances par le biais de la mise en cache : Vous pouvez utiliser le SDK Node.js pour récupérer des expériences et les mettre en cache localement sur votre serveur Node.js afin de minimiser les appels au serveur [!DNL Target] et d’optimiser les performances de votre application.
* **** Possibilité de récupérer les activités créées par le compositeur d’expérience visuelle : Récupérez les activités créées par le compositeur d’expérience visuelle côté serveur. La réponse qui contient des activités créées par le compositeur d’expérience visuelle comporte des sélecteurs qui peuvent être utilisés pour masquer au préalable uniquement les parties de votre page qui doivent être personnalisées. Cela permet d’optimiser la mesure [](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Première peinture de contenu de votre page, qui est un indicateur clé de performance clé important pour votre entreprise afin d’obtenir un score élevé dans le système de classement [des pages](https://en.wikipedia.org/wiki/PageRank) Google.

## SDK Java Target

Le SDK Java est un kit de développement logiciel sophistiqué qui élimine les complexités de la gestion des cookies, des sessions et de l’intégration avec [!DNL Adobe Experience Cloud] des solutions, telles que [!DNL Adobe Analytics], le [!DNL Experience Cloud Visitor ID Service]et [!DNL Adobe Audience Manager]. En arrière-plan, le SDK Java utilise l’ `/rest/v1/delivery` API. Voici quelques fonctionnalités notables prises en charge par le SDK Java :

* **Prise en charge de la prérécupération et des notifications qui vous permettent d’optimiser les performances via la mise en cache**: Vous pouvez utiliser le JavaSDK pour récupérer des expériences et les mettre en cache localement sur votre serveur Java afin de minimiser les appels au serveur [!DNL Target] et d’optimiser les performances de votre application.
* **Possibilité de récupérer les activités** créées par le compositeur d’expérience visuelle : Récupérez les activités créées par le compositeur d’expérience visuelle côté serveur. La réponse qui contient des activités créées par le compositeur d’expérience visuelle comporte des sélecteurs qui peuvent être utilisés pour masquer au préalable uniquement les parties de votre page qui doivent être personnalisées. Cela permet d’optimiser la mesure [Première peinture](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html) de contenu de votre page, qui est un indicateur clé de performance clé important pour votre entreprise afin d’obtenir un score élevé dans le système de classement [des pages](https://en.wikipedia.org/wiki/PageRank) Google.

## API de recommandation Target

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
