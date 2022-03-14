---
keywords: créer une expérience;création d’une expérience;priorité;audience;expérience;compositeur d’expérience visuelle
description: Découvrez comment utiliser l’Adobe [!DNL Target] compositeur d’expérience visuelle (VEC) pour créer et modifier des expériences sur votre page dans une activité de ciblage d’expérience (XT).
title: Comment créer des expériences dans une activité de ciblage d’expérience ?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 87%

---

# Créer une expérience dans les activités de ciblage d’expérience (XT)

Le [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] fournit une interface visuelle pour la modification des expériences de votre page dans une [!UICONTROL Ciblage d’expérience] (XT).

1. Sélectionnez les éléments que vous souhaitez modifier et apportez les modifications de votre choix.

   Lors de la [création d’une activité XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), la première étape du workflow assisté en trois parties ([!UICONTROL Expériences]) affiche [!UICONTROL l’expérience A] par défaut avec une audience [!UICONTROL Tous les visiteurs].

   ![Audience Tous les visiteurs](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Les modifications que vous apportez à présent s’appliquent à l’expérience A. Dans une étape ci-dessous, vous allez cliquer sur **[!UICONTROL Ajouter un ciblage d’expérience]** pour créer d’autres expériences.

   Lorsque vous pointez sur les éléments de votre page, ils sont mis en surbrillance. Vous pouvez modifier un élément en surbrillance à l’aide du VEC. Pour obtenir la liste des actions pouvant être exécutées sur un élément pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Si vous avez créé une [!DNL Target] requête sur la page à l’aide de [!DNL Target Classic], que [!DNL Target] s’affiche sous la forme d’un élément qui indique le nom de la requête et qui peut être modifié comme tout autre élément.

   >[!NOTE]
   >
   >Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez choisir de désactiver JavaScript pour modifier ces éléments à l’aide du compositeur d’expérience visuelle (VEC).

1. Pour créer d’autres expériences, cliquez sur **[!UICONTROL Ajouter un ciblage d’expérience]**.

   ![Lien Ajouter un ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   La boîte de dialogue [!UICONTROL Choisir audience] s’affiche. Pour cibler une expérience vers une audience, vous devez sélectionner l’audience avant de pouvoir ajouter une expérience.

   La bibliothèque d’audiences contient les audiences qui ont été précédemment définies ainsi que les audiences courantes préconfigurées dans [!DNL Target]. Vous pouvez sélectionner une audience dans la bibliothèque ou [créer une audience](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Lors de la création d’une audience, vous pouvez sélectionner un emplacement et spécifier des paramètres pour cet emplacement. Sous [!UICONTROL Personnalisé] (Créer une audience > Ajouter une règle > Personnaliser), sélectionnez l’emplacement, puis spécifiez les paramètres souhaités.

   >[!NOTE]
   >
   >Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste d’audiences et que les audiences ont été importées il y a plus de 10 minutes.

1. Sélectionnez une ou plusieurs audiences à cibler avec l’expérience, puis cliquez sur **[!UICONTROL Terminé]**.

   ![Expérience B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   L’expérience B s’affiche désormais dans l’illustration précédente et cette expérience est ciblée sur l’audience Visiteurs US.

1. Sélectionnez les éléments à modifier pour cette expérience et apportez les modifications souhaitées, comme expliqué à l’étape 1 ci-dessus.

1. Répétez les étapes précédentes pour créer d’autres expériences ciblées, si nécessaire.

1. Cliquez sur **[!UICONTROL Suivant]** lorsque vous avez terminé de concevoir vos expériences.

   Le diagramme des activités affiche :

   ![Diagramme de ciblage XT](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Si vous publiez une image provenant d’une source autre que votre page principale (une image hébergée sur `akamai.net` et publiée sur `adobe.com`, par exemple), cette image ne s’affiche pas dans la miniature de la page dans le diagramme de flux.

1. (Conditionnel) Faites glisser des paires audience / expérience lors de la création ou de la modification d’activités de ciblage d’expérience afin d’organiser les paires dans l’ordre souhaité.

   Les expériences des visiteurs sont évaluées dans l’ordre, du haut vers le bas.

   ![Déplacement d’expériences](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL Le ciblage d’expérience présume que l’ordre est important. ] Si un visiteur appartient à la première paire audience/expérience, la première expérience est diffusée.

   Par exemple, supposons que vous ne sachiez pas que l’ordre est important lors de la création d’une activité de ciblage d’expérience. Vous réalisez, par la suite, durant les tests, que les visiteurs que vous pensiez qualifiés pour les expériences B ou C sont en fait qualifiés pour l’expérience A. Cela peut être dû au fait que les audiences ne s’excluent pas mutuellement et ne sont pas dans le bon ordre (par exemple, expérience A = États-Unis, expérience B = San Francisco et expérience C = Californie). Dans ce scénario, tous les utilisateurs des États-Unis sont qualifiés pour l’expérience A, même s’ils sont situés à San Francisco ou ailleurs en Californie. Vous pouvez réorganiser les paires audience/expérience de la plus restrictive à la moins restrictive (San Francisco > Californie > États-Unis) sans recréer toute l’activité.

   Si vous avez une audience [!UICONTROL Tous les visiteurs], assurez-vous qu’il ne s’agit pas de la première audience sur le diagramme. Une expérience ciblée sur « Tous les visiteurs » peut être utilisée comme dernière expérience de l’activité de ciblage d’expérience pour « rattraper » les visiteurs qui n’ont pas été dirigés vers une autre expérience.

## Renommer ou modifier une expérience

Vous pouvez cliquer sur l’icône [!UICONTROL Modifier] (trois points alignés verticalement) d’une expérience dans une activité XT et choisir l’une des options suivantes, selon vos besoins :

* Renommer
* Modifier

![Options Renommer et Modifier](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Suppression d’une expérience

Sur la page **[!UICONTROL Expériences]** (la première étape du processus assisté en trois étapes), cliquez sur les trois points alignés verticalement > **[!UICONTROL Supprimer]**.

![Suppression d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplication d’une expérience

Vous pouvez désormais copier une expérience dans une activité de ciblage d’expérience (XT) afin d’y apporter des changements mineurs, sans devoir la recréer de zéro.

Sur la page **[!UICONTROL Expériences]** (la première étape du processus assisté en trois étapes), cliquez sur les trois points alignés verticalement > **[!UICONTROL Dupliquer]**.

![Duplication d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vidéos de formation :

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Des tests A/B au ciblage de l’expérience

Cette vidéo explique comment faire évoluer les tests A/B avec le ciblage d’expérience (XT).

* Décrire le processus assisté en trois étapes pour configurer une activité XT
* Décrire comment diffuser du contenu d’emplacement auprès d’audiences situées dans différentes zones géographiques
* Décrire comment réorganiser les expériences afin de garantir que le bon contenu est diffusé à la bonne audience

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Types d’activité (9:03)

Cette vidéo explique les types d’activités disponibles dans Target Standard/Premium. Le ciblage d’expérience est abordé dans la vidéo à partir de 5:15.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Utilisation du compositeur d’expérience visuelle

La vidéo ci-après fournit des informations sur l’utilisation des options du compositeur d’expérience visuelle.

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/17399)
