---
keywords: SDK web Adobe Experience Platform;sdk web aep;sdk web;sdk;adobe experience cloud;réseau Edge de la plateforme;réseau Edge d’adobe experience platform;réseau Edge;réseau Edge d’aep edge
description: Découvrez comment utiliser le SDK Web de Adobe Experience Platform pour interagir avec les différents services de Adobe Experience Cloud par le biais d’AEP Edge Network.
title: Comment mettre en oeuvre avec le SDK Web Experience Platform ?
feature: SDK Web AEP
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: eb3cae982ecb62f7745549562ea144228ad895fa
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 7%

---

# SDK web Adobe Experience Platform

[!DNL Adobe Experience Platform Web SDK] (SDK Web AEP) est une bibliothèque JavaScript côté client qui permet  [!DNL Adobe Experience Cloud] aux clients d’ interagir avec les différents services de l’Experience Cloud (y compris  [!DNL Target]) par le biais du  [!UICONTROL réseau Adobe Experience Platform Edge]. Outre la bibliothèque JavaScript, il existe une extension [!DNL Experience Platform Launch] pour vous aider à configurer vos SDK Web.

Pour plus d’informations, voir les liens suivants dans l’*aide du SDK Web Adobe Experience Platform* :

* Pour obtenir des informations complètes : [Qu’est-ce que le SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* Pour plus d’informations spécifiques à [!DNL Target] : [Présentation de Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## Documentation recommandée dans ce guide

Outre la documentation [!DNL Platform Web SDK] mentionnée ci-dessus, les rubriques de ce guide contiennent également des informations spécifiques à [!DNL Platform Web SDK] en ce qui concerne les fonctionnalités de [!DNL Target].

| Fonctionnalité | Description/Lien |
| --- | --- |
| [AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md) | Utilisez les URL AQ dans [!DNL Adobe Target] pour vérifier simplement et de manière exhaustive la qualité des activités avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’AQ qui restent segmentés à partir des données d’activité actives. [!UICONTROL L’] AQ des activités vous permet de tester entièrement vos  [!DNL Target] activités avant de les lancer en ligne.<br>Voir  [Compatibilité du mode AQ de la bibliothèque JavaScript de Target ](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) et  [URL d’aperçu](/help/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T) est une intégration intersolutions qui vous permet de créer des activités basées sur des mesures de  [!DNL Analytics] conversion et des segments d’audience. L’intégration A4T vous permet d’utiliser des rapports [!DNL Analytics] pour examiner vos résultats.<br>Voir  [Types d’activité pris en charge ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) et  [Etapes de mise en oeuvre pour une mise en oeuvre du SDK Web Adobe Experience Platform](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [Audiences](/help/c-target/target.md) | Les audiences de [!DNL Adobe Target] déterminent qui voit le contenu et les expériences dans une activité ciblée.<br>Voir  [Utilisation de la liste Audiences ](/help/c-target/c-audiences/audiences.md#use-list) et  [Combinaison de plusieurs audiences](/help/c-target/combining-multiple-audiences.md). |
| [FAQ sur les offres de redirection - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Les offres de redirection provoquent la redirection des navigateurs des visiteurs vers une nouvelle page.<br>Voir  [Ces offres  [!DNL Adobe Experience Platform Web SDK] de redirection sont-elles prises en charge pour A4T ?](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Jetons de réponse](/help/administrating-target/response-tokens.md) | Les jetons de réponse vous permettent d’envoyer des données Target à des Google Analytics et à d’autres intégrations tierces.<br>Voir  [Envoi de données à des Google Analytics via le ](/help/administrating-target/response-tokens.md#platform-web-sdk) SDK Web Platform pour obtenir un exemple de code expliquant comment réaliser cette tâche. |
| [Modifications du chiffrement de TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS (Transport Layer Security) vous aide à maintenir les normes de sécurité les plus élevées et à promouvoir la sécurité des données client. |
