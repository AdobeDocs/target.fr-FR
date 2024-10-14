---
keywords: déduplication;autoriser les doublons;exclure les offres en double;personnalisation automatisée;interdire les offres en double;exclure;contenu par défaut;groupe d’exclusion;
description: Gestion des exclusions dans les activités [!UICONTROL Automated Personalization] (AP).
title: Comment gérer les exclusions dans les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
hide: true
hidefromtoc: true
source-git-commit: 8038be5a536ad52b5fd7e1c835bb0b48630a8a11
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 41%

---

# Gestion des exclusions

Gérez les exclusions en créant des groupes d’exclusion, à l’exclusion des offres en double, des expériences spécifiques et du contenu par défaut dans les activités [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target].

## Création de groupes d’exclusion {#task_AAAA6C7239A84F7696C8492F04B575A2}

Créez des groupes d’exclusion dans les activités [!UICONTROL Automated Personalization] (AP) pour vous assurer que les expériences avec les offres désignées sont automatiquement exclues.

Les groupes d’exclusion constituent un excellent moyen de s’assurer que des offres incompatibles ne sont pas présentées dans la même expérience à des emplacements différents. Supposons, par exemple, que vous ayez deux offres : l’une correspond à une remise de 20 % sur l’ensemble des marchandises, l’autre à une remise de 15 %. Vous ne souhaitez jamais que ces deux offres soient présentées aux visiteurs dans la même expérience. Si vous ajoutez ces deux offres à un groupe d’exclusion, vous pouvez vous assurer que cette situation n’est jamais le cas.

Vous pouvez également limiter quelles audiences peuvent voir des offres spécifiques dans les activités AP. Pour plus d’informations, voir [Offres de personnalisation automatisée Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

**Pour créer un groupe d’exclusion, procédez comme suit :**

1. Lors de la [création ou modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), cliquez sur l’icône **[!UICONTROL Manage Content]** ( ![Icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ).

   La boîte de dialogue [!UICONTROL Manage Content] s’affiche.

1. Cliquez sur l’onglet **[!UICONTROL Experiences]** .

1. Dans la boîte de dialogue [!UICONTROL Manage Content], cliquez sur **[!UICONTROL Exclusion Groups]**.

   ![Gérer le contenu > Boîte de dialogue Groupes d’exclusion](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   Si vous avez déjà créé des groupes d’exclusion, ils s’affichent dans la liste. Si vous n’avez pas encore créé de groupe d’exclusion, vous êtes invité à en créer un.

1. Cliquez sur **[!UICONTROL Create Exclusion Group.]**

   ![Boîte de dialogue Créer un groupe d’exclusion](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Obligatoire) Attribuez un nom explicite au groupe d’exclusion.

   Un nom explicite vous aide, ainsi que les autres utilisateurs, à localiser et à comprendre rapidement l’objectif d’un groupe.

1. Localisez et sélectionnez les offres que vous souhaitez ajouter au groupe d’exclusion.

   Vous pouvez sélectionner plusieurs offres du même emplacement d’un groupe d’exclusion.

1. Cliquez sur **[!UICONTROL Save]**.

Les offres du groupe d’exclusion sont automatiquement exclues des mêmes expériences à l’avenir.

## Exclusion des offres en double {#concept_4EF78013F80E48EFA024AE0274C9F037}

Empêchez la duplication des offres de la bibliothèque d’offres lorsqu’elles sont utilisées à différents emplacements dans des activités [!UICONTROL Automated Personalization].

Vous pouvez par exemple avoir une activité avec six emplacements sur une page comportant 12 offres. Il existe un risque que la même offre soit placée dans un ou plusieurs emplacements de cette activité. Cette fonctionnalité empêche que des offres en double s’affichent en même temps à des endroits différents dans la même activité.

Cliquez sur l’option d’engrenage **[!UICONTROL Configure]** > **[!UICONTROL Duplicate Offers]**, puis sur **[!UICONTROL Allow Duplicates]** ou **[!UICONTROL Disallow Duplicates]**.

![Options d’offres en double](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exclusion d’expériences spécifiques {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluez des expériences spécifiques si vous souhaitez exclure certaines combinaisons d’offres de votre activité [!UICONTROL Automated Personalization].

Certaines combinaisons peuvent ne pas fonctionner ensemble ou vous pouvez limiter le nombre d’expériences testées afin de réduire les exigences de trafic de votre activité.

1. Lors de la [création ou de la modification d’une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), cliquez sur **Gérer le contenu** dans la barre d’en-tête.

   ![Lien Gérer le contenu](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   La liste [!UICONTROL Experiences] affiche chaque expérience générée à partir des permutations de toutes les options de contenu et d’emplacement.

1. Excluez d’autres expériences, selon les besoins.

   Vous pouvez exclure certaines expériences en survolant l’expérience souhaitée, puis en cliquant sur l’icône Exclure.

   ![Exclusion d’une expérience en survolant](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Vous pouvez également exclure des expériences par lots en cochant la case correspondant aux expériences pertinentes, puis en cliquant sur l’icône **[!UICONTROL Exclude]** dans le coin supérieur droit de la boîte de dialogue. L’icône [!UICONTROL Exclude] s’affiche lorsqu’une ou plusieurs expériences sont cochées.

   ![Exclusion d’expériences par lots](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   Vous pouvez filtrer cette vue sous forme de liste pour afficher uniquement les activités incluses ou exclues en cliquant sur la liste déroulante [!UICONTROL Status] .

   Les expériences sont désormais exclues de l’activité et leur [!UICONTROL Status] s’affiche comme [!UICONTROL Excluded].

   ![Expériences exclues](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Exclure le contenu par défaut {#task_DCB4528989DF4C05A3A4729E5891D18F}

Parfois, vous pouvez ne pas vouloir inclure votre contenu par défaut dans votre activité [!UICONTROL Automated Personalization]. La manière dont vous accédez à ce paramètre est différente par rapport à la création de groupes d’exclusion. Vous pouvez appliquer cette méthode de manière à conserver une seule offre (différente de votre contenu par défaut) à un emplacement donné dans le cadre de votre activité AP.

L’exclusion de contenu par défaut est un excellent moyen de modifier l’aspect du reste de la page pour l’adapter aux offres que vous testez avec votre activité AP. Supposons par exemple que vous souhaitiez faire correspondre la palette de couleurs des offres que vous testez ; dans ce cas, vous pouvez modifier la couleur d’arrière-plan de votre page et exclure la couleur d’arrière-plan par défaut.

**Pour exclure le contenu par défaut à l’aide de [!UICONTROL Visual Experience Composer] (VEC) :**

1. Lors de la [création ou modification d&#39;une activité AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), sélectionnez le contenu à remplacer, puis cliquez pour accéder à **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]** ou **[!UICONTROL Change Background Color]**.
1. Dans la boîte de dialogue, créez votre nouveau contenu et désélectionnez la case **Inclure** à droite du contenu par défaut (ou désélectionnez l’image/vidéo par défaut dans l’écran [!UICONTROL Select Content]).

   Selon le contenu ou le type d’offre, la case à cocher [!UICONTROL Include] se trouve à un emplacement légèrement différent.

   Pour le contenu texte/HTML :

   ![Case à cocher Inclure dans la boîte de dialogue Modifier le texte/HTML](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   Pour le contenu image/vidéo :

   ![Case à cocher Inclure dans la boîte de dialogue Sélectionner le contenu](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   Pour la couleur d’arrière-plan :

   ![Case à cocher Inclure dans la boîte de dialogue Modifier la couleur d’arrière-plan](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Cliquez sur **[!UICONTROL Save]**.

   Vous pouvez voir les expériences créées à partir des offres que vous avez spécifiées sous [!UICONTROL Manage Content]. Vous remarquerez qu’aucune expérience n’est créée dans [!UICONTROL Manage Content] à l’aide de l’offre par défaut que vous avez exclue.

   ![image exclude_content_vec_4](assets/exclude_content_vec_4.png)

**Pour exclure le contenu par défaut à l’aide de [!UICONTROL Form-Based Experience Composer]:**

1. Lors de la création ou de la modification d’une activité AP, cliquez sur **[!UICONTROL Change Text/HTML]** ou **[!UICONTROL Change Image Offer]** sous **[!UICONTROL Content]**.
1. Dans la boîte de dialogue, créez votre nouveau contenu et désélectionnez la case **[!UICONTROL Include]** située à droite du contenu par défaut (ou désélectionnez l’image/vidéo par défaut dans l’écran [!UICONTROL Select Content]).

   Selon le contenu ou le type d’offre, la case à cocher [!UICONTROL Include] se trouve à un emplacement légèrement différent.

   Pour le contenu texte/HTML :

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   Pour le contenu image/vidéo :

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Cliquez sur **[!UICONTROL Save]**.

   Vous pouvez voir les expériences créées à partir des offres que vous avez spécifiées sous [!UICONTROL Manage Content]. Vous remarquerez qu’aucune expérience n’est créée dans [!UICONTROL Manage Content] à l’aide de l’offre par défaut que vous avez exclue.

   ![image exclude_content_form_3](assets/exclude_content_form_3.png)