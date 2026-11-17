---
keywords: déduplication;autoriser les doublons;exclure les offres en double;automated personalization;interdire les offres en double;exclure;contenu par défaut;
description: Gérez les exclusions dans les activités [!UICONTROL Automated Personalization] (AP).
title: Comment gérer les exclusions dans les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: 'https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%
---
# Gestion des exclusions {#manage-exclusions}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment empêcher les offres en double, exclure des expériences spécifiques et exclure le contenu par défaut dans les activités **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Les exclusions contrôlent les offres et expériences qu’une activité **[!UICONTROL Automated Personalization]** (AP) diffuse. Elles empêchent l’affichage simultané de deux offres, suppriment les combinaisons d’offres qui ne fonctionnent pas ensemble et suppriment le contenu par défaut, de sorte que l’activité offre des expériences plus épurées et plus pertinentes qui correspondent à vos objectifs et à votre audience.

## Autoriser ou interdire les offres en double {#allow-duplicate-offers}

<a id="concept_4EF78013F80E48EFA024AE0274C9F037"></a>

Empêcher la duplication des offres de la bibliothèque des offres lorsqu&#39;elles sont utilisées à différents emplacements dans des activités AP.

Une activité peut avoir, par exemple, six emplacements sur une page contenant 12 offres. Une même offre peut donc être placée à plusieurs emplacements. La désactivation des offres en double empêche l’affichage simultané d’une même offre à différents emplacements d’une même activité.

1. Lors de la [création ou modification d&#39;une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), cliquez sur l&#39;icône **[!UICONTROL Configurer]** ( ![Icône Configurer](/help/main/assets/icons/Setting.svg) ).

1. Cliquez sur **[!UICONTROL Autoriser les offres en double]** pour activer ou désactiver cette fonctionnalité, selon vos besoins.

   ![Icône Configurer](../assets/exclusion-1.png)

## Exclure des expériences spécifiques {#exclude-experiences}

<a id="task_C17D36EF58AF4908B17A3D84CA6DE85A"></a>

Excluez les expériences spécifiques pour supprimer certaines combinaisons d’offres de votre activité AP. Certaines combinaisons peuvent ne pas fonctionner ensemble ou vous pouvez limiter le nombre d’expériences testées afin de réduire les exigences de trafic de l’activité.

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), cliquez sur l’icône **[!UICONTROL Gérer le contenu]** ( ![Icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ).

   La liste **[!UICONTROL Expériences]** indique chaque expérience générée à partir des permutations de toutes les options de contenu et de lieu.

1. Excluez les expériences que vous ne souhaitez pas tester.

   * Pour exclure une seule expérience, cliquez sur l’icône **[!UICONTROL Autres actions]** ( ![Icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ), puis sur **[!UICONTROL Exclure]**.
   * Pour exclure plusieurs expériences à la fois, cochez la case pour chaque expérience, puis cliquez sur **[!UICONTROL Exclure]**. L’icône **[!UICONTROL Exclure]** s’affiche lorsqu’une ou plusieurs expériences sont sélectionnées.

   ![Exclusion d’expériences par lots](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   Les expériences sont désormais exclues de l’activité, et leur **[!UICONTROL Statut]** indique **[!UICONTROL Exclu]**.

## Exclure le contenu par défaut {#exclude-default-content}

<a id="task_DCB4528989DF4C05A3A4729E5891D18F"></a>

Excluez le contenu par défaut lorsque vous ne souhaitez pas qu’il fasse partie de votre activité AP, de sorte qu’un emplacement ne contienne qu’une seule offre différente de votre contenu par défaut. Cette approche vous permet également de modifier l’aspect du reste de la page en fonction des offres que vous testez. Par exemple, pour correspondre à la palette de couleurs des offres, vous pouvez modifier la couleur d’arrière-plan de la page et exclure la couleur d’arrière-plan par défaut.

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), sélectionnez le contenu à remplacer, puis cliquez sur **[!UICONTROL Modifier le texte/HTML]**, **[!UICONTROL Modifier l’offre d’image]** ou **[!UICONTROL Modifier la couleur d’arrière-plan]**. Les options disponibles varient en fonction du type de contenu.

   ![Modifier les options](../assets/exclusion-1.png)

1. Créez votre nouveau contenu.

1. Cliquez sur l’icône **[!UICONTROL Plus d’actions]** (![Icône Plus d’actions](/help/main/assets/icons/Setting.svg) ), puis cliquez sur le bouton (bascule) **Exclure l’offre par défaut/Inclure l’offre par défaut** pour exclure ou inclure l’offre par défaut.

   <!--
   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)
   -->

<!--
1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**To exclude default content using the [!UICONTROL Form-Based Experience Composer]:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the [!UICONTROL Select Content] screen). 

   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
-->
