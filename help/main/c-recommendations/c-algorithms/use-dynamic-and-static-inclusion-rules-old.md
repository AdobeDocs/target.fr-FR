---
keywords: règles d’inclusion;critères d’inclusion;recommandations;créer des critères;promotion;promotions;filtrage dynamique;dynamique;valeurs vides;ignorer la règle de filtrage;filtre statique;filtrer par valeur;correspondance des attributs d’entité;correspondance des attributs de profil;correspondance de paramètres;filtrer par valeur;filtre statique
description: Découvrez comment créer des règles d’inclusion dans Adobe [!DNL Target] Recommendations pour les critères et les promotions. Pour obtenir de meilleurs résultats, ajoutez des règles de filtrage plus dynamiques ou statiques.
title: Comment utiliser les règles d’inclusion dynamiques et statiques dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '2013'
ht-degree: 16%

---

# Utilisation de règles d’inclusion dynamiques et statiques

Informations sur la création de règles d’inclusion pour les critères et les promotions dans [!DNL Adobe Target] et l’ajout de règles de filtrage dynamiques ou statiques pour obtenir de meilleurs résultats pour vos recommandations.

Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Les critères et les promotions, ainsi que l’utilisation des règles d’inclusion, sont abordés dans cette section.

## Ajout de règles de filtrage à des critères {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Lorsque vous [créez des critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), cliquez sur **[!UICONTROL Add Filtering Rule]** sous **[!UICONTROL Inclusion Rules]**.

![inclusion_options_new image](assets/inclusion_options_new.png)

Les options disponibles varient en fonction du secteur industriel vertical et de la clé de recommandation sélectionnés.

## Ajout de règles de filtrage à des promotions {#section_D59AFB62E2EE423086281CF5D18B1076}

Lors de la [création d’une promotion](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), sélectionnez **[!UICONTROL Promote by Attribute]**, puis cliquez sur **[!UICONTROL Add Filtering Rule]**.

![image inclusion_options](assets/inclusion_options.png)

## Types de filtre {#section_0125F1ED10A84C0EB45325122460EBCD}

Les sections suivantes répertorient les types d’options de filtrage pour les [!UICONTROL Dynamic Filtering] et les [!UICONTROL Filter by Value] pour les critères et les promotions :

### Filtrage dynamique

Les règles d’inclusion dynamiques sont plus puissantes que les règles d’inclusion statiques et elles génèrent de meilleurs résultats et un meilleur engagement. Tenez compte des points suivants :

* Les règles d’inclusion dynamique fournissent des recommandations en faisant correspondre un attribut dans le paramètre de profil d’un utilisateur ou dans un appel de mbox.

  Par exemple, vous pouvez créer une recommandation « Critères les plus populaires ». À partir de l’ensemble des recommandations renvoyées, vous pouvez filtrer les recommandations (en temps réel) par rapport à un attribut transmis lorsque l’utilisateur accède à une page où les recommandations sont affichées.

* Utilisez des règles statiques pour limiter les éléments inclus dans la recommandation (au lieu d’utiliser des collections).

* Vous pouvez créer autant de règles d’inclusion dynamiques que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

Les options suivantes sont disponibles pour le filtrage dynamique :

