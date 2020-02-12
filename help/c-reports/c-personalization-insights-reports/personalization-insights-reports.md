---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
description: 'Deux rapports spécialisés sont disponibles pour les utilisateurs des activités de personnalisation automatisée (AP) et de ciblage automatique (AT) : Segments automatisés et Attributs importants.'
title: Rapports de statistiques de personnalisation
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# ![PREMIUM](/help/assets/premium.png) Rapports Informations sur la personnalisation{#personalization-insights-reports}

Deux rapports spécialisés sont disponibles pour les utilisateurs des activités Automated Personalization (AP) et de ciblage automatique (AT) : Segments automatisés et Attributs importants.

>[!NOTE]
>
>Les activités AP et AT sont disponibles dans le cadre de la solution [!DNL Target Premium]. Elles ne sont pas incluses dans [!DNL Target Standard] sans licence [!DNL Target Premium].
>
>Les rapports Informations sur la personnalisation sont disponibles uniquement pour les activités AP et AT ayant un objectif d’optimisation de la conversion. Les activités passées d’un objectif d’optimisation des revenus à un objectif d’optimisation de la conversion, alors qu’elles étaient déjà actives, ne sont pas non plus prises en charge.
>
>Les rapports Informations sur la personnalisation sont uniquement pris en charge dans l’[environnement par défaut](../../administrating-target/hosts.md).
>
>Les rapports Custom Insights sont générés uniquement pour les activités qui sont à l’état En direct et qui ont été activées et reçoivent du trafic pendant au moins 15 jours.

## Présentation des rapports Informations sur la personnalisation {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

L’objectif des rapports [!UICONTROL Informations sur la personnalisation] est de fournir plus d’informations sur la manière dont les modèles de personnalisation Target sous-jacents à vos activités AP et AT personnalisent le trafic de visiteurs. L’[algorithme Forêt aléatoire](/help/c-activities/t-automated-personalization/algo-random-forest.md) est la base des modèles de personnalisation de Target.

Parce que l’objectif des rapports Informations sur la personnalisation est de comprendre comment les modèles de personnalisation de Target ont décidé d’envoyer quel visiteur à quel contenu, les rapports Informations sur la personnalisation ne reflètent qu’un sous-segment de l’ensemble du trafic traité par votre activité AP ou AT. Les deux rapports montrent, plus précisément, l’ensemble du trafic ayant utilisé le modèle de personnalisation. En d’autres termes, les rapports Informations sur la personnalisation ne prennent pas en compte le contrôle du trafic ou le trafic traité par le modèle gagnant global.

Deux rapports Custom Insights sont disponibles :

| Rapport | Détails |
|--- |--- |
| Segments automatisés | Différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité. |
| Attributs importants | Dans les différentes activités, différents attributs sont plus ou moins importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative. |

## Interprétation des attributs dans Informations sur la personnalisation {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Il existe deux types d’attribut représentés dans les rapports [!UICONTROL Informations sur la personnalisation] et utilisés dans vos modèles AP ou de ciblage automatique :

* **Attributs automatiquement collectés par Target :** Target utilise un ensemble de données de base pour construire ses algorithmes de personnalisation dans les activités AP et AT qui sont reflétés dans Informations sur la personnalisation. Voir [Collecte de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058) pour les types de données, les exemples d’attributs et leur convention de dénomination [!UICONTROL Informations sur la personnalisation]. Notez que même si ces attributs sont pris en compte, les modèles d’une activité individuelle peuvent ne pas utiliser tous ces attributs dans le modèle final.
* **Attributs transmis à Target :** Voir [Chargement de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

Target vous offre de nombreuses façons de lui transmettre des données supplémentaires afin d’enrichir l’ensemble de données de base utilisé pour créer ses algorithmes de personnalisation dans les activités AP et AT :

| Type de données | Description | Convention de dénomination des types de données |
|--- |--- |--- |
| Attributs de profil, y compris scripts de profil, API de mise à jour des profils et attributs de profil internes à la page | Toutes les informations que vous avez décidé d’inclure dans le profil utilisateur de Target.<br>Ces informations peuvent provenir de scripts de profil, d’informations chargées à l’aide de l’API de mise à jour du profil, ou des paramètres de profil in-mbox préfixés par « profile ». | `Custom - Profile - [parameter name]` |
| Paramètres de page (également nommés « paramètres mbox ») | Paires nom/valeur transmises directement via le code de page qui ne sont pas stockées dans le profil du visiteur pour une utilisation future. | `Custom - Mbox Parameter - [parameter name]` |
| Attributs du client | Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le chargement effectué, vous pouvez exploiter les données dans Adobe Analytics et Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Audiences partagées (Adobe Audience Manager ou Adobe Analytics) | Audiences créées avec Adobe Audience Manager ou Adobe Analytics et partagées avec Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Audiences/Segments de rapport dans les activités | Audiences définies dans votre activité AP ou de ciblage automatique pendant la configuration dans « Objectifs &amp; Mesures ». | `Custom - Reporting Segment - [segment name]` |

## Vidéo de formation : Utilisation des rapports Informations sur la personnalisation Badge de ![didacticiel](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Pour plus d’informations, voir [Utilisation des rapports Custom Insights dans Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs Adobe

* Partie 1 : Tirer le mystère de la magie de la personnalisation basée sur l&#39;IA [Comprendre le mystère](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Partie 2 : [Un aperçu derrière le rideau de l’IA pour la personnalisation dans Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Partie 3 : [MAGIX — la solution au problème de la personnalisation basée sur l&#39;IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
