---
keywords: recherche catalogue;catalogue;recherche;exclusion;collection;filtre
description: Découvrez comment utiliser la recherche catalogue Recommendations pour localiser des produits ou du contenu, créer des collections ou des exclusions, supprimer des éléments de votre catalogue, etc.
title: Comment utiliser la recherche catalogue Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 23%

---

# Recherche catalogue

Le [!UICONTROL Recherche catalogue] page [!DNL Adobe Recommendations] vous aide à localiser les produits ou le contenu dans votre catalogue. La tâche la plus élémentaire que vous pouvez effectuer sur cette page est de rechercher un élément. En outre, vous pouvez modifier l’environnement, enregistrer les résultats de recherche dans des collections ou des exclusions, ajouter des facettes de filtre, modifier des colonnes dans le tableau, ajouter de nouvelles facettes de recherche, etc.

Les catalogues font référence à l’ensemble de vos produits (entités). Votre catalogue peut contenir de nombreuses collections, un moyen d’organiser vos produits dans des compartiments logiques.

## Accès à la recherche catalogue

Pour accéder au [!UICONTROL Recherche catalogue] page, cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Recherche catalogue]**.

![Page Recherche catalogue](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## Recherche d’un élément

Vous pouvez utiliser une recherche simple ou avancée pour localiser des éléments dans votre catalogue.

### Exécution d’une recherche simple

1. Saisissez un terme de recherche dans la variable **[!UICONTROL Rechercher des produits]** champ .

1. (Facultatif) Vous pouvez affiner votre recherche en sélectionnant une option de recherche dans le menu d’options qui s’affiche lorsque vous cliquez sur la flèche vers le bas dans le champ de recherche.

   ![image searchproducts menu](assets/searchproductsmenu.png)

   Les options de recherche disponibles sont les suivantes :

   * TOUT - Recherche sur tous les autres critères de recherche, à l’aide de la logique OU.
   * Nom
   * Marque
   * Catégorie
   * ID
   * Message

1. Vous pouvez désormais faire défiler les éléments des résultats de recherche pour afficher des miniatures et d’autres informations sur les produits.

   L’illustration suivante présente les résultats pour le &quot;vélo&quot; à l’aide de l’option Tous.

   ![Recherche catalogue de vélos](/help/main/c-recommendations/c-products/assets/bike-results.png)

   Le nombre qui s’affiche en regard de « Produits » est le nombre de produits qui correspondent au terme de recherche, sur le total disponible dans l’environnement spécifié.

   Vous pouvez utiliser la fonctionnalité de saisie semi-automatique de la recherche. Sur l’illustration suivante, la saisie de &quot;vélo&quot; renvoie tous les produits contenant le mot &quot;vélo&quot;.

   ![Recherche automatique](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >Lorsque vous effectuez une recherche catalogue sur un attribut personnalisé doté d’une valeur numérique, les résultats traitent l’attribut personnalisé comme une valeur de type chaîne plutôt que comme une valeur numérique.
   >
   >Actuellement, aucune fonctionnalité n’est disponible pour vous permettre de modifier le type d’un attribut. Pour apporter une modification, [ouvrez un problème client](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) avec en référence les attributs dont le type doit être passé de chaîne à numérique.

1. Vous pouvez également utiliser des filtres pour trouver le produit souhaité. Dans l’exemple suivant, en développant la variable [!UICONTROL Collections] et en sélectionnant &quot;Bike Tools&quot;, tous les outils de vélo de votre catalogue.

   ![Outils pour vélos](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. Vous pouvez effectuer une recherche plus approfondie dans la liste des résultats en saisissant un terme de recherche, par exemple &quot;chaîne&quot;.

   ![Recherche de chaîne](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### Exécution d’une recherche avancée {#advanced-search}

Vous pouvez utiliser [!UICONTROL Recherche avancée] pour affiner davantage vos résultats de recherche ou enregistrer vos résultats de recherche en tant que [collection](/help/main/c-recommendations/c-products/collections.md) ou [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Cliquez sur le bouton **[!UICONTROL Recherche avancée]** lien.

   ![Page Recherche avancée](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Utilisez les listes déroulantes pour spécifier le paramètre, l’opérateur et les valeurs de votre recherche.

1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]** pour ajouter une règle de recherche supplémentaire.

   Chaque règle de recherche supplémentaire est associée à l’opérateur AND.

1. Cliquez sur **[!UICONTROL Rechercher]**.

1. (Facultatif) Cliquez sur **[!UICONTROL Enregistrer sous]**, puis cliquez sur **[!UICONTROL Collection]** ou **[!UICONTROL Exclusion]**.

   ![Enregistrer en tant que options](/help/main/c-recommendations/c-products/assets/save-as.png)

   Pour plus d’informations, voir [Création d’une collection ou d’une exclusion à partir de la recherche avancée](#save-as) ci-dessous.

## Affichage des détails d’un élément

Vous pouvez afficher les détails d’un élément individuel, y compris son identifiant, son nom, son message, sa catégorie, etc. en affichant ses détails.

1. Cliquez sur un élément dans les résultats de recherche pour en afficher les détails.

   ![Détails du produit](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## Supprimer un élément du catalogue

1. Cliquez sur un élément dans les résultats de recherche pour en afficher les détails.

1. Cliquez sur **[!UICONTROL Supprimer du catalogue]**.

1. Confirmez que vous souhaitez supprimer l’élément.

Toutes les informations sur cet élément sont supprimées de l’index de catalogue. L’élément sera inclus dans votre catalogue uniquement s’il est de nouveau ajouté à un flux de données. Un élément supprimé doit être supprimé séparément des flux.

## Actualiser le catalogue

L’index de votre catalogue est automatiquement créé lorsque vous chargez votre premier flux et actualisé en fonction de la variable [planning spécifié](/help/main/c-recommendations/c-products/feeds.md#steps).

Le catalogue est automatiquement actualisé lorsque des mises à jour sont reçues via des fichiers de flux, des API ou des mises à jour de mbox. Les mises à jour sont généralement effectuées en une heure. Si des mises à jour sont en cours, l’heure de début de la mise à jour la plus récente s’affiche. Si aucune mise à jour n’est en cours, l’heure de début et de fin de la mise à jour la plus récente s’affiche.

## Création d’une collection ou d’une exclusion à l’aide de la recherche avancée {#save-as}

Vous pouvez créer des [collections](/help/main/c-recommendations/c-products/collections.md) ou des [exclusions](/help/main/c-recommendations/c-products/exclusions.md) à l’aide de la fonctionnalité de recherche avancée de la page de recherche catalogue ([!UICONTROL Recommandations] > [!UICONTROL Recherche catalogue] > [!UICONTROL Recherche avancée]).

1. Effectuez une [recherche avancée](#advanced-search).

1. Cliquez sur **[!UICONTROL Enregistrer sous]**, puis cliquez sur **[!UICONTROL Collection]** ou **[!UICONTROL Exclusion]**.

   ![Enregistrer en tant que options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >Le [!UICONTROL Recherche avancée] La fonctionnalité n’est pas sensible à la casse ; cependant, les produits renvoyés au moment de la livraison sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des collections ou des exclusions en fonction des résultats de l’utilisation de la variable [!UICONTROL Recherche avancée] . Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite un catalogue avec l’intention de renvoyer les produits contenant « vacances », seuls les produits contenant « vacances » sont renvoyés. Les produits contenant « Vacances » ne sont pas renvoyés. Les exclusions sont traitées de façon similaire. 

## Modification de l’environnement

[Environnements](/help/main/administrating-target/environments.md) vous permettent d’organiser vos sites et environnements de préproduction pour une gestion facile et des rapports distincts.

1. Cliquez sur le lien Environnement .

   ![Lien d’environnement](/help/main/c-recommendations/c-products/assets/environment.png)

1. Sélectionnez l’environnement souhaité.

## Modification de la page de recherche catalogue (filtres et colonnes)

Vous pouvez temporairement modifier les filtres et les colonnes disponibles sur l’ [!UICONTROL Recherche catalogue] pour la session en cours.

### Modification des filtres

Vous pouvez ajouter d’autres facettes de filtrage à la variable [!UICONTROL Recherche catalogue] page.

1. Dans le **[!UICONTROL Filtres]** panneau, cliquez sur **[!UICONTROL Modifier]**.

   ![Lien des filtres de modification](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Sélectionnez les facettes de recherche (ID, nom, message, etc.), puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![Ajouter des filtres](/help/main/c-recommendations/c-products/assets/add-filters.png)

Gardez à l’esprit que les facettes de filtrage supplémentaires ne sont disponibles que dans la session en cours.

### Modifier les colonnes

Vous pouvez temporairement modifier les principales colonnes du [!UICONTROL Recherche catalogue] page.

1. Cliquez sur le bouton **[!UICONTROL Colonnes]** lien.

   ![Options Colonnes](/help/main/c-recommendations/c-products/assets/columns.png)

1. (Conditionnel) Pour réorganiser l’ordre des principales colonnes, effectuez un glisser-déposer des colonnes dans le **[!UICONTROL Principales colonnes]** dans l’ordre souhaité.

1. (Conditionnel) Faites glisser et déposez des éléments du **[!UICONTROL Principales colonnes]** au **[!UICONTROL Colonnes inactives]** (et vice versa), selon vos besoins.

   Vous pouvez également cliquer sur l’icône de suppression ( x ) en regard de la colonne que vous souhaitez déplacer de la section principale à la section inactive.

Gardez à l’esprit que les modifications que vous apportez s’appliquent uniquement à la session en cours.
