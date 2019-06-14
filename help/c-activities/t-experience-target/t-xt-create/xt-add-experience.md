---
description: Le compositeur d'expérience visuelle fournit une interface visuelle permettant de modifier les expériences sur votre page.
keywords: créer une expérience;création d’une expérience;priorité;audience;expérience;compositeur d’expérience visuelle
seo-description: Le compositeur d'expérience visuelle d'Adobe Target fournit une interface visuelle permettant de modifier les expériences sur votre page.
seo-title: Création d’une expérience
solution: Target
title: Création d’une expérience
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# Créer une expérience{#create-experience}

Le compositeur d&#39;expérience visuelle fournit une interface visuelle permettant de modifier les expériences sur votre page dans une activité de ciblage d&#39;expérience (XT).

1. Sélectionnez les éléments que vous souhaitez modifier et apportez les modifications de votre choix.

   Lors [de la création d&#39;une activité de ciblage d&#39;](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)expérience, l&#39;étape un du workflow assisté en trois parties (Expériences) affiche l&#39; [!UICONTROL expérience A par défaut] avec une [!UICONTROL audience Tous les visiteurs] .

   ![Audience Tous les visiteurs](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Les modifications que vous apportez à présent s&#39;appliquent à l&#39;expérience A. Dans une étape ci-dessous, vous allez cliquer [!UICONTROL sur Ajouter un ciblage] d&#39;expérience pour créer d&#39;autres expériences.

   Lorsque vous pointez sur les éléments de votre page, ils sont mis en surbrillance. Tout élément surligné peut être modifié à l&#39;aide du compositeur d&#39;expérience visuelle. Pour obtenir la liste des actions pouvant être exécutées sur un élément pour modifier l&#39;expérience, voir [Options du compositeur d&#39;expérience visuelle](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Si vous créez une mbox sur la page à l’aide de Target Classic (anciennement Test&amp;Target), celle-ci apparaît comme un élément qui indique le nom de la mbox et qui peut être modifié comme tout autre élément.

1. Pour créer d&#39;autres expériences, cliquez sur **[!ADD Ciblage d&#39;expérience]**.

   ![Lien Ajouter un ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   La boîte de dialogue [!UICONTROL Choisir l&#39;audience] s&#39;affiche. Pour cibler une expérience sur une audience, vous devez sélectionner l&#39;audience avant de pouvoir ajouter une expérience.

   La bibliothèque d’audiences contient les audiences qui ont été précédemment définies ainsi que les audiences courantes préconfigurées dans Target. Vous pouvez sélectionner une audience dans la bibliothèque ou [en créer une](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271). Pour afficher la même expérience pour tous les entrants, sélectionnez Tous les visiteurs.

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Lors de la création d’une audience, vous pouvez sélectionner un emplacement (mbox) et préciser les paramètres de ce dernier. Sous Paramètres personnalisés, sélectionnez la mbox, puis spécifiez les paramètres souhaités.

   >[!NOTE]
   >
   >Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste d’audiences et que les audiences ont été importées il y a plus de 10 minutes.

1. Sélectionnez une ou plusieurs audiences à cibler avec l&#39;expérience, puis cliquez **[!UICONTROL sur Terminé]**.

   ![Expérience B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   L&#39;expérience B s&#39;affiche désormais dans l&#39;illustration précédente et cette expérience est ciblée sur l&#39;audience Visiteurs US.

1. Sélectionnez les éléments à modifier pour cette expérience et apportez les modifications souhaitées, comme expliqué à l&#39;étape 1 ci-dessus.

1. Répétez les étapes précédentes pour créer d&#39;autres expériences ciblées, si nécessaire.

1. Cliquez **[!UICONTROL sur Suivant]** lorsque vous avez terminé de concevoir les expériences.

   Le diagramme des activités affiche :

   ![Diagramme de ciblage XT](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

1. (Conditionnel) Faites glisser des paires audience/expérience pendant la création ou la modification des activités de ciblage d&#39;expérience pour organiser les paires dans l&#39;ordre souhaité.

   Les visiteurs sont évalués pour les expériences dans l&#39;ordre, de haut en bas.

   ![Déplacement d&#39;expériences](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   Le ciblage d’expérience présume que l’ordre est important. Si un visiteur appartient à la première paire audience/expérience, la première expérience est diffusée.

   Par exemple, supposons que vous ne sachiez pas que l’ordre est important lors de la création d’une activité de ciblage d’expérience. Vous réalisez, par la suite, durant les tests, que les visiteurs que vous pensiez qualifiés pour les expériences B ou C sont en fait qualifiés pour l’expérience A. Cela peut être dû au fait que les audiences ne s’excluent pas mutuellement et ne sont pas dans le bon ordre (par exemple, expérience A = États-Unis, expérience B = San Francisco et expérience C = Californie). Dans ce scénario, tous les utilisateurs des États-Unis sont qualifiés pour l’expérience A, même s’ils sont situés à San Francisco ou ailleurs en Californie. Vous pouvez réorganiser les paires audience/expérience de la plus restrictive à la moins restrictive (San Francisco &gt; Californie &gt; États-Unis) sans recréer toute l’activité.

## Modification du nom ou modification d&#39;une expérience

Vous pouvez cliquer sur l&#39;icône [!UICONTROL Modifier] (trois points de suspension verticaux) sur une expérience dans une activité XT et choisir parmi les options suivantes, si nécessaire :

* Renommer
* Modifier

![Attribution d&#39;un nouveau nom et modification des options](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Suppression d&#39;une expérience

Sur la page **[!UICONTROL Expériences]** (la première étape du workflow assisté en trois étapes), cliquez sur les trois points de suspension verticaux &gt; **[!UICONTROL Supprimer]**.

![Supprimer une expérience](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplication d’une expérience

Vous pouvez désormais copier une expérience dans une activité de ciblage d’expérience (XT) afin d’y apporter des changements mineurs, sans devoir la recréer de zéro.

Sur la page **[!UICONTROL Expériences]** (la première étape du processus assisté en trois étapes), cliquez sur les trois points alignés verticalement &gt; **[!UICONTROL Dupliquer]**.

![Dupliquer l&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vidéo de formation : utilisation du compositeur d’expérience visuelle

La vidéo ci-après fournit des informations sur l’utilisation des options du compositeur d’expérience visuelle.

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=fre_fr)