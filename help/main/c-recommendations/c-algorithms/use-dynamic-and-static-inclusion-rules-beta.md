---
keywords: règles d’inclusion;critères d’inclusion;recommandations;créer des critères;promotion;promotions;filtrage dynamique;dynamique;valeurs vides;ignorer la règle de filtrage;filtre statique;filtrer par valeur;correspondance des attributs d’entité;correspondance des attributs de profil;correspondance de paramètres;filtrer par valeur;filtre statique
description: Découvrez comment créer des règles d’inclusion dans  [!DNL Target] Recommendations pour les critères et les promotions.
title: Comment utiliser les règles d’inclusion dynamiques et statiques dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
mini-toc-levels: 3
hide: true
hidefromtoc: true
source-git-commit: 84f2ea906dcab939b3892b11eabf96494f4514cb
workflow-type: tm+mt
source-wordcount: '1825'
ht-degree: 16%

---

# Utilisation de règles d’inclusion dynamiques et statiques

Créez des règles d’inclusion pour les critères et les promotions dans [!DNL Adobe Target] et ajoutez des règles de filtrage dynamiques ou statiques afin d’obtenir de meilleurs résultats pour vos recommandations.

Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Les critères et les promotions ainsi que l’utilisation des règles d’inclusion sont abordés dans cette section.

## Ajout de règles de filtrage à des critères et des promotions {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Les sections suivantes comprennent davantage d’informations :

### Ajout de règles de filtrage aux critères

