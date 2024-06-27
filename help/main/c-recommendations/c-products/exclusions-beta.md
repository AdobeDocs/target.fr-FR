---
keywords: exclusions
description: Découvrez comment créer des exclusions dans [!DNL Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs.
title: Comment utiliser les exclusions dans [!UICONTROL Recommendations] Activités ?
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b6eaf89ef71ea3448584dcdadc926c45dba77504
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 26%

---

# Exclusions

Création d’une exclusion dans [!DNL Adobe Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs. Une exclusion est un sous-ensemble de produits ou de contenu qui ne doit pas être recommandé aux visiteurs.

Les exclusions sont disponibles pour l’ensemble du compte. Contrairement aux collections, dans lesquelles vous spécifiez une collection spécifique pour chaque expérience lorsque vous créez une [!UICONTROL Recommendations] , les exclusions s’appliquent à toutes les activités sur l’ensemble du compte. Il n’existe pas d’option permettant d’affecter un groupe d’exclusion lors de la création de l’activité.

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

   Le &quot;nombre d’éléments&quot; signalé pour chaque exclusion sur la variable [!UICONTROL Exclusions] le mode Liste est le nombre de produits correspondant aux règles de cette exclusion dans le Recommendations par défaut configuré. [groupe d’hôtes](/help/main/administrating-target/hosts.md) (environnement). Voir [Planification et implémentation [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank} dans le *Guide du développeur d’Adobe Target* pour plus d’informations sur la modification du groupe d’hôtes par défaut.

1. (Conditionnel) Cliquez sur le bouton [!UICONTROL Filter] , puis choisissez la [environnement](/help/main/administrating-target/environments.md) de la **[!UICONTROL Environment]** liste déroulante lors de la création (ou de la mise à jour) d’une exclusion pour prévisualiser le contenu de l’exclusion dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

   ![Créer une exclusion](/help/main/c-recommendations/c-products/assets/choose-environment.png)

1. Cliquez sur **[!UICONTROL Create Exclusion]**.

   ![Boîte de dialogue Créer une exclusion](/help/main/c-recommendations/c-products/assets/create-exclusion.png)

1. Type d’exclusion **[!UICONTROL Name]** et saisissez une description facultative.

1. Utilisez le créateur de règles pour créer les exclusions.

   Sélectionnez un paramètre dans la liste Règles, sélectionnez un opérateur, puis saisissez une ou plusieurs valeurs pour identifier les produits. Séparez les diverses valeurs par des virgules.

1. Cliquez sur **[!UICONTROL Create]**.

## Création d’une exclusion à l’aide de la recherche avancée

Vous pouvez également créer des exclusions à l’aide de [!UICONTROL Advanced Search] sur le [Recherche catalogue](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Enregistrer sous, boîte de dialogue](/help/main/c-recommendations/c-products/assets/save-as.png)

Après avoir créé une recherche avec &quot;id > contient&quot;, par exemple, vous pouvez cliquer sur [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>La variable [!UICONTROL Advanced Search] Cette fonctionnalité n’est pas sensible à la casse. Toutefois, les produits renvoyés au moment de l’envoi sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des exclusions sur la base de résultats obtenus à l’aide de la fonctionnalité de recherche avancée. Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite une exclusion avec l’intention d’exclure les produits contenant « vacances », seuls les produits contenant « vacances » sont exclus. Les produits contenant « Vacances » ne sont pas exclus.

## Modification, copie ou suppression d’une exclusion

Cliquez sur le bouton **ellipse** en regard de l’exclusion souhaitée dans la liste, puis cliquez sur l’icône appropriée : modifier, copier ou supprimer.

![Options : modification, copie et suppression](/help/main/c-recommendations/c-products/assets/edit-copy-delete.png)

Vous pouvez copier une exclusion existante pour créer une exclusion en double que vous pourrez ensuite modifier. Cette option vous permet de créer une exclusion similaire avec moins d’effort.

Gardez à l’esprit que les exclusions sont disponibles pour l’ensemble du compte. Veillez à tenir compte de cet avertissement avant de supprimer une exclusion. Les exclusions supprimées ne peuvent pas être récupérées.

## Vidéo de formation : création de collections et d’exclusions dans Recommendations (7:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)