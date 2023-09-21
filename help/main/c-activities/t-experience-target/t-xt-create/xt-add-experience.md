---
keywords: créer une expérience;création d’une expérience;priorité;audience;expérience;compositeur d’expérience visuelle
description: Découvrez comment utiliser le [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour créer et modifier des expériences sur votre page dans une [!UICONTROL Ciblage d’expérience] (XT).
title: Comment créer des expériences dans une [!UICONTROL Ciblage d’expérience] Activité ?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 39%

---

# Création d’une expérience dans [!UICONTROL Ciblage d’expérience] Activités (XT)

La variable [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] fournit une interface visuelle pour la modification des expériences de votre page dans une [!UICONTROL Ciblage d’expérience] (XT).

1. Sélectionnez les éléments à modifier et apportez les modifications souhaitées.

   while [création d’un [!UICONTROL Ciblage d’expérience] activité](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), l’étape 1 du processus assisté en trois parties ([!UICONTROL Expériences]) affiche la valeur par défaut [!UICONTROL Expérience A] avec un [!UICONTROL Tous les visiteurs] audience.

   ![Audience Tous les visiteurs](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Les modifications que vous apportez maintenant s’appliquent à [!UICONTROL Expérience A]. Dans une étape ci-dessous, cliquez sur **[!UICONTROL Ajout du ciblage d’expérience]** pour créer d’autres expériences.

   Lorsque vous placez le pointeur de la souris sur les éléments de votre page, ceux-ci sont mis en surbrillance. Vous pouvez modifier un élément en surbrillance à l’aide du VEC. Pour obtenir la liste des actions pouvant être exécutées sur un élément pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez désactiver JavaScript pour modifier ces éléments à l’aide du VEC.

1. Pour créer d’autres expériences, cliquez sur **[!UICONTROL Ajouter un ciblage d’expérience]**.

   ![Lien Ajouter un ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   La variable [!UICONTROL Ajouter une audience] s’affiche. Pour cibler une expérience sur une audience, sélectionnez l’audience avant d’ajouter l’expérience.

   La bibliothèque d’audiences contient les audiences qui ont été précédemment définies ainsi que les audiences courantes préconfigurées dans [!DNL Target]. Vous pouvez sélectionner une audience dans la bibliothèque ou [créer une audience](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Lors de la création d’une audience, vous pouvez sélectionner un emplacement et spécifier des paramètres pour cet emplacement. Sous [!UICONTROL Personnalisé] ([!UICONTROL Création d’une audience] > [!UICONTROL Personnalisé]), sélectionnez l’emplacement, puis spécifiez les paramètres souhaités.

   >[!NOTE]
   >
   >Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste d’audiences et que les audiences importées ont plus de dix minutes.

1. Sélectionnez une ou plusieurs audiences à cibler avec l’expérience, puis cliquez sur **[!UICONTROL Terminé]**.

   ![Expérience B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   L’expérience B s’affiche désormais dans l’illustration précédente et cette expérience est ciblée sur l’audience Visiteurs E.U.

1. Sélectionnez les éléments à modifier pour cette expérience et apportez les modifications souhaitées, comme expliqué à l’étape 1 ci-dessus.

1. Répétez les étapes précédentes pour créer d’autres expériences ciblées, si nécessaire.

1. Cliquez sur **[!UICONTROL Suivant]** lorsque vous avez terminé de concevoir vos expériences.

   Le diagramme des activités affiche :

   ![Diagramme de ciblage XT](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Vous pouvez diffuser une image à partir d’une source autre que votre page principale (telle qu’une image hébergée sur `akamai.net` et remis le `adobe.com`). Les images hébergées ailleurs ne s’affichent pas dans la miniature de la page dans le diagramme de flux.

1. (Conditionnel) Faites glisser des paires audience et expérience lors de la création ou de la modification. [!UICONTROL Ciblage d’expérience] activités pour organiser les paires dans l’ordre souhaité.

   Les expériences des visiteurs sont évaluées dans l’ordre, du haut vers le bas.

   ![Déplacement d’expériences](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL Le ciblage d’expérience présume que l’ordre est important. ] Si un visiteur appartient à la première paire audience/expérience, la première expérience est diffusée.

   Supposons, par exemple, que vous ne sachiez pas que l’ordre est important lors de la création d’un [!UICONTROL Ciblage d’expérience] activité. Vous réalisez, par la suite, durant les tests, que les visiteurs que vous pensiez qualifiés pour les expériences B ou C sont en fait qualifiés pour l’expérience A. Cela peut être dû au fait que les audiences ne s’excluent pas mutuellement et ne sont pas dans le bon ordre (par exemple, expérience A = États-Unis, expérience B = San Francisco et expérience C = Californie). Dans ce scénario, tous les utilisateurs des États-Unis sont qualifiés pour l’expérience A, même s’ils se trouvent à San Francisco ou ailleurs en Californie. Vous pouvez réorganiser les paires audience et expérience de la plus restrictive à la moins restrictive (San Francisco > Californie > États-Unis) sans recréer l’ensemble de l’activité.

   Si vous avez une audience [!UICONTROL Tous les visiteurs], assurez-vous qu’il ne s’agit pas de la première audience sur le diagramme. Une expérience ciblée sur &quot;[!UICONTROL Tous les visiteurs]&quot; peut être utilisé comme dernière expérience dans la variable [!UICONTROL Ciblage d’expérience] pour &quot;rattraper&quot; les visiteurs qui n’ont pas été dirigés vers une autre expérience.

## Renommer ou modifier une expérience

Vous pouvez cliquer sur le bouton [!UICONTROL Modifier] Icône (points de suspension verticaux) sur une expérience dans une [!UICONTROL Ciblage d’expérience] et choisissez l’une des options suivantes, selon les besoins :

* [!UICONTROL Renommer]
* [!UICONTROL Modifier]

![Options Renommer et Modifier](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Suppression d’une expérience

Sur le **[!UICONTROL Expériences]** (la première étape du processus assisté en trois étapes), cliquez sur les points de suspension verticaux > **[!UICONTROL Supprimer]**.

![Suppression d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplication d’une expérience

Vous pouvez copier une expérience dans une [!UICONTROL Ciblage d’expérience] afin que vous puissiez y apporter des modifications mineures sans avoir à recréer l’expérience entière.

Sur le **[!UICONTROL Expériences]** (la première étape du processus assisté en trois étapes), cliquez sur les points de suspension verticaux > **[!UICONTROL Dupliquer]**.

![Duplication d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vidéos de formation :

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Des tests A/B aux tests [!UICONTROL Ciblage d’expérience]

Cette vidéo explique comment passer le test A/B au niveau suivant avec [!UICONTROL Ciblage d’expérience] (XT).

* décrire le processus assisté en trois étapes pour configurer une [!UICONTROL Ciblage d’expérience] activité
* Décrire comment diffuser du contenu spécifique à un emplacement à des audiences dans différentes zones géographiques
* Décrire comment réorganiser les expériences afin de garantir que le bon contenu est diffusé à la bonne audience

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Types d’activité (9:03)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target]. [!UICONTROL Le ciblage d’expérience est abordé dans la vidéo à partir de 5:15.]

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### En utilisant la variable [!UICONTROL Compositeur d’expérience visuelle]

Cette vidéo fournit des informations sur l’utilisation de la fonction [!UICONTROL Ciblage d’expérience] (VEC).

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/17399)
