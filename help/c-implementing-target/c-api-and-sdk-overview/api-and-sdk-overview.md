---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Informations sur les API de diffusion côté serveur Adobe Target, le SDK Node.js et les API Cible Recommendations.
title: Informations sur les API de diffusion côté serveur Adobe Target, le SDK Node.js et les API Cible Recommendations.
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: b6d4cc35e32f118ff46fcd3b235c8b5deae35d05
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 21%

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

* Proposez des expériences sur le Web, y compris sur les canaux SPA et mobiles, ainsi que sur les périphériques IoT non basés sur un navigateur, tels que les téléviseurs connectés, les kiosques ou les écrans numériques en magasin.
* Proposez des expériences à partir de n’importe quelle plate-forme ou application côté serveur pouvant effectuer des appels HTTP/s.
* Proposez des expériences cohérentes et personnalisées à un visiteur quel que soit le ou les canaux utilisés par le visiteur pour interagir avec votre entreprise.
* Mettez en cache des expériences pour un visiteur au cours d’une session sur votre serveur afin d’éviter plusieurs appels d’API, ce qui permet d’obtenir de meilleures performances.
* S’intégrer en toute transparence à [!DNL Adobe Experience Cloud] des produits, tels que [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) et le côté [!DNL Experience Cloud ID Service] serveur.

## SDK côté serveur

Lien : [SDK Adobe Target](https://adobetarget-sdks.gitbook.io/docs/)

Le portail de documentation du SDK côté [!DNL Adobe Target] serveur vous permet de mettre en oeuvre [!DNL Target] sur vos serveurs dans la langue de votre choix.

## API de recommandation Target

Lien : [API](https://developers.adobetarget.com/api/recommendations) Recommendations cible et présentation [de l’API](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html)Adobe Recommendations.

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
