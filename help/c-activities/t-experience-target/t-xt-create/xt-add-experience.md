---
description: Le compositeur d'expérience visuelle fournit une interface visuelle permettant de modifier les expériences sur votre page dans une activité de ciblage d'expérience (XT).
keywords: créer une expérience;création d’une expérience;priorité;audience;expérience;compositeur d’expérience visuelle
seo-description: Le compositeur d'expérience visuelle d'Adobe Target fournit une interface visuelle permettant de modifier les expériences sur votre page dans une activité de ciblage d'expérience (XT).
seo-title: Création d’une expérience
solution: Target
title: Création d’une expérience
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Create experience{#create-experience}

Le compositeur d'expérience visuelle fournit une interface visuelle permettant de modifier les expériences sur votre page dans une activité de ciblage d'expérience (XT).

1. Sélectionnez les éléments que vous souhaitez modifier et apportez les modifications de votre choix.

   While [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), step one of the three-part guided workflow (Experiences) displays the default [!UICONTROL Experience A] with an [!UICONTROL All Visitors] audience.

   ![Audience Tous les visiteurs](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Any changes you make now apply to Experience A. In a step below, you'll click **[!UICONTROL Add Experience Targeting]** to create additional experiences.

   Lorsque vous pointez sur les éléments de votre page, ils sont mis en surbrillance. Tout élément surligné peut être modifié à l'aide du compositeur d'expérience visuelle. For a list of actions that can be performed on an element to change the experience, see [Visual Experience Composer Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Si vous créez une mbox sur la page à l’aide de Target Classic (anciennement Test&amp;Target), celle-ci apparaît comme un élément qui indique le nom de la mbox et qui peut être modifié comme tout autre élément.

   >[!NOTE]
   >
   >Par défaut, le compositeur d’expérience visuelle n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez choisir de désactiver JavaScript si vous souhaitez pouvoir modifier ces éléments à l'aide du compositeur d'expérience visuelle.

1. To create additional experiences, click **[!Add Experience Targeting]**.

   ![Lien Ajouter un ciblage d'expérience](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL Choose Audience] dialog box displays. Pour cibler une expérience sur une audience, vous devez sélectionner l'audience avant de pouvoir ajouter une expérience.

   La bibliothèque d’audiences contient les audiences qui ont été précédemment définies ainsi que les audiences courantes préconfigurées dans Target. Vous pouvez sélectionner une audience dans la bibliothèque ou [en créer une](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Lors de la création d’une audience, vous pouvez sélectionner un emplacement (mbox) et préciser les paramètres de ce dernier. Under [!UICONTROL Custom] (Create Audience &gt; Add Rule &gt; Custom), select the mbox, then specify the desired parameters.

   >[!NOTE]
   >
   >Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste d’audiences et que les audiences ont été importées il y a plus de 10 minutes.

1. Select one or more audiences to target with the experience, then click **[!UICONTROL Done]**.

   ![Expérience B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   L'expérience B s'affiche désormais dans l'illustration précédente et cette expérience est ciblée sur l'audience Visiteurs US.

1. Sélectionnez les éléments à modifier pour cette expérience et apportez les modifications souhaitées, comme expliqué à l'étape 1 ci-dessus.

1. Répétez les étapes précédentes pour créer d'autres expériences ciblées, si nécessaire.

1. Click **[!UICONTROL Next]** when you are finished designing your experiences.

   Le diagramme des activités affiche :

   ![Diagramme de ciblage XT](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Si vous fournissez une image à partir d'une source autre que la page principale (telle qu'une image hébergée sur akamai. net et diffusée sur adobe.com), cette image ne s'affiche pas dans la miniature de la page affichée dans le diagramme de flux.

1. (Conditionnel) Faites glisser des paires audience/expérience pendant la création ou la modification des activités de ciblage d'expérience pour organiser les paires dans l'ordre souhaité.

   Les visiteurs sont évalués pour les expériences dans l'ordre, de haut en bas.

   ![Déplacement d'expériences](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   Le ciblage d’expérience présume que l’ordre est important. Si un visiteur appartient à la première paire audience/expérience, la première expérience est diffusée.

   Par exemple, supposons que vous ne sachiez pas que l’ordre est important lors de la création d’une activité de ciblage d’expérience. Vous réalisez, par la suite, durant les tests, que les visiteurs que vous pensiez qualifiés pour les expériences B ou C sont en fait qualifiés pour l’expérience A. Cela peut être dû au fait que les audiences ne s’excluent pas mutuellement et ne sont pas dans le bon ordre (par exemple, expérience A = États-Unis, expérience B = San Francisco et expérience C = Californie). Dans ce scénario, tous les utilisateurs des États-Unis sont qualifiés pour l’expérience A, même s’ils sont situés à San Francisco ou ailleurs en Californie. Vous pouvez réorganiser les paires audience/expérience de la plus restrictive à la moins restrictive (San Francisco &gt; Californie &gt; États-Unis) sans recréer toute l’activité.

   If you have an [!UICONTROL All Visitors] audience, ensure that it is not the first audience in the diagram. Une expérience ciblée sur « Tous les visiteurs » peut être utilisée comme dernière expérience de l’activité de ciblage d’expérience pour « rattraper » les visiteurs qui n’ont pas été dirigés vers une autre expérience.

## Modification du nom ou modification d'une expérience

You can click the [!UICONTROL Edit] icon (three vertical ellipses) on an experience in an XT activity and choose from the following options, as necessary:

* Renommer
* Modifier

![Attribution d'un nouveau nom et modification des options](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Suppression d'une expérience

On the **[!UICONTROL Experiences]** page (the first step in the three-step guided workflow), click the three vertical ellipses &gt; **[!UICONTROL Delete]**.

![Supprimer une expérience](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplication d’une expérience

Vous pouvez désormais copier une expérience dans une activité de ciblage d’expérience (XT) afin d’y apporter des changements mineurs, sans devoir la recréer de zéro.

Sur la page **[!UICONTROL Expériences]** (la première étape du processus assisté en trois étapes), cliquez sur les trois points alignés verticalement &gt; **[!UICONTROL Dupliquer]**.

![Dupliquer l'expérience](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vidéos de formation :

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Des tests A/B au ciblage de l’expérience

Cette vidéo explique comment faire évoluer les tests A/B avec le ciblage d’expérience (XT).

* Décrire le processus assisté en trois étapes pour configurer une activité XT
* Décrire comment diffuser du contenu d’emplacement auprès d’audiences situées dans différentes zones géographiques
* Décrire comment réorganiser les expériences afin de garantir que le bon contenu est diffusé à la bonne audience

>[!VIDEO](https://video.tv.adobe.com/v/22418/?captions=fre_fr)

### Types d’activité (9:03)

Cette vidéo explique les types d’activités disponibles dans Target Standard/Premium. Le ciblage d’expérience est abordé dans la vidéo à partir de 5:15.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386?captions=fre_fr)

### Utilisation du compositeur d'expérience visuelle

La vidéo ci-après fournit des informations sur l’utilisation des options du compositeur d’expérience visuelle.

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=fre_fr)