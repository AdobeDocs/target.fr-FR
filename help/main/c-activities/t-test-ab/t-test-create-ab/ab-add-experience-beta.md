---
keywords: ciblage;expérience;ajouter une expérience;ajout d’une expérience
description: Principal utilisant le [!UICONTROL Visual Experience Composer] (VEC) pour ajouter des expériences aux activités.
title: Comment ajouter des expériences dans une activité A/B ?
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 6e9d18b8347d8ae68be699640c4cde91bdec762c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 28%

---

# Ajout d’une expérience

Le [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) fournit une interface visuelle pour l’ajout et la modification des expériences sur votre page.

Pour plus d’informations sur les expériences, voir [Expériences](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Sur la page **[!UICONTROL Experiences]** du VEC, cliquez sur l’icône [!UICONTROL Add] ( ![ icône Ajouter ](/help/main/assets/icons/Add.svg) ) en haut du volet [!UICONTROL Experiences].

   Le VEC affiche deux onglets sur le côté gauche après la création d’une activité : Expérience A et Expérience B. L’Expérience A est l’expérience de contrôle. Vous pouvez ajouter plusieurs expériences au test.

1. Sélectionnez les éléments à modifier et apportez les modifications souhaitées.

   Lorsque vous placez le pointeur de la souris sur les éléments de votre page, ceux-ci sont mis en surbrillance. Tout élément en surbrillance peut être modifié à l’aide du VEC.

   Si vous avez créé une requête [!DNL Target] sur la page en utilisant [!DNL Target Classic] (anciennement [!DNL Test&Target]), cette requête [!DNL Target] apparaît comme un élément qui indique le nom de la requête et peut être modifiée comme tout autre élément.

   Pour obtenir la liste des actions pouvant être exécutées sur un élément de la page affichée pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si vous publiez une image provenant d’une source autre que votre page principale (une image hébergée sur `akamai.net` et publiée sur `example.com`, par exemple), cette image ne s’affiche pas dans la miniature de la page dans le diagramme de flux.

1. Cliquez sur **[!UICONTROL Next]** lorsque vous avez fini de concevoir l’expérience.

## Renommer l’expérience

1. Cliquez sur l’icône **[!UICONTROL Rename Experience]** ( ![Icône Renommer](/help/main/assets/icons/Rename.svg) ) en regard d’une expérience pour donner un nouveau nom à l’expérience.

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

1. Dans le volet **[!UICONTROL Experiences]**, cliquez sur l’icône **[!UICONTROL More]** ( ![Icône Plus ](/help/main/assets/icons/MoreSmall.svg) ) en regard d’une expérience, puis cliquez sur **[!UICONTROL Redirect to URL]**.

   Pour plus d’informations, voir [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

1. Indiquez l’URL vers laquelle vous souhaitez rediriger l’expérience.

1. (Conditionnel) Cochez la case **[!UICONTROL Include Current Query Parameters]** .

1. Cliquez sur **[!UICONTROL Save]**.

## Duplication d’une expérience

Vous pouvez copier une expérience dans un [!UICONTROL A/B Test] afin d’y apporter des modifications mineures sans avoir à la recréer.

1. Dans le volet **[!UICONTROL Experiences]**, cliquez sur l’icône **[!UICONTROL More]** ( ![Icône Plus ](/help/main/assets/icons/MoreSmall.svg) ) en regard d’une expérience, puis cliquez sur **[!UICONTROL Duplicate]**.

## Suppression d’une expérience

1. Dans le volet **[!UICONTROL Experiences]**, cliquez sur l’icône **[!UICONTROL More]** ( ![Icône Plus ](/help/main/assets/icons/MoreSmall.svg) ) en regard d’une expérience, cliquez sur **[!UICONTROL Delete]**, puis sur **[!UICONTROL Delete]** pour confirmer l’action.