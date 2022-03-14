---
keywords: règles d’inclusion;critères d’inclusion;recommandations;créer des critères;promotion;promotions;filtrage dynamique;dynamique;valeurs vides;ignorer la règle de filtrage;filtre statique;filtrer par valeur;correspondance des attributs d’entité;correspondance des attributs de profil;correspondance de paramètres;filtrer par valeur;filtre statique
description: Découvrez comment créer des règles d’inclusion dans Adobe [!DNL Target] Recommendations pour les critères et les promotions. Pour obtenir de meilleurs résultats, ajoutez des règles de filtrage plus dynamiques ou statiques.
title: Comment utiliser les règles d’inclusion dynamiques et statiques dans Recommendations ?
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2078'
ht-degree: 17%

---

# ![PREMIUM](/help/main/assets/premium.png) Utilisation de règles d’inclusion dynamiques et statiques

Informations sur la création de règles d’inclusion pour les critères et les promotions dans [!DNL Adobe Target] et ajouter des règles de filtrage dynamiques ou statiques afin d’obtenir de meilleurs résultats pour vos recommandations.

Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Les critères et les promotions ainsi que l’utilisation des règles d’inclusion sont abordés dans cette section.

## Ajout de règles de filtrage à des critères {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Lorsque vous [créez des critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), cliquez sur **[!UICONTROL Ajouter une règle de filtrage]** sous **[!UICONTROL Règles d’inclusion]**.

![](assets/inclusion_options_new.png)

Les options disponibles varient en fonction du secteur industriel vertical et de la clé de recommandation sélectionnés.

## Ajout de règles de filtrage à des promotions {#section_D59AFB62E2EE423086281CF5D18B1076}

Lors de la [création d’une promotion](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), sélectionnez **[!UICONTROL Promouvoir par attribut]**, puis cliquez sur **[!UICONTROL Ajouter une règle de filtrage]**.

![](assets/inclusion_options.png)

## Types de filtre {#section_0125F1ED10A84C0EB45325122460EBCD}

Les sections suivantes répertorient les types d’options de filtrage pour [!UICONTROL Filtrage dynamique] et [!UICONTROL Filtrer par valeur] pour les critères et les promotions :

### Filtrage dynamique

Les règles d’inclusion dynamique sont plus puissantes que les règles d’inclusion statique et elles produisent de meilleurs résultats et une meilleure interaction. Tenez compte des points suivants :

* Les règles d’inclusion dynamique fournissent des recommandations en faisant correspondre un attribut dans le paramètre de profil d’un utilisateur ou dans un appel de mbox.

   Vous pouvez par exemple créer une recommandation &quot;Critères les plus populaires&quot;. À partir de l’ensemble de recommandations renvoyées, vous pouvez filtrer toutes les recommandations (en temps réel) par rapport à un attribut transmis lorsque l’utilisateur accède à une page où les recommandations sont affichées.

* Utilisez des règles statiques pour limiter les éléments inclus dans la recommandation (au lieu d’utiliser des collections).

* Vous pouvez créer autant de règles d’inclusion dynamiques que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

Les options suivantes sont disponibles pour le filtrage dynamique :

