---
keywords: collection, ciblage
description: Découvrez comment utiliser des collections de produits ou d’éléments dans  [!DNL Target Recommendations].
title: Comment utiliser les collections dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: be9cb6da17f125c127d64ed8f9002987188fdf3d
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 25%

---

# Collections

Une collection est un ensemble de produits ou d’éléments éligibles à une recommandation. Une collection est définie en spécifiant les conditions qui doivent être remplies par les éléments qui doivent en faire partie.

Généralement, une collection est un ensemble d’éléments similaires ou associés, par exemple une collection de produits uniques. Cependant, vous pouvez regrouper n’importe quels éléments dans une catégorie qui est logique pour votre entreprise, tels que les produits d’une certaine plage de prix ou d’une certaine couleur ou les éléments susceptibles d’intéresser une zone géographique particulière.

Utilisez les collections pour organiser vos produits dans des groupes logiques. Par exemple, si certains éléments sont disponibles dans une région, mais pas dans une autre, vous pouvez créer une collection qui exclut les éléments qui ne sont pas disponibles dans la région du visiteur. Vous pouvez également utiliser les collections pour organiser des éléments saisonniers ou d’autres paramètres fonctionnels qui s’appliquent à votre entreprise.

[Recommandations de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) générées pour chaque critère de la recommandation utilisent également cette collection, de sorte que seuls les éléments de la collection soient inclus dans la recommandation de sauvegarde. Avec les collections, vous avez la garantie que seuls les produits qu’il y a lieu de présenter à un emplacement donné sont affichés.

Les collections peuvent être recréées ou mises à jour chaque fois qu’un critère s’exécute.

Vous pouvez regrouper vos éléments dans des catalogues, puis créer des recommandations distinctes pour chaque collection.

Les critères d’inclusion vous permettent d’effectuer des opérations similaires aux collections mais ils doivent être configurés chaque fois que vous créez une activité. Les collections vous permettent de créer un ensemble d’éléments une seule fois, puis de l’utiliser chaque fois que cela est approprié, sans avoir à le configurer à nouveau.

Lorsque vous créez ou modifiez une activité de [!DNL Recommendations], le nom de la collection s’affiche en regard du libellé de la [!UICONTROL Criteria] sur le diagramme d’activité.

>[!NOTE]
>
>* Les règles de collection s’appliquent aux éléments de recommandation générés après l’exécution du critère. Elles affectent uniquement les recommandations d’entité (RE) dans la sortie, et non la clé.
>
>* Les collections ne sont pas appliquées lors de l’utilisation de la clé de recommandation [!UICONTROL Recently Viewed Items].

## Création d’une collection {#task_1256DFF6842141FCAADD9E1428EF7F08}

Créez une collection pour organiser les produits ou le contenu à afficher dans vos recommandations.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** pour afficher la liste des collections existantes.

   La page [!UICONTROL Collections] affiche une liste de vos collections existantes. Pour créer de nouvelles collections, cliquez sur le bouton [!UICONTROL Create Collection] . Vous pouvez également modifier, copier et supprimer des collections existantes en cliquant sur l’icône Plus d’actions ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) à côté de la collection souhaitée, puis en cliquant sur l’option souhaitée.

   Le « Nombre d’éléments » signalé pour chaque collection dans la vue Liste [!UICONTROL Collections] correspond au nombre de produits correspondant aux règles de cette collection dans les Recommendations par défaut configurées [groupe hôte](/help/main/administrating-target/hosts.md) (environnement). Voir [Paramètres](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=fr){target=_blank} pour modifier le groupe d’hôtes par défaut.

1. Cliquez sur **[!UICONTROL Create Collection]**.

1. Saisissez un **[!UICONTROL Name]** pour la collection.

   Vous pouvez également saisir un **[!UICONTROL Description]** facultatif.

1. (Conditionnel) Choisissez un [environnement](/help/main/administrating-target/environments.md) à partir du filtre **[!UICONTROL Environment]** lors de la création (ou de la mise à jour) d’une collection pour prévisualiser le contenu de la collection dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

1. Définissez les règles utilisées pour générer la collection.

   Ainsi, votre collection peut-elle être créée sur la base d’une catégorie ou d’un ID de produit, d’une marge bénéficiaire ou de tout autre paramètre de la liste.

   Vous pouvez ajouter des règles pour utiliser plusieurs paramètres pour définir une collection. Plusieurs règles sont reliées par un opérateur AND. Pour que la collection soit appliquée, toutes les règles spécifiées doivent être respectées.

1. Cliquez sur **[!UICONTROL Create]**.

<!-- ## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. -->

## Modifier, copier ou supprimer une collection

Cliquez sur l’icône ( ![Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de la collection souhaitée dans la liste, puis cliquez sur l’icône appropriée : [!UICONTROL Edit], [!UICONTROL Copy] ou [!DNL Delete].

Vous pouvez copier une collection existante pour créer une collection en double que vous pouvez ensuite modifier. Vous pouvez ainsi créer une collection similaire avec moins d’effort.

Sachez que les collections sont disponibles sur l’ensemble du compte. Assurez-vous d’en tenir compte avant de supprimer une collection. Les collections supprimées ne peuvent pas être récupérées.

## Utilisation d’une collection dans une activité [!DNL Recommendations]

1. Créez une collection en utilisant l’une des méthodes mentionnées ci-dessus.

1. Cliquez sur **[!UICONTROL Activities]** et [créez une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) ou modifiez une activité existante.

1. Après avoir sélectionné un critère et une conception, la page [!UICONTROL Options] s’affiche à l’emplacement où vous sélectionnez la collection souhaitée.

1. (Conditionnel) Pour modifier un paramètre de collection existant, sur la page **[!UICONTROL Experiences]** (étape 1 du workflow en trois parties), cliquez sur un emplacement où vous avez placé des recommandations, cliquez sur **[!UICONTROL Change Collection]**, puis sélectionnez la collection souhaitée.
