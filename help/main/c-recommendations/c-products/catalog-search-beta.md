---
keywords: recherche catalogue;catalogue;recherche;exclusion;collection;filtre;recommandations
description: Découvrez comment utiliser le  [!DNL Recommendations] [!UICONTROL Catalog Search] pour localiser des produits ou du contenu, supprimer des éléments de votre catalogue, etc.
title: Comment utiliser le  [!DNL Recommendations] [!UICONTROL Catalog Search] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: 6b0175b1-0eee-498d-8a08-513cf6695114
source-git-commit: 16a7c11e8b9b1a08b1e467519f997d0b05e47529
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 21%

---

# [!UICONTROL Catalog Search]

La page [!UICONTROL Catalog Search] de [!DNL Adobe Recommendations] vous aide à localiser les produits ou le contenu dans votre catalogue. La tâche la plus élémentaire que vous pouvez effectuer sur cette page est de rechercher un élément. En outre, vous pouvez modifier l’environnement, filtrer les facettes, modifier les colonnes du tableau, ajouter de nouvelles facettes de recherche, etc.

Les catalogues font référence à l’ensemble de vos produits (entités). Votre catalogue peut contenir de nombreuses collections, un moyen d’organiser vos produits dans des compartiments logiques.

## Accès [!UICONTROL Catalog Search]

Pour accéder à la page [!UICONTROL Catalog Search], cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

![Page de recherche catalogue](/help/main/c-recommendations/c-products/assets/catalog-search-new.png)

## Exécution d’une recherche simple

1. Saisissez un terme de recherche dans le champ **[!UICONTROL Search In]**.

1. (Facultatif) Vous pouvez affiner votre recherche en sélectionnant une option de recherche dans le menu d’options qui s’affiche lorsque vous cliquez sur la flèche vers le bas dans le champ [!UICONTROL Search In].

   Les options de recherche disponibles sont les suivantes :

   * ID
   * Nom
   * Message

1. Faites défiler les éléments dans les résultats de recherche pour afficher des miniatures et d’autres informations sur les produits.

   >[!NOTE]
   >
   > Lorsque vous effectuez une recherche catalogue sur un attribut personnalisé doté d’une valeur numérique, les résultats traitent l’attribut personnalisé comme une valeur de type chaîne plutôt que comme une valeur numérique.
   >
   >Aucune fonctionnalité actuellement disponible ne permet de modifier le type d’un attribut. Pour apporter une modification, [ouvrez un problème client](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) avec en référence les attributs dont le type doit être passé de chaîne à numérique.

   Vous pouvez également utiliser des filtres pour trouver les produits souhaités. Par exemple, en cliquant sur l’icône **[!UICONTROL Show Filters]** ( ![Icône Afficher les filtres](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) ), en développant la facette [!UICONTROL Collections], puis en sélectionnant une ou plusieurs collections, tous les produits appartenant aux collections sélectionnées de votre catalogue s’affichent.

<!-- ### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.-->

## Affichage des détails d’un élément

Vous pouvez afficher les détails d’un élément individuel, y compris son identifiant, son nom, son message, sa catégorie, etc. en affichant ses détails.

1. Cliquez sur un élément dans les résultats de recherche pour en afficher les détails.

## Supprimer un élément du catalogue

1. Cliquez sur un élément dans les résultats de recherche pour en afficher les détails.

1. Cliquez sur **[!UICONTROL Remove from Catalog]**.

1. Confirmez que vous souhaitez supprimer l’élément.

Toutes les informations sur cet élément sont supprimées de l’index de catalogue. L’élément sera inclus dans votre catalogue uniquement s’il est de nouveau ajouté à un flux de données. Un élément supprimé doit être supprimé séparément des flux.

## Actualiser le catalogue

L’index de votre catalogue est automatiquement créé lorsque vous chargez votre premier flux et actualisé selon la [planification spécifiée](/help/main/c-recommendations/c-products/feeds.md#steps).

Le catalogue est automatiquement actualisé lorsque des mises à jour sont reçues via des fichiers de flux, des API ou des mises à jour de mbox. Les mises à jour sont généralement effectuées dans l’heure. Si des mises à jour sont en cours, l’heure de début de la mise à jour la plus récente s’affiche. Si aucune mise à jour n’est en cours, l’heure de début et de fin de la mise à jour la plus récente s’affiche.

<!-- ## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.-->

## Modification de l’environnement

Les [environnements](/help/main/administrating-target/environments.md) vous permettent d’organiser vos sites et environnements de préproduction pour une gestion facile et des rapports distincts.

1. Cliquez sur l’icône Afficher les filtres ( ![Icône Afficher les filtres](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) ).

1. Sélectionnez l’environnement souhaité dans la liste déroulante **[!UICONTROL Environment]**.

<!-- ## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.-->

## Modifier les colonnes

Vous pouvez temporairement modifier les colonnes actives sur la page [!UICONTROL Catalog Search].

1. Cliquez sur l’icône **[!UICONTROL Customize Table]** ( ![Icône Personnaliser la table](/help/main/c-recommendations/c-products/assets/icon-customize-table.png) ).

1. Sélectionnez ou désélectionnez les colonnes que vous souhaitez afficher ou masquer.

Gardez à l’esprit que les modifications que vous apportez s’appliquent uniquement à la session en cours.
