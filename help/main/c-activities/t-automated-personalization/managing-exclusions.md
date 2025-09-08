---
keywords: déduplication;autoriser les doublons;exclure les offres en double;automated personalization;interdire les offres en double;exclure;contenu par défaut;
description: Gérer les exclusions dans les activités [!UICONTROL Automated Personalization] (AP).
title: Comment gérer les exclusions dans les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: e620cd189e2783ba3abbe93bb9c5000866c41b99
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 28%

---

# Gestion des exclusions

Gérez les exclusions en excluant les offres en double, en excluant les expériences spécifiques et en excluant le contenu par défaut dans les activités [!UICONTROL Automated Personalization] (AP) de [!DNL Adobe Target].

## Autoriser ou interdire les offres en double {#concept_4EF78013F80E48EFA024AE0274C9F037}

Empêcher la duplication des offres de la bibliothèque des offres lorsqu&#39;elles sont utilisées à différents emplacements dans des activités [!UICONTROL Automated Personalization].

Vous pouvez par exemple avoir une activité avec six emplacements sur une page comportant 12 offres. Il existe un risque que la même offre soit placée dans un ou plusieurs emplacements de cette activité. Cette fonctionnalité permet d’empêcher l’affichage simultané d’offres en double à différents emplacements d’une même activité.

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), cliquez sur l’icône **[!UICONTROL Configure]** ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ) > cliquez sur l’**[!UICONTROL Allow Duplicate Offers]** pour activer ou désactiver cette fonctionnalité, selon vos besoins.

## Exclure des expériences spécifiques {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluez des expériences spécifiques si vous souhaitez exclure certaines combinaisons d’offres de votre activité [!UICONTROL Automated Personalization].

Certaines combinaisons peuvent ne pas fonctionner ensemble, ou vous pouvez limiter le nombre d’expériences testées afin de réduire les exigences de trafic pour votre activité.

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), cliquez sur l’icône **Gérer le contenu** ( ![Icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ).

   La liste [!UICONTROL Experiences] affiche chaque expérience générée à partir des permutations de toutes les options de contenu et d’emplacement.

1. Excluez d’autres expériences, selon les besoins.

   Vous pouvez exclure des expériences spécifiques en cliquant sur l’icône [!UICONTROL **Plus d’actions**] ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmall.svg) ), puis sur [!UICONTROL **Exclure**].

   Vous pouvez également exclure des expériences par lots en cochant les cases correspondant aux expériences pertinentes, puis en cliquant sur **[!UICONTROL Exclude]**. L’icône [!UICONTROL Exclude] s’affiche lorsqu’une ou plusieurs expériences sont cochées.

   ![Exclusion d’expériences par lots](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   Les expériences sont désormais exclues de l’activité et leur [!UICONTROL Status] s’affiche comme [!UICONTROL Excluded].

## Exclure le contenu par défaut {#task_DCB4528989DF4C05A3A4729E5891D18F}

Parfois, vous ne souhaitez pas inclure votre contenu par défaut dans le cadre de votre activité [!UICONTROL Automated Personalization]. Vous pouvez appliquer cette méthode de manière à conserver une seule offre (différente de votre contenu par défaut) à un emplacement donné dans le cadre de votre activité AP.

L’exclusion de contenu par défaut est un excellent moyen de modifier l’aspect du reste de la page pour l’adapter aux offres que vous testez avec votre activité AP. Supposons par exemple que vous souhaitiez faire correspondre la palette de couleurs des offres que vous testez ; dans ce cas, vous pouvez modifier la couleur d’arrière-plan de votre page et exclure la couleur d’arrière-plan par défaut.

**Pour exclure le contenu par défaut à l’aide du [!UICONTROL Visual Experience Composer] (VEC) :**

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), sélectionnez le contenu à remplacer et cliquez pour accéder aux **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image Offer]** ou **[!UICONTROL Change Background Color]**. Les options disponibles varient en fonction du type de contenu.

   ![Modifier les options](/help/main/c-activities/t-automated-personalization/assets/options.png)

1. Créez votre nouveau contenu et désélectionnez **Inclure** à droite du contenu par défaut (ou désélectionnez l’option Image/vidéo par défaut dans l’écran de [!UICONTROL Select Content]).

   <!-- Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)-->

<!-- 1. Click **[!UICONTROL Save]**.

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

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)-->
