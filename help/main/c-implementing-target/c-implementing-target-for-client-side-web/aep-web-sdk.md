---
keywords: SDK web Adobe Experience Platform;sdk web aep;sdk web;sdk;adobe experience cloud;réseau Edge de la plateforme;réseau Edge d’adobe experience platform;réseau Edge;réseau Edge d’aep edge
description: Découvrez comment utiliser le SDK Web de Adobe Experience Platform pour interagir avec les différents services de Adobe Experience Cloud par le biais d’AEP Edge Network.
title: Comment mettre en oeuvre avec le SDK Web Experience Platform ?
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 16%

---

# SDK web Adobe Experience Platform

[!DNL Adobe Experience Platform Web SDK] (SDK Web AEP) est une bibliothèque JavaScript côté client qui permet aux clients de [!DNL Adobe Experience Cloud] pour interagir avec les différents services de l’Experience Cloud (y compris [!DNL Target]) par l’intermédiaire de la variable [!UICONTROL Adobe Experience Platform Edge Network]. Outre la bibliothèque JavaScript, il existe une [!DNL Adobe Experience Platform] extension pour faciliter les configurations de votre SDK Web.

Pour plus d’informations, voir les liens suivants dans la section *SDK Web Adobe Experience Platform* help:

* Pour obtenir des informations complètes : [Présentation du SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr)
* Pour plus d’informations spécifiques à [!DNL Target]: [Présentation de Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html?lang=fr)

## Tutoriel : Mise en oeuvre de Adobe Experience Cloud avec le SDK Web Platform

Découvrez comment [mettre en oeuvre des applications Experience Cloud à l’aide du SDK Web de Adobe Experience Platform ;](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}. Pour plus d’informations spécifiques à Target, voir [Configuration de Target avec le SDK Web de Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html){target=_blank} dans le tutoriel.

## Documentation recommandée

En plus de la variable [!DNL Platform Web SDK] documentation mentionnée ci-dessus, les rubriques de ce guide contiennent également des informations spécifiques à la [!DNL Platform Web SDK] en ce qui concerne [!DNL Target] fonctionnalités et .

| Fonctionnalité | Description/Lien |
| --- | --- |
| [AQ d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md) | Utilisation d’URL AQ dans [!DNL Adobe Target] pour effectuer une AQ d’activité de bout en bout simple avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’AQ qui restent segmentés à partir des données d’activité actives. [!UICONTROL AQ d’activité] permet de tester entièrement votre [!DNL Target] activités avant de les lancer en direct.<br>Voir [Compatibilité du mode AQ de la bibliothèque JavaScript Target](/help/main/c-activities/c-activity-qa/activity-qa.md#compatibility) et [URL d’aperçu](/help/main/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T) est une intégration intersolutions permettant de créer des activités basées sur les mesures de conversion d’[!DNL Analytics] ainsi que sur les segments d’audience. L’intégration A4T vous permet d’utiliser les rapports d’[!DNL Analytics] pour étudier vos résultats.<br>Voir [Types d’activité pris en charge](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) et [Étapes de mise en oeuvre d’une mise en oeuvre SDK Web Adobe Experience Platform](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [Audiences](/help/main/c-target/target.md) | Audiences dans [!DNL Adobe Target] déterminer qui voit le contenu et les expériences dans une activité ciblée ;<br>Voir [Utilisation de la liste Audiences](/help/main/c-target/c-audiences/audiences.md#use-list) et [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md). |
| [Création dʼaudiences](/help/main/c-target/c-audiences/audiences.md) | Les audiences créées dans [!DNL Adobe Experience Platform] fournissent des données client plus riches, qui conduisent de facto à une personnalisation ayant plus dʼimpact.<ul>Voir [Utilisation d’audiences provenant de [!DNL Adobe Experience Platform]](/help/main/c-target/c-audiences/audiences.md#aep). |
| [Décisions d’offre](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | Ajoutez les décisions d’offre créées dans Adobe Journey Optimizer aux activités Target (test A/B manuel ou ciblage d’expérience) afin de déterminer et de diffuser la meilleure offre qui s’offre aux visiteurs sur le web et les appareils mobiles. |
| [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Les offres de redirection provoquent la redirection des navigateurs des visiteurs vers une nouvelle page.<br>Voir [La variable [!DNL Adobe Experience Platform Web SDK] prendre en charge les offres de redirection pour A4T ?](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Jetons de réponse](/help/main/administrating-target/response-tokens.md) | Les jetons de réponse vous permettent d’envoyer des données Target à des Google Analytics et à d’autres intégrations tierces.<br>Voir [Envoi de données à des Google Analytics via le SDK Web Platform](/help/main/administrating-target/response-tokens.md#platform-web-sdk) pour voir un exemple de code montrant comment effectuer cette tâche. |
| [Implémentation d’applications d’une seule page](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) dans le *Présentation du SDK Web Platform* guide. | [!UICONTROL SDK Web Adobe Experience Platform] fournit des fonctionnalités riches qui permettent à votre entreprise d’exécuter la personnalisation sur les technologies côté client de nouvelle génération, telles que les applications d’une seule page (SPA). |
| [Modifications du chiffrement de TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/) | TLS (Transport Layer Security){target=_blank} vous aide à maintenir les normes de sécurité les plus élevées et à promouvoir la sécurité des données client. |
