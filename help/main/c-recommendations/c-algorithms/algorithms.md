---
keywords: recommandations;activité de recommandations;critères;algorithme;clé de recommandation;clé personnalisée;secteur industriel vertical;vente au détail;commerce électronique;génération de pistes;b2b;services financiers;média;publication
description: Découvrez comment utiliser les critères dans Adobe [!DNL Target] [!DNL Recommendations].
title: Comment utiliser des critères dans  [!DNL Target] Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 16%

---

# Critères

Les critères dans [!DNL Adobe Target] [!DNL Recommendations] sont des règles qui déterminent quels produits ou contenu recommander selon un jeu prédéterminé de comportements de visiteurs. Les critères peuvent être basés sur les tendances populaires, les comportements actuels et passés d’un visiteur ou des produits et contenus similaires. Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Les sections suivantes expliquent plus d’informations sur les clés de critère et sur la logique de recommandation que vous pouvez utiliser pour chaque clé. Cliquez sur les liens pour obtenir des informations plus détaillées.

## Secteur industriel vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Lors de la création d’un critère, vous sélectionnez un secteur industriel vertical en fonction des objectifs de votre activité de recommandations.

| Secteur industriel vertical | Objectif |
|--- |--- |
| Vente au détail / commerce électronique | Conversion entraînant un achat |
| Génération de piste / B2B / Services financiers | Conversion sans achat |
| Médias / Publication | Engagement |

Les autres options de critère changent en fonction du secteur industriel vertical que vous sélectionnez. Vous pouvez définir votre secteur industriel vertical par défaut sur la page **[!UICONTROL Recommendations > Settings]** ou vous pouvez spécifier le secteur industriel vertical pour chaque critère.

## Type d’algorithme {#section_885B3BB1B43048A88A8926F6B76FC482}

Le type d’algorithme sélectionné détermine les algorithmes disponibles. Il existe plusieurs types d’algorithmes, qui sont représentés sous forme de cartes de critères lors de la configuration d’une activité [!DNL Recommendations].

![Page de critères](assets/criteria-page.png)

Le tableau suivant explique les différents types d’algorithmes et leurs algorithmes associés.

| Type d’algorithme | Quand utiliser | Algorithmes disponibles |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Effectuez des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>Les personnes qui les ont consultés ont consulté ceux-ci</li><li>Les personnes qui les ont consultés ont acheté ces</li><li>Les personnes qui les ont achetés ont acheté ces</li></ul>Pour plus d’informations, voir [Basé sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) dans *Baser la recommandation sur une clé de recommandation*. |
| [!UICONTROL Popularity-Based] | Effectuez des recommandations en fonction de la popularité globale d’un élément sur votre site ou de la popularité des éléments au sein de la catégorie, de la marque, du genre, préférée ou la plus consultée d’un utilisateur, etc. | <ul><li>Les plus consultés sur l’ensemble du site</li><li>Les plus consultés par catégorie</li><li>Attribut d’élément le plus consulté</li><li>Meilleurs vendeurs sur le site</li><li>Meilleurs vendeurs par catégorie</li><li>Meilleurs vendeurs par attribut d’article</li><li>Mesure Début par Analytics</li></ul> |
| [!UICONTROL Item-Based] | Effectuez des recommandations sur la base de la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Les personnes ayant consulté ceci ont acheté cela</li><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Éléments avec des attributs similaires</li></ul> |
| [!UICONTROL User-Based] | Effectuez des recommandations en fonction du comportement de l’utilisateur. | <ul><li>Éléments récemment consultés</li><li>Recommandé pour vous</li></ul> |
| [!UICONTROL Custom Criteria] | Faites des recommandations en fonction d’un fichier personnalisé que vous chargez. | <ul><li>Algorithme personnalisé</li></ul> |

Pour plus d’informations sur chaque algorithme, voir [Baser la recommandation sur une clé de recommandation](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Utilisation d’une clé de recommandation personnalisée {#custom-key}

Vous pouvez également baser les recommandations sur la valeur d’un attribut de profil personnalisé.

>[!NOTE]
>
>Les paramètres de profil personnalisés peuvent être transmis à [!DNL Target] via JavaScript, l’API ou les intégrations. Pour plus d’informations sur les attributs de profil personnalisés, voir [Profils des visiteurs](/help/main/c-target/c-visitor-profile/visitor-profile.md).

Supposons, par exemple, que vous souhaitiez afficher les films recommandés en fonction du film ajouté le plus récemment à la file d’attente par un utilisateur.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Renseignez les informations de la [section Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Dans la section [Algorithme recommandé](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo) , sélectionnez **[!UICONTROL Item Based]** dans la liste **[!UICONTROL Algorithm Type]**.

1. Sélectionnez **[!UICONTROL People Who Viewed This, Viewed That]** dans la liste **[!UICONTROL Algorithm]**.

1. Sélectionnez votre attribut de profil personnalisé dans la liste **[!UICONTROL Recommendation Key]** (par exemple, [!UICONTROL Last Show Added to Watchlist]).

   ![Boîte de dialogue Créer de nouveaux critères](assets/custom-key1.png)

## Affichage des informations sur les critères {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Vous pouvez afficher les détails d’un critère sur une carte pop-up en faisant glisser le pointeur de la souris sur une carte et en cliquant sur l’icône Informations sur une carte de critère sans ouvrir le critère.

![Survol de la carte Critères](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

Cliquez sur l’onglet **[!UICONTROL Algorithm Info]** pour afficher des informations générales sur le critère sélectionné, notamment son nom, ses descriptions, son secteur industriel vertical, son ou ses types de page, sa clé de recommandation, sa logique de recommandation et son identifiant d’algorithme.

![Onglet Informations sur l’algorithme](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

Cliquez sur l’onglet **[!UICONTROL Algorithm Usage]** pour afficher la liste des activités qui font référence aux critères sélectionnés. La carte répertorie les activités actives, inactives et de brouillon. Cliquez sur les listes déroulantes Activités actives/Activités inactives/Activités de brouillon pour afficher la liste complète des activités qui font référence à ce critère. Vous pouvez cliquer sur le lien Activité pour ouvrir l’activité à modifier.

![Onglet Utilisation de l’algorithme](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Algorithm Usage] est actuellement prise en charge pour les activités Recommendations uniquement. Cette fonctionnalité n’est actuellement pas prise en charge pour les activités de test A/B, d’affectation automatique, de ciblage automatique et de ciblage d’expérience (XT) qui incluent [des recommandations sous forme d’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).
