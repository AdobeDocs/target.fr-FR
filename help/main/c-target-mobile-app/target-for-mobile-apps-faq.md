---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: Afficher les questions fréquentes et leurs réponses sur l’Adobe [!DNL Target] pour les applications mobiles.
title: What Are Frequently Asked Questions About [!DNL Target] for Mobile Apps?
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 3%

---

# FAQ sur Target pour les applications mobiles

Liste des questions fréquentes sur [!DNL Target] pour les applications mobiles.

## Dois-je utiliser des balises dans [!DNL Adobe Experience Platform] pour déployer le SDK ou puis-je le déployer sans utiliser [!DNL Launch]?

Le SDK est disponible sur la page [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si vous n’utilisez pas [balises dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr), vous devez gérer votre propre fichier de paramètres et le gérer dans votre application.

## Which SDKs are available today?

The Adobe Experience Platform Mobile SDKs currently support iOS, Android, and React. Pour plus d’informations, voir [Guide des SDK Mobile Adobe Experience Cloud Platform](https://aep-sdks.gitbook.io/docs/).

## Quelle est la fréquence de la fonction basée sur l’emplacement, en termes de vérification de la latitude et de la longitude ?

Voir [Documentation du service Adobe Places](https://experienceleague.adobe.com/docs/places/using/home.html) pour plus d’informations.

## Ai-je besoin d’at.js pour que les SDK Adobe Experience Platform Mobile fonctionnent ?

Non, vous n’avez pas besoin d’at.js pour utiliser les SDK mobiles. at.js est la variable [!DNL Target] Bibliothèque JavaScript pour les sites web. Les SDK Adobe Experience Platform Mobile sont destinés aux applications mobiles.

## Is [!DNL Target] Mobile : fonctionnalité d’Adobe [!DNL Target] SKU du produit Premium uniquement ?

Non. Pour [!DNL Adobe Target Standard] Pour les clients, vous pouvez utiliser nos SDK mobiles pour les activités de test A/B et de ciblage d’expérience (XT) uniquement avec les [!DNL Target Standard] Module complémentaire Applications mobiles. If you want to use Recommendations or AI-powered features in the mobile app, you need an [Adobe Target Premium](/help/main/c-intro/intro.md#premium) license.

## Is there a mobile app integration between Adobe Experience Manager (AEM) and [!DNL Target] mobile activities?

It is on our roadmap but there is no timeline yet. Actuellement, vous pouvez partager JSON. [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) d’AEM à Target et il est possible de les utiliser ensuite dans une activité d’application mobile.
