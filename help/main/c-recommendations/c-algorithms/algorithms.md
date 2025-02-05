---
keywords: recommendations;activité recommendations;critères;algorithme;clé de recommandation;clé personnalisée;secteur vertical;vente au détail;commerce électronique;génération de pistes;b2b;services financiers;médias;publication
description: Découvrez comment utiliser les critères dans Adobe [!DNL Target] [!DNL Recommendations].
title: Comment utiliser les critères dans [!DNL Target] Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%

---

# [!UICONTROL Criteria]

Les [!UICONTROL Criteria] dans [!DNL Adobe Target] [!DNL Recommendations] sont des règles qui déterminent quels produits ou contenus recommander selon un ensemble prédéterminé de comportements de visiteurs. Les critères peuvent être basés sur des tendances populaires, les comportements actuels et passés d’un visiteur ou des produits et contenus similaires. Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Les sections suivantes en disent plus sur les clés de critère et la logique de recommandation que vous pouvez utiliser pour chaque clé. Cliquez sur les liens pour obtenir des informations plus détaillées.

## Secteur industriel vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Lors de la création d’un critère, vous sélectionnez un secteur vertical en fonction des objectifs de votre activité Recommendations .

| Secteur industriel vertical | Objectif |
|--- |--- |
| [!UICONTROL Retail/Ecommerce] | Conversion entraînant un achat |
| [!UICONTROL Lead Generation/B2B/Financial Services] | Conversion sans achat |
| [!UICONTROL Media/Publishing] | Engagement |

Les autres options de critères changent en fonction du secteur vertical que vous sélectionnez. Vous pouvez définir le secteur d’activité vertical par défaut sur la page **[!UICONTROL Administration]>[!UICONTROL Recommendations]** ou spécifier le secteur d’activité vertical pour chaque critère.

## Type d’algorithme {#section_885B3BB1B43048A88A8926F6B76FC482}

Le type d’algorithme que vous sélectionnez détermine les algorithmes disponibles.

Le tableau suivant explique les différents types d’algorithmes et les algorithmes associés.

| Type d’algorithme | Quand l’utiliser | Algorithmes disponibles |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Faites des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul>Pour plus d’informations, voir [Basé sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) dans *Baser la recommandation sur une clé de recommandation*. |
| [!UICONTROL Popularity-Based] | Faites des recommandations en fonction de la popularité globale d’un élément sur votre site ou en fonction de la popularité des éléments dans la catégorie, la marque, le genre préféré ou le plus consulté d’un utilisateur, etc. | <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | Faites des recommandations basées sur la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | Faites des recommandations basées sur le comportement de l’utilisateur. | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | Faites des recommandations basées sur un fichier personnalisé que vous téléchargez. | <ul><li>Algorithme personnalisé</li></ul> |

Pour plus d’informations sur chaque algorithme, voir [Baser la recommandation sur une clé de recommandation](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Utilisation d’une clé de recommandation personnalisée {#custom-key}

Vous pouvez également baser les recommandations sur la valeur d’un attribut de profil personnalisé.

>[!NOTE]
>
>Les paramètres de profil personnalisés peuvent être transmis à [!DNL Target] par le biais de JavaScript, de l’API ou des intégrations. Pour plus d’informations sur les attributs de profil personnalisés, voir [Profils des visiteurs](/help/main/c-target/c-visitor-profile/visitor-profile.md).

Supposons, par exemple, que vous souhaitiez afficher des séquences recommandées en fonction de la dernière séquence ajoutée par un utilisateur à la file d’attente.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Renseignez les informations de la [section Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Dans la section [Algorithme recommandé](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), sélectionnez **[!UICONTROL Item Based]** dans la liste **[!UICONTROL Algorithm Type]**.

1. Sélectionnez **[!UICONTROL People Who Viewed This, Viewed That]** dans la liste **[!UICONTROL Algorithm]**.

1. Sélectionnez votre attribut de profil personnalisé dans la liste des **[!UICONTROL Recommendation Key]** (par exemple, [!UICONTROL Last Show Added to Watchlist]).

## Affichage des informations sur les critères {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Vous pouvez afficher les détails des critères en cliquant sur les critères souhaités dans la colonne [!UICONTROL Name] .

Les sections **[!UICONTROL Attributes]** et Détails vous permettent d’afficher des informations générales sur les critères sélectionnés, y compris leurs [!UICONTROL Name], [!UICONTROL Description], [!UICONTROL Industry Vertical], [!UICONTROL Page Types], [!UICONTROL Recommendation Key], [!UICONTROL Recommendation Logic], [!UICONTROL Algorithm ID] et les informations sur la dernière modification (date et auteur de la modification de l’algorithme).

La section **[!UICONTROL Usage]** vous permet de consulter une liste des activités qui font référence aux critères sélectionnés.

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Algorithm Usage] est actuellement prise en charge pour les activités [!DNL Recommendations] uniquement. Cette fonctionnalité n’est actuellement pas prise en charge pour les activités [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Experience Targeting] (XT) qui incluent des [recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).
