---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
description: 'Deux rapports spécialisés sont disponibles pour les utilisateurs des activités de personnalisation automatisée (AP) et de ciblage automatique (AT) : Segments automatisés et Attributs importants.'
title: Rapports de statistiques de personnalisation
feature: reports
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 68%

---


# ![PREMIUM](/help/assets/premium.png) Rapports Informations sur la personnalisation{#personalization-insights-reports}

Deux rapports spécialisés sont disponibles pour les utilisateurs des activités [!UICONTROL Automated Personalization] (AP) et de [!UICONTROL ciblage automatique] (AT) : Segments automatisés et Attributs importants.

>[!NOTE]
>
>Tenez compte des points suivants lors de l’utilisation des rapports Custom Insights :
>
>* Les activités AP et AT sont disponibles dans le cadre de la solution [!DNL Target Premium]. Elles ne sont pas incluses dans [!DNL Target Standard] sans licence [!DNL Target Premium].
   >
   >
* [!UICONTROL Les rapports Informations sur la personnalisation sont disponibles uniquement pour les activités AP et AT ayant un objectif d’optimisation de la conversion. ] Les activités passées d’un objectif d’optimisation des revenus à un objectif d’optimisation de la conversion, alors qu’elles étaient déjà actives, ne sont pas non plus prises en charge.
   >
   >
* [!UICONTROL Les rapports Custom Insights] ne sont disponibles que si l’objectif  Principal est sélectionné dans la liste déroulante Mesure [!UICONTROL des] rapports.
   >
   >
* Les rapports Informations sur la personnalisation sont uniquement pris en charge dans l’[environnement par défaut](../../administrating-target/hosts.md).
   >
   >
* [!UICONTROL Les rapports Custom Insights] sont générés uniquement pour les activités qui sont dans l’état [!UICONTROL Live] et qui ont été activées et reçoivent du trafic pendant au moins 15 jours.


## Présentation des rapports Informations sur la personnalisation {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

L’objectif des rapports [!UICONTROL Informations sur la personnalisation] est de fournir plus d’informations sur la manière dont les modèles de personnalisation Target sous-jacents à vos activités AP et AT personnalisent le trafic de visiteurs.  The [Random Forest algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md) is the basis for the [!DNL Target] personalization models.

Because the goal of the [!UICONTROL Personalization Insights] reports is to understand how the [!DNL Target] personalization models decided to send which visitor to what piece(s) of content, the [!UICONTROL Personalization Insights] reports reflect only a sub-segment of all the traffic served by your AP or AT activity. Les deux rapports montrent, plus précisément, l’ensemble du trafic ayant utilisé le modèle de personnalisation. En d’autres termes, les rapports [!UICONTROL Informations sur la personnalisation] ne prennent pas en compte le contrôle du trafic ou le trafic traité par le modèle gagnant global.

Deux rapports [!UICONTROL Personnalisation Insights] sont disponibles :

| Rapport | Détails |
|--- |--- |
| [!UICONTROL Segments automatisés] | Différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. This report shows how different automated segments defined by the [!DNL Target] personalization models responded to the offers/experiences in the activity. |
| [!UICONTROL Attributs importants] | Dans les différentes activités, différents attributs sont plus ou moins importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative. |

## Interprétation des attributs dans Informations sur la personnalisation {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Il existe deux types d’attribut représentés dans les rapports [!UICONTROL Informations sur la personnalisation] et utilisés dans vos modèles AP ou de ciblage automatique :

* **Attributs automatiquement collectés par  :**[!DNL Target] Target utilise un ensemble de données de base pour construire ses algorithmes de personnalisation dans les activités AP et AT qui sont reflétés dans Informations sur la personnalisation. Voir [Collecte de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058) pour les types de données, les exemples d’attributs et leur convention de dénomination [!UICONTROL Informations sur la personnalisation]. Notez que même si ces attributs sont pris en compte, les modèles d’une activité individuelle peuvent ne pas utiliser tous ces attributs dans le modèle final.
* **Attributs transmis à Target :** Voir [Chargement de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

[!DNL Target] fournit plusieurs méthodes pour transmettre des données supplémentaires afin d’enrichir le jeu de données de base utilisé pour créer ses algorithmes de personnalisation dans les activités AP et AT : [!DNL Target]

| Type de données | Description | Convention de dénomination des types de données |
|--- |--- |--- |
| Attributs de profil, y compris scripts de profil, API de mise à jour des profils et attributs de profil internes à la page | Toutes les informations que vous avez décidé d’inclure dans le profil utilisateur de Target.<br>Ces informations peuvent provenir de scripts de profil, d’informations chargées à l’aide de l’API de mise à jour du profil, ou des paramètres de profil in-mbox préfixés par « profile ». | `Custom - Profile - [parameter name]` |
| Paramètres de page (également nommés « paramètres mbox ») | Paires nom/valeur transmises directement via le code de page qui ne sont pas stockées dans le profil du visiteur pour une utilisation future. | `Custom - Mbox Parameter - [parameter name]` |
| Attributs du client | Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le chargement effectué, vous pouvez exploiter les données dans Adobe Analytics et Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Audiences partagées (Adobe Audience Manager ou Adobe Analytics) | Audiences créées avec Adobe Audience Manager ou Adobe Analytics et partagées avec Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Audiences/Segments de rapport dans les activités | Audiences définies dans votre activité AP ou de ciblage automatique pendant la configuration dans « Objectifs &amp; Mesures ». | `Custom - Reporting Segment - [segment name]` |

## Vidéo de formation : Utilisation des rapports Informations sur la personnalisation ![Badge de didacticiel](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Pour plus d’informations, voir [Utilisation des rapports Custom Insights en Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs d&#39;Adobe

* Partie 1 : [Sortir le mystère de la magie de la personnalisation pilotée par l&#39;IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Partie 2 : [Un aperçu derrière le rideau de l&#39;IA pour la personnalisation en Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Partie 3 : [MAGIX — La solution au problème de la personnalisation pilotée par l&#39;IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
