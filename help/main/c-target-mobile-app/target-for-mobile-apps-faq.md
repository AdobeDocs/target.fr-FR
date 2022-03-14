---
keywords: application mobile;questions fréquentes;faq;application mobile target
description: Afficher les questions fréquentes et leurs réponses sur l’Adobe [!DNL Target] pour les applications mobiles.
title: Questions fréquentes sur [!DNL Target] pour les applications mobiles ?
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 3%

---

# FAQ sur Target pour les applications mobiles

Liste des questions fréquentes sur [!DNL Target] pour les applications mobiles.

## Dois-je utiliser des balises dans [!DNL Adobe Experience Platform] pour déployer le SDK ou puis-je le déployer sans utiliser [!DNL Launch]?

Le SDK est disponible sur la page [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si vous n’utilisez pas [balises dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr), vous devez gérer votre propre fichier de paramètres et le gérer dans votre application.

## Quels SDK sont disponibles aujourd’hui ?

Les SDK Adobe Experience Platform Mobile prennent actuellement en charge iOS, Android et React. Pour plus d’informations, voir [Guide des SDK Mobile Adobe Experience Cloud Platform](https://aep-sdks.gitbook.io/docs/).

## Quelle est la fréquence de la fonction basée sur l’emplacement, en termes de vérification de la latitude et de la longitude ?

Voir [Documentation sur Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/) pour plus d’informations.

## Ai-je besoin d’at.js pour que les SDK Adobe Experience Platform Mobile fonctionnent ?

Non, vous n’avez pas besoin d’at.js pour utiliser les SDK mobiles. at.js est la variable [!DNL Target] Bibliothèque JavaScript pour les sites web. Les SDK Adobe Experience Platform Mobile sont destinés aux applications mobiles.

## Is [!DNL Target] Mobile : fonctionnalité d’Adobe [!DNL Target] SKU du produit Premium uniquement ?

Non. Pour [!DNL Adobe Target Standard] Pour les clients, vous pouvez utiliser nos SDK mobiles pour les activités de test A/B et de ciblage d’expérience (XT) uniquement avec les [!DNL Target Standard] Module complémentaire Applications mobiles. Si vous souhaitez utiliser des fonctionnalités Recommendations ou optimisées par l’IA dans l’application mobile, vous avez besoin d’une [Adobe Target Premium](/help/main/c-intro/intro.md#premium) licence.

## Existe-t-il une intégration d’applications mobiles entre Adobe Experience Manager (AEM) et [!DNL Target] activités mobiles ?

C&#39;est sur notre feuille de route, mais il n&#39;y a pas encore de calendrier. Actuellement, vous pouvez partager JSON. [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) d’AEM à Target et il est possible de les utiliser ensuite dans une activité d’application mobile.
