---
keywords: application mobile ; questions fréquentes ; faq ; application mobile cible
description: Vue foire aux questions et leurs réponses sur l’Adobe [!DNL Target] pour les applications mobiles.
title: Questions fréquentes sur  [!DNL Target] pour les applications mobiles
feature: Mise en oeuvre de Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

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

## [!DNL Target] Mobile est-il une fonctionnalité de SKU de produit Premium [!DNL Target] Adobe uniquement ?

Non. Pour les clients [!DNL Adobe Target Standard], vous pouvez utiliser nos SDK mobiles pour les activités de test A/B et de ciblage d’expérience (XT) uniquement avec le module complémentaire d’application mobile [!DNL Target Standard]. Si vous souhaitez utiliser des fonctionnalités Recommendations ou AI dans l’application mobile, vous devez disposer d’une licence [Adobe Target Premium](/help/c-intro/intro.md#premium).

## Existe-t-il une intégration d’applications mobiles entre les activités mobiles Adobe Experience Manager (AEM) et [!DNL Target] ?

Elle figure sur notre feuille de route, mais il n&#39;y a pas encore de calendrier. Actuellement, vous pouvez partager des fragments d’expérience [JSON](/help/c-experiences/c-manage-content/aem-experience-fragments.md) d’AEM à Cible et il est possible de les utiliser ensuite dans une activité d’application mobile.
