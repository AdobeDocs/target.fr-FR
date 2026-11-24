---
keywords: règles d’inclusion;critères d’inclusion;recommandations;créer des critères;promotion;promotions;filtrage dynamique;dynamique;valeurs vides;ignorer la règle de filtrage;filtre statique;filtrer par valeur;correspondance des attributs d’entité;correspondance des attributs de profil;correspondance de paramètres;filtrer par valeur;filtre statique
description: Découvrez comment créer des règles d’inclusion dans [!DNL Target] Recommendations pour les critères et les promotions.
title: Utilisation de règles d’inclusion dynamiques et statiques
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
TQID: 'https://experienceleague.adobe.com/PM9h863-uQWm3wrU7OVWfmnqQgyUGmF7QFpTUaAZuCQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '2164'
ht-degree: 7%
---
# Utilisation de règles d’inclusion dynamiques et statiques {#inclusion-rules}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment ajouter des règles de filtrage dynamiques et statiques aux critères et aux promotions dans [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Les règles d’inclusion limitent les éléments pouvant apparaître dans les recommandations. Ils sont créés pour les critères et les promotions dans [!DNL Adobe Target], avec des règles de filtrage dynamiques ou statiques. Le processus, les cas d’utilisation et les exemples sont similaires pour les critères et les promotions, cette page couvre donc les deux.

## Ajouter des règles de filtrage {#add-filtering-rules}

Les étapes suivantes ajoutent une règle de filtrage aux critères.

