---
keywords: côté serveur ; côté serveur ; api ; sdk ; node.js ; nodejs ; node js ; recommendations api ; api:apis
description: Informations sur les API de diffusion côté serveur d’Adobe Target, les SDK et les API de Cible Recommendations.
title: Informations sur les API de Diffusion côté serveur, le SDK Node.js et les API Recommendations
feature: Implement Server-side
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 20%

---


# Côté serveur : implémentation de Target

Informations sur les [!DNL Adobe Target] API de diffusion côté serveur, les SDK et les API [!DNL Target Recommendations].

Le processus suivant se produit dans une implémentation côté serveur de [!DNL Target] :

1. Un périphérique client émet une demande d’expérience via votre serveur.
1. Votre serveur envoie cette demande à [!DNL Target].
1. [!DNL Target] envoie la réponse à votre serveur.
1. Votre serveur décide de l’expérience à diffuser sur le périphérique client à rendre.

Il n’est pas nécessaire que l’expérience s’affiche dans un navigateur. L’expérience peut s’afficher dans un courrier électronique ou un kiosque, par le biais d’un assistant vocal ou d’une autre expérience non visuelle ou d’un périphérique non navigateur. Étant donné que votre serveur se trouve entre le client et [!DNL Target], ce type d’implémentation est également idéal si vous avez besoin de plus de contrôle et de sécurité ou si vous avez des processus complexes de serveur principal, que vous souhaitez exécuter sur votre serveur.

>[!NOTE]
>
>Un nouveau visiteur ne peut être initialisé que côté client. Un nouveau visiteur *ne peut pas* être initialisé côté serveur.

Les sections suivantes fournissent des informations supplémentaires sur les différentes API et le SDK NodeJS :

## API de diffusion côté serveur

Lien : [API de Diffusion côté serveur](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Grâce à l&#39;API de Diffusion [!DNL Target], vous pouvez :

* Proposez des expériences sur le Web, y compris sur les canaux SPA et mobiles, ainsi que sur les périphériques IoT non basés sur un navigateur, tels que les téléviseurs connectés, les kiosques ou les écrans numériques en magasin.
* Proposez des expériences à partir de n’importe quelle plate-forme ou application côté serveur pouvant effectuer des appels HTTP/s.
* Proposez des expériences cohérentes et personnalisées à un visiteur quel que soit le ou les canaux utilisés par le visiteur pour interagir avec votre entreprise.
* Mettez en cache des expériences pour un visiteur au cours d’une session sur votre serveur afin d’éviter plusieurs appels d’API, ce qui permet d’obtenir de meilleures performances.
* Intégrez en toute transparence les produits [!DNL Adobe Experience Cloud], tels que [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) et [!DNL Experience Cloud ID Service] du côté serveur.

## SDK côté serveur

Lien : [Adobe Target SDKs](https://adobetarget-sdks.gitbook.io/docs/)

Le portail de documentation du SDK côté serveur [!DNL Adobe Target] vous aide à implémenter [!DNL Target] sur vos serveurs dans la langue de votre choix.

## API de recommandation Target

Lien : [API Recommendations de Cible](https://developers.adobetarget.com/api/recommendations) et [Aperçu de l’API Adobe Recommendations](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html).

Les API Recommendations vous permettent d’interagir par programmation avec les serveurs de Recommandations [!DNL Target]. Ces API peuvent être intégrées à une gamme de piles d&#39;applications pour exécuter des fonctions que vous utiliseriez habituellement dans l&#39;interface utilisateur [!DNL Target].
