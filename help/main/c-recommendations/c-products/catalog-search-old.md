---
keywords: recherche catalogue;catalogue;recherche;exclusion;collection;filtre
description: Découvrez comment utiliser la recherche catalogue Recommendations pour localiser des produits ou du contenu, créer des collections ou des exclusions, supprimer des éléments de votre catalogue, etc.
title: Comment utiliser la recherche catalogue Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 22%

---

# Recherche catalogue

La page [!UICONTROL Catalog Search] dans [!DNL Adobe Recommendations] vous aide à localiser les produits ou le contenu de votre catalogue. La tâche la plus simple que vous pouvez effectuer sur cette page consiste à rechercher un élément. En outre, vous pouvez modifier l’environnement, enregistrer les résultats de la recherche dans des collections ou des exclusions, ajouter des facettes de filtre, et modifier des colonnes du tableau, ajouter de nouvelles facettes de recherche, etc.

Les catalogues font référence à l’ensemble de vos produits (entités). Votre catalogue peut contenir de nombreuses collections, ce qui permet d’organiser vos produits en intervalles logiques.

## Accéder à la recherche catalogue

Pour accéder à la page [!UICONTROL Catalog Search], cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

![Page de recherche catalogue](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## Rechercher un élément

Vous pouvez utiliser une recherche simple ou une recherche avancée pour localiser les articles de votre catalogue.

### Exécution d’une recherche simple

1. Saisissez un terme de recherche dans le champ **[!UICONTROL Search Products]** .

1. (Facultatif) Vous pouvez affiner votre recherche en sélectionnant une option de recherche dans le menu d’options qui s’affiche lorsque vous cliquez sur la flèche vers le bas dans le champ de recherche.

   ![image searchproductsmenu](assets/searchproductsmenu.png)

   Les options de recherche disponibles sont les suivantes :

   * ALL : effectue une recherche dans tous les autres critères de recherche, à l’aide de la logique OR.
   * Nom
   * Marque
   * Catégorie
   * ID
   * Message

1. Vous pouvez désormais faire défiler les éléments dans les résultats de recherche pour afficher les miniatures et d’autres informations sur les produits.

   L’illustration suivante présente les résultats pour « vélo » à l’aide de l’option Tout .

   ![Recherche catalogue de vélo](/help/main/c-recommendations/c-products/assets/bike-results.png)

   Le nombre qui s’affiche en regard de « Produits » est le nombre de produits qui correspondent au terme de recherche, sur le total disponible dans l’environnement spécifié.

   Notez que vous pouvez utiliser la fonctionnalité de saisie automatique. Dans l’illustration suivante, la saisie de « vélo » renvoie tous les produits qui contiennent le mot « vélo ».

   ![Saisie automatique de la recherche](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >Lorsque vous effectuez une recherche catalogue sur un attribut personnalisé doté d’une valeur numérique, les résultats traitent l’attribut personnalisé comme une valeur de type chaîne plutôt que comme une valeur numérique.
   >
   >Actuellement, aucune fonctionnalité disponible ne vous permet de modifier le type d’un attribut. Pour apporter une modification, [ouvrez un problème client](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) avec en référence les attributs dont le type doit être passé de chaîne à numérique.

1. Vous pouvez également utiliser des filtres pour trouver le produit souhaité. Dans l’exemple suivant, en développant la facette [!UICONTROL Collections] et en sélectionnant « Outils de vélo », tous les outils de vélo de votre catalogue s’affichent.

   ![Outils pour vélo](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. Vous pouvez effectuer une recherche plus approfondie dans la liste des résultats en saisissant un terme de recherche, par exemple « chaîne ».

   ![Rechercher une chaîne](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### Exécution d’une recherche avancée {#advanced-search}

Vous pouvez utiliser [!UICONTROL Advanced Search] pour affiner davantage vos résultats de recherche ou pour enregistrer vos résultats de recherche en tant que [collection](/help/main/c-recommendations/c-products/collections.md) ou [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Cliquez sur le lien **[!UICONTROL Advanced Search]**.

   ![Page Recherche avancée](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Utilisez les listes déroulantes pour spécifier le paramètre, l’opérateur et les valeurs de votre recherche.

1. (Facultatif) Cliquez sur **[!UICONTROL Add Rule]** pour ajouter une règle de recherche supplémentaire.

   Chaque règle de recherche supplémentaire est associée à l’opérateur AND.

1. Cliquez sur **[!UICONTROL Search]**.

1. (Facultatif) Cliquez sur **[!UICONTROL Save As]**, puis sur **[!UICONTROL Collection]** ou **[!UICONTROL Exclusion]**.

   ![Options Enregistrer en tant que ](/help/main/c-recommendations/c-products/assets/save-as.png)

   Pour plus d’informations, consultez [Création d’une collection ou d’une exclusion basée sur la recherche avancée](#save-as) ci-dessous.

## Afficher les détails d&#39;un article

Vous pouvez afficher les détails d’un élément individuel, notamment son identifiant, son nom, son message, sa catégorie, etc. en affichant ses détails.

1. Cliquez sur un élément dans les résultats de la recherche pour en afficher les détails.

   ![ Détails du produit ](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## Supprimer un élément du catalogue

1. Cliquez sur un élément dans les résultats de la recherche pour en afficher les détails.

1. Cliquez sur **[!UICONTROL Remove from Catalog]**.

1. Confirmez que vous souhaitez supprimer l’élément.

Toutes les informations sur cet élément sont supprimées de l’index du catalogue. L’élément sera inclus dans votre catalogue uniquement s’il est ajouté à nouveau dans un flux de données. Un élément supprimé doit être supprimé séparément des flux.

## Actualiser le catalogue

L’index de votre catalogue est automatiquement créé lorsque vous chargez votre premier flux et actualisé selon le [planning spécifié](/help/main/c-recommendations/c-products/feeds.md#steps).

Le catalogue est automatiquement actualisé lorsque des mises à jour sont reçues via des fichiers de flux, des API ou des mises à jour de mbox. Les mises à jour sont généralement effectuées en une heure. Si des mises à jour sont en cours, l’heure de début de la mise à jour la plus récente s’affiche. Si aucune mise à jour n’est en cours, l’heure de début et de fin de la mise à jour la plus récente s’affiche.

## Création d’une collection ou d’une exclusion à l’aide de la recherche avancée {#save-as}

Vous pouvez créer des [collections](/help/main/c-recommendations/c-products/collections.md) ou [exclusions](/help/main/c-recommendations/c-products/exclusions.md) à l’aide des [!UICONTROL Advanced Search] sur la page [!UICONTROL Catalog Search] ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Effectuez une [recherche avancée](#advanced-search).

1. Cliquez sur **[!UICONTROL Save As]**, puis sur **[!UICONTROL Collection]** ou **[!UICONTROL Exclusion]**.

   ![Options Enregistrer en tant que ](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >La fonctionnalité [!UICONTROL Advanced Search] ne respecte pas la casse ; toutefois, les produits renvoyés au moment de la diffusion sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte de la casse lorsque vous créez des collections ou des exclusions en fonction des résultats à l’aide de la fonctionnalité [!UICONTROL Advanced Search]. Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite un catalogue avec l’intention de renvoyer les produits contenant « vacances », seuls les produits contenant « vacances » sont renvoyés. Les produits contenant « Vacances » ne sont pas renvoyés. Les exclusions sont traitées de façon similaire.

## Modification de l’environnement

[Environnements](/help/main/administrating-target/environments.md) vous permet d’organiser vos sites et vos environnements de préproduction pour une gestion facile et des rapports séparés.

1. Cliquez sur le lien Environnement .

   ![Lien Environnement](/help/main/c-recommendations/c-products/assets/environment.png)

1. Sélectionnez l’environnement souhaité.

## Modification de la page Recherche catalogue (filtres et colonnes)

Vous pouvez modifier temporairement les filtres et colonnes disponibles sur la page [!UICONTROL Catalog Search] pour la session en cours.

### Modification des filtres

Vous pouvez ajouter des facettes de filtre supplémentaires à la page de [!UICONTROL Catalog Search].

1. Dans le panneau **[!UICONTROL Filters]**, cliquez sur **[!UICONTROL Modify]**.

   ![Lien Modifier les filtres](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Sélectionnez les facettes de recherche souhaitées (identifiant, nom, message, etc.), puis cliquez sur **[!UICONTROL Save]**.

   ![Ajouter des filtres](/help/main/c-recommendations/c-products/assets/add-filters.png)

Gardez à l’esprit que les facettes de filtrage supplémentaires ne sont disponibles que dans la session en cours.

### Modifier les colonnes

Vous pouvez temporairement modifier les colonnes actives de la page [!UICONTROL Catalog Search].

1. Cliquez sur le lien **[!UICONTROL Columns]**.

   ![Options des colonnes](/help/main/c-recommendations/c-products/assets/columns.png)

1. (Conditionnel) Pour réorganiser l’ordre des colonnes actives, faites glisser et déposez les colonnes de la section **[!UICONTROL Active Columns]** dans l’ordre souhaité.

1. (Conditionnel) Faites glisser des éléments du **[!UICONTROL Active Columns]** vers le **[!UICONTROL Inactive Columns]** (et vice versa), selon vos besoins.

   Vous pouvez également cliquer sur l’icône de suppression ( x ) en regard de la colonne à déplacer de la section active vers la section inactive.

Gardez à l’esprit que toutes les modifications que vous apportez s’appliquent uniquement à la session en cours.
