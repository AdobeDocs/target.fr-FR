---
keywords: ciblage;expérience;ajouter une expérience;ajout d’une expérience
description: Découvrez comment utiliser le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target].
title: Comment ajouter des expériences dans une activité a [!DNL Target] B ?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 41%

---

# Ajout d’une expérience

Le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience visuelle] (VEC) fournit une interface visuelle pour ajouter et modifier des expériences sur votre page.

Pour plus d’informations sur les expériences, voir [Expériences](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Sur la page **[!UICONTROL Expériences]** du VEC, cliquez sur **[!UICONTROL Ajouter une expérience]**.

   ![Option Ajouter une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >Si vous ciblez une expérience vers une audience, vous devez sélectionner l’audience avant de pouvoir ajouter une expérience. Un message s’affiche pour vous rappeler de sélectionner l’audience.

1. Sélectionnez les éléments à modifier et apportez les modifications souhaitées.

   Lorsque vous passez la souris sur les éléments de la page, les éléments sont mis en surbrillance. Vous pouvez modifier un élément en surbrillance à l’aide du VEC.

   Si vous avez créé une requête [!DNL Target] sur la page à l’aide de [!DNL Target Classic] (anciennement [!DNL Test&Target]), cette requête [!DNL Target] s’affiche sous la forme d’un élément indiquant le nom de la requête et peut être modifiée comme tout autre élément.

   Pour obtenir la liste des actions pouvant être exécutées sur un élément de la page affichée pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si vous publiez une image provenant d’une source autre que votre page principale (une image hébergée sur `akamai.net` et publiée sur `example.com`, par exemple), cette image ne s’affiche pas dans la miniature de la page dans le diagramme de flux.

1. Cliquez sur **[!UICONTROL Enregistrer]** lorsque vous avez terminé de concevoir l’expérience.

## Renommer l’expérience

1. Cliquez sur l’icône **[!UICONTROL Renommer l’expérience]** sur une expérience dans une activité de [!UICONTROL Test A/B] ou [!UICONTROL Ciblage d’expérience] (XT) pour donner un nouveau nom à l’expérience.

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

1. Cliquez sur l’icône **[!UICONTROL Plus]** (les points de suspension verticaux) d’une expérience dans une activité [!UICONTROL Test A/B] ou [!UICONTROL Ciblage d’expérience] (XT), puis cliquez sur **[!UICONTROL Rediriger vers l’URL]**.

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

1. (Conditionnel) Cochez la case **[!UICONTROL Inclure les paramètres de requête actuels]**.

## Duplication d’une expérience

Vous pouvez copier une expérience dans un test [!UICONTROL A/B] afin d’y apporter des modifications mineures sans avoir à recréer l’expérience depuis le début.

1. Sur la page **[!UICONTROL Expériences]** (première étape du workflow guidé en trois étapes), cliquez sur l’icône représentant des points de suspension verticaux > **[!UICONTROL Dupliquer]**.

   ![Option de duplication d’une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## Suppression d’une expérience

1. Sur la page **[!UICONTROL Expériences]** (première étape du workflow guidé en trois étapes), cliquez sur l’icône représentant des points de suspension verticaux > **[!UICONTROL Dupliquer]**.

   ![Option de suppression d’une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## Vidéo de formation : Utilisation du [!UICONTROL compositeur d’expérience visuelle]

La vidéo ci-dessous fournit des informations sur l’utilisation des options du [!UICONTROL compositeur d’expérience visuelle]. (7:17)

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/29229?captions=fre_fr)