1. Lors de la [création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) (**[!UICONTROL Recommendations]> [!UICONTROL Criteria] > [!UICONTROL Create Criteria] >[!UICONTROL Create Criteria]**), cliquez sur **[!UICONTROL Add Filtering Rule]** sous **[!UICONTROL Inclusion Rules]**.

   ![Ajouter une règle de filtrage](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. Cliquez sur la liste déroulante **Filtre statique** dans la zone &quot;Quelles autres règles doivent respecter la recommandation&quot;, puis sélectionnez l’option de votre choix dans la liste déroulante [!UICONTROL Static Filter].

   ![Liste déroulante Filtre statique](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   Les options disponibles varient en fonction du secteur industriel vertical et de la clé de recommandation sélectionnés.

### Ajout de règles de filtrage aux promotions

1. Lors de la [création d&#39;une promotion](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), sélectionnez **[!UICONTROL Promote by Attribute]**, puis cliquez sur **[!UICONTROL Add Filtering Rule]**.

## Types de filtre {#section_0125F1ED10A84C0EB45325122460EBCD}

Les sections suivantes répertorient les types d’options de filtrage pour [!UICONTROL Dynamic Filtering] et [!UICONTROL Filter by Value] pour les critères et les promotions :

### Filtrage dynamique

Les règles d’inclusion dynamique sont plus puissantes que les règles d’inclusion statique et elles produisent de meilleurs résultats et une meilleure interaction. Tenez compte des points suivants :

* Les règles d’inclusion dynamique fournissent des recommandations en faisant correspondre un attribut dans le paramètre de profil d’un utilisateur ou dans un appel de mbox.

  Vous pouvez par exemple créer une recommandation &quot;Critères les plus populaires&quot;. À partir de l’ensemble de recommandations renvoyées, vous pouvez filtrer toutes les recommandations (en temps réel) par rapport à un attribut transmis lorsque l’utilisateur accède à une page où les recommandations sont affichées.

* Utilisez des règles statiques pour limiter les éléments inclus dans la recommandation (au lieu d’utiliser des collections).

* Vous pouvez créer autant de règles d’inclusion dynamiques que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

Les options suivantes sont disponibles pour le filtrage dynamique :

| Option de filtrage dynamique | Détails |
| --- | --- |
| [[!UICONTROL Entity Attribute Matching]](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrez dynamiquement en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel les utilisateurs ont interagi.<P>Utilisez [!UICONTROL Entity Attribute Matching] lorsque vous souhaitez afficher des recommandations susceptibles d’intéresser le visiteur, telles que la marque préférée du visiteur. |
| [[!UICONTROL Profile Attribute Matching]](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrez dynamiquement en comparant les éléments (entités) à une valeur du profil de l’utilisateur.<P>Utilisez [!UICONTROL Profile Attribute Matching] lorsque vous souhaitez afficher des recommandations qui correspondent à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée. |
| [[!UICONTROL Parameter Matching]](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtrez dynamiquement en comparant les éléments (entités) à une valeur de la requête (API ou mbox).<P>Utilisez [!UICONTROL Parameter Matching] pour recommander du contenu qui correspond aux paramètres de la page ou aux paramètres du visiteur, tels que les dimensions de l’appareil ou la géolocalisation. |

### Filtrer par valeur

L’option suivante est disponible pour le filtrage par valeur :

| Option de filtrage par valeur | Détails |
| --- | --- |
| [[!UICONTROL Static Filter]](/help/main/c-recommendations/c-algorithms/static-value.md) | Saisissez manuellement une ou plusieurs valeurs statiques à filtrer. |

## Opérateurs disponibles {#operators}

Les critères et promotions dynamiques sont beaucoup plus puissants que les critères et les promotions statiques et produisent de meilleurs résultats et un meilleur engagement.

Les exemples suivants apportent des idées générales sur la manière d’utiliser les promotions et exclusions dynamiques dans vos efforts marketing :

| Opérateur | Exemples |
| --- | --- |
| [!UICONTROL equals any of]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | En utilisant l’opérateur &quot;est égal à&quot; dans les promotions dynamiques, lorsqu’un visiteur consulte un élément de votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments issus :<ul><li>Même marque</li><li>Même catégorie</li><li>Même catégorie ET de la marque-mère</li><li>Même magasin</li></ul> |
| [!UICONTROL does not equal any of]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | En utilisant l’opérateur &quot;[!UICONTROL does not equal any of]&quot; dans les promotions dynamiques, lorsqu’un visiteur consulte un élément de votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments issus de :<ul><li>Différentes séries télévisées</li><li>Un genre différent</li><li>Une autre série de produits</li><li>Identifiant de style différent</li></ul> |
| [!UICONTROL is greater than or equal to any of]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | À l’aide de l’opérateur &quot;[!UICONTROL is greater than or equal to any of]&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coût identique ou plus cher</li></ul> |
| [!UICONTROL is less than or equal to any of]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | À l’aide de l’opérateur &quot;[!UICONTROL is less than or equal to an of]&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coût identique ou moins cher</li><li>Exclusion des éléments moins chers</li></ul> |
| [!UICONTROL contains any of] (Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | À l’aide de l’opérateur &quot;[!UICONTROL contains any of]&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le titre contient la même marque</li></ul> |
| [!UICONTROL does not contain any of]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | À l’aide de l’opérateur &quot;ne contient aucun des&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le titre ne contient pas de mot de serment</li></ul> |
| [!UICONTROL starts with any of]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | À l’aide de l’opérateur &quot;[!UICONTROL starts with an of]&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le nom du produit commence par iPhone</li></ul> |
| [!UICONTROL ends with any of]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] et [!UICONTROL Static Filter].) | À l’aide de l’opérateur &quot;[!UICONTROL ends with an of]&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le contenu se termine par EN, qui indique la langue anglaise</li></ul> |
| [!UICONTROL is between]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].) | En utilisant l’opérateur &quot;i[!UICONTROL s between]&quot; dans les promotions dynamiques, lorsqu’un visiteur consulte un élément de votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Plus cher</li><li>Moins cher</li><li>Coût plus ou moins 30 %</li><li>Épisodes ultérieurs dans la même saison</li><li>Livres antérieurs à une série</li></ul> |
| [!UICONTROL list contains an item in]<P>(Disponible avec [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].) | En utilisant l’opérateur &quot;[!UICONTROL list contains an item in]&quot; dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Disponible dans la zone géographique du visiteur</li></ul>**Exemple** : vous souhaitez recommander des éléments disponibles uniquement dans la zone géographique d’un visiteur.<P>Votre règle de filtre peut se présenter comme suit :<P>`availableGeographies list contains an item in user.currentGeography`<P>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans le [côté droit](#caveats) de la règle. |
| [!UICONTROL list does not contain an item in]<P>(Disponible avec [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].) | En utilisant l’opérateur &quot;[!UICONTROL list does not contain an item in]&quot; dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (un produit, un article ou un film, par exemple), vous pouvez exclure d’autres éléments qui sont :<ul><li>Dans la liste des dix derniers éléments consultés par le visiteur</li></ul></ul>**Exemple** : vous ne souhaitez pas promouvoir des éléments que le visiteur a récemment consultés et dans lesquels il n’a manifesté aucun intérêt.<P>Votre règle de filtrage peut se présenter comme suit :<P>`id is not contained in list user.lastViewedItems`<P>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans le [côté droit](#caveats) de la règle. |
| [!UICONTROL list contains an item in]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].) | En utilisant l’opérateur &quot;[!UICONTROL list contains an item in]&quot; dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (un événement sportif ou un concert, par exemple), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Associé à l’une des équipes préférées du visiteur</li></ul>**Exemple** : vous souhaitez recommander des jeux associés à l’une des équipes préférées du visiteur.<P>Votre règle de filtrage peut se présenter comme suit :<P>` teamsPlaying list contains an item in user.favoriteTeams`<P>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans les [deux côtés](#caveats) de la règle. |
| [!UICONTROL list does not contain an item in]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].) | En utilisant l’opérateur &quot;[!UICONTROL list does not contain an item in]&quot; dans la correspondance des attributs de paramètre, lorsqu’un visiteur consulte un élément sur votre site web (un produit, un article ou un film, par exemple), vous pouvez exclure d’autres éléments qui sont :<ul><li>Contenu dans une liste de types interdits</li></ul>**Exemple** : vous souhaitez exclure les éléments disponibles pour les visiteurs adultes, tels que le tabac et l’alcool.<P>Votre règle de filtrage peut se présenter comme suit :<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans les [deux côtés](#caveats) de la règle. |
| [!UICONTROL list contains all items in]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].) | En utilisant l’opérateur &quot;[!UICONTROL list does not contain an item in]&quot; dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (une publication de tâche ou une recette, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Inclure un ensemble de compétences</li><li>Inclure un ensemble d’ingrédients requis</li></ul>**Exemple 1** : supposons qu’un visiteur possède un ensemble de compétences (Java, C++ et HTML). Les éléments du catalogue sont des tâches avec les compétences requises (Java et HTML). Vous souhaitez vous assurer que le profil du visiteur contient toutes les compétences requises avant de recommander la tâche au visiteur.<P>Votre règle de filtrage peut se présenter comme suit :<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**Exemple 2** : supposons qu’un utilisateur dispose d’une liste d’ingrédients de l’entreprise. La recette comporte une liste des ingrédients nécessaires. Vous souhaitez vous assurer que le profil du visiteur contient tous les ingrédients requis avant de recommander la recette au visiteur.<P>Votre règle de filtrage peut se présenter comme suit :<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans les [deux côtés](#caveats) de la règle. |
| [!UICONTROL list does not contain all items in]<P>(Disponible avec [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].) | En utilisant l’opérateur &quot;[!UICONTROL list does not contain all items in]&quot; dans la correspondance des attributs d’entité, lorsqu’un visiteur consulte un élément sur votre site web (un événement sportif ou un concert, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Ne pas inclure un ensemble d’équipes</li></ul>**Exemple** : supposons qu’un événement sportif comporte deux équipes. Le profil du visiteur indique que ce visiteur ne souhaite pas afficher les jeux pour ces équipes. Vous souhaitez vous assurer de ne pas recommander un jeu si ces équipes jouent.<P>Votre règle de filtrage peut se présenter comme suit :<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans les [deux côtés](#caveats) de la règle. |

## Gestion des valeurs vides lors du filtrage par [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Vous pouvez choisir plusieurs options pour gérer les valeurs vides lors du filtrage par [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] pour les critères de sortie et les promotions.

Auparavant, aucun résultat n’était renvoyé si une valeur était vide. La liste déroulante « Si *x* est vide » permet de choisir l’action appropriée à exécuter si le critère contient des valeurs vides, comme illustré ci-dessous :

![image_valeur_vide](assets/empty_value.png)

Pour sélectionner l’action souhaitée, survolez l’icône d’engrenage (![icon_engrenage image](assets/icon_gear.png)), puis choisissez l’action souhaitée :

| Action | Disponible pour | Détails |
|--- |--- |--- |
| [!UICONTROL Ignore this filtering rule] | [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Cette action est la valeur par défaut de [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].<P>Cette option indique que la règle est ignorée. Par exemple, s’il existe trois règles de filtrage et que la troisième règle ne transmet aucune valeur, vous pouvez simplement ignorer la troisième règle avec les valeurs vides au lieu de ne renvoyer aucun résultat. |
| [!UICONTROL Do not show any results for this criteria]<P>(Critères uniquement) | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Cette action est la valeur par défaut de [!UICONTROL Entity Attribute Matching].<P>Cette action est la manière dont [!DNL Target] a géré les valeurs vides avant l’ajout de cette option : aucun résultat n’est affiché pour ce critère. |
| [!UICONTROL  Ne promeut aucun élément<P>(Promotions uniquement)] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Cette action est la valeur par défaut de [!UICONTROL Entity Attribute Matching].<P>Cette action est la manière dont [!DNL Target] a géré les valeurs vides avant l’ajout de cette option : aucun résultat n’est affiché pour ce critère. |
| [!UICONTROL Use a static value] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Si une valeur est vide, vous pouvez choisir d’utiliser une valeur statique. |

## Avertissements {#caveats}

>[!IMPORTANT]
>
>Différents attributs de type de données peuvent ne pas être compatibles dans les critères ou promotions dynamiques au moment de l’exécution avec les opérateurs « est égal à » et « n’est pas égal à ». Utilisez sagement les valeurs [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] et [!UICONTROL Environment] sur le côté droit si le côté gauche comporte des attributs prédéfinis ou personnalisés.

![image left_right](assets/left_right.png)

Le tableau suivant répertorie les règles efficaces et celles qui peuvent ne pas être compatibles au moment de l’exécution :

| Règles compatibles | Règles potentiellement incompatibles |
|--- |--- |
| value - est compris entre - 90 % et 110 % de l’article actif - salesValue | salesValue - est compris entre - 90 % et 110 % de l’article actif - value |
| value - est compris entre - 90 % et 110 % de l’article actif - value | clearancePrice - est compris entre - 90 % et 110 % de l’article actif - margin |
| margin - est comprise entre - 90 % et 110 % de l’article actif - margin | storeInventory - est égal à - de l’article actif - inventory |
| inventory - est égal à - de l’article actif - inventory |  |
