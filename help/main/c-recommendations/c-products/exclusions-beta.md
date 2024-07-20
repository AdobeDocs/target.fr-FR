---
keywords: exclusions
description: Découvrez comment créer des exclusions dans  [!DNL Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs.
title: Comment utiliser les exclusions dans les activités [!UICONTROL Recommendations] ?
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 31cf23a52c331eabad0e5f6423eeeca84df87625
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 18%

---

# Exclusions

Créez une exclusion dans [!DNL Adobe Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs. Une exclusion est un sous-ensemble de produits ou de contenu qui ne doit pas être recommandé aux visiteurs.

Les exclusions sont disponibles pour l’ensemble du compte. Contrairement aux collections, où vous spécifiez une collection spécifique pour chaque expérience lorsque vous créez une activité [!UICONTROL Recommendations], les exclusions s’appliquent à toutes les activités du compte. Il n’existe pas d’option permettant d’affecter un groupe d’exclusion lors de la création de l’activité.

Voici quelques exemples d’utilisation des exclusions :

* Produits qui ont été abandonnés.
* Le catalogue d’automne et d’hiver est désormais le seul catalogue qui devrait être présent en ligne. Tout article du catalogue d’été n’est plus disponible à l’achat.
* Éléments qui peuvent être inappropriés à recommander sur la plupart des pages ou écrans (produits pour adultes, films NC-17, etc.).
* Produits avec des champs de métadonnées incomplets (miniature, prix ou autres métadonnées importantes manquants).
* Produits qui ne doivent jamais être recommandés (il existe peut-être un SKU dans le système pour quelque chose, mais ce n’est pas un article achetable. Ou peut-être s’agit-il d’un faux SKU pour l’équipe d’assurance qualité afin de simuler un achat sans vraiment commander quelque chose, etc.).

>[!IMPORTANT]
>
>Les règles d’exclusion sont appliquées globalement à tous les [environnements](/help/main/administrating-target/environments.md).
>
>Les règles d’exclusion statiques et dynamiques sont des fonctionnalités puissantes qui peuvent vous aider dans vos efforts de marketing. Pour plus d’informations, des exemples et des scénarios de cas d’utilisation, voir [Utilisation des règles d’inclusion dynamique et statique](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Créer une exclusion

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** pour afficher la liste des exclusions existantes.

   ![image exclusions_list](assets/exclusions-list.png)

   Le &quot;nombre d’éléments&quot; consigné pour chaque exclusion sur la liste [!UICONTROL Exclusions] est le nombre de produits correspondant aux règles de cette exclusion dans le [groupe d’hôtes](/help/main/administrating-target/hosts.md) par défaut configuré de Recommendations (environnement). Pour plus d’informations sur la modification du groupe d’hôtes par défaut, voir [Planification et implémentation [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank} dans le *Guide du développeur Adobe Target*.

1. (Conditionnel) Cliquez sur l’icône [!UICONTROL Filter], puis sélectionnez l’ [environnement](/help/main/administrating-target/environments.md) souhaité dans la liste déroulante **[!UICONTROL Environment]** lors de la création (ou de la mise à jour) d’une exclusion pour prévisualiser le contenu de l’exclusion dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

   ![Créer une exclusion](/help/main/c-recommendations/c-products/assets/choose-environment.png)

1. Cliquez sur **[!UICONTROL Create Exclusion]**.

   ![Boîte de dialogue Créer une exclusion](/help/main/c-recommendations/c-products/assets/create-exclusion.png)

1. Saisissez une exclusion **[!UICONTROL Name]** et une description facultative.

1. Utilisez le créateur de règles pour créer les exclusions.

   Sélectionnez un paramètre dans la liste Règles, sélectionnez un opérateur, puis saisissez une ou plusieurs valeurs pour identifier les produits. Séparez les diverses valeurs par des virgules.

1. Cliquez sur **[!UICONTROL Create]**.

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## Modification, copie ou suppression d’une exclusion

Cliquez sur l’icône **ellipse** en regard de l’exclusion souhaitée dans la liste, puis cliquez sur l’icône appropriée : modification, copie ou suppression.

![Options : modification, copie et suppression](/help/main/c-recommendations/c-products/assets/edit-copy-delete.png)

Vous pouvez copier une exclusion existante pour créer une exclusion en double que vous pourrez ensuite modifier. Cette option vous permet de créer une exclusion similaire avec moins d’effort.

Gardez à l’esprit que les exclusions sont disponibles pour l’ensemble du compte. Veillez à tenir compte de cet avertissement avant de supprimer une exclusion. Les exclusions supprimées ne peuvent pas être récupérées.

## Vidéo de formation : création de collections et d’exclusions dans Recommendations (7:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)