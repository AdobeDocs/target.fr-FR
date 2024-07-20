---
keywords: Ciblage;rapports AP;rapports de personnalisation automatisée;ciblage automatique;rapport ciblage automatique;personnalisation;informations;segments automatisés;faq;forum aux questions;attributs importants
description: Découvrez comment utiliser les rapports spécialisés pour les activités Automated Personalization (AP) et de ciblage automatique (AT) - Segments automatisés et Attributs importants.
title: Comment utiliser les rapports Personalization Insights ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 28%

---

# [!UICONTROL Personalization Insights] rapports

Deux rapports spécialisés sont disponibles pour les utilisateurs des activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT) : les rapports [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes].

## Considérations

Tenez compte des points suivants lors de l’utilisation des rapports [!UICONTROL Personalization Insights] :

* Les activités AP et AT sont disponibles dans le cadre de la [[!DNL Target Premium] solution](/help/main/c-intro/intro.md#premium). Elles ne sont pas incluses dans [!DNL Target Standard] sans licence [!DNL Target Premium].

* [!UICONTROL Personalization Insights] Les rapports sont disponibles uniquement pour les activités AP et AT configurées comme suit :

   * [!DNL Target] création de rapports > [!UICONTROL Conversion]

     Par exemple :

     ![Rapport Target > Conversion](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] création de rapports > [!DNL Conversion]

     Par exemple :

     ![Rapports Analytics > Conversion](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] création de rapports > [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     Par exemple :

     ![Utiliser une mesure Analytics > Maximiser le taux de conversion des visites](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* Les activités passées d’un objectif d’optimisation des revenus à un objectif d’optimisation de la conversion, alors qu’elles étaient déjà actives, ne sont pas non plus prises en charge.

* Les rapports [!UICONTROL Personalization Insights] ne sont disponibles que si [!UICONTROL Primary Goal] est sélectionné dans la liste déroulante [!UICONTROL Report Metric].

* Les rapports [!UICONTROL Personalization Insights] sont uniquement pris en charge dans l&#39; [environnement par défaut](/help/main/administrating-target/hosts.md).

* Les rapports [!UICONTROL Personalization Insights] sont générés uniquement pour les activités dont l’état est [!UICONTROL Live] et qui ont été activées et qui reçoivent du trafic pendant au moins 15 jours.

## Présentation de la création de rapports Personalization Insights {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

L’objectif des rapports [!UICONTROL Personalization Insights] est de fournir plus d’informations sur la manière dont les modèles de personnalisation [!UICONTROL Target] sous-jacents à vos activités AP et AT personnalisent le trafic des visiteurs. L’ [algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) est la base des modèles de personnalisation [!DNL Target].

L’objectif des rapports [!UICONTROL Personalization Insights] étant de comprendre comment les modèles de personnalisation [!DNL Target] ont décidé d’envoyer quel visiteur à quel contenu, les rapports [!UICONTROL Personalization Insights] ne reflètent qu’un sous-segment de l’ensemble du trafic traité par votre activité AP ou AT. Les deux rapports montrent, plus précisément, l’ensemble du trafic ayant utilisé le modèle de personnalisation. En d’autres termes, les rapports [!UICONTROL Personalization Insights] ne prennent pas en compte le contrôle du trafic ou du trafic traité par le modèle gagnant global.

Deux [!UICONTROL Personalization Insights] rapports sont disponibles :

| Rapport | Détails |
|--- |--- |
| [!UICONTROL Automated Segments] | Différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres/expériences de l’activité. |
| [!UICONTROL Important Attributes] | Dans les différentes activités, différents attributs sont plus ou moins importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative. |

## Interprétation des attributs dans Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Il existe deux types d’attributs représentés dans les rapports [!UICONTROL Personalization Insights] utilisés dans vos modèles AP ou de ciblage automatique :

* **Attributs collectés automatiquement par Target :** [!DNL Target] utilise un jeu de données de base pour créer ses algorithmes de personnalisation dans les activités AP et AT qui sont reflétés dans Personalization Insights. Voir [Collecte de données pour les algorithmes Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-data.md) pour les types de données, les exemples d’attributs et leur convention d’affectation des noms [!UICONTROL Personalization Insights]. Notez que bien que ces attributs soient pris en compte, les modèles d’une activité individuelle peuvent ne pas utiliser tous ces attributs dans le modèle final.
* **Attributs transmis à Target :** Voir [ Téléchargement de données pour les algorithmes Target Personalization ](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] offre plusieurs moyens de transmettre des données supplémentaires à [!DNL Target] afin d’enrichir le jeu de données de base utilisé pour créer ses algorithmes de personnalisation dans les activités AP et AT :

| Type de données | Description | Convention de dénomination des types de données |
|--- |--- |--- |
| Attributs de profil, y compris scripts de profil, API de mise à jour des profils et attributs de profil internes à la page | Toutes les informations que vous avez décidé d’inclure dans le profil utilisateur de Target.<br>Ces informations peuvent provenir de scripts de profil, d’informations chargées à l’aide de l’API de mise à jour du profil, ou des paramètres de profil in-mbox préfixés par « profile ». | `Custom - Profile - [parameter name]` |
| Paramètres de page (également appelés &quot;paramètres de mbox&quot;) | Paires nom/valeur transmises directement via le code de page qui ne sont pas stockées dans le profil du visiteur pour une utilisation future. | `Custom - Mbox Parameter - [parameter name]` |
| Attributs du client | Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le chargement effectué, vous pouvez exploiter les données dans Adobe Analytics et Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Audiences partagées (Adobe Audience Manager ou Adobe Analytics) | Audiences créées avec Adobe Audience Manager ou Adobe Analytics et partagées avec Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Audiences partagées (plateforme de données clients en temps réel/Adobe Experience Platform) | Audiences créées via la plateforme de données clients en temps réel de Adobe Experience Platform et partagées avec Target via les destinations. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Attributs partagés (plateforme de données clients en temps réel/Adobe Experience Platform) | Attributs créés via la plateforme de données clients en temps réel de Adobe Experience Platform et partagés avec Target via les destinations. Cette fonctionnalité est actuellement dans Beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Audiences/Segments de rapport dans les activités | Audiences définies dans votre activité AP ou de ciblage automatique lors de la configuration dans &quot;Objectifs et mesures&quot;. | `Custom - Reporting Segment - [segment name]` |

## Questions fréquentes

Liste des questions fréquentes sur les rapports [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] [!UICONTROL Insights].

### Quelle est la durée de conservation des données pour les modèles [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] ?

Les modèles [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] sont formés sur les 45 derniers jours du comportement de l’utilisateur (profils utilisateur, événements d’impression et événements de conversion) pour l’activité.

Les modèles [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] conservent le comportement de l’utilisateur, les enregistrements d’entraînement et les données de décision de modèle pendant 90 jours pour produire des rapports [!UICONTROL Insights]. Au bout de 90 jours, les enregistrements de formation et les décisions de modèle sont ignorés. Les modèles [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] conservent également les données d’impression et de conversion agrégées au niveau de l’expérience/de l’offre à des fins de création de rapports pendant deux ans. Ces données sont uniquement des données au niveau agrégé et ne contiennent aucune donnée de profil au niveau individuel.

## Vidéo de formation : utilisation des rapports Personalization Insights ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Pour plus d’informations, voir [Utilisation des rapports Personalization Insights dans Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe Blogs

* Partie 1 : [Sortir le mystère de la magie de Personalization piloté par l&#39;IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Partie 2 : [Un aperçu derrière le rideau de l’IA pour Personalization dans Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Partie 3 : [MAGIX — la solution au problème de boîte noire de Personalization piloté par l’IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
