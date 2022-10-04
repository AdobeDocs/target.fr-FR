---
keywords: exclusions
description: Découvrez comment créer des exclusions dans Adobe [!DNL Target] Recommendations pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs.
title: Comment utiliser les exclusions dans les activités Recommendations ?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 42%

---

# Exclusions

Création d’une exclusion dans [!DNL Adobe Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs. Une exclusion est un sous-ensemble de produits ou de contenu qui ne doit pas être recommandé aux visiteurs.

Les exclusions sont disponibles pour l’ensemble du compte. Contrairement aux collections, dans lesquelles vous spécifiez une collection spécifique pour chaque expérience lorsque vous créez une [!UICONTROL Recommendations] , les exclusions s’appliquent à toutes les activités sur l’ensemble du compte. Il n’existe pas d’option permettant d’affecter un groupe d’exclusion lors de la création de l’activité.

Voici quelques exemples d’utilisation des exclusions :

* Produits abandonnés
* Le catalogue d’automne/d’hiver est désormais le seul catalogue à être présent en ligne. Tout article du catalogue d’été n’est plus disponible à l’achat.
* Éléments qui peuvent être inappropriés à recommander sur la plupart des pages/écrans (produits pour adultes, films NC-17, etc.)
* Produits avec des champs de métadonnées incomplets (miniature, prix ou autres métadonnées importantes manquants)
* Produits qui ne doivent jamais être recommandés (il se peut qu’il existe un SKU dans le système pour quelque chose, mais il ne s’agit pas d’un article à acheter, ou qu’il s’agisse d’un SKU falsifié pour que l’équipe d’assurance qualité simule un achat sans commander réellement quelque chose, etc.)

>[!IMPORTANT]
>
>Les règles d’exclusion sont appliquées globalement à tous les environnements.
>
>Les règles d’exclusion statiques et dynamiques sont des fonctionnalités puissantes qui peuvent vous aider dans vos efforts de marketing. Pour plus d’informations, des exemples et des scénarios de cas d’utilisation, voir [Utilisation des règles d’inclusion dynamique et statique](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Créer une exclusion

1. Cliquez sur **[!UICONTROL Recommandations]** > **[!UICONTROL Exclusions]** pour afficher la liste des exclusions existantes. 

   ![image exclusions_list](assets/exclusions_list.png)

   Le « nombre d’éléments » consigné pour chaque exclusion sur la liste [!UICONTROL Exclusions] est le nombre de produits correspondant aux règles de ladite exclusion, dans le [groupe d’hôtes](/help/main/administrating-target/hosts.md) des Recommandations par défaut (environnement). Voir [Paramètres](https://developer.adobe.com/target/implement/recommendations/){target=_blank} pour modifier le groupe d’hôtes par défaut.

1. Cliquez sur **[!UICONTROL Créer une exclusion]**.

1. (Conditionnel) Sélectionnez un environnement dans le filtre **[!UICONTROL Environnement]** tout en créant (ou en mettant à jour) une exclusion afin de prévisualiser le contenu de l’exclusion dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

   ![Créer une exclusion](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. Saisissez un **[!UICONTROL Nom]** d’exclusion et une description (facultatif).

1. Utilisez le créateur de règles pour créer les exclusions.

   Sélectionnez un paramètre dans la liste Règles, sélectionnez un opérateur, puis saisissez une ou plusieurs valeurs pour identifier les produits. Séparez les diverses valeurs par des virgules.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Création d’une exclusion à l’aide de la recherche avancée

Vous pouvez également créer des exclusions à l’aide de [!UICONTROL Recherche avancée] sur le [Recherche catalogue](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Recherche catalogue] > [!UICONTROL Recherche avancée]).

![Enregistrer sous, boîte de dialogue](/help/main/c-recommendations/c-products/assets/save-as.png)

Après avoir créé une recherche avec « id > contient », par exemple, vous pouvez cliquer sur [!UICONTROL Enregistrer sous] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>Le [!UICONTROL Recherche avancée] La fonctionnalité n’est pas sensible à la casse ; cependant, les produits renvoyés au moment de la livraison sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des exclusions sur la base de résultats obtenus à l’aide de la fonctionnalité de recherche avancée. Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite une exclusion avec l’intention d’exclure les produits contenant « vacances », seuls les produits contenant « vacances » sont exclus. Les produits contenant « Vacances » ne sont pas exclus.

## Modification, copie ou suppression d’une exclusion

Passez la souris sur l’exclusion souhaitée dans la liste, puis cliquez sur l’icône appropriée : modifier, copier ou supprimer.

![Icônes de survol pour une exclusion](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

Vous pouvez copier une exclusion existante pour créer une exclusion en double que vous pourrez ensuite modifier. Vous pouvez ainsi créer une exclusion similaire avec moins d’effort.

Gardez à l’esprit que les exclusions sont disponibles pour l’ensemble du compte. Veillez à tenir compte de ce point avant de supprimer une exclusion. Les exclusions supprimées ne peuvent pas être récupérées.

## Vidéo de formation : Création de collections et d’exclusions dans Recommendations (07:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)
