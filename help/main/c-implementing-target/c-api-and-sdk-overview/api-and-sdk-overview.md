---
keywords: côté serveur;api;sdk;node.js;nodejs;node js;api de recommandations;api:apis
description: En savoir plus sur l’Adobe [!DNL Target] API de diffusion côté serveur, SDK et [!DNL Target] API Recommendations.
title: Où puis-je en savoir plus sur [!DNL Target] API et SDK de diffusion côté serveur ?
feature: Implement Server-side
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 21%

---

# Côté serveur : implémentation de Target

Informations sur [!DNL Adobe Target] API de diffusion côté serveur, SDK et [!DNL Target Recommendations] API.

Le processus suivant se produit dans une implémentation côté serveur de [!DNL Target] :

1. Un périphérique client émet une demande d’expérience via votre serveur.
1. Votre serveur envoie cette demande à [!DNL Target].
1. [!DNL Target] envoie la réponse à votre serveur.
1. Votre serveur décide de l’expérience à diffuser sur l’appareil client pour qu’elle soit rendue.

L’expérience ne doit pas s’afficher dans un navigateur. L’expérience peut s’afficher dans un e-mail ou un kiosque, par le biais d’un assistant vocal ou par le biais d’une autre expérience non visuelle ou d’un périphérique non basé sur un navigateur. Étant donné que votre serveur se trouve entre le client et [!DNL Target], ce type d’implémentation est également idéal si vous avez besoin de plus de contrôle et de sécurité ou si vous avez des processus complexes de serveur principal, que vous souhaitez exécuter sur votre serveur.

>[!NOTE]
>
>Un nouveau visiteur ne peut être initialisé que côté client. Un nouveau visiteur *cannot* être initialisé côté serveur.

Les sections suivantes apportent des informations supplémentaires sur les différentes API et le SDK NodeJS :

## API de diffusion côté serveur

Lien : [API de diffusion côté serveur](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

En utilisant la variable [!DNL Target] API de diffusion, vous pouvez :

* diffuser des expériences sur le web, y compris les canaux SPA et mobiles, ainsi que sur des appareils IoT hors navigateur, tels que des télévisions connectées, des kiosques ou des écrans numériques en magasin ;
* diffuser des expériences à partir de n’importe quelle plateforme ou application côté serveur pouvant effectuer des appels HTTP/s ;
* diffuser des expériences cohérentes et personnalisées à un visiteur quel que soit le canal ou les appareils utilisés par le visiteur pour interagir avec votre entreprise ;
* Mettez en cache les expériences d’un visiteur au cours d’une session sur votre serveur afin d’éviter plusieurs appels d’API, ce qui améliore les performances.
* Intégration transparente avec [!DNL Adobe Experience Cloud] les produits, tels que [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) et la variable [!DNL Experience Cloud ID Service] du côté serveur.

## SDK côté serveur

Lien : [SDK Adobe Target](https://developer.adobe.com/target/)

Le [!DNL Adobe Target] Le portail de documentation du SDK côté serveur vous aide à mettre en oeuvre [!DNL Target] sur vos serveurs dans la langue de votre choix.

## API de recommandation Target

Lien : [API Recommendations de Target](https://developer.adobe.com/target/){target=_blank}.

Les API Recommendations vous permettent d’interagir par programmation avec [!DNL Target] serveurs de recommandations. Ces API peuvent être intégrées à diverses piles d’applications pour exécuter des fonctions que vous exécuteriez généralement via la fonction [!DNL Target] de l’interface utilisateur.
