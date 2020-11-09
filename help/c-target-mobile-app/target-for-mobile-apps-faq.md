---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: Questions fréquentes sur Adobe Target pour les applications mobiles.
title: Questions fréquentes sur Adobe Target pour les applications mobiles
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 2%

---


# FAQ sur Target pour les applications mobiles

Liste des questions fréquentes sur [!DNL Target] les applications mobiles.

## Dois-je utiliser [!DNL Adobe Experience Platform Launch] pour déployer le SDK ou puis-je le déployer sans l’utiliser [!DNL Launch]?

Le SDK est disponible sur le git [](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)Adobe Marketing Cloud. Si vous n’utilisez pas [Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html), vous devez gérer votre propre fichier de paramètres et le gérer dans votre application.

## Quels sont les SDK disponibles aujourd’hui ?

Les SDK Adobe Experience Platform Mobile prennent actuellement en charge iOS, Android et React. Pour plus d&#39;informations, reportez-vous au guide [des kits SDK mobiles de la plateforme](https://aep-sdks.gitbook.io/docs/)Adobe Experience Cloud.

## Quelle est la fréquence de la fonction basée sur l&#39;emplacement, en termes de vérification de la latitude et de la longitude ?

Pour plus d’informations, consultez la documentation [Lieux d’](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe.

## Ai-je besoin d’at.js pour que les kits SDK Adobe Experience Platform Mobile fonctionnent ?

Non, vous n’avez pas besoin d’at.js pour utiliser les SDK mobiles. at.js est la bibliothèque [!DNL Target] JavaScript pour les sites Web. Les kits SDK Adobe Experience Platform Mobile sont destinés aux applications mobiles.

## Cible Mobile est-elle une fonctionnalité du SKU du produit Adobe Target Premium uniquement ?

Non. Pour [!DNL Adobe Target Standard] les clients, vous pouvez utiliser nos SDK mobiles pour les activités A/B Test and Experience Targeting (XT) uniquement avec le module complémentaire [!DNL Target Standard] Mobile App. Si vous souhaitez utiliser des fonctionnalités Recommendations ou AI dans l’application mobile, vous devez disposer d’une licence [Adobe Target Premium](/help/c-intro/intro.md#premium) .

## Existe-t-il une intégration d&#39;applications mobiles entre Adobe Experience Manager (AEM) et les activités mobiles Cible ?

Elle figure sur notre feuille de route, mais il n&#39;y a pas encore de calendrier. Actuellement, vous pouvez partager des fragments [d’](/help/c-experiences/c-manage-content/aem-experience-fragments.md) expérience JSON d’AEM à Cible et il est possible de les utiliser ensuite dans une activité d’application mobile.
