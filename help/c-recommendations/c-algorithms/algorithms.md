---
description: Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.
keywords: recommandations, activité de recommandations, critères; algorithme
seo-description: Les critères dans Adobe Target sont des règles qui déterminent les produits à recommander en fonction d'un ensemble prédéterminé de comportements de visiteurs.
seo-title: Critères
solution: Target
title: Critères
title-outputclass: Premium
topic: Premium
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
badge: Premium
translation-type: tm+mt
source-git-commit: c0e4b2243160013224138603bb53d8569d486e31

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

## Clé de recommandation {#section_885B3BB1B43048A88A8926F6B76FC482}

La clé de recommandation sélectionnée détermine le type de critère. Il existe plusieurs types de critères, qui sont représentés sous forme de cartes de critères lorsque vous configurez une activité [!DNL Recommendations].

| Type de critère | Clés |
|--- |--- |
| Activité de la page en cours | Éléments recommandés en fonction des activités des utilisateurs sur la page en cours. Par exemple, les visiteurs qui consultent un élément spécifique souhaitent peut-être voir d’autres éléments de la même catégorie.<ul><li>Article actuel</li><li>Catégorie en cours</li></ul> |
| Personnalisé | Éléments recommandés en fonction d’attributs personnalisés.<ul><li>Attribut personnalisé</li></ul>Lorsque vous basez des recommandations sur des attributs personnalisés, vous devez sélectionner l’attribut personnalisé, puis le type de recommandation.<br>Vous pouvez effectuer un filtrage en temps réel en plus de vos propres critères de sortie personnalisés. Vous pouvez par exemple limiter vos éléments recommandés uniquement à ceux de la catégorie ou de la marque préférée d’un visiteur. Vous avez ainsi la possibilité de combiner les calculs hors ligne avec filtrage en temps réel.<br>Cette fonctionnalité signifie que vous pouvez utiliser Target pour ajouter de la personnalisation en plus de vos recommandations calculées hors ligne ou de vos listes gérées de façon personnalisée. Elle combine la puissance de vos analystes des données et de votre recherche avec la livraison approuvée, le filtrage d’exécution, les tests A/B, le ciblage, la génération de rapports, les intégrations et bien d’autres fonctions Adobe encore.<br>Avec l’ajout de règles d’inclusion dans les critères personnalisés, les recommandations qui seraient statiques deviennent dynamiques et fondées sur les intérêts du visiteur.<ul><li>Les critères personnalisés sont configurables au même titre que les autres critères contenus dans les recommandations.</li><li>Vous pouvez utiliser les [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), et [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.</li></ul>Les cas d’utilisation possibles incluent :<ul><li>Vous souhaitez recommander des films à partir d’une liste gérée de façon personnalisée, mais uniquement si le visiteur ne les a pas déjà vus.</li><li>Vous voulez exécuter un algorithme en mode hors ligne et utiliser les résultats pour alimenter vos recommandations, mais vous devez vous assurer que les articles épuisés ne soient jamais recommandés.</li><li>Vous souhaitez inclure uniquement les articles extraits de la catégorie préférée de ce visiteur.</li></ul> |
| Comportement passé | Éléments recommandés en fonction du type de réponse des visiteurs à un élément par le passé. Par exemple, les visiteurs qui ont acheté une marque spécifique ont été plus susceptibles d’acheter un autre article de cette marque.<ul><li>Dernier article acheté</li><li>Dernier article consulté</li><li>Article le plus consulté</li><li>Catégorie préférée</li></ul> |
| Popularité | Recommandez les éléments les plus populaires tels que les vidéos les plus populaires d’une catégorie associée ou les produits qui ont été consultés le plus souvent sur votre site.<ul><li>Popularité</li></ul> |
| Éléments récemment consultés | Recommandez les éléments qui ont été consultés le plus récemment tels que les éléments qu’un visiteur a consulté la dernière fois qu’il a visité votre site ou les éléments qui sont le plus tendance à l’heure actuelle.<br>L’algorithme des articles récemment consultés renvoie les résultats propres à l’activité d’un visiteur au sein d’un [environnement](/help/administrating-target/hosts.md). Si deux sites appartiennent à des environnements différents et qu’un visiteur passe de l’un à l’autre, l’algorithme ne renvoie que les articles récemment consultés du site approprié.<br>Ce type de critère n’est pas limité par collections.<ul><li>Éléments récemment consultés</li></ul>**Remarque :** Vous ne pouvez pas utiliser le critère Éléments récemment consultés pour les recommandations de sauvegarde.<br>Les éléments/médias récemment consultés peuvent être filtrés de sorte que seuls les éléments ayant un attribut particulier soient affichés.<ul><li>Les critères récemment consultés sont configurables au même titre que les autres critères contenus dans les recommandations.</li><li>Vous pouvez utiliser les [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), et [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.</li></ul>Les cas d’utilisation possibles incluent :<ul><li>Une multinationale regroupant plusieurs entreprises peut comporter des éléments d’affichage de visiteur répartis entre plusieurs propriétés numériques. Dans ce cas, vous pouvez limiter les éléments récemment consultés de manière à les afficher uniquement pour la propriété respective dans laquelle ils ont été consultés. Cette mesure empêche les articles récemment consultés d’être affichés sur le site d’une autre propriété numérique.</li></ul> |


## Critères/algorithmes {#section_DC4E38A00B9744959F05F8E10A0087A1}

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

>[!NOTE] {class="- topic/note "}
>
>Si vous exécutez une recommandation et que vous modifiez ses critères, les données de création de rapports sont perdues.

Vous pouvez également utiliser d’autres informations connues sur un visiteur pour améliorer vos recommandations.

Tous les critères « un jour » s’exécutent deux fois par jour. Tous les critères « une semaine » et plus longs s’exécutent une fois par jour. Les critères « Affinité du site » s’exécutent une fois par jour. Les critères de sauvegarde s’exécutent deux fois par jour.

## Affichage des informations sur les critères {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Vous pouvez afficher les détails d’un critère sur une carte contextuelle en faisant glisser le pointeur de la souris sur une carte et en cliquant sur l’icône Informations sur une carte de critère sans ouvrir le critère.

![Survol de carte de critères](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Cliquez sur l’onglet **[!UICONTROL Informations sur l’algorithme]pour afficher des informations générales sur le critère sélectionné, y compris son Nom, ses Descriptions, son Secteur industriel vertical, son ou ses Type(s) de page, sa Clé de recommandation, sa Logique de recommandation et son ID d’algorithme.**

![Onglet Informations sur l'algorithme](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Cliquez sur l’onglet **[!UICONTROL Utilisation de l’algorithme]** pour afficher la liste des activités qui font référence au critère sélectionné. La carte répertorie les activités actives et inactives. Cliquez sur les listes déroulantes Activités actives et Activités inactives pour afficher la liste complète des activités faisant référence à ce critère. Vous pouvez cliquer sur le lien Activité pour ouvrir l’activité à modifier.

![Onglet Utilisation des critères](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

## Détermination du moment auquel les résultats des critères sont prêts à être affichés {#section_03F328C07F234692B6D996DF745584B3}

Dans le diagramme d’activité, les cartes de critère indiquent désormais à quel moment les résultats sont prêts à être affichés. Savoir si les résultats sont prêts à être affichés vous aide à déterminer si votre activité est prête à être activée pour l’activer. Savoir si les résultats sont prêts à être affichés vous aide également à savoir s’il existe des problèmes avec les critères.

>[!NOTE]
>
>Pour une discussion à propos des temps de chargement, voir « Critères de temps de traitement attendus » sur la page [Création de critères](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

L’illustration suivante présente le diagramme d’activité sur la page Présentation d’une activité de recommandation. Vous pouvez également voir le diagramme d’activité avec les résultats de statut de l’étape via l’étape 2 du workflow de création d’activité.

![Etat des critères sur la page Aperçu](/help/c-recommendations/c-algorithms/assets/criteria_status.png)

Les résultats de statut incluent les informations suivantes : Résultats prêts, Résultats non prêts et Échec du flux, comme illustré dans le diagramme suivant :

![](assets/criteria_status_multi.png)

