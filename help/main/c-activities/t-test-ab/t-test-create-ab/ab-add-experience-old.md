---
keywords: ciblage;expérience;ajouter une expérience;ajout d’une expérience
description: Découvrez comment utiliser le [!UICONTROL Visual Experience Composer] (VEC) dans  [!DNL Adobe Target].
title: Comment ajouter des expériences dans une activité a [!DNL Target] B ?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 43%

---

# Ajout d’une expérience

Le [!UICONTROL Visual Experience Composer] d’[!DNL Adobe Target] (VEC) fournit une interface visuelle permettant d’ajouter et de modifier des expériences sur votre page.

Pour plus d’informations sur les expériences, voir [Expériences](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Dans la page **[!UICONTROL Experiences]** du compositeur d’expérience visuelle, cliquez sur **[!UICONTROL Add Experience]**.

   ![Option Ajouter une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >Si vous ciblez une expérience vers une audience, vous devez sélectionner l’audience avant de pouvoir ajouter une expérience. Un message s’affiche pour vous rappeler de sélectionner l’audience.

1. Sélectionnez les éléments à modifier et apportez les modifications souhaitées.

   Lorsque vous passez la souris sur les éléments de la page, les éléments sont mis en surbrillance. Tout élément mis en surbrillance peut être modifié à l’aide du compositeur d’expérience visuelle.

   Si vous avez créé une requête [!DNL Target] sur la page à l’aide de [!DNL Target Classic] (anciennement [!DNL Test&Target]), cette requête [!DNL Target] s’affiche sous la forme d’un élément indiquant le nom de la requête et peut être modifiée comme tout autre élément.

   Pour obtenir la liste des actions pouvant être exécutées sur un élément de la page affichée pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si vous publiez une image provenant d’une source autre que votre page principale (une image hébergée sur `akamai.net` et publiée sur `example.com`, par exemple), cette image ne s’affiche pas dans la miniature de la page dans le diagramme de flux.

1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé de concevoir l’expérience.

## Renommer l’expérience

1. Cliquez sur l’icône **[!UICONTROL Rename Experience]** d’une expérience dans une activité [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] (XT) pour donner un nouveau nom à l’expérience.

   ![Renommer l’expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/rename-experience.png)

2. Spécifiez un nouveau nom.

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

1. Cliquez sur l’icône **[!UICONTROL More]** (les points de suspension verticaux) d’une expérience dans une activité [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] (XT), puis cliquez sur **[!UICONTROL Redirect to URL]**.

   Pour plus d’informations, voir [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

   **REMARQUE** : Les caractères suivants sont interdits lorsque vous nommez ou renommez une expérience :

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

1. Indiquez l’URL vers laquelle vous souhaitez rediriger l’expérience.

1. (Conditionnel) Cochez la case **[!UICONTROL Include Current Query Parameters]** .

## Duplication d’une expérience

Vous pouvez copier une expérience dans une [!UICONTROL A/B Test] afin d’y apporter des modifications mineures sans avoir à recréer l’expérience depuis le début.

1. Sur la page **[!UICONTROL Experiences]** (première étape du processus assisté en trois étapes), cliquez sur l’icône représentant des points de suspension verticaux > **[!UICONTROL Duplicate]**.

   ![Option de duplication d’une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## Suppression d’une expérience

1. Sur la page **[!UICONTROL Experiences]** (première étape du processus assisté en trois étapes), cliquez sur l’icône représentant des points de suspension verticaux > **[!UICONTROL Duplicate]**.

   ![Option de suppression d’une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## Vidéo de formation : Utilisation de l’[!UICONTROL Visual Experience Composer]

La vidéo ci-dessous fournit des informations sur l’utilisation des options [!UICONTROL Visual Experience Composer]. (07:17)

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/29229?captions=fre_fr)