1. Lors de la [création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#create-criteria) (**[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** > **[!UICONTROL Création de critères]** > **[!UICONTROL Création de critères]**), cliquez sur **[!UICONTROL Ajouter une règle de filtrage]** sous **[!UICONTROL Règles d’inclusion]**.

   ![Ajouter Une Règle De Filtrage](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. Dans la zone « À quelles autres règles la recommandation doit-elle se conformer », cliquez sur la liste déroulante **[!UICONTROL Filtre statique]**, puis sélectionnez l’option souhaitée.

   ![Liste déroulante Filtre statique](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   Les options disponibles varient en fonction du secteur industriel vertical et de la clé de recommandation sélectionnés.

Pour ajouter une règle de filtrage à une promotion, sélectionnez **[!UICONTROL Promouvoir par attribut]** lors de la [création de la promotion](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), puis cliquez sur **[!UICONTROL Ajouter une règle de filtrage]**.

## Types de filtre {#filter-types}

Les sections suivantes décrivent les options de filtrage pour **[!UICONTROL le filtrage dynamique]** et **[!UICONTROL le filtrage par valeur]**, tant pour les critères que pour les promotions.

### Filtrage dynamique

Les règles d’inclusion dynamiques s’adaptent au visiteur ou à la requête, tandis que les règles d’inclusion statiques utilisent des valeurs fixes.

* Les règles d’inclusion dynamique fournissent des recommandations en faisant correspondre un attribut dans un paramètre de profil de l’utilisateur ou dans un appel de mbox.

  Par exemple, une recommandation « Critères les plus populaires » peut être créée. À partir de l’ensemble des recommandations renvoyées, il est possible de filtrer toute recommandation (en temps réel) en fonction d’un attribut transmis lorsque l’utilisateur accède à une page où les recommandations sont affichées.

* Vous pouvez créer un nombre illimité de règles d’inclusion dynamiques. Les règles d’inclusion sont jointes à un opérateur AND. Par conséquent, toutes les règles doivent être respectées pour qu’un élément soit inclus dans une recommandation.

Les options suivantes sont disponibles pour le filtrage dynamique :

| Option de filtrage dynamique | Détails |
| --- | --- |
| [**[!UICONTROL Correspondance des attributs d’entité]**](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dynamiquement en comparant un groupe d’éléments recommandés potentiels à un élément spécifique avec lequel le visiteur a interagi.<P>Utilisez la fonction **[!UICONTROL Correspondance des attributs d’entité]** pour afficher les recommandations les plus susceptibles de séduire le visiteur, telles que la marque préférée du visiteur. |
| [**[!UICONTROL Correspondance des attributs de profil]**](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dynamiquement en comparant des éléments (entités) à une valeur dans le profil du visiteur.<P>Utilisez **[!UICONTROL Correspondance des attributs de profil]** pour afficher les recommandations correspondant à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée. |
| [**[!UICONTROL Correspondance de paramètres]**](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dynamiquement en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).<P>Utilisez **[!UICONTROL Correspondance des paramètres]** pour recommander du contenu correspondant aux paramètres de la page ou aux paramètres du visiteur, tels que les dimensions de l’appareil ou la géolocalisation. |

### Filtrer par valeur

Les règles statiques limitent les éléments inclus dans la recommandation, au lieu d’utiliser des collections. L’option suivante est disponible pour le filtrage par valeur :

| Option Filtrer par valeur | Détails |
| --- | --- |
| [**[!UICONTROL Filtre statique]**](/help/main/c-recommendations/c-algorithms/static-value.md) | Filtre par une ou plusieurs valeurs statiques saisies manuellement. |

## Opérateurs et opératrices disponibles {#operators}

Les exemples suivants montrent comment les promotions et exclusions dynamiques peuvent être utilisées pour le marketing.

>[!NOTE]
>
>Les opérateurs « liste » nécessitent que les entités et les attributs de profil soient stockés sous forme de tableaux. Une liste séparée par des virgules ne fonctionne pas.

| Opérateur | Disponible avec | Exemples |
|--- |--- |--- |
| **[!UICONTROL est égal à l’un des]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un article sur le site web (un produit, un article ou un film, par exemple), les promotions dynamiques qui utilisent l’opérateur « égal à » peuvent promouvoir d’autres articles à partir de :<ul><li>La même marque</li><li>La même catégorie</li><li>La même catégorie ET de la marque maison</li><li>Le même magasin</li></ul> |
| **[!UICONTROL n&#39;est égal à aucun(e)]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un élément sur le site web (tel qu’un produit, un article ou un film), les promotions dynamiques qui utilisent l’opérateur « **[!UICONTROL n’est égal à aucun de]** » peuvent promouvoir d’autres éléments à partir de :<ul><li>Une autre série télé</li><li>Un genre différent</li><li>Une autre série de produits</li><li>Un identifiant de style différent</li></ul> |
| **[!UICONTROL est supérieur ou égal à l&#39;un des]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un élément sur le site web (un produit, par exemple), l’opérateur « **[!UICONTROL est supérieur ou égal à l’un des]** » peut promouvoir d’autres éléments qui :<ul><li>Coûtent le même prix ou sont plus chers</li></ul> |
| **[!UICONTROL est inférieur ou égal à l&#39;un des]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un élément sur le site web (un produit, par exemple), l’opérateur « **[!UICONTROL est inférieur ou égal à l’un des]** » peut promouvoir d’autres éléments qui :<ul><li>Coûtent le même prix ou sont moins chers</li></ul> |
| **[!UICONTROL contient n’importe lequel]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un élément sur le site web (un produit, par exemple), l’opérateur « **[!UICONTROL contains any of]** » peut promouvoir d’autres éléments qui :<ul><li>Le titre contient la même marque</li></ul> |
| **[!UICONTROL ne contient pas n’importe lequel]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un élément sur le site web (un produit, par exemple), l’opérateur « **[!UICONTROL ne contient aucun des]** » peut promouvoir d’autres éléments qui :<ul><li>Le titre ne contient pas de juron</li></ul> |
| **[!UICONTROL commence par l&#39;un des]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un élément sur le site web (un produit, par exemple), l’opérateur « **[!UICONTROL commence par l’un des]** » peut promouvoir d’autres éléments qui :<ul><li>Le nom du produit commence par iPhone.</li></ul> |
| **[!UICONTROL se termine par l&#39;un des]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]**, **[!UICONTROL Correspondance des paramètres]** et **[!UICONTROL Filtre statique]** | Lorsqu’un visiteur consulte un élément sur le site web (un produit, par exemple), l’opérateur « **[!UICONTROL se termine par l’un des]** » peut promouvoir d’autres éléments qui :<ul><li>Le contenu se termine par EN, qui indique la langue anglaise</li></ul> |
| **[!UICONTROL est compris entre]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Lorsqu’un visiteur consulte un élément sur le site web (tel qu’un produit, un article ou un film), les promotions dynamiques qui utilisent l’opérateur « **[!UICONTROL est compris entre]** » peuvent promouvoir d’autres éléments qui sont :<ul><li>Plus cher</li><li>Moins cher</li><li>Coût plus ou moins 30 %</li><li>Épisodes ultérieurs de la même saison</li><li>Livres antérieurs dans une série</li></ul> |
| **[!UICONTROL la liste contient un élément de]** (liste sur le côté droit) | **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur le site web (tel qu’un produit, un article ou un film), l’opérateur « **[!UICONTROL list contains an]** » peut promouvoir d’autres éléments qui sont :<ul><li>Disponible dans la zone géographique du visiteur</li></ul>**Exemple** : recommander des éléments disponibles uniquement dans la zone géographique du visiteur.<P>La règle de filtrage peut se présenter comme suit :<P>`availableGeographies list contains an item in user.currentGeography`<P>**Remarque** : lorsque cet opérateur est utilisé, une liste est attendue sur le [côté droit](#caveats) de la règle. |
| **[!UICONTROL la liste ne contient pas un élément de]** (liste sur le côté droit) | **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur le site web (tel qu’un produit, un article ou un film), l’opérateur « **[!UICONTROL list ne contient pas d’élément dans]** » peut exclure d’autres éléments qui sont :<ul><li>Dans la liste des dix derniers éléments que le visiteur a consultés</li></ul>**Exemple** : les éléments que le visiteur a récemment consultés et qui ne l’intéressent pas ne font pas l’objet d’une promotion.<P>La règle de filtrage peut se présenter comme suit :<P>`id is not contained in list user.lastViewedItems`<P>**Remarque** : lorsque cet opérateur est utilisé, une liste est attendue sur le [côté droit](#caveats) de la règle. |
| **[!UICONTROL la liste contient un élément de]** (listes des deux côtés) | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur le site web (un événement sportif ou un concert, par exemple), l’opérateur « **[!UICONTROL list contains an item in]** » peut promouvoir d’autres éléments qui sont :<ul><li>Associé à l’une des équipes préférées du visiteur</li></ul>**Exemple** : recommandez des jeux associés à l&#39;une des équipes préférées du visiteur.<P>La règle de filtrage peut se présenter comme suit :<P>`teamsPlaying list contains an item in user.favoriteTeams`<P>**Remarque** : lorsque cet opérateur est utilisé, une liste est attendue des [deux côtés](#caveats) de la règle. |
| **[!UICONTROL la liste ne contient pas un élément de]** (listes des deux côtés) | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Dans la correspondance des paramètres, lorsqu’un visiteur consulte un élément sur le site web (tel qu’un produit, un article ou un film), la liste « **[!UICONTROL ne contient pas d’élément dans]** » peut exclure d’autres éléments qui sont :<ul><li>Contenu dans une liste de types interdits</li></ul>**Exemple** : les articles disponibles uniquement pour les visiteurs adultes, tels que le tabac et l&#39;alcool, sont exclus.<P>La règle de filtrage peut se présenter comme suit :<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**Remarque** : lorsque cet opérateur est utilisé, une liste est attendue des [deux côtés](#caveats) de la règle. |
| **[!UICONTROL la liste contient tous les éléments de]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur le site web (une offre d’emploi ou une recette, par exemple), l’opérateur « **[!UICONTROL list contains all items in]** » peut promouvoir d’autres éléments qui :<ul><li>Inclure un ensemble de compétences</li><li>Inclure un ensemble d’ingrédients requis</li></ul>**Exemple 1** : un visiteur possède un ensemble de compétences (Java, C++ et HTML). Les éléments du catalogue sont des tâches avec les compétences requises (Java et HTML). Le profil du visiteur doit contenir toutes les compétences requises avant que la tâche ne soit recommandée au visiteur.<P>La règle de filtrage peut se présenter comme suit :<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**Exemple 2** : un utilisateur possède une liste d’ingrédients pour garde-manger. La recette comporte une liste des ingrédients requis. Le profil du visiteur doit contenir tous les ingrédients requis avant que la recette ne soit recommandée au visiteur.<P>La règle de filtrage peut se présenter comme suit :<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**Remarque** : lorsque cet opérateur est utilisé, une liste est attendue des [deux côtés](#caveats) de la règle. |
| La liste **[!UICONTROL ne contient pas tous les éléments de]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Dans la correspondance des attributs d’entité, lorsqu’un visiteur consulte un élément sur le site web (un événement sportif ou un concert, par exemple), l’opérateur « **[!UICONTROL list ne contient pas tous les éléments dans]** » peut promouvoir d’autres éléments qui :<ul><li>Ne pas inclure un ensemble d’équipes</li></ul>**Exemple** : un événement sportif comprend deux équipes. Le profil du visiteur indique que celui-ci ne souhaite pas voir les jeux de ces équipes. Par conséquent, un jeu ne doit pas être recommandé si ces équipes sont en train de jouer.<P>La règle de filtrage peut se présenter comme suit :<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**Remarque** : lorsque cet opérateur est utilisé, une liste est attendue des [deux côtés](#caveats) de la règle. |

## Gérer les valeurs vides {#empty-values}

Plusieurs options sont disponibles pour gérer les valeurs vides lors du filtrage par **[!UICONTROL correspondance des attributs d’entité]**, **[!UICONTROL correspondance des attributs de profil]** et **[!UICONTROL correspondance des paramètres]**, pour les critères et les promotions.

Auparavant, aucun résultat n’était renvoyé si une valeur était vide. La liste déroulante « Si *x* est vide » spécifie l’action à effectuer lorsque le critère contient des valeurs vides, comme illustré ci-dessous :

![Options de valeur vide](/help/main/c-recommendations/c-algorithms/assets/empty_value.png)

Pour sélectionner l’action souhaitée, pointez sur l’icône d’engrenage ( ![Icône d’engrenage](/help/main/c-recommendations/c-algorithms/assets/icon_gear.png) ), puis choisissez l’action souhaitée :

| Action | Disponible pour | Détails |
|--- |--- |--- |
| **[!UICONTROL Ignorer cette règle de filtrage]** | **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Il s’agit de l’action par défaut pour la **[!UICONTROL correspondance des attributs de profil]** et la **[!UICONTROL correspondance des paramètres]**.<P>La règle est ignorée. Par exemple, s’il existe trois règles de filtrage et que la troisième règle ne transmet aucune valeur, la troisième règle avec les valeurs vides peut être ignorée au lieu de ne renvoyer aucun résultat. |
| **[!UICONTROL Aucun résultat affiché pour ce critère]**<P>(Critères uniquement) | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Il s&#39;agit de l&#39;action par défaut pour **[!UICONTROL Correspondance des attributs d&#39;entité]**.<P>Cette action est la manière dont [!DNL Target] gérait les valeurs vides avant l&#39;ajout de cette option : aucun résultat n&#39;est affiché pour ce critère. |
| **[!UICONTROL Ne promouvoir aucun élément]**<P>(Promotions uniquement) | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Il s&#39;agit de l&#39;action par défaut pour **[!UICONTROL Correspondance des attributs d&#39;entité]**.<P>Cette action correspond à la manière dont [!DNL Target] gérait les valeurs vides avant l&#39;ajout de cette option : aucun résultat ne s&#39;affiche pour cette promotion. |
| **[!UICONTROL Utiliser une valeur statique]** | **[!UICONTROL Correspondance des attributs d’entité]**, **[!UICONTROL Correspondance des attributs de profil]** et **[!UICONTROL Correspondance des paramètres]** | Une valeur statique peut être utilisée lorsqu’une valeur est vide. |

## Avertissements {#caveats}

>[!IMPORTANT]
>
>Différents attributs de type de données peuvent ne pas être compatibles dans les critères dynamiques ou les promotions au moment de l’exécution avec les opérateurs « égal à » et « n’est pas égal à ». Lorsque le côté gauche comporte des attributs prédéfinis ou des attributs personnalisés, choisissez soigneusement les valeurs **[!UICONTROL Value]**, **[!UICONTROL Margin]**, **[!UICONTROL Inventory]** et **[!UICONTROL Environment]** sur le côté droit.

![Côté gauche et côté droit d&#39;une règle de filtrage](/help/main/c-recommendations/c-algorithms/assets/left_right.png)

Le tableau suivant présente les règles compatibles et celles susceptibles de ne pas l’être au moment de l’exécution :

| Règles compatibles | Règles potentiellement incompatibles |
|--- |--- |
| value - est compris entre - 90 % et 110 % de l’article actif - salesValue | salesValue - est compris entre - 90 % et 110 % de l’article actif - value |
| value - est compris entre - 90 % et 110 % de l’article actif - value | clearancePrice - est compris entre - 90 % et 110 % de l’article actif - margin |
| margin - est comprise entre - 90 % et 110 % de l’article actif - margin | storeInventory - est égal à - de l’article actif - inventory |
| inventory - est égal à - de l’article actif - inventory |  |
