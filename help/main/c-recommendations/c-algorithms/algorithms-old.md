---
keywords: recommendations;activité recommendations;critères;algorithme;clé de recommandation;clé personnalisée;secteur vertical;vente au détail;commerce électronique;génération de pistes;b2b;services financiers;médias;publication
description: Découvrez comment utiliser les critères dans Adobe [!DNL Target] [!DNL Recommendations].
title: Comment utiliser les critères dans [!DNL Target] Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 16%

---

# Critères

Les critères de [!DNL Adobe Target] [!DNL Recommendations] sont des règles qui déterminent quels produits ou contenus recommander selon un ensemble prédéterminé de comportements de visiteurs. Les critères peuvent être basés sur des tendances populaires, les comportements actuels et passés d’un visiteur ou des produits et contenus similaires. Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Les sections suivantes en disent plus sur les clés de critère et sur la logique de recommandation que vous pouvez utiliser pour chaque clé. Cliquez sur les liens pour obtenir des informations plus détaillées.

## Secteur industriel vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Lors de la création d’un critère, vous sélectionnez un secteur vertical en fonction des objectifs de votre activité Recommendations .

| Secteur industriel vertical | Objectif |
|--- |--- |
| Vente au détail / commerce électronique | Conversion entraînant un achat |
| Génération de piste / B2B / Services financiers | Conversion sans achat |
| Médias / Publication | Engagement |

Les autres options de critères changent en fonction du secteur vertical que vous sélectionnez. Vous pouvez définir le secteur d’activité vertical par défaut sur la page **[!UICONTROL Recommendations > Settings]** ou spécifier le secteur d’activité vertical pour chaque critère.

## Type d’algorithme {#section_885B3BB1B43048A88A8926F6B76FC482}

Le type d’algorithme que vous sélectionnez détermine les algorithmes disponibles. Il existe plusieurs types d’algorithmes, représentés sous forme de cartes de critères lorsque vous configurez une activité [!DNL Recommendations].

![Page Critères](assets/criteria-page.png)

Le tableau suivant explique les différents types d’algorithmes et les algorithmes associés.

| Type d’algorithme | Quand l’utiliser | Algorithmes disponibles |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Faites des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>Les Personnes Qui Ont Consulté Ces/Ces Ont Consulté Ces/Ces</li><li>Les Personnes Qui Les Ont Consultés Les Ont Achetés</li><li>Les Personnes Qui Ont Acheté Ces Éléments Ont Acheté Ceux-Ci</li></ul>Pour plus d’informations, voir [Basé sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) dans *Baser la recommandation sur une clé de recommandation*. |
| [!UICONTROL Popularity-Based] | Faites des recommandations en fonction de la popularité globale d’un élément sur votre site ou en fonction de la popularité des éléments dans la catégorie, la marque, le genre préféré ou le plus consulté d’un utilisateur, etc. | <ul><li>Les plus consultés sur le site</li><li>Les plus consultés par catégorie</li><li>Éléments les plus consultés par attribut d’élément</li><li>Meilleurs vendeurs sur le site</li><li>Meilleurs vendeurs par catégorie</li><li>Meilleurs vendeurs par attribut d&#39;article</li><li>Meilleure mesure par Analytics</li></ul> |
| [!UICONTROL Item-Based] | Faites des recommandations basées sur la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Les personnes ayant consulté ceci ont acheté cela</li><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Éléments avec des attributs similaires</li></ul> |
| [!UICONTROL User-Based] | Faites des recommandations basées sur le comportement de l’utilisateur. | <ul><li>Éléments récemment consultés</li><li>Recommandé pour vous</li></ul> |
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

   ![Boîte de dialogue Créer un critère](assets/custom-key1.png)

## Affichage des informations sur les critères {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Vous pouvez afficher les détails d’un critère sur une carte pop-up en faisant glisser le pointeur de la souris sur une carte et en cliquant sur l’icône Informations sur une carte de critère sans ouvrir le critère.

![Survol de la carte Critères](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

Cliquez sur l’onglet **[!UICONTROL Algorithm Info]** pour afficher des informations générales sur les critères sélectionnés, y compris le nom, les descriptions, le secteur d’activité vertical, le ou les types de page, la clé de recommandation, la logique de recommandation et l’ID d’algorithme.

![Onglet Informations sur l’algorithme](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

Cliquez sur l’onglet **[!UICONTROL Algorithm Usage]** pour afficher la liste des activités qui font référence aux critères sélectionnés. La carte répertorie les activités actives, inactives et brouillons. Cliquez sur les listes déroulantes Activités actives/Activités inactives/Activités préliminaires pour afficher la liste complète des activités qui font référence à ce critère. Vous pouvez cliquer sur le lien Activité pour ouvrir l’activité à modifier.

![Onglet Utilisation des algorithmes](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>La fonction [!UICONTROL Algorithm Usage] est actuellement prise en charge uniquement pour les activités Recommendations. Cette fonctionnalité n’est actuellement pas prise en charge pour les activités de test A/B, d’affectation automatique, de ciblage automatique et de ciblage d’expérience (XT) qui incluent des [recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).
