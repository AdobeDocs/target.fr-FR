---
keywords: déduplication;autoriser les doublons;exclure les offres en double;automated personalization;interdire les offres en double;exclure;contenu par défaut;
description: Gérez les exclusions dans les activités  (AP).
title: Comment gérer les exclusions dans les activités  ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 521
ht-degree: 23%

---

# Gestion des exclusions

Contrôlez votre stratégie  (AP) en maîtrisant les exclusions. Que vous préviez les offres en double, affiniez les combinaisons d’expériences ou supprimiez le contenu par défaut, les exclusions vous permettent de proposer des expériences plus propres et plus pertinentes, conformes à vos objectifs et aux attentes de votre audience.

## Autoriser ou interdire les offres en double {#concept_4EF78013F80E48EFA024AE0274C9F037}

Empêcher la duplication des offres de la bibliothèque des offres lorsqu&#39;elles sont utilisées à différents emplacements dans des activités AP.

Vous pouvez par exemple avoir une activité avec six emplacements sur une page comportant 12 offres. Il existe un risque que la même offre soit placée dans un ou plusieurs emplacements de cette activité. Cette fonctionnalité permet d’empêcher l’affichage simultané d’offres en double à différents emplacements d’une même activité.

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), cliquez sur l’icône **[!UICONTROL Configurer]** ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ) > cliquez sur l’icône **[!UICONTROL Autoriser les offres en double]** pour activer ou désactiver cette fonctionnalité, selon vos besoins.

## Exclure des expériences spécifiques {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluez des expériences spécifiques si vous souhaitez exclure certaines combinaisons d’offres de votre activité AP.

Certaines combinaisons peuvent ne pas fonctionner ensemble, ou vous pouvez limiter le nombre d’expériences testées afin de réduire les exigences de trafic pour votre activité.

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), cliquez sur l’icône **Gérer le contenu** ( ![Icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ).

   La liste [!UICONTROL Expériences] indique chaque expérience générée à partir des permutations de toutes les options de contenu et de lieu.

1. Excluez d’autres expériences, selon les besoins.

   Vous pouvez exclure des expériences spécifiques en cliquant sur l’icône [!UICONTROL **Plus d’actions**] ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmall.svg) ), puis sur [!UICONTROL **Exclure**].

   Vous pouvez également exclure des expériences par lots en cochant les cases correspondant aux expériences pertinentes, puis en cliquant sur **[!UICONTROL Exclure]**. L’icône [!UICONTROL Exclure] s’affiche lorsqu’une ou plusieurs expériences sont cochées.

   ![Exclusion d’expériences par lots](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   Les expériences sont désormais exclues de l’activité et leur [!UICONTROL Statut] s’affiche comme [!UICONTROL Exclus].

## Exclure le contenu par défaut {#task_DCB4528989DF4C05A3A4729E5891D18F}

Parfois, vous pouvez ne pas vouloir inclure votre contenu par défaut dans votre activité AP. Vous pouvez utiliser cette méthode pour n’avoir qu’une seule offre (différente de votre contenu par défaut) à un emplacement dans le cadre de votre activité.

L’exclusion de contenu par défaut est un excellent moyen de modifier l’aspect du reste de la page pour l’adapter aux offres que vous testez avec votre activité AP. Supposons par exemple que vous souhaitiez faire correspondre la palette de couleurs des offres que vous testez ; dans ce cas, vous pouvez modifier la couleur d’arrière-plan de votre page et exclure la couleur d’arrière-plan par défaut.

**Pour exclure le contenu par défaut à l’aide du [!UICONTROL compositeur d’expérience visuelle] (VEC) :**

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), sélectionnez le contenu à remplacer et cliquez pour accéder à **[!UICONTROL Modifier le texte/l’HTML]**, **[!UICONTROL Modifier l’offre d’image]** ou **[!UICONTROL Modifier la couleur d’arrière-plan]**. Les options disponibles varient en fonction du type de contenu.

   ![Modifier les options](/help/main/c-activities/t-automated-personalization/assets/options.png)
1. Créez votre nouveau contenu.

1. Cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![icône Plus d’actions](/help/main/assets/icons/Setting.svg) ), puis sur le bouton (bascule) **Exclure l’offre par défaut/Inclure l’offre par défaut**/ pour exclure ou inclure l’offre par défaut.

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
