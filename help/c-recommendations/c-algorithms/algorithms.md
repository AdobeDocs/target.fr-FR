---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Les critères en Adobe Target sont des règles qui déterminent quels produits ou contenus recommander en fonction d’un ensemble prédéfini de comportements de visiteur.
title: Critères en Adobe Target Recommendations
feature: criteria
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: d276693eeab095b7f2f5fad293a03ab10eb1faf6
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 53%

---


# ![PREMIUM](/help/assets/premium.png) Critères

Criteria in [!DNL Adobe Target] are rules that determine which products or content to recommend based on a predetermined set of visitor behaviors. Les critères peuvent être basés sur des tendances populaires, les comportements actuel et passé d’un visiteur ou des produits et contenus similaires. Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Les sections suivantes décrivent plus en détail les clés de critères et la logique de recommandation que vous pouvez utiliser pour chaque clé. Cliquez sur les liens pour obtenir des informations plus détaillées.

## Secteur industriel vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Lors de la création d’un critère, vous sélectionnez un secteur industriel vertical en fonction des objectifs de votre activité de recommandations.

| Secteur industriel vertical | Objectif |
|--- |--- |
| Vente au détail / commerce électronique | Conversion entraînant un achat |
| Génération de piste / B2B / Services financiers | Conversion sans achat |
| Médias / Publication | Engagement |

Les autres options de critères changent en fonction du secteur industriel vertical que vous sélectionnez. Vous pouvez définir votre secteur industriel vertical par défaut sur la page **[!UICONTROL Recommendations > Paramètres]** ou vous pouvez spécifier le secteur industriel vertical pour chaque critère.

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

La clé de recommandation sélectionnée détermine le type de critère. Il existe plusieurs types de critères, qui sont représentés sous forme de cartes de critères lorsque vous configurez une activité [!DNL Recommendations].

