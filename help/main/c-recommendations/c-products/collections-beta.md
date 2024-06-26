---
keywords: collection, ciblage
description: Découvrez comment utiliser des collections de produits ou d’éléments dans [!DNL Target Recommendations].
title: Comment utiliser les collections dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: c8bd2bb45ee8ef1a849fd9091554caec77effba0
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 29%

---

# Collections

Une collection est un ensemble de produits ou d’éléments admissibles pour la recommandation. Une collection est définie en spécifiant les conditions qui doivent être remplies par les éléments pour en faire partie.

Généralement, une collection est un ensemble d’éléments similaires ou associés, par exemple une collection de produits uniques. Cependant, vous pouvez regrouper n’importe quel élément dans une catégorie qui convient à votre entreprise, par exemple des produits d’une certaine plage de prix ou d’une certaine couleur ou des éléments susceptibles d’être intéressants dans une zone géographique particulière.

Utilisez les collections pour organiser vos produits dans des groupes logiques. Par exemple, si certains éléments sont disponibles dans une région mais pas dans une autre, vous pouvez créer une collection qui exclut les éléments qui ne sont pas disponibles dans la région du visiteur. Vous pouvez également utiliser les collections pour organiser des éléments saisonniers ou d’autres paramètres fonctionnels qui s’appliquent à votre entreprise.

[Recommandations de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) généré pour chaque critère dans la recommandation utilise également cette collection. Dès lors, seuls les éléments de la collection sont inclus dans la recommandation de sauvegarde. Avec les collections, vous avez la garantie que seuls les produits qu’il y a lieu de présenter à un emplacement donné sont affichés.

Les collections peuvent être recréées ou mises à jour chaque fois qu’un critère s’exécute.

Vous pouvez regrouper vos éléments dans des catalogues, puis créer des recommandations distinctes pour chaque collection.

Les critères d’inclusion vous permettent d’effectuer des opérations similaires aux collections mais ils doivent être configurés chaque fois que vous créez une activité. Les collections vous permettent de créer un ensemble d’éléments une seule fois, puis de l’utiliser chaque fois que cela est approprié sans avoir à le reconfigurer.

Lorsque vous créez ou modifiez une [!DNL Recommendations] , le nom de la collection s’affiche en regard de l’activité [!UICONTROL Criteria] libellé sur le diagramme d’activité.

>[!NOTE]
>
>Les collections ne sont pas appliquées lors de l’utilisation de la variable [!UICONTROL Recently Viewed Items] clé de recommandation.

## Création d’une collection {#task_1256DFF6842141FCAADD9E1428EF7F08}

Créez une collection pour organiser les produits ou le contenu que vous souhaitez afficher dans vos recommandations.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** pour afficher la liste des collections existantes.

   ![Liste des collections](assets/collections-list.png)

   La variable [!UICONTROL Collections] affiche une liste de vos collections existantes. Pour créer des collections, cliquez sur le bouton [!UICONTROL Create Collection] bouton . Vous pouvez également modifier, copier et supprimer des collections existantes en cliquant sur l’icône représentant des points de suspension en regard de la collection souhaitée, puis en cliquant sur l’option de votre choix.

   Le &quot;nombre d’éléments&quot; consigné pour chaque collection sur la variable [!UICONTROL Collections] le mode Liste est le nombre de produits correspondant aux règles de cette collection dans le Recommendations par défaut configuré. [groupe d’hôtes](/help/main/administrating-target/hosts.md) (environnement). Voir [Paramètres](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} pour modifier le groupe d’hôtes par défaut.

1. Cliquez sur **[!UICONTROL Create Collection]**.

   ![Création d’une collection ](/help/main/c-recommendations/c-products/assets/create-collection.png)

1. Saisissez un **[!UICONTROL Name]** pour la collection.

   Vous pouvez également saisir une **[!UICONTROL Description]**.

1. (Conditionnel) Choisissez une [environnement](/help/main/administrating-target/environments.md) de la **[!UICONTROL Environment]** filtrer lors de la création (ou de la mise à jour) d’une collection pour prévisualiser le contenu de cette collection dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

1. Définissez les règles utilisées pour générer la collection.

   Ainsi, votre collection peut-elle être créée sur la base d’une catégorie ou d’un ID de produit, d’une marge bénéficiaire ou de tout autre paramètre de la liste.

   Vous pouvez ajouter des règles pour utiliser plusieurs paramètres pour définir une collection. Plusieurs règles sont unies par un opérateur ET. Pour que la collection soit appliquée, toutes les règles spécifiées doivent être respectées.

1. Cliquez sur **[!UICONTROL Create]**.

## Créez une collection à l’aide de [!UICONTROL Advanced Search]

Vous pouvez également créer des collections à l’aide de [!UICONTROL Advanced Search] sur le [Recherche catalogue](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Enregistrer sous, boîte de dialogue](/help/main/c-recommendations/c-products/assets/save-as.png)

Après avoir créé une recherche avec &quot;id > contient&quot;, par exemple, vous pouvez cliquer sur [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>La variable [!UICONTROL Advanced Search] Cette fonctionnalité n’est pas sensible à la casse. Toutefois, les produits renvoyés au moment de l’envoi sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des collections en fonction des résultats de l’utilisation de la variable [!UICONTROL Advanced Search] . Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite un catalogue avec l’intention de renvoyer les produits contenant « vacances », seuls les produits contenant « vacances » sont renvoyés. Les produits contenant « Vacances » ne sont pas renvoyés.

## Modification, copie ou suppression d’une collection

Cliquez sur le bouton **ellipse** en regard de la collection souhaitée dans la liste, puis cliquez sur l’icône appropriée : modifier, copier ou supprimer.

![Icônes de survol : modification, copie et suppression](/help/main/c-recommendations/c-products/assets/hover-icons-new.png)

Vous pouvez copier une collection existante pour créer une collection en double que vous pourrez ensuite modifier. Vous pouvez ainsi créer une exclusion similaire avec moins d’effort.

Gardez à l’esprit que les collections sont disponibles pour l’ensemble du compte. Veillez à tenir compte de ce point avant de supprimer une collection. Les collections supprimées le sont définitivement.

## Utilisation d’une collection dans une [!DNL Recommendations] activité

1. Créez une collection à l’aide de l’une des méthodes mentionnées ci-dessus.

1. Cliquez sur **[!UICONTROL Activities]** et [créer un Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) activité ou modifier une activité existante.

1. Une fois que vous avez sélectionné un critère et une conception, la variable [!UICONTROL Options] s’affiche à l’emplacement où vous sélectionnez la collection souhaitée.

   ![Choisir l’option de collection](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Conditionnel) Pour modifier un paramètre de collection existant, sur la page **[!UICONTROL Experiences]** (étape 2 du processus assisté en trois parties), cliquez sur un emplacement où vous avez placé les recommandations, puis cliquez sur **[!UICONTROL Change Collection]**, puis sélectionnez la collection souhaitée.

   ![Option Changer la collection](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Vidéo de formation : création de collections et d’exclusions dans Recommendations (7:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)