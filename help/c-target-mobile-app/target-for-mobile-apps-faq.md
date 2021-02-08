---
keywords: application mobile ; questions fréquentes ; faq ; application mobile cible
description: Vue foire aux questions et leurs réponses sur Adobe Target pour les applications mobiles.
title: Quelles sont les questions fréquentes sur la Cible des applications mobiles ?
feature: Implement Mobile
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# FAQ sur Target pour les applications mobiles

Liste des questions fréquentes sur [!DNL Target] pour les applications mobiles.

## Dois-je utiliser [!DNL Adobe Experience Platform Launch] pour déployer le SDK ou puis-je le déployer sans utiliser [!DNL Launch] ?

Le SDK est disponible sur le [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si vous n’utilisez pas [Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html), vous devez gérer votre propre fichier de paramètres et le gérer dans votre application.

## Quels sont les SDK disponibles aujourd’hui ?

Les SDK Adobe Experience Platform Mobile prennent actuellement en charge iOS, Android et React. Pour plus d’informations, voir le [Guide des SDK mobiles de la plateforme Adobe Experience Cloud](https://aep-sdks.gitbook.io/docs/).

## Quelle est la fréquence de la fonction basée sur l&#39;emplacement, en termes de vérification de la latitude et de la longitude ?

Pour plus d&#39;informations, consultez la documentation [Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/).

## Ai-je besoin d’at.js pour que les kits SDK Adobe Experience Platform Mobile fonctionnent ?

Non, vous n’avez pas besoin d’at.js pour utiliser les SDK mobiles. at.js est la [!DNL Target] bibliothèque JavaScript pour les sites Web. Les kits SDK Adobe Experience Platform Mobile sont destinés aux applications mobiles.

## Cible Mobile est-elle une fonctionnalité du SKU du produit Adobe Target Premium uniquement ?

Non. Pour les clients [!DNL Adobe Target Standard], vous pouvez utiliser nos SDK mobiles pour les activités de test A/B et de ciblage d’expérience (XT) uniquement avec le module complémentaire d’application mobile [!DNL Target Standard]. Si vous souhaitez utiliser des fonctionnalités Recommendations ou AI dans l’application mobile, vous devez disposer d’une licence [Adobe Target Premium](/help/c-intro/intro.md#premium).

## Existe-t-il une intégration d&#39;applications mobiles entre Adobe Experience Manager (AEM) et les activités mobiles Cible ?

Elle figure sur notre feuille de route, mais il n&#39;y a pas encore de calendrier. Actuellement, vous pouvez partager des fragments d’expérience [JSON](/help/c-experiences/c-manage-content/aem-experience-fragments.md) d’AEM à Cible et il est possible de les utiliser ensuite dans une activité d’application mobile.
