---
keywords: collection, ciblage
description: Découvrez comment utiliser des collections de produits ou d'éléments dans [!DNL Target Recommendations].
title: Comment utiliser les collections dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
TQID: 'https://experienceleague.adobe.com/kdjl2cpjaRWYZRqHFqARHvbTaTuu0iAH7ZWbD2Lrs7o'
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
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 8%
---
# Collections {#collections}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer, gérer et utiliser des collections d’éléments dans [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Une collection correspond à l’ensemble des produits ou éléments admissibles pour la recommandation. Une collection est définie par les conditions que les éléments doivent remplir pour en faire partie. Les articles peuvent être regroupés de toute manière logique pour l’entreprise, comme des articles similaires ou apparentés, des produits appartenant à une certaine gamme de prix ou d’une certaine couleur, ou des articles susceptibles d’intéresser une zone géographique particulière.

Les collections organisent les produits en intervalles logiques. Par exemple, si certains éléments sont disponibles dans une région, mais pas dans une autre, une collection peut exclure les éléments qui ne sont pas disponibles dans la région du visiteur. Les collections peuvent également organiser les articles saisonniers ou tout autre paramètre organisationnel qui s&#39;applique à l&#39;entreprise. Les éléments peuvent être regroupés dans des catalogues, puis des recommandations distinctes peuvent être créées pour chaque collection.

Les points suivants décrivent la manière dont les collections interagissent avec le reste de [!DNL Recommendations] :

* [Les recommandations de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) générées pour chaque critère utilisent également la collection, de sorte que seuls les éléments de la collection sont inclus dans la recommandation de sauvegarde. Par conséquent, seuls les produits adaptés à un emplacement s’affichent.
* Les collections peuvent être recréées ou mises à jour chaque fois qu’un critère s’exécute.
* Les règles de collection s’appliquent aux éléments de recommandation générés après l’exécution du critère. Elles affectent uniquement les recommandations d’entité (RE) dans la sortie, et non la clé.
* Les collections ne sont pas appliquées lors de l’utilisation de la clé de recommandation **[!UICONTROL Éléments récemment consultés]**.
* Les critères d’inclusion peuvent produire des résultats similaires, mais ils doivent être configurés chaque fois qu’une activité est créée. Une collection est créée une fois et peut ensuite être réutilisée sans être configurée à nouveau.
* Lorsqu’une activité [!DNL Recommendations] est créée ou modifiée, le nom de la collection s’affiche en regard du libellé **[!UICONTROL Critères]** sur le diagramme d’activité.

## Créer une collection {#task_1256DFF6842141FCAADD9E1428EF7F08}

Les collections sont disponibles sur l’ensemble du compte. Par conséquent, une collection créée une fois peut être sélectionnée dans n’importe quelle activité [!DNL Recommendations]. Les règles sont définies dans la collection. Il n’est donc pas nécessaire de les configurer à nouveau pour chaque activité.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** pour afficher la liste des collections existantes.

   Pour modifier, copier ou supprimer une collection existante, cliquez sur l’icône Plus d’actions ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de la collection, puis cliquez sur l’option souhaitée.

   >[!NOTE]
   >
   >Le « Nombre d’éléments » signalé pour chaque collection sur la vue de liste **[!UICONTROL Collections]** correspond au nombre de produits correspondant aux règles de cette collection dans le [groupe hôte](/help/main/administrating-target/hosts.md) de Recommendations par défaut configuré (environnement). Consultez les [Paramètres](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=fr){target=_blank} pour modifier le groupe d’hôtes par défaut.

1. Cliquez Sur **[!UICONTROL Créer Une Collection]**.

   ![Page de collections avec le bouton Créer une collection](../assets/collection_1.png)

1. Saisissez un **[!UICONTROL Nom]** pour la collection. Une **[!UICONTROL Description]** facultative peut également être saisie.

1. (Conditionnel) Sélectionnez un [environnement](/help/main/administrating-target/environments.md) dans le filtre **[!UICONTROL Environnement]** pour prévisualiser le contenu de la collection dans cet environnement. Par défaut, les résultats du groupe d’hôtes par défaut s’affichent.

1. Définissez les règles utilisées pour générer la collection.

   Une collection peut être créée autour d’un ID de produit ou d’une catégorie, d’une marge ou de tout autre paramètre de la liste. Ajoutez des règles pour utiliser plusieurs paramètres afin de définir une collection. Plusieurs règles sont jointes avec un opérateur AND. Pour que la collection s’applique, toutes les règles spécifiées doivent donc correspondre.

1. Cliquez sur **[!UICONTROL Créer]**.

1. Une fois la collection créée, cliquez sur l’icône Autres actions ( ![icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) et sélectionnez l’option appropriée : **[!UICONTROL Modifier]**, **[!UICONTROL Copier]** ou **[!UICONTROL Supprimer]**.

   ![Liste des collections avec le menu Autres actions ouvert, affichant Modifier, Copier et Supprimer](../assets/collection_2.png)

<!--
## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned.
-->

## Utilisation d’une collection dans une activité

Une collection est sélectionnée pour chaque expérience d’une activité [!DNL Recommendations]. La collection détermine les éléments pouvant apparaître dans les recommandations de cette expérience.

1. [Créer une collection](#task_1256DFF6842141FCAADD9E1428EF7F08).

   ![Créez un écran de collection avec les sections Détails de la collection et Règles](../assets/collection_3.png)

1. Cliquez sur **[!UICONTROL Activités]** et [créez une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) ou modifiez une activité existante.

   ![Page Toutes les activités avec Recommendations sélectionnée dans le menu Créer une activité](../assets/collection_4.png)

1. Après avoir sélectionné un critère et une conception, sélectionnez la collection souhaitée sur la page **[!UICONTROL Options]**.

1. (Conditionnel) Pour modifier la collection d’une activité existante, cliquez sur un emplacement de recommandations sur les pages **[!UICONTROL Expériences]**, cliquez sur **[!UICONTROL Modifier la collection]**, puis sélectionnez la collection souhaitée.
