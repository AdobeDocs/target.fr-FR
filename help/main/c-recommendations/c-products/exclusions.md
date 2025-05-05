---
keywords: exclusions
description: Découvrez comment créer des exclusions dans  [!DNL Target Recommendations]  empêcher que des produits ou du contenu ne soient recommandés aux visiteurs.
title: Comment utiliser les exclusions dans les activités [!UICONTROL Recommendations] ?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 14%

---

# Exclusions

Créez une exclusion dans [!DNL Adobe Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs. Une exclusion est un sous-ensemble de produits ou de contenu qui ne doit pas être recommandé aux visiteurs.

Les exclusions sont disponibles sur l’ensemble du compte. Contrairement aux collections, où vous spécifiez une collection spécifique pour chaque expérience lorsque vous créez une activité de [!UICONTROL Recommendations], les exclusions s’appliquent à toutes les activités sur le compte. Il n’existe aucune option pour affecter un groupe d’exclusion lors de la création de l’activité.

Voici quelques exemples d’exclusions :

* Produits qui ont été interrompus.
* Le catalogue d’automne et d’hiver est désormais le seul catalogue qui devrait être présent en ligne. Les articles du catalogue d&#39;été ne peuvent plus être achetés.
* Éléments qu’il pourrait être inapproprié de recommander sur la plupart des pages ou des écrans (produits pour adultes, films NC-17, etc.).
* Produits avec des champs de métadonnées incomplets (miniature, prix ou autres métadonnées importantes manquantes).
* Produits qui ne devraient jamais être recommandés (il se peut qu’un SKU existe dans le système pour quelque chose, mais il ne s’agit pas d’un article achetable). Ou peut-être s’agit-il d’un faux SKU permettant à l’équipe d’assurance qualité de simuler un achat sans réellement commander quelque chose, et ainsi de suite).

>[!IMPORTANT]
>
>Les règles d’exclusion sont appliquées globalement à tous les [environnements](/help/main/administrating-target/environments.md).
>
>Les règles d’exclusion statiques et dynamiques sont des fonctionnalités puissantes qui peuvent vous aider dans vos efforts de marketing. Pour plus d’informations, des exemples et des scénarios de cas d’utilisation, voir [Utilisation des règles d’inclusion dynamique et statique](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Créer une exclusion

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** pour afficher la liste des exclusions existantes.

   Le « Nombre d’éléments » signalé pour chaque exclusion sur la vue de liste [!UICONTROL Exclusions] correspond au nombre de produits correspondant aux règles de cette exclusion dans le Recommendations [groupe d’hôtes](/help/main/administrating-target/hosts.md) (environnement) par défaut configuré. Consultez [Planification et implémentation [!DNL Recommendations]](https://experienceleague.adobe.com/fr/docs/target-dev/developer/recommendations){target=_blank} dans le *Guide du développeur d’Adobe Target* pour plus d’informations sur la modification du groupe d’hôtes par défaut.

1. (Conditionnel) Cliquez sur l’icône **[!UICONTROL Show Filters]** ( ![icône Afficher les filtres](/help/main/assets/icons/Filter.svg) ), puis choisissez l’[environnement](/help/main/administrating-target/environments.md) souhaité dans la liste déroulante **[!UICONTROL Environment]** lors de la création (ou de la mise à jour) d’une exclusion afin de prévisualiser le contenu de l’exclusion dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

1. Cliquez sur **[!UICONTROL Create Exclusion]**.

1. Saisissez un **[!UICONTROL Name]** d’exclusion et saisissez une description facultative.

1. Utilisez le créateur de règles pour créer les exclusions.

   Sélectionnez un paramètre dans la liste [!UICONTROL Rules], sélectionnez un opérateur, puis saisissez une ou plusieurs valeurs pour identifier les produits. Séparez les diverses valeurs par des virgules.

1. Cliquez sur **[!UICONTROL Create]**.

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## Modifier, copier ou supprimer une exclusion

Cliquez sur l’icône Plus d’actions ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) à côté de l’exclusion souhaitée dans la liste, puis cliquez sur l’icône appropriée : [!UICONTROL Edit], [!UICONTROL Copy] ou [!UICONTROL Delete].

Vous pouvez copier une exclusion existante pour créer une exclusion en double que vous pouvez ensuite modifier. Cette option vous permet de créer une exclusion similaire avec moins d’effort.

N’oubliez pas que les exclusions sont disponibles sur l’ensemble du compte. Veillez à tenir compte de cet avertissement avant de supprimer une exclusion. Les exclusions supprimées ne peuvent pas être récupérées.

## Vidéo de formation : création de collections et d’exclusions dans Recommendations (7:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)
