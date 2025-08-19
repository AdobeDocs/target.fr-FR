---
keywords: collection, ciblage
description: Découvrez comment utiliser des collections de produits ou d’éléments dans  [!DNL Target Recommendations].
title: Comment utiliser les collections dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 41%

---

# Collections

Une collection est un ensemble de produits ou d’éléments éligibles à une recommandation. Une collection est définie en spécifiant les conditions qui doivent être remplies par les éléments qui doivent en faire partie.

Généralement, une collection est un ensemble d’éléments similaires ou associés, par exemple une collection de produits uniques. Cependant, vous pouvez regrouper n’importe quels éléments dans une catégorie qui est logique pour votre entreprise, tels que les produits d’une certaine plage de prix ou d’une certaine couleur ou les éléments susceptibles d’intéresser une zone géographique particulière.

Utilisez les collections pour organiser vos produits dans des groupes logiques. Par exemple, si certains éléments sont disponibles dans une région, mais pas dans une autre, vous pouvez créer une collection qui exclut les éléments qui ne sont pas disponibles dans la région du visiteur. Vous pouvez également utiliser les collections pour organiser des éléments saisonniers ou d’autres paramètres fonctionnels qui s’appliquent à votre entreprise.

Les [recommandations de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) générées pour chaque critère dans la recommandation utilisent également cette collection. Dès lors, seuls les éléments de la collection sont inclus dans la recommandation de sauvegarde. Avec les collections, vous avez la garantie que seuls les produits qu’il y a lieu de présenter à un emplacement donné sont affichés.

Les collections peuvent être recréées ou mises à jour chaque fois qu’un critère s’exécute.

Vous pouvez regrouper vos éléments dans des catalogues, puis créer des recommandations distinctes pour chaque collection.

Les critères d’inclusion vous permettent d’effectuer des opérations similaires aux collections mais ils doivent être configurés chaque fois que vous créez une activité. Les collections vous permettent de créer un ensemble d’éléments une seule fois et de l’utiliser chaque fois que vous le souhaitez sans avoir à le configurer à nouveau.

Lorsque vous créez ou modifiez une activité de [!DNL Recommendations], le nom de la collection s’affiche en regard du libellé de la [!UICONTROL Criteria] sur le diagramme d’activité.

>[!NOTE]
>
>Les collections ne sont pas appliquées lors de l’utilisation de la clé de recommandation [!UICONTROL Recently Viewed Items].

## Création d’une collection {#task_1256DFF6842141FCAADD9E1428EF7F08}

Créez une collection pour organiser les produits ou le contenu à afficher dans vos recommandations.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** pour afficher la liste des collections existantes.

   ![Liste des collections](assets/collections_list.png)

   La page [!UICONTROL Collections] affiche une liste de vos collections existantes. Pour créer de nouvelles collections, cliquez sur le bouton [!UICONTROL Create Collection] . Vous pouvez également modifier, copier et supprimer des collections existantes en pointant sur la collection souhaitée et en cliquant sur l’icône souhaitée.

   ![Icônes de survol : modifier, copier et supprimer](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   Le « Nombre d’éléments » signalé pour chaque collection dans la vue Liste [!UICONTROL Collections] correspond au nombre de produits correspondant aux règles de cette collection dans les Recommendations par défaut configurées [groupe hôte](/help/main/administrating-target/hosts.md) (environnement). Consultez les [Paramètres](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=fr){target=_blank} pour modifier le groupe d’hôtes par défaut.

1. Cliquez sur **[!UICONTROL Create Collection]**.

1. (Conditionnel) Sélectionnez un environnement à partir du filtre **[!UICONTROL Environment]** lors de la création (ou de la mise à jour) d’une collection pour prévisualiser le contenu de la collection dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

   ![Création d’une collection ](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. Saisissez un **[!UICONTROL Name]** pour la collection.

   Vous pouvez également saisir un **[!UICONTROL Description]** facultatif.

1. Définissez les règles utilisées pour générer la collection.

   Ainsi, votre collection peut-elle être créée sur la base d’une catégorie ou d’un ID de produit, d’une marge bénéficiaire ou de tout autre paramètre de la liste.

   Vous pouvez ajouter des règles pour utiliser plusieurs paramètres pour définir une collection. Plusieurs règles sont reliées par un opérateur AND. Pour que la collection soit appliquée, toutes les règles spécifiées doivent être respectées.

1. Cliquez sur **[!UICONTROL Save]**.

## Création d’une collection à l’aide de la recherche avancée

Vous pouvez également créer des collections à l’aide de la recherche avancée sur la page [Recherche catalogue](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Boîte de dialogue Enregistrer sous](/help/main/c-recommendations/c-products/assets/save-as.png)

Après avoir créé une recherche à l’aide de « id > contains », par exemple, vous pouvez cliquer sur [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>La fonctionnalité de recherche avancée n’est pas sensible à la casse ; cependant, les produits renvoyés lors de la diffusion sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des collections sur la base de résultats obtenus à l’aide de la fonctionnalité de recherche avancée. Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite un catalogue avec l’intention de renvoyer les produits contenant « vacances », seuls les produits contenant « vacances » sont renvoyés. Les produits contenant « Vacances » ne sont pas renvoyés.

## Modifier, copier ou supprimer une collection

Pointez sur la collection souhaitée dans la liste, puis cliquez sur l’icône appropriée : modifier, copier ou supprimer.

![Icônes de pointage pour une collection](/help/main/c-recommendations/c-products/assets/hover-collections.png)

Vous pouvez copier une collection existante pour créer une collection en double que vous pouvez ensuite modifier. Vous pouvez ainsi créer une exclusion similaire avec moins d’effort.

Sachez que les collections sont disponibles sur l’ensemble du compte. Assurez-vous d’en tenir compte avant de supprimer une collection. Les collections supprimées ne peuvent pas être récupérées.

## Utilisation d’une collection dans une activité Recommendations

1. Créez une collection en utilisant l’une des méthodes mentionnées ci-dessus.

1. Cliquez sur **[!UICONTROL Activities]** et [créez une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) ou modifiez une activité existante.

1. Après avoir sélectionné un critère et une conception, la page [!UICONTROL Options] s’affiche lorsque vous sélectionnez la collection souhaitée.

   ![Choisir l’option de collection](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Conditionnel) Pour modifier un paramètre de collection existant, sur la page **[!UICONTROL Experiences]** (étape 2 du workflow en trois parties), cliquez sur un emplacement où vous avez placé des recommandations, cliquez sur **[!UICONTROL Change Collection]**, puis sélectionnez la collection souhaitée.

   ![Option Modifier la collection](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Vidéo de formation : créer des collections et des exclusions dans Recommendations (7:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)