| Option de filtrage dynamique | Détails |
| --- | --- |
| [Correspondance des attributs d’entité](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrez dynamiquement en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel les utilisateurs ont interagi.<br>Utilisation [!UICONTROL Correspondance des attributs d’entité] lorsque vous souhaitez afficher des recommandations susceptibles d’intéresser le visiteur, telles que la marque préférée du visiteur. |
| [Correspondance des attributs de profil](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrez dynamiquement en comparant les éléments (entités) à une valeur du profil de l’utilisateur.<br>Utilisation [!UICONTROL Correspondance des attributs de profil] lorsque vous souhaitez afficher des recommandations qui correspondent à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée. |
| [Correspondance de paramètres](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtrez dynamiquement en comparant les éléments (entités) à une valeur de la requête (API ou mbox).<br>Utilisation [!UICONTROL Correspondance de paramètres] pour recommander du contenu correspondant aux paramètres de la page ou aux paramètres du visiteur, tels que les dimensions de l’appareil ou la géolocalisation. |

### Filtrer par valeur

L’option suivante est disponible pour le filtrage par valeur :

| Option de filtrage par valeur | Détails |
| --- | --- |
| [Filtre statique](/help/main/c-recommendations/c-algorithms/static-value.md) | Saisissez manuellement une ou plusieurs valeurs statiques à filtrer. |

## Opérateurs disponibles {#operators}

Les critères et promotions dynamiques sont beaucoup plus puissants que les critères et les promotions statiques et produisent de meilleurs résultats et un meilleur engagement.

Les exemples suivants apportent des idées générales sur la manière d’utiliser les promotions et exclusions dynamiques dans vos efforts marketing :

| Opérateur | Exemples |
| --- | --- |
| Est égal à<br>(Disponible avec Correspondance des attributs d’entité, Correspondance des attributs de profil, Correspondance de paramètres et Filtre statique.) | En utilisant l’opérateur &quot;est égal à&quot; dans les promotions dynamiques, lorsqu’un visiteur consulte un élément de votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments issus de :<ul><li>Même marque</li><li>Même catégorie</li><li>Même catégorie ET de la marque-mère</li><li>Même magasin</li></ul> |
| N’est pas égal à<br>(Disponible avec Correspondance des attributs d’entité, Correspondance des attributs de profil, Correspondance de paramètres et Filtre statique.) | En utilisant l’opérateur &quot;n’est pas égal à&quot; dans les promotions dynamiques, lorsqu’un visiteur consulte un élément sur votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments issus de :<ul><li>Différentes séries télévisées</li><li>Un genre différent</li><li>Une autre série de produits</li><li>Identifiant de style différent</li></ul> |
| Ne contient pas de sous-chaîne<br>(Disponible avec Correspondance des attributs d’entité, Correspondance des attributs de profil, Correspondance de paramètres et Filtre statique.) | À l’aide de l’opérateur &quot;ne contient pas de sous-chaîne&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le titre ne contient pas de mot de serment</li></ul> |
| Commence par<br>(Disponible avec Correspondance des attributs d’entité, Correspondance des attributs de profil, Correspondance de paramètres et Filtre statique.) | À l’aide de l’opérateur &quot;commence par&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le nom du produit commence par iPhone</li></ul> |
| Se termine par<br>(Disponible avec Correspondance des attributs d’entité, Correspondance des attributs de profil, Correspondance de paramètres et Filtre statique.) | À l’aide de l’opérateur &quot;se termine par&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Le contenu se termine par EN, qui indique la langue anglaise</li></ul> |
| Is Greater Than or Equal To<br>(Disponible avec Correspondance des attributs d’entité, Correspondance des attributs de profil, Correspondance de paramètres et Filtre statique.) | À l’aide de l’opérateur &quot;est supérieur ou égal à&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coût identique ou plus cher</li></ul> |
| Is Less Than or Equal To<br>(Disponible avec Correspondance des attributs d’entité, Correspondance des attributs de profil, Correspondance de paramètres et Filtre statique.) | À l’aide de l’opérateur &quot;est inférieur ou égal à&quot;, lorsqu’un visiteur consulte un élément de votre site web (un produit, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coût identique ou moins cher</li><li>Exclusion des éléments moins chers</li></ul> |
| Est compris entre<br>(Disponible avec la correspondance des attributs d’entité, la correspondance des attributs de profil et la correspondance de paramètres.) | En utilisant l’opérateur &quot;est compris entre&quot; dans les promotions dynamiques, lorsqu’un visiteur consulte un élément de votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Plus cher</li><li>Moins cher</li><li>Coût plus ou moins 30 %</li><li>Les épisodes suivants de la même saison</li><li>Livres antérieurs à une série</li></ul> |
| Contient Dans La Liste<br>(Disponible avec la correspondance des attributs de profil et la correspondance de paramètres.) | En utilisant l’opérateur &quot;est contenu dans la liste&quot; dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (un produit, un article ou un film, par exemple), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Disponible dans la zone géographique du visiteur</li></ul>**Exemple**: Vous souhaitez recommander uniquement les éléments disponibles dans la zone géographique d’un visiteur.<br>Votre règle de filtre peut se présenter comme suit :<br>`availableGeographies list contains an item in user.currentGeography`<br>**Remarque**: Lorsque vous utilisez cet opérateur, une liste est attendue dans la variable [côté droit](#caveats) de la règle. |
| Ne Se Trouve Pas Dans La Liste<br>(Disponible avec la correspondance des attributs de profil et la correspondance de paramètres.) | En utilisant l’opérateur &quot;ne figure pas dans la liste&quot; dans la correspondance d’attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (un produit, un article ou un film, par exemple), vous pouvez exclure d’autres éléments qui sont :<ul><li>Dans la liste des dix derniers éléments consultés par le visiteur</li></ul></ul>**Exemple**: Vous ne souhaitez pas promouvoir des éléments que le visiteur a récemment consultés et dans lesquels il n’a manifesté aucun intérêt.<br>Votre règle de filtrage peut se présenter comme suit :<br>`id is not contained in list user.lastViewedItems`<br>**Remarque**: Lorsque vous utilisez cet opérateur, une liste est attendue dans la variable [côté droit](#caveats) de la règle. |
| La Liste Contient Un Élément Dans<br>(Disponible avec la correspondance des attributs d’entité, la correspondance des attributs de profil et la correspondance de paramètres.) | En utilisant l’opérateur &quot;liste contient un élément dans&quot; dans la correspondance des attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (un événement sportif ou un concert, par exemple), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Associé à l’une des équipes préférées du visiteur</li></ul>**Exemple**: Vous souhaitez recommander des jeux associés à l’une des équipes favorites du visiteur.<br>Votre règle de filtrage peut se présenter comme suit :<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**Remarque**: Lorsque vous utilisez cet opérateur, une liste est attendue dans [des deux côtés](#caveats) de la règle. |
| La Liste Ne Contient Pas D’Élément Dans<br>(Disponible avec la correspondance des attributs d’entité, la correspondance des attributs de profil et la correspondance de paramètres.) | En utilisant l’opérateur &quot;La liste ne contient pas d’élément dans&quot; dans la correspondance des attributs de paramètre, lorsqu’un visiteur consulte un élément sur votre site web (un produit, un article ou un film, par exemple), vous pouvez exclure d’autres éléments qui sont :<ul><li>Contenu dans une liste de types interdits</li></ul>**Exemple**: Vous souhaitez exclure les éléments qui sont disponibles pour les visiteurs adultes, tels que le tabac et l’alcool.<br>Votre règle de filtrage peut se présenter comme suit :<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**Remarque**: Lorsque vous utilisez cet opérateur, une liste est attendue dans [des deux côtés](#caveats) de la règle. |
| La Liste Contient Tous Les Éléments De<br>(Disponible avec la correspondance des attributs d’entité, la correspondance des attributs de profil et la correspondance de paramètres.) | En utilisant l’opérateur &quot;La liste contient tous les éléments dans&quot; dans la correspondance d’attributs de profil, lorsqu’un visiteur consulte un élément sur votre site web (une publication de tâche ou une recette, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Inclure un ensemble de compétences</li><li>Inclure un ensemble d’ingrédients requis</li></ul>**Exemple 1**: Supposons qu’un visiteur ait un ensemble de compétences (Java, C++ et HTML). Les éléments du catalogue sont des tâches avec les compétences requises (Java et HTML). Vous souhaitez vous assurer que le profil du visiteur contient toutes les compétences requises avant de recommander la tâche au visiteur.<br>Votre règle de filtrage peut se présenter comme suit :<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**Exemple 2**: Supposons qu’un utilisateur dispose d’une liste d’ingrédients de la société. La recette comporte une liste des ingrédients nécessaires. Vous souhaitez vous assurer que le profil du visiteur contient tous les ingrédients requis avant de recommander la recette au visiteur.<br>Votre règle de filtrage peut se présenter comme suit :<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**Remarque**: Lorsque vous utilisez cet opérateur, une liste est attendue dans [des deux côtés](#caveats) de la règle. |
| La Liste Ne Contient Pas Tous Les Éléments De<br>(Disponible avec la correspondance des attributs d’entité, la correspondance des attributs de profil et la correspondance de paramètres.) | En utilisant l’opérateur &quot;La liste ne contient pas tous les éléments dans&quot; dans la correspondance des attributs d’entité, lorsqu’un visiteur consulte un élément sur votre site web (un événement sportif ou un concert, par exemple), vous pouvez promouvoir d’autres éléments qui :<ul><li>Ne pas inclure un ensemble d’équipes</li></ul>**Exemple**: Supposons qu’un événement sportif comporte deux équipes. Le profil du visiteur indique que ce visiteur ne souhaite pas afficher les jeux pour ces équipes. Vous souhaitez vous assurer de ne pas recommander un jeu si ces équipes jouent.<br>Votre règle de filtrage peut se présenter comme suit :<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**Remarque**: Lorsque vous utilisez cet opérateur, une liste est attendue dans [des deux côtés](#caveats) de la règle. |

## Gestion des valeurs vides lors du filtrage par correspondance des attributs d’entité, correspondance des attributs de profil et correspondance de paramètres {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Vous pouvez choisir plusieurs options pour gérer les valeurs vides lors du filtrage par [!UICONTROL Correspondance des attributs d’entité], [!UICONTROL Correspondance des attributs de profil], et [!UICONTROL Correspondance de paramètres] pour les critères de sortie et les promotions.

Auparavant, aucun résultat n’était renvoyé si une valeur était vide. La liste déroulante « Si *x* est vide » permet de choisir l’action appropriée à exécuter si le critère contient des valeurs vides, comme illustré ci-dessous :

![](assets/empty_value.png)

Pour sélectionner une action spécifique, survolez l’icône représentant un engrenage (![](assets/icon_gear.png)), puis choisissez l’action souhaitée :

| Action | Disponible pour | Détails |
|--- |--- |--- |
| [!UICONTROL Ignorer cette règle de filtrage] | [!UICONTROL Correspondance des attributs de profil] et [!UICONTROL Correspondance de paramètres] | Cette action est la valeur par défaut pour [!UICONTROL Correspondance des attributs de profil] et [!UICONTROL Correspondance de paramètres].<br>Cette option indique que la règle est ignorée. Par exemple, s’il existe trois règles de filtrage et que la troisième règle ne transmet aucune valeur, vous pouvez simplement ignorer la troisième règle avec les valeurs vides au lieu de ne renvoyer aucun résultat. |
| [!UICONTROL N’affiche aucun résultat pour ce critère]<br>(Critères uniquement) | [!UICONTROL Correspondance des attributs d’entité], [!UICONTROL Correspondance des attributs de profil], et [!UICONTROL Correspondance de paramètres] | Cette action est la valeur par défaut pour [!UICONTROL Correspondance des attributs d’entité].<br>Cette action montre comment [!DNL Target] a géré des valeurs vides avant l’ajout de cette option : aucun résultat n’est affiché pour ce critère. |
| [!UICONTROL Ne promeut aucun élément<br>(Promotions uniquement)] | [!UICONTROL Correspondance des attributs d’entité], [!UICONTROL Correspondance des attributs de profil], et [!UICONTROL Correspondance de paramètres] | Cette action est la valeur par défaut pour [!UICONTROL Correspondance des attributs d’entité].<br>Cette action montre comment [!DNL Target] a géré des valeurs vides avant l’ajout de cette option : aucun résultat n’est affiché pour ce critère. |
| [!UICONTROL Utiliser une valeur statique] | [!UICONTROL Correspondance des attributs d’entité], [!UICONTROL Correspondance des attributs de profil], et [!UICONTROL Correspondance de paramètres] | Si une valeur est vide, vous pouvez choisir d’utiliser une valeur statique. |

## Avertissements {#caveats}

>[!IMPORTANT]
>
>Différents attributs de type de données peuvent ne pas être compatibles dans les critères ou promotions dynamiques au moment de l’exécution avec les opérateurs « est égal à » et « n’est pas égal à ». Utilisation [!UICONTROL Valeur], [!UICONTROL Marge], [!UICONTROL Inventaire], et [!UICONTROL Environnement] sur le côté droit si le côté gauche contient des attributs prédéfinis ou personnalisés.

![](assets/left_right.png)

Le tableau suivant répertorie les règles efficaces et celles qui peuvent ne pas être compatibles au moment de l’exécution :

| Règles compatibles | Règles potentiellement incompatibles |
|--- |--- |
| value - est compris entre - 90 % et 110 % de l’article actif - salesValue | salesValue - est compris entre - 90 % et 110 % de l’article actif - value |
| value - est compris entre - 90 % et 110 % de l’article actif - value | clearancePrice - est compris entre - 90 % et 110 % de l’article actif - margin |
| margin - est comprise entre - 90 % et 110 % de l’article actif - margin | storeInventory - est égal à - de l’article actif - inventory |
| inventory - est égal à - de l’article actif - inventory |  |
