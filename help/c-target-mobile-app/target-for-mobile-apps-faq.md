---
keywords: application mobile;questions fréquentes;faq;application mobile target
description: Affichez les questions fréquentes et leurs réponses sur Adobe [!DNL Target] pour les applications mobiles.
title: Que sont les questions fréquentes sur [!DNL Target] pour les applications mobiles ?
feature: Implémentation de Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# FAQ sur Target pour les applications mobiles

Liste des questions fréquentes sur [!DNL Target] pour les applications mobiles.

## Dois-je utiliser des balises dans [!DNL Adobe Experience Platform] pour déployer le SDK ou puis-je le déployer sans utiliser [!DNL Launch] ?

Le SDK est disponible sur le [Git Adobe Marketing Cloud](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si vous n’utilisez pas de balises [dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html), vous devez gérer votre propre fichier de paramètres et le gérer dans votre application.

## Quels SDK sont disponibles aujourd’hui ?

Les SDK Adobe Experience Platform Mobile prennent actuellement en charge iOS, Android et React. Pour plus d’informations, voir le [Guide des SDK Mobile de Adobe Experience Cloud Platform](https://aep-sdks.gitbook.io/docs/).

## Quelle est la fréquence de la fonction basée sur l’emplacement, en termes de vérification de la latitude et de la longitude ?

Pour plus d’informations, consultez la [documentation relative à Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/) .

## Ai-je besoin d’at.js pour que les SDK Adobe Experience Platform Mobile fonctionnent ?

Non, vous n’avez pas besoin d’at.js pour utiliser les SDK mobiles. at.js est la bibliothèque JavaScript [!DNL Target] pour les sites web. Les SDK Adobe Experience Platform Mobile sont destinés aux applications mobiles.

## [!DNL Target] Mobile est-il une fonctionnalité d’Adobe [!DNL Target] Produit Premium SKU uniquement ?

Non. Pour les clients [!DNL Adobe Target Standard] , vous pouvez utiliser nos SDK mobiles pour les activités de test A/B et de ciblage d’expérience (XT) uniquement avec le module complémentaire d’application mobile [!DNL Target Standard]. Si vous souhaitez utiliser des fonctionnalités Recommendations ou optimisées par l’IA dans l’application mobile, vous avez besoin d’une licence [Adobe Target Premium](/help/c-intro/intro.md#premium).

## Existe-t-il une intégration d’applications mobiles entre Adobe Experience Manager (AEM) et les activités mobiles [!DNL Target] ?

C&#39;est sur notre feuille de route, mais il n&#39;y a pas encore de calendrier. Actuellement, vous pouvez partager des [fragments d’expérience](/help/c-experiences/c-manage-content/aem-experience-fragments.md) JSON d’AEM vers Target et il est possible de les utiliser ensuite dans une activité d’application mobile.