![Page Critères](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

Le tableau suivant explique les différents types de critères et les clés qui les accompagnent. Cliquez sur les liens pour obtenir des informations plus détaillées sur chaque clé.

| Type de critère | Clés |
|--- |--- |
| Activité de la page en cours | Éléments recommandés en fonction des activités des utilisateurs sur la page en cours. Par exemple, les visiteurs qui consultent un élément spécifique souhaitent peut-être voir d’autres éléments de la même catégorie.<ul><li>[Article actuel](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[Catégorie en cours](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| Personnalisé | Éléments recommandés en fonction d’attributs personnalisés.<ul><li>[Attribut personnalisé](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>Lorsque vous basez des recommandations sur des attributs personnalisés, vous devez sélectionner l’attribut personnalisé, puis le type de recommandation. |
| Comportement passé | Éléments recommandés en fonction du type de réponse des visiteurs à un élément par le passé. Par exemple, les visiteurs qui ont acheté une marque spécifique ont été plus susceptibles d’acheter un autre article de cette marque.<ul><li>[Dernier article acheté](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[Dernier article consulté](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[Article le plus consulté](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[Catégorie préférée](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| Popularité | Recommandez les éléments les plus populaires tels que les vidéos les plus populaires d’une catégorie associée ou les produits qui ont été consultés le plus souvent sur votre site.<ul><li>[Popularité](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [Éléments récemment consultés](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | Recommandez les éléments qu’un visiteur a consultés le plus récemment, tels que les éléments qu’un visiteur a consulté la dernière fois qu’il a visité votre site ou les articles qui sont les plus tendance à l’heure actuelle. |

## Utilisation d’une clé de recommandation personnalisée {#custom-key}

Vous pouvez également baser les recommandations sur la valeur d’un attribut de profil personnalisé.

>[!NOTE]
>
>Les paramètres de profil personnalisés peuvent être transmis à la Cible par le biais de JavaScript, d’API ou d’intégrations. Pour plus d’informations sur les attributs de profil personnalisés, voir profils [](/help/c-target/c-visitor-profile/visitor-profile.md)Visiteurs.

Supposons, par exemple, que vous souhaitiez afficher les films recommandés en fonction du film qu’un utilisateur a récemment ajouté à la file d’attente.

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Last Show Added to Watchlist]).

1. Select your [!UICONTROL Recommendation Logic] (for example, [!UICONTROL People Who Viewed This, Viewed That]).

   ![Créer de nouveaux critères, boîte de dialogue](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

If your custom profile attribute does not directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur.

Supposons, par exemple, que vous souhaitiez afficher les articles les plus vendus de la marque préférée d’un utilisateur.

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Favorite Brand]).

1. Select the [!UICONTROL Recommendation Logic] you want to use with this key (for example, [!UICONTROL Top Sellers]).

   L’option [!UICONTROL Groupe par valeur unique de] s’affiche.

1. Sélectionnez l’attribut d’entité correspondant à la clé choisie. In this case [!UICONTROL Favorite Brand] matches to `entity.brand`.

   [!DNL Recommendations] génère désormais une liste &quot;Meilleurs vendeurs&quot; pour chaque marque et montre à l’utilisateur la liste &quot;Meilleurs vendeurs&quot; appropriée en fonction de la valeur stockée dans l’attribut profil de marque  préférée.

   ![Attribut Meilleurs vendeurs](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Criteria/algorithms {#criteria-algorithms}

[!DNL Target Recommendations] applique des algorithmes élaborés pour déterminer quand les actions d’un visiteur remplissent les critères définis dans votre activité. La clé de recommandation détermine quelles options de la logique des recommandations sont disponibles.

| Critères | Description |
|--- |--- |
| [Éléments/Médias avec des attributs similaires](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#similar-attributes) | Recommande des éléments ou des médias similaires à d’autres éléments ou médias selon l’activité de la page ou le comportement du visiteur précédent. |
| [Les personnes ayant consulté ceci ont consulté cela](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-viewed) | Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté. |
| [Les personnes ayant consulté ceci ont acheté cela](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-bought) | Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. |
| [Les personnes ayant acheté ceci ont acheté cela](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#bought-bought) | Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié. |
| [Affinité du site](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#site-affinity) | Recommande des éléments selon la certitude d’une relation entre ceux-ci. |
| [Meilleurs vendeurs](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#top-sellers) | Éléments figurant dans les commandes les plus fréquemment passées. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande. |
| [Les plus consultés](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed) | Éléments ou médias les plus consultés. |
| [Recommendations basée sur l’utilisateur](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | Recommande les éléments en fonction de l&#39;historique de navigation, d&#39;affichage et d&#39;achat de chaque visiteur. Ces éléments sont généralement appelés &quot;Recommandé pour vous&quot;. |

>[!NOTE]
>
>Si vous exécutez une recommandation et que vous modifiez ses critères, les données de création de rapports sont perdues.

Vous pouvez également utiliser d’autres informations connues sur un visiteur pour améliorer vos recommandations.

Tous les critères « un jour » s’exécutent deux fois par jour. Tous les critères « une semaine » et plus longs s’exécutent une fois par jour. Les critères « Affinité du site » s’exécutent une fois par jour. Les critères de sauvegarde s’exécutent deux fois par jour.

## Viewing criteria information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Vous pouvez afficher les détails d’un critère sur une carte contextuelle en faisant glisser le pointeur de la souris sur une carte et en cliquant sur l’icône Informations sur une carte de critère sans ouvrir le critère.

![Survol de la carte Critères](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Cliquez sur l’onglet **[!UICONTROL Informations sur l’algorithme]** pour afficher des informations générales sur le critère sélectionné, y compris son Nom, ses Descriptions, son Secteur industriel vertical, son ou ses Type(s) de page, sa Clé de recommandation, sa Logique de recommandation et son ID d’algorithme.

![Onglet Informations sur l’algorithme](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Cliquez sur l’onglet **[!UICONTROL Utilisation de l’algorithme]** pour afficher la liste des activités qui font référence au critère sélectionné. La carte liste des activités principales, inactives et de brouillon. Cliquez sur les listes déroulantes Activités en direct/Activités inactives/Brouillons d’Activités pour vue la liste entière des activités qui font référence à ces critères. Vous pouvez cliquer sur le lien Activité pour ouvrir l’activité à modifier.

![Onglet Utilisation de l’algorithme](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>La fonctionnalité Utilisation  d’algorithme est actuellement prise en charge pour les activités Recommendations uniquement. Cette fonctionnalité n’est actuellement pas prise en charge pour les activités Test A/B, Affectation automatique, Cible automatique et Ciblage d’expérience (XT) qui incluent des [recommandations en tant qu’offre](/help/c-recommendations/recommendations-as-an-offer.md).
