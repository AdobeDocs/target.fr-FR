---
keywords: exclusions
description: Créez une liste d’exclusions dans Adobe Target pour empêcher des éléments d’être recommandés.
title: Exclusions dans Adobe Target
feature: entities
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 99%

---


# Exclusions{#exclusions}

Créez une liste d’exclusion pour empêcher des éléments d’être recommandés.

>[!IMPORTANT]
>
>Les règles d’exclusion statiques et dynamiques sont des fonctionnalités puissantes qui peuvent vous aider dans vos efforts de marketing. Pour plus d’informations, des exemples et des scénarios de cas d’utilisation, voir [Utilisation des règles d’inclusion dynamique et statique](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

**Pour créer une exclusion :**

1. Cliquez sur **[!UICONTROL Recommandations]** > **[!UICONTROL Exclusions]** pour afficher la liste des exclusions existantes. 

   ![](assets/exclusions_list.png)

   Le « nombre d’éléments » consigné pour chaque exclusion sur la liste [!UICONTROL Exclusions] est le nombre de produits correspondant aux règles de ladite exclusion, dans le [groupe d’hôtes](/help/administrating-target/hosts.md) des Recommandations par défaut (environnement). Voir [Paramètres](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) pour modifier le groupe d’hôtes par défaut.

1. Cliquez sur **[!UICONTROL Créer une exclusion]**.

1. (Conditionnel) Sélectionnez un environnement dans le filtre **[!UICONTROL Environnement]** tout en créant (ou en mettant à jour) une exclusion afin de prévisualiser le contenu de l’exclusion dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

   ![Créer une exclusion](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. Saisissez un **[!UICONTROL Nom]** d’exclusion et une description (facultatif).

1. Utilisez le créateur de règles pour créer les exclusions.

   Sélectionnez un paramètre dans la liste Règles, sélectionnez un opérateur, puis saisissez une ou plusieurs valeurs pour identifier les produits. Séparez les diverses valeurs par des virgules.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Création d’une exclusion à l’aide de la recherche avancée

Vous pouvez également créer des exclusions à l’aide de la fonctionnalité de recherche avancée de la page de recherche catalogue ([!UICONTROL Recommandations] > [!UICONTROL Recherche catalogue] > [!UICONTROL Recherche avancée]).

![Enregistrer sous](/help/c-recommendations/c-products/assets/save-as-dialog.png)

Après avoir créé une recherche avec « id > contient », par exemple, vous pouvez cliquer sur [!UICONTROL Enregistrer sous] > [!UICONTROL Exclusion]. Pour plus d’informations, voir [Recherche catalogue](/help/c-recommendations/c-products/catalog-search.md).

>[!IMPORTANT]
>
>La fonctionnalité de recherche avancée n’est pas sensible à la casse ; cependant, les produits renvoyés lors de la diffusion sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des exclusions sur la base de résultats obtenus à l’aide de la fonctionnalité de recherche avancée. Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite une exclusion avec l’intention d’exclure les produits contenant « vacances », seuls les produits contenant « vacances » sont exclus. Les produits contenant « Vacances » ne sont pas exclus.

## Vidéo de formation : Créer des collections et des exclusions dans Recommendations (7:05) ![Badge de didacticiel](/help/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)