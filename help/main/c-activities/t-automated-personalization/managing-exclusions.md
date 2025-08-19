---
keywords: déduplication;autoriser les doublons;exclure les offres en double;automated personalization;interdire les offres en double;exclure;contenu par défaut;
description: Gérer les exclusions dans les activités [!UICONTROL Automated Personalization] (AP).
title: Comment gérer les exclusions dans les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: c5016d212edafa908b8755044e73d28167e20e8a
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 37%

---

# Gestion des exclusions

Gérez les exclusions en excluant les offres en double, en excluant les expériences spécifiques et en excluant le contenu par défaut dans les activités [!UICONTROL Automated Personalization] (AP) de [!DNL Adobe Target].

## Exclure les offres en double {#concept_4EF78013F80E48EFA024AE0274C9F037}

Empêcher la duplication des offres de la bibliothèque des offres lorsqu&#39;elles sont utilisées à différents emplacements dans des activités [!UICONTROL Automated Personalization].

Vous pouvez par exemple avoir une activité avec six emplacements sur une page comportant 12 offres. Il existe un risque que la même offre soit placée dans un ou plusieurs emplacements de cette activité. Cette fonctionnalité empêche que des offres en double s’affichent en même temps à des endroits différents dans la même activité.

Cliquez sur l’icône **[!UICONTROL Configure]** > **[!UICONTROL Duplicate Offers]**, puis sur **[!UICONTROL Allow Duplicates]** ou **[!UICONTROL Disallow Duplicates]**.

![Options d’offres en double](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exclure des expériences spécifiques {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluez des expériences spécifiques si vous souhaitez exclure certaines combinaisons d’offres de votre activité [!UICONTROL Automated Personalization].

Certaines combinaisons peuvent ne pas fonctionner ensemble, ou vous pouvez limiter le nombre d’expériences testées afin de réduire les exigences de trafic pour votre activité.

1. Lors de la [création ou de la modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), cliquez sur **Gérer le contenu** dans la barre d’en-tête.

   ![Lien Gérer le contenu](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   La liste [!UICONTROL Experiences] affiche chaque expérience générée à partir des permutations de toutes les options de contenu et d’emplacement.

1. Excluez d’autres expériences, selon les besoins.

   Vous pouvez exclure certaines expériences en survolant l’expérience souhaitée, puis en cliquant sur l’icône Exclure.

   ![Exclusion d’une expérience en survolant](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Vous pouvez également exclure des expériences par lots en cochant les cases correspondant aux expériences pertinentes, puis en cliquant sur l’icône **[!UICONTROL Exclude]** dans le coin supérieur droit de la boîte de dialogue. L’icône [!UICONTROL Exclude] s’affiche lorsqu’une ou plusieurs expériences sont cochées.

   ![Exclusion d’expériences par lots](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   Vous pouvez filtrer cette vue de liste pour n’afficher que les activités exclues ou incluses uniquement en cliquant sur la liste déroulante [!UICONTROL Status] .

   Les expériences sont désormais exclues de l’activité et leur [!UICONTROL Status] s’affiche comme [!UICONTROL Excluded].

   ![Expériences exclues](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Exclure le contenu par défaut {#task_DCB4528989DF4C05A3A4729E5891D18F}

Parfois, vous ne souhaitez pas inclure votre contenu par défaut dans le cadre de votre activité [!UICONTROL Automated Personalization]. La manière dont vous accédez à ce paramètre est différente par rapport à la création de groupes d’exclusion. Vous pouvez appliquer cette méthode de manière à conserver une seule offre (différente de votre contenu par défaut) à un emplacement donné dans le cadre de votre activité AP.

L’exclusion de contenu par défaut est un excellent moyen de modifier l’aspect du reste de la page pour l’adapter aux offres que vous testez avec votre activité AP. Supposons par exemple que vous souhaitiez faire correspondre la palette de couleurs des offres que vous testez ; dans ce cas, vous pouvez modifier la couleur d’arrière-plan de votre page et exclure la couleur d’arrière-plan par défaut.

**Pour exclure le contenu par défaut à l’aide du [!UICONTROL Visual Experience Composer] (VEC) :**

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), sélectionnez le contenu à remplacer et cliquez pour accéder aux **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]** ou **[!UICONTROL Change Background Color]**.
1. Dans la boîte de dialogue, créez votre nouveau contenu et désélectionnez **Inclure** à droite du contenu par défaut (ou désélectionnez l’option Image/vidéo par défaut dans l’écran [!UICONTROL Select Content]).

   Selon le contenu ou le type d’offre, la case à cocher [!UICONTROL Include] se trouve à un emplacement légèrement différent.

   Pour le contenu texte/HTML :

   ![Case à cocher Inclure dans la boîte de dialogue Modifier le texte/HTML](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   Pour le contenu image/vidéo :

   ![Case à cocher Inclure dans la boîte de dialogue Sélectionner le contenu](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   Pour la couleur d’arrière-plan :

   ![Case à cocher Inclure dans la boîte de dialogue Modifier la couleur d’arrière-plan](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Cliquez sur **[!UICONTROL Save]**.

   Vous pouvez voir les expériences créées à partir des offres que vous avez spécifiées sous [!UICONTROL Manage Content]. Notez qu’aucune expérience n’est créée dans [!UICONTROL Manage Content] à l’aide de l’offre par défaut que vous avez exclue.

   ![image exclude_content_vec_4](assets/exclude_content_vec_4.png)

**Pour exclure le contenu par défaut à l’aide du [!UICONTROL Form-Based Experience Composer] :**

1. Lors de la création ou de la modification d’une activité AP, cliquez sur **[!UICONTROL Change Text/HTML]** ou **[!UICONTROL Change Image Offer]** sous **[!UICONTROL Content]**.
1. Dans la boîte de dialogue, créez votre nouveau contenu et désélectionnez **[!UICONTROL Include]** à droite du contenu par défaut (ou désélectionnez Image/vidéo par défaut dans l’écran [!UICONTROL Select Content]).

   Selon le contenu ou le type d’offre, la case à cocher [!UICONTROL Include] se trouve à un emplacement légèrement différent.

   Pour le contenu texte/HTML :

   ![image exclude_content_form_1](assets/exclude_content_form_1.png)

   Pour le contenu image/vidéo :

   ![image exclude_content_form_2](assets/exclude_content_form_2.png)

1. Cliquez sur **[!UICONTROL Save]**.

   Vous pouvez voir les expériences créées à partir des offres que vous avez spécifiées sous [!UICONTROL Manage Content]. Notez qu’aucune expérience n’est créée dans [!UICONTROL Manage Content] à l’aide de l’offre par défaut que vous avez exclue.

   ![image exclude_content_form_3](assets/exclude_content_form_3.png)
