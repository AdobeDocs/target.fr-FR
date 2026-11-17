---
keywords: mvt;test multivarié;offres;combinaisons
description: Découvrez comment utiliser le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans Adobe [!DNL Target] pour créer les offres à inclure dans votre [!UICONTROL test multivarié] (MVT).
title: Comment créer des combinaisons dans un [!UICONTROL test multivarié] (MVT) ?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
TQID: 'https://experienceleague.adobe.com/3vxuP07ZViE1etmmvBdYVHIOrtZqRZfL3nE5RMHo9rU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 29%
---
# Création de combinaisons {#create-combinations}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer l’image et les offres HTML qui composent les combinaisons d’un **[!UICONTROL test multivarié]**.

>[!ENDSHADEBOX]

Dans un **[!UICONTROL test multivarié]** (MVT), chaque emplacement contient plusieurs offres et chaque combinaison d’offres entre les emplacements est une expérience. Utilisez le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) dans [!DNL Adobe Target] pour créer les offres à inclure dans votre test.

Pour plus d’informations sur l’utilisation du VEC pour créer et modifier des offres, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Vous pouvez cliquer sur **[!UICONTROL Développer la sélection]** lors de la sélection d&#39;objets sur la page pour sélectionner l&#39;élément parent en plus de l&#39;élément sélectionné à l&#39;origine. Lorsque vous sélectionnez un élément parent, tous les enfants de cet élément sont automatiquement sélectionnés. Vous pouvez étendre plusieurs fois la sélection.
>
>Vous pouvez également utiliser le [chemin DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) pour parcourir les éléments.

## Offres d’image {#image-offers}

Testez plusieurs offres d’image dans un emplacement afin de déterminer l’image qui remporte le plus de succès.

1. Cliquez sur une image de votre page, puis sélectionnez **[!UICONTROL Modifier l&#39;offre d&#39;image]**.

   ![Menu Modifier l’offre d’image](../assets/multivariate-1.png)

1. Dans la boîte de dialogue **[!UICONTROL Offre d&#39;image]**, sélectionnez toutes les images à inclure dans le test, puis cliquez sur **[!UICONTROL Ajouter]**.

   ![Menu Modifier l’offre d’image](../assets/multivariate-3.png)

Chaque image devient une expérience distincte à cet emplacement.

## Offres HTML {#html-offers}

Testez plusieurs offres HTML dans un emplacement afin de déterminer l’offre qui remporte le plus de succès.

1. Cliquez sur une offre HTML sur votre page, puis sur **[!UICONTROL Modifier l’offre HTML]**.

   ![Modifier le menu d’offres d’HTML](../assets/multivariate-2.png)

1. Choisissez votre offre HTML et cliquez sur **[!UICONTROL Créer une offre]** puis sur **[!UICONTROL Offre HTML]**.

   ![Modifier le menu d’offres d’HTML](../assets/multivariate-4.png)

1. Nommez l&#39;offre, saisissez ou collez le code de l&#39;offre HTML, puis cliquez sur **[!UICONTROL Créer]**.

   Répétez l’opération pour toutes les offres HTML supplémentaires que vous souhaitez inclure.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Chaque offre HTML devient une expérience distincte à cet emplacement.

Pour obtenir des recommandations sur le nombre de combinaisons à inclure et sur la manière de les examiner avant de lancer le test, consultez [Bonnes pratiques en matière de test multivarié](/help/main/c-activities/c-multivariate-testing/best-practices.md#create).
