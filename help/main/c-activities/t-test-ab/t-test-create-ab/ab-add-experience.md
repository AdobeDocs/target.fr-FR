---
keywords: ciblage;expérience;ajouter une expérience;ajout d’une expérience
description: Utilisez le [!UICONTROL Visual Experience Composer] (VEC) pour ajouter des expériences aux activités .
title: Comment ajouter des expériences dans une activité A/B ?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 28%

---

# Ajout d’une expérience

Le [!DNL Adobe Target] d’[!UICONTROL Visual Experience Composer] (VEC) fournit une interface visuelle permettant d’ajouter et de modifier des expériences sur votre page.

Pour plus d’informations sur les expériences, voir [Expériences](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Dans la page **[!UICONTROL Experiences]** du compositeur d’expérience visuelle, cliquez sur l’icône [!UICONTROL Add] ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ) en haut du volet [!UICONTROL Experiences].

   Le compositeur d’expérience visuelle affiche deux onglets sur le côté gauche après la création d’une activité : Expérience A et Expérience B. L’expérience A est l’expérience de contrôle. Vous pouvez ajouter plusieurs expériences au test.

1. Sélectionnez les éléments à modifier et apportez les modifications souhaitées.

   Lorsque vous passez la souris sur les éléments de la page, les éléments sont mis en surbrillance. Tout élément mis en surbrillance peut être modifié à l’aide du compositeur d’expérience visuelle.

   Si vous avez créé une requête [!DNL Target] sur la page à l’aide de [!DNL Target Classic] (anciennement [!DNL Test&Target]), cette requête [!DNL Target] s’affiche sous la forme d’un élément indiquant le nom de la requête et peut être modifiée comme tout autre élément.

   Pour obtenir la liste des actions pouvant être exécutées sur un élément de la page affichée pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si vous publiez une image provenant d’une source autre que votre page principale (une image hébergée sur `akamai.net` et publiée sur `example.com`, par exemple), cette image ne s’affiche pas dans la miniature de la page dans le diagramme de flux.

1. Cliquez sur **[!UICONTROL Next]** lorsque vous avez terminé de concevoir l’expérience.

## Renommer l’expérience

1. Cliquez sur l’icône **[!UICONTROL Rename Experience]** ( ![icône Renommer](/help/main/assets/icons/Rename.svg) ) en regard d’une expérience pour lui donner un nouveau nom.

2. Indiquez un nouveau nom, puis cliquez sur **[!UICONTROL Save]**.

   Lorsque vous nommez ou renommez une expérience, les caractères suivants ne sont pas autorisés :

   | Caractère | Description |
   |--- |--- |
   | / | Barre oblique |
   | ? | Point d’interrogation |
   | # | Croisillon |
   | : | Deux-points |
   | = | Égal |
   | + | Plus |
   | - | Moins |
   | @ | Arobase |

## Rediriger vers l’URL

1. Dans le volet de **[!UICONTROL Experiences]**, cliquez sur l’icône **[!UICONTROL More]** ( ![icône Plus](/help/main/assets/icons/MoreSmall.svg) ) en regard d’une expérience, puis cliquez sur **[!UICONTROL Redirect to URL]**.

   Pour plus d’informations, voir [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

1. Indiquez l’URL vers laquelle vous souhaitez rediriger l’expérience.

1. (Conditionnel) Cochez la case **[!UICONTROL Include Current Query Parameters]** .

1. Cliquez sur **[!UICONTROL Save]**.

## Duplication d’une expérience

Vous pouvez copier une expérience dans une [!UICONTROL A/B Test] afin d’y apporter des modifications mineures sans avoir à recréer l’expérience.

1. Dans le volet de **[!UICONTROL Experiences]**, cliquez sur l’icône **[!UICONTROL More]** ( ![icône Plus](/help/main/assets/icons/MoreSmall.svg) ) en regard d’une expérience, puis cliquez sur **[!UICONTROL Duplicate]**.

## Suppression d’une expérience

1. Dans le volet de **[!UICONTROL Experiences]**, cliquez sur l’icône **[!UICONTROL More]** ( ![icône Plus](/help/main/assets/icons/MoreSmall.svg) ) à côté d’une expérience, cliquez sur **[!UICONTROL Delete]**, puis sur **[!UICONTROL Delete]** pour confirmer l’action.
