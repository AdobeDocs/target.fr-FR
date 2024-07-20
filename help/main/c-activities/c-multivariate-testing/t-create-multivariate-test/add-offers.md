---
keywords: mvt;test multivarié;offres;combinaisons
description: Découvrez comment utiliser le [!UICONTROL Visual Experience Composer] (VEC) dans Adobe [!DNL Target]  pour créer les offres que vous souhaitez inclure dans votre [!UICONTROL Multivariate Test] (MVT).
title: Comment créer des combinaisons dans un [!UICONTROL Multivariate Test] (MVT) ?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 56%

---

# Création de combinaisons

Utilisez le [!UICONTROL Visual Experience Composer] (VEC) dans [!DNL Adobe Target] pour créer les offres que vous souhaitez inclure dans votre [!UICONTROL Multivariate Test] (MVT).

Pour plus d’informations sur l’utilisation du VEC pour créer et modifier des offres, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Vous pouvez cliquer sur **[!UICONTROL Expand Selection]** lors de la sélection d’objets sur la page pour sélectionner l’élément parent en plus de l’élément sélectionné d’origine. Lorsque vous sélectionnez un élément parent, tous les enfants de cet élément sont automatiquement sélectionnés. Vous pouvez étendre plusieurs fois la sélection.
>
>Vous pouvez également utiliser le [chemin DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) pour parcourir les éléments.

## Offres d’image {#section_A48333211DB149ED926AE467D0032914}

Testez plusieurs offres d’images dans un emplacement afin de déterminer l’image qui remporte le plus de succès.

1. Cliquez sur une image de la page, puis sélectionnez **[!UICONTROL Change Image]**.

   ![Option de modification d’image](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changeimage.png)

1. Sélectionnez toutes les images à inclure dans le test, puis cliquez sur **[!UICONTROL Save]**.

   ![Boîte de dialogue Sélection du contenu utilisé pour ajouter des images](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/addimage.png)

Chaque image devient une expérience distincte à cet emplacement.

## Offres HTML {#section_DF016101AFA9412C9B99862C23DE77B1}

Testez plusieurs offres Texte/HTML dans un emplacement afin de déterminer l’offre qui remporte le plus de succès.

1. Cliquez sur une offre Texte/HTML sur votre page, puis cliquez sur **[!UICONTROL Change Text/HTML]**.

   ![Modification du texte/HTML](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changehtml.png)

1. Cliquez sur **[!UICONTROL Add Text/HTML Offer]**, nommez l&#39;offre, puis saisissez ou collez le code de l&#39;offre Texte/HTML.

   ![Modification des offres](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Répétez cette opération pour toute offre Texte/HTML supplémentaire que vous souhaitez inclure.

1. Cliquez sur **[!UICONTROL Save]**.

Chaque offre Texte/HTML devient une expérience distincte à cet emplacement.

## Bonnes pratiques {#section_2E98C23D2F1A460FA732A31799CE6291}

* N’incluez pas plus d’emplacements que nécessaire pour le test. Chaque expérience que vous incluez dans le test augmente de manière significative le volume de trafic et le temps requis pour obtenir des résultats acceptables. Par exemple, en présence d’éléments de page comportant trois offres chacun, vous obtenez neuf combinaisons possibles (3x3). Trois éléments, dont deux contiennent trois offres possibles et un deux offres, fournissent 18 options (3x3x2). Les nombres augmentent substantiellement avec chaque élément et offre supplémentaires.
* Lors de la création de tests multivariés, vous pouvez exclure plus de 10 % des expériences du test, à condition d’utiliser les rapports hors ligne pour l’analyse.
* Tirez parti des fonctionnalités d’aperçu pour éviter des combinaisons non souhaitables de contenu. Par exemple, vous pourriez avoir deux images qui offrent des remises différentes sur le même élément ou service. L’affichage de ces images sur la même page n’est pas logique et est susceptible de prêter à confusion.
* Utilisez l’ [ estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) pour vous assurer que votre test est conçu pour le volume de trafic que votre page reçoit. Assurez-vous que l’estimateur de trafic donne le feu vert à votre configuration de test afin que vous puissiez obtenir les résultats souhaités.
* Vous devez avoir au moins trois éléments à tester. Si vous en avez moins, exécutez une série de tests A/B.
* Les alternatives de chaque élément doivent être significativement différentes les unes des autres.
* Bien que cela ne soit pas requis, la bonne pratique consiste à ce que chaque élément ait le même nombre d’alternatives.