| Option de filtrage dynamique | Détails |
| --- | --- |
| [Correspondance des attributs d’entité](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrez de manière dynamique en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel les utilisateurs et utilisatrices ont interagi.<br>Utilisez [!UICONTROL Entity Attribute Matching] lorsque vous souhaitez afficher les recommandations les plus susceptibles d’intéresser le visiteur, telles que sa marque préférée. |
| [Correspondance des attributs de profil](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrez de manière dynamique en comparant des éléments (entités) à une valeur dans le profil de l’utilisateur.<br>Utilisez [!UICONTROL Profile Attribute Matching] lorsque vous souhaitez afficher des recommandations correspondant à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée. |
| [Correspondance de paramètres](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtrez de manière dynamique en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).<br>Utilisez des [!UICONTROL Parameter Matching] pour recommander du contenu correspondant aux paramètres de la page ou aux paramètres du visiteur, tels que les dimensions de l’appareil ou la géolocalisation. |

### Filtrer par valeur

L’option suivante est disponible pour le filtrage par valeur :

| Option Filtrer par valeur | Détails |
| --- | --- |
| [Filtre statique](/help/main/c-recommendations/c-algorithms/static-value.md) | Saisissez manuellement une ou plusieurs valeurs statiques à filtrer. |

## Opérateurs disponibles {#operators}

Les critères dynamiques et les promotions sont beaucoup plus puissants que les critères statiques et les promotions et produisent de meilleurs résultats et un meilleur engagement.

Les exemples suivants donnent des idées générales sur l’utilisation des promotions et exclusions dynamiques dans vos efforts marketing :

| Opérateur | Exemples |
| --- | --- |
| Est égal à <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil, correspondance de paramètres et filtre statique). | En utilisant l’opérateur « égal à » dans les promotions dynamiques, lorsqu’un visiteur consulte un article sur votre site web (tel qu’un produit, un article ou un film), vous pouvez promouvoir d’autres articles à partir de :<ul><li>La même marque</li><li>La même catégorie</li><li>La même catégorie ET de la marque maison</li><li>Le même magasin</li></ul> |
| Non égal à <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil, correspondance de paramètres et filtre statique). | En utilisant l’opérateur « n’est pas égal à » dans les promotions dynamiques, lorsqu’un visiteur consulte un élément de votre site web (tel qu’un produit, un article ou un film), vous pouvez promouvoir d’autres éléments à partir de :<ul><li>Une autre série télé</li><li>Un genre différent</li><li>Une autre série de produits</li><li>Un identifiant de style différent</li></ul> |
| Ne contient pas de sous-chaîne <br>(disponible avec la correspondance d’attributs d’entité, la correspondance d’attributs de profil, la correspondance de paramètres et le filtre statique). | À l’aide de l’opérateur « ne contient pas de sous-chaîne », lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le titre ne contient pas de juron</li></ul> |
| Commence par <br>(disponible avec la correspondance d’attributs d’entité, la correspondance d’attributs de profil, la correspondance de paramètres et le filtre statique). | Avec l’opérateur « commence par », lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le nom du produit commence par iPhone.</li></ul> |
| Se termine par <br>(disponible avec la correspondance d’attributs d’entité, la correspondance d’attributs de profil, la correspondance de paramètres et le filtre statique). | Avec l’opérateur « se termine par », lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le contenu se termine par EN, qui indique la langue anglaise</li></ul> |
| Est supérieur ou égal à <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil, correspondance de paramètres et filtre statique). | Avec l’opérateur « Est supérieur ou égal à », lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coûtent le même prix ou sont plus chers</li></ul> |
| Est inférieur ou égal à <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil, correspondance de paramètres et filtre statique). | Avec l’opérateur « Est inférieur ou égal à », lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coûtent le même prix ou sont moins chers</li><li>Exclure les éléments moins coûteux</li></ul> |
| Est compris entre <br>(disponible avec la correspondance d’attributs d’entité, la correspondance d’attributs de profil et la correspondance de paramètres). | En utilisant l’opérateur « est compris entre » dans les promotions dynamiques, lorsqu’un visiteur consulte un élément de votre site web (tel qu’un produit, un article ou un film), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Plus cher</li><li>Moins cher</li><li>Coût plus ou moins 30 %</li><li>Épisodes ultérieurs de la même saison</li><li>Livres antérieurs dans une série</li></ul> |
| Est contenu dans la liste <br>(disponible avec la correspondance des attributs de profil et la correspondance des paramètres). | À l’aide de l’opérateur « est contenu dans la liste » dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément de votre site web (tel qu’un produit, un article ou un film), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Disponible dans la zone géographique du visiteur</li></ul>**Exemple** : vous souhaitez recommander uniquement des éléments disponibles dans la zone géographique d’un visiteur.<br>Votre règle de filtrage peut ressembler à :<br>`availableGeographies list contains an item in user.currentGeography`<br>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans le [côté droit](#caveats) de la règle. |
| N’est pas contenu dans la liste <br>(disponible avec la correspondance des attributs de profil et des paramètres). | À l’aide de l’opérateur « n’est pas contenu dans la liste » dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément de votre site web (tel qu’un produit, un article ou un film), vous pouvez exclure d’autres éléments qui sont :<ul><li>Dans la liste des dix derniers éléments que le visiteur a consultés</li></ul></ul>**Exemple** : vous ne souhaitez pas promouvoir des éléments que le visiteur a récemment consultés et qui ne l’intéressent pas.<br>Votre règle de filtrage peut ressembler à :<br>`id is not contained in list user.lastViewedItems`<br>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue dans le [côté droit](#caveats) de la règle. |
| Liste contient un élément dans <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil et correspondance de paramètres). | En utilisant l’opérateur « la liste contient un élément dans » dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (un événement sportif ou un concert, par exemple), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Associé à l’une des équipes préférées du visiteur</li></ul>**Exemple** : vous souhaitez recommander des jeux associés à l’une des équipes préférées du visiteur.<br>Votre règle de filtrage peut ressembler à :<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue des [deux côtés](#caveats) de la règle. |
| La liste ne contient pas d’élément dans <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil et correspondance de paramètres). | En utilisant l’opérateur « la liste ne contient pas d’élément dans » dans la correspondance d’attributs de paramètre, lorsqu’un visiteur consulte un élément de votre site web (comme un produit, un article ou un film), vous pouvez exclure d’autres éléments qui sont :<ul><li>Contenu dans une liste de types interdits</li></ul>**Exemple** : vous souhaitez exclure les éléments disponibles pour les visiteurs qui sont des adultes, tels que le tabac et l’alcool.<br>Votre règle de filtrage peut ressembler à :<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue des [deux côtés](#caveats) de la règle. |
| Liste contient tous les éléments de <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil et correspondance de paramètres). | À l’aide de l’opérateur « liste contient tous les éléments de » dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément de votre site web (une offre d’emploi ou une recette, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Inclure un ensemble de compétences</li><li>Inclure un ensemble d’ingrédients requis</li></ul>**Exemple 1** : supposons qu’un visiteur possède un ensemble de compétences (Java, C++ et HTML). Les éléments du catalogue sont des tâches avec les compétences requises (Java et HTML). Vous devez vous assurer que le profil du visiteur contient toutes les compétences requises avant de recommander le travail au visiteur.<br>Votre règle de filtrage peut ressembler à :<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**Exemple 2** : supposons qu’un utilisateur dispose d’une liste d’ingrédients de garde-manger. La recette comporte une liste des ingrédients requis. Vous devez vous assurer que le profil du visiteur contient tous les ingrédients requis avant de recommander la recette au visiteur.<br>Votre règle de filtrage peut ressembler à :<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue des [deux côtés](#caveats) de la règle. |
| La liste ne contient pas tous les éléments dans <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de profil et correspondance de paramètres). | En utilisant l’opérateur « la liste ne contient pas tous les éléments de » dans la correspondance des attributs d’entité, lorsqu’un visiteur consulte un élément de votre site web (un événement sportif ou un concert, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Ne pas inclure un ensemble d’équipes</li></ul>**Exemple** : supposons qu’un événement sportif inclue deux équipes. Le profil du visiteur indique que ce visiteur ne souhaite pas voir les jeux de ces équipes. Vous devez vous assurer de ne pas recommander un jeu si ces équipes jouent.<br>Votre règle de filtrage peut ressembler à :<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**Remarque** : lors de l’utilisation de cet opérateur, une liste est attendue des [deux côtés](#caveats) de la règle. |

## Gérer les valeurs vides lors du filtrage par correspondance d’attributs d’entité, correspondance d’attributs de profil et correspondance de paramètres {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Vous pouvez choisir plusieurs options pour gérer les valeurs vides lors du filtrage par [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] pour les critères de sortie et les promotions.

Auparavant, aucun résultat n’était renvoyé si une valeur était vide. La liste déroulante « Si *x* est vide » permet de choisir l’action appropriée à exécuter si le critère contient des valeurs vides, comme illustré ci-dessous :

![image empty_value](assets/empty_value.png)

Pour sélectionner l’action souhaitée, placez le pointeur de la souris sur l’icône d’engrenage (![icon_gear image](assets/icon_gear.png)), puis choisissez l’action souhaitée :

| Action | Disponible pour | Détails |
|--- |--- |--- |
| [!UICONTROL Ignore this filtering rule] | [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Il s’agit de l’action par défaut pour [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching].<br>Cette option indique que la règle est ignorée. Par exemple, s’il existe trois règles de filtrage et que la troisième règle ne transmet aucune valeur, vous pouvez simplement ignorer la troisième règle avec les valeurs vides au lieu de ne renvoyer aucun résultat. |
| [!UICONTROL Do not show any results for this criteria]<br>(Critères uniquement) | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Il s’agit de l’action par défaut pour [!UICONTROL Entity Attribute Matching].<br>Cette action est [!DNL Target] comment gérer les valeurs vides avant l&#39;ajout de cette option : aucun résultat n&#39;est affiché pour ce critère. |
| [!UICONTROL Do not promote any items<br>(Promotions uniquement)] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Il s’agit de l’action par défaut pour [!UICONTROL Entity Attribute Matching].<br>Cette action est [!DNL Target] comment gérer les valeurs vides avant l&#39;ajout de cette option : aucun résultat n&#39;est affiché pour ce critère. |
| [!UICONTROL Use a static value] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] et [!UICONTROL Parameter Matching] | Si une valeur est vide, vous pouvez choisir d’utiliser une valeur statique. |

## Avertissements {#caveats}

>[!IMPORTANT]
>
>Différents attributs de type de données peuvent ne pas être compatibles dans les critères ou promotions dynamiques au moment de l’exécution avec les opérateurs « est égal à » et « n’est pas égal à ». Utilisez judicieusement les valeurs [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] et [!UICONTROL Environment] sur le côté droit si le côté gauche comporte des attributs prédéfinis ou des attributs personnalisés.

![image left_right](assets/left_right.png)

Le tableau suivant répertorie les règles efficaces et celles qui peuvent ne pas être compatibles au moment de l’exécution :

| Règles compatibles | Règles potentiellement incompatibles |
|--- |--- |
| value - est compris entre - 90 % et 110 % de l’article actif - salesValue | salesValue - est compris entre - 90 % et 110 % de l’article actif - value |
| value - est compris entre - 90 % et 110 % de l’article actif - value | clearancePrice - est compris entre - 90 % et 110 % de l’article actif - margin |
| margin - est comprise entre - 90 % et 110 % de l’article actif - margin | storeInventory - est égal à - de l’article actif - inventory |
| inventory - est égal à - de l’article actif - inventory |  |
