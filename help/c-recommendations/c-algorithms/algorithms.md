---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Les critères de Adobe Target Recommendations sont des règles qui déterminent quels produits recommander en fonction d’un ensemble prédéfini de comportements visiteurs.
title: Critères en Adobe Target Recommendations
feature: criteria
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 74%

---


# ![PREMIUM](/help/assets/premium.png) Critères{#criteria}

Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.

Les critères déterminent la recommandation qui est générée par chaque action. Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

## Secteur industriel vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Vous sélectionnez un secteur industriel vertical en fonction des objectifs de l’activité de recommandations :

| Secteur industriel vertical | Objectif |
|--- |--- |
| Vente au détail / commerce électronique | Conversion entraînant un achat |
| Génération de piste / B2B / Services financiers | Conversion sans achat |
| Médias / Publication | Engagement |

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

La clé de recommandation sélectionnée détermine le type de critère. Il existe plusieurs types de critères, qui sont représentés sous forme de cartes de critères lorsque vous configurez une activité [!DNL Recommendations].

| Type de critère | Clés |
|--- |--- |
| Activité de la page en cours | Éléments recommandés en fonction des activités des utilisateurs sur la page en cours. Par exemple, les visiteurs qui consultent un élément spécifique souhaitent peut-être voir d’autres éléments de la même catégorie.<ul><li>Article actuel</li><li>Catégorie en cours</li></ul> |
| Personnalisé | Éléments recommandés en fonction d’attributs personnalisés.<ul><li>Attribut personnalisé</li></ul>Lorsque vous basez des recommandations sur des attributs personnalisés, vous devez sélectionner l’attribut personnalisé, puis le type de recommandation.<br>Vous pouvez effectuer un filtrage en temps réel en plus de vos propres critères de sortie personnalisés. Vous pouvez par exemple limiter vos éléments recommandés uniquement à ceux de la catégorie ou de la marque préférée d’un visiteur. Vous avez ainsi la possibilité de combiner les calculs hors ligne avec filtrage en temps réel.<br>Cette fonctionnalité signifie que vous pouvez utiliser Target pour ajouter de la personnalisation en plus de vos recommandations calculées hors ligne ou de vos listes gérées de façon personnalisée. Elle combine la puissance de vos analystes des données et de votre recherche avec la livraison approuvée, le filtrage d’exécution, les tests A/B, le ciblage, la génération de rapports, les intégrations et bien d’autres fonctions Adobe encore.<br>Avec l’ajout de règles d’inclusion dans les critères personnalisés, les recommandations qui seraient statiques deviennent dynamiques et fondées sur les intérêts du visiteur.<ul><li>Les critères personnalisés sont configurables au même titre que les autres critères contenus dans les recommandations.</li><li>Vous pouvez utiliser les [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), et [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.</li></ul>Les cas d’utilisation possibles incluent :<ul><li>Vous souhaitez recommander des films à partir d’une liste gérée de façon personnalisée, mais uniquement si le visiteur ne les a pas déjà vus.</li><li>Vous voulez exécuter un algorithme en mode hors ligne et utiliser les résultats pour alimenter vos recommandations, mais vous devez vous assurer que les articles épuisés ne soient jamais recommandés.</li><li>Vous souhaitez inclure uniquement les articles extraits de la catégorie préférée de ce visiteur.</li></ul> |
| Comportement passé | Éléments recommandés en fonction du type de réponse des visiteurs à un élément par le passé. Par exemple, les visiteurs qui ont acheté une marque spécifique ont été plus susceptibles d’acheter un autre article de cette marque.<ul><li>Dernier article acheté</li><li>Dernier article consulté</li><li>Article le plus consulté</li><li>Catégorie préférée</li></ul> |
| Popularité | Recommandez les éléments les plus populaires tels que les vidéos les plus populaires d’une catégorie associée ou les produits qui ont été consultés le plus souvent sur votre site.<ul><li>Popularité</li></ul> |
| Éléments récemment consultés | Recommandez les éléments qui ont été consultés le plus récemment tels que les éléments qu’un visiteur a consulté la dernière fois qu’il a visité votre site ou les éléments qui sont le plus tendance à l’heure actuelle.<br>L’algorithme des articles récemment consultés renvoie les résultats propres à l’activité d’un visiteur au sein d’un [environnement](/help/administrating-target/hosts.md). Si deux sites appartiennent à des environnements différents et qu’un visiteur passe de l’un à l’autre, l’algorithme ne renvoie que les articles récemment consultés du site approprié.<br>Ce type de critère n’est pas limité par collections.<ul><li>Éléments récemment consultés</li></ul>**Remarque :** Vous ne pouvez pas utiliser le critère Éléments récemment consultés pour les recommandations de sauvegarde.<br>Les éléments/médias récemment consultés peuvent être filtrés de sorte que seuls les éléments ayant un attribut particulier soient affichés.<ul><li>Les critères récemment consultés sont configurables au même titre que les autres critères contenus dans les recommandations.</li><li>Vous pouvez utiliser les [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), et [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.</li></ul>Les cas d’utilisation possibles incluent :<ul><li>Une multinationale regroupant plusieurs entreprises peut comporter des éléments d’affichage de visiteur répartis entre plusieurs propriétés numériques. Dans ce cas, vous pouvez limiter les éléments récemment consultés de manière à les afficher uniquement pour la propriété respective dans laquelle ils ont été consultés. Cette mesure empêche les articles récemment consultés d’être affichés sur le site d’une autre propriété numérique.</li></ul> |

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
| Éléments/Médias avec des attributs similaires | Recommande des éléments ou des médias similaires à d’autres éléments ou médias selon l’activité de la page ou le comportement du visiteur précédent.<br>**Remarque :** Si vous sélectionnez des Éléments/Médias avec des attributs similaires, vous aurez la possibilité de définir des règles sur le contenu similaire. |
| Les personnes ayant consulté ceci ont consulté cela | Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté. |
| Les personnes ayant consulté ceci ont acheté cela | Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Ces critères renvoient d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu des résultats. |
| Les personnes ayant acheté ceci ont acheté cela | Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié. |
| Affinité du site | Recommande des éléments selon la certitude d’une relation entre ceux-ci. Vous pouvez configurer ce critère pour déterminer la quantité de données requises avant qu’une recommandation ne soit présentée à l’aide du curseur Règles d’inclusion. Si vous sélectionnez par exemple très forte, les produits qui ont le plus de chances d’avoir une correspondance sont recommandés.<br>Par exemple, si vous définissez une très forte affinité et si votre conception comporte cinq éléments dont trois qui correspondent à la force du seuil de connexion, les deux éléments qui ne répondent pas aux exigences de force minimales ne sont pas affichés dans vos recommandations et sont remplacés par les éléments de sauvegarde. Les éléments avec l’affinité la plus forte s’affichent en premier.<br>Certains clients qui proposent plusieurs collections de produits et plusieurs comportements de site obtiendront de meilleurs résultats en définissant une affinité faible. |
| Meilleurs vendeurs | Éléments figurant dans les commandes les plus fréquemment passées. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande. |
| Les plus consultés | Éléments ou médias les plus consultés. |
| Éléments/Médias récemment consultés | Éléments récemment consultés par le visiteur. Lorsque vous utilisez ces critères, vous devez mettre à jour la conception Target pour gérer les cas où des recommandations vierges s’afficheraient alors qu’il n’y a pas assez d’éléments consultés antérieurement à afficher. |
| Recommendations basée sur l’utilisateur | Recommande les éléments en fonction de l&#39;historique de navigation, d&#39;affichage et d&#39;achat de chaque visiteur. Ces éléments sont généralement appelés &quot;Recommandé pour vous&quot;.<br>Ce critère vous permet de fournir du contenu et des expériences personnalisés aux nouveaux visiteurs et aux  de retour. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur et est mise à jour en cours de session et devient plus personnalisée lorsque l’utilisateur parcourt votre site.<br>Les vues et les achats sont utilisés pour déterminer les articles recommandés. La clé de recommandation spécifiée (par exemple, Article actuel) est utilisée pour appliquer les filtres de règle d&#39;inclusion que vous sélectionnez. Par exemple, vous pouvez effectuer les opérations suivantes :<ul><li>Exclure les éléments qui ne répondent pas à certains critères (produits en rupture de stock, articles publiés il y a plus de 30 jours, films classés R, etc.)</li><li>Limiter les articles inclus à une seule catégorie ou à la catégorie actuelle</li></ul> |

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

Cliquez sur l’onglet **[!UICONTROL Utilisation de l’algorithme]** pour afficher la liste des activités qui font référence au critère sélectionné. La carte répertorie les activités actives et inactives. Cliquez sur les listes déroulantes Activités actives et Activités inactives pour afficher la liste complète des activités faisant référence à ce critère. Vous pouvez cliquer sur le lien Activité pour ouvrir l’activité à modifier.

![Onglet Utilisation de l’algorithme](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>La fonctionnalité Utilisation  d’algorithme est actuellement prise en charge pour les activités Recommendations uniquement. Cette fonctionnalité n’est actuellement pas prise en charge pour les activités de test A/B et de ciblage d’expérience qui incluent des [recommandations en tant qu’offre](/help/c-recommendations/recommendations-as-an-offer.md).
