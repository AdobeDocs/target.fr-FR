---
keywords: collection, ciblage
description: Découvrez comment utiliser des collections de produits ou d’éléments dans [!DNL Target Recommendations].
title: Comment utiliser les collections dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: c8bd2bb45ee8ef1a849fd9091554caec77effba0
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 40%

---

# Collections

Une collection est un ensemble de produits ou d’éléments admissibles pour la recommandation. Une collection est définie en spécifiant les conditions qui doivent être remplies par les éléments pour en faire partie.

Généralement, une collection est un ensemble d’éléments similaires ou associés, par exemple une collection de produits uniques. Cependant, vous pouvez regrouper n’importe quel élément dans une catégorie qui convient à votre entreprise, par exemple des produits d’une certaine plage de prix ou d’une certaine couleur ou des éléments susceptibles d’être intéressants dans une zone géographique particulière.

Utilisez les collections pour organiser vos produits dans des groupes logiques. Par exemple, si certains éléments sont disponibles dans une région mais pas dans une autre, vous pouvez créer une collection qui exclut les éléments qui ne sont pas disponibles dans la région du visiteur. Vous pouvez également utiliser les collections pour organiser des éléments saisonniers ou d’autres paramètres fonctionnels qui s’appliquent à votre entreprise.

Les [recommandations de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) générées pour chaque critère dans la recommandation utilisent également cette collection. Dès lors, seuls les éléments de la collection sont inclus dans la recommandation de sauvegarde. Avec les collections, vous avez la garantie que seuls les produits qu’il y a lieu de présenter à un emplacement donné sont affichés.

Les collections peuvent être recréées ou mises à jour chaque fois qu’un critère s’exécute.

Vous pouvez regrouper vos éléments dans des catalogues, puis créer des recommandations distinctes pour chaque collection.

Les critères d’inclusion vous permettent d’effectuer des opérations similaires aux collections mais ils doivent être configurés chaque fois que vous créez une activité. Les collections vous permettent de créer un ensemble d’éléments une seule fois et de l’utiliser chaque fois que vous le souhaitez sans avoir à le configurer à nouveau.

Lorsque vous créez ou modifiez une activité [!DNL Recommendations], le nom de la collection s’affiche en regard du libellé [!UICONTROL Criteria] sur le diagramme d’activités.

>[!NOTE]
>
>Les collections ne sont pas appliquées lors de l’utilisation de la clé de recommandation [!UICONTROL Recently Viewed Items].

## Création d’une collection {#task_1256DFF6842141FCAADD9E1428EF7F08}

Créez une collection pour organiser les produits ou le contenu que vous souhaitez afficher dans vos recommandations.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** pour afficher la liste des collections existantes.

   ![Liste des collections](assets/collections_list.png)

   La page [!UICONTROL Collections] affiche une liste de vos collections existantes. Pour créer des collections, cliquez sur le bouton [!UICONTROL Create Collection] . Vous pouvez également modifier, copier et supprimer des collections existantes en faisant glisser le curseur sur la collection souhaitée et en cliquant sur l’icône souhaitée.

   ![Icônes de survol : modification, copie et suppression](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   Le &quot;nombre d’éléments&quot; consigné pour chaque collection sur la liste [!UICONTROL Collections] est le nombre de produits correspondant aux règles de cette collection dans le [groupe d’hôtes](/help/main/administrating-target/hosts.md) par défaut configuré de Recommendations (environnement). Voir [Paramètres](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} pour modifier le groupe d’hôtes par défaut.

1. Cliquez sur **[!UICONTROL Create Collection]**.

1. (Conditionnel) Sélectionnez un environnement dans le filtre **[!UICONTROL Environment]** lors de la création (ou de la mise à jour) d’une collection pour prévisualiser le contenu de la collection dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

   ![Création d’une collection ](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. Saisissez un **[!UICONTROL Name]** pour la collection.

   Vous pouvez également saisir un **[!UICONTROL Description]** facultatif.

1. Définissez les règles utilisées pour générer la collection.

   Ainsi, votre collection peut-elle être créée sur la base d’une catégorie ou d’un ID de produit, d’une marge bénéficiaire ou de tout autre paramètre de la liste.

   Vous pouvez ajouter des règles pour utiliser plusieurs paramètres pour définir une collection. Plusieurs règles sont unies par un opérateur ET. Pour que la collection soit appliquée, toutes les règles spécifiées doivent être respectées.

1. Cliquez sur **[!UICONTROL Save]**.

## Création d’une collection à l’aide de la recherche avancée

Vous pouvez également créer des collections à l’aide de la fonctionnalité de recherche avancée de la page [Recherche catalogue](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Enregistrer comme boîte de dialogue](/help/main/c-recommendations/c-products/assets/save-as.png)

Après avoir créé une recherche à l’aide de &quot;id > contient&quot;, par exemple, vous pouvez cliquer sur [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>La fonctionnalité de recherche avancée n’est pas sensible à la casse ; cependant, les produits renvoyés lors de la diffusion sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des collections sur la base de résultats obtenus à l’aide de la fonctionnalité de recherche avancée. Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite un catalogue avec l’intention de renvoyer les produits contenant « vacances », seuls les produits contenant « vacances » sont renvoyés. Les produits contenant « Vacances » ne sont pas renvoyés.

## Modification, copie ou suppression d’une collection

Passez la souris sur la collection souhaitée dans la liste, puis cliquez sur l’icône appropriée : modifier, copier ou supprimer.

![Icônes de survol pour une collection](/help/main/c-recommendations/c-products/assets/hover-collections.png)

Vous pouvez copier une collection existante pour créer une collection en double que vous pourrez ensuite modifier. Vous pouvez ainsi créer une exclusion similaire avec moins d’effort.

Gardez à l’esprit que les collections sont disponibles pour l’ensemble du compte. Veillez à tenir compte de ce point avant de supprimer une collection. Les collections supprimées le sont définitivement.

## Utilisation d’une collection dans une activité Recommendations

1. Créez une collection à l’aide de l’une des méthodes mentionnées ci-dessus.

1. Cliquez sur **[!UICONTROL Activities]** et [créer une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) ou modifiez une activité existante.

1. Une fois que vous avez sélectionné un critère et une conception, la page [!UICONTROL Options] s’affiche lorsque vous sélectionnez la collection souhaitée.

   ![Choisir l’option de collection](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Conditionnel) Pour modifier un paramètre de collection existant, sur la page **[!UICONTROL Experiences]** (étape 2 du processus assisté en trois parties), cliquez sur un emplacement où vous avez placé les recommandations, cliquez sur **[!UICONTROL Change Collection]**, puis sélectionnez la collection souhaitée.

   ![Option de modification de la collection](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Vidéo de formation : création de collections et d’exclusions dans Recommendations (7:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)
