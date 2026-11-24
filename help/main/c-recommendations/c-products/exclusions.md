---
keywords: exclusions
description: Découvrez comment créer des exclusions dans [!DNL Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs.
title: Comment utiliser les exclusions dans les activités [!UICONTROL Recommendations] ?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
TQID: 'https://experienceleague.adobe.com/6-PWkqq5eXAwyLcGGbSqSZmFdJa85yU3x7FPNEt8-2o'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%
---
# Exclusions {#exclusions}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer et gérer des exclusions dans [!DNL Adobe Target Recommendations] pour empêcher que des produits ou du contenu ne soient recommandés aux visiteurs.

>[!ENDSHADEBOX]

Une exclusion est un sous-ensemble de produits ou de contenu qui ne doit pas être recommandé aux visiteurs. Les exclusions sont disponibles sur l’ensemble du compte. Contrairement aux collections, qui sont sélectionnées pour chaque expérience lorsqu’une activité [!DNL Recommendations] est créée, les exclusions s’appliquent à toutes les activités sur le compte et aucun groupe d’exclusion ne peut être attribué lors de la création de l’activité.

Les exclusions sont généralement utilisées pour :

* Produits qui ont été interrompus.
* Éléments d&#39;un catalogue qui ne sont plus disponibles. Par exemple, lorsque seul le catalogue automne et hiver doit être présent en ligne, aucun article du catalogue été ne peut être acheté.
* Éléments qu’il pourrait être inapproprié de recommander sur la plupart des pages ou des écrans (produits pour adultes, films NC-17, etc.).
* Produits avec des champs de métadonnées incomplets (miniature, prix ou autres métadonnées importantes manquantes).
* Produits qui ne doivent jamais être recommandés, tels qu’un SKU qui existe dans le système mais qui n’est pas un article achetable, ou un faux SKU que l’équipe d’assurance qualité utilise pour simuler un achat sans rien commander.

>[!IMPORTANT]
>
>Les règles d’exclusion sont appliquées globalement à tous les [environnements](/help/main/administrating-target/environments.md).
>
>Pour obtenir des informations détaillées, des exemples et des scénarios d’utilisation sur les règles d’exclusion statiques et dynamiques, consultez la section [Utiliser des règles d’inclusion dynamiques et statiques](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules).

## Créer une exclusion

Les règles d’exclusion sont définies une seule fois, puis s’appliquent à chaque activité [!DNL Recommendations] du compte.

1. Cliquez sur **[!UICONTROL Recommandations]** > **[!UICONTROL Exclusions]** pour afficher la liste des exclusions existantes.

   >[!NOTE]
   >
   >Le « Nombre d’éléments » signalé pour chaque exclusion sur la vue de liste **[!UICONTROL Exclusions]** correspond au nombre de produits correspondant aux règles de cette exclusion dans le [groupe d’hôtes](/help/main/administrating-target/hosts.md) de Recommendations par défaut configuré (environnement). Voir [Planification et implémentation [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank} dans le *Guide du développeur d’Adobe Target* pour plus d’informations sur la modification du groupe d’hôtes par défaut.


1. Cliquez sur l’icône **[!UICONTROL Afficher les filtres]** ( ![Afficher l’icône des filtres](/help/main/assets/icons/Filter.svg) ), puis choisissez l’environnement [souhaité](/help/main/administrating-target/environments.md) dans la liste déroulante **[!UICONTROL Environnement]** pour prévisualiser le contenu de l’exclusion dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

   ![Page des exclusions avec le panneau des filtres ouvert et la liste des environnements](../assets/exclusions_2.png)

1. Cliquez Sur **[!UICONTROL Créer Une Exclusion]**.

   ![Page des exclusions avec le bouton Créer une exclusion](../assets/exclusions_1.png)

1. Saisissez un **[!UICONTROL nom]** d&#39;exclusion. Vous pouvez également saisir une description facultative.

1. Utilisez le créateur de règles pour définir l’exclusion.

   Sélectionnez un paramètre dans la liste **[!UICONTROL Règles]**, sélectionnez un opérateur, puis saisissez une ou plusieurs valeurs pour identifier les produits. Séparez les diverses valeurs par des virgules.

1. Cliquez sur **[!UICONTROL Créer]**.

1. Cliquez sur l’icône Plus d’actions (![Icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) à côté de l’exclusion souhaitée dans la liste, puis cliquez sur l’option appropriée : **[!UICONTROL Modifier]**, **[!UICONTROL Copier]** ou **[!UICONTROL Supprimer]**.

   ![Liste des exclusions avec le menu Autres actions ouvert, affichant Modifier, Copier et Supprimer](../assets/exclusions_3.png)

<!--
## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded.
-->


## Vidéo de formation : créer des collections et des exclusions dans Recommendations (7:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Créer une collection
* Créer une exclusion

>[!VIDEO](https://video.tv.adobe.com/v/27689)
