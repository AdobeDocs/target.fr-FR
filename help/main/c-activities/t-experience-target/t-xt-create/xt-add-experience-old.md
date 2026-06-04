---
keywords: créer une expérience;création d’une expérience;priorité;audience;expérience;compositeur d’expérience visuelle
description: Découvrez comment utiliser le  [!DNL Adobe Target] [!UICONTROL compositeur d’expérience visuelle] (VEC) pour créer et modifier des expériences sur votre page dans une activité de [!UICONTROL ciblage d’expérience] (XT).
title: Comment créer des expériences dans une activité de [!UICONTROL ciblage d’expérience] ?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 32%

---

# Créer une expérience dans des activités [!UICONTROL Ciblage d’expérience] (XT)

Le [!UICONTROL compositeur d’expérience visuelle] (VEC) d’[!DNL Adobe Target] fournit une interface visuelle permettant de modifier les expériences de votre page dans une activité de [!UICONTROL ciblage d’expérience] (XT).

1. Sélectionnez les éléments à modifier et apportez les modifications souhaitées.

   Lors de la [création d’une activité [!UICONTROL Ciblage d’expérience]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), la première étape du workflow guidé en trois parties ([!UICONTROL Expériences]) affiche l’audience par défaut [!UICONTROL Experience A] avec une audience [!UICONTROL Tous les visiteurs].

   ![Audience Tous les visiteurs](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Toutes les modifications que vous apportez maintenant s’appliquent à [!UICONTROL Experience A]. Dans une étape ci-dessous, cliquez sur **[!UICONTROL Ajouter le ciblage d’expérience]** pour créer des expériences supplémentaires.

   Lorsque vous passez la souris sur les éléments de la page, les éléments sont mis en surbrillance. Vous pouvez modifier un élément en surbrillance à l’aide du VEC. Pour obtenir la liste des actions pouvant être exécutées sur un élément pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez désactiver JavaScript pour modifier ces éléments à l’aide du compositeur d’expérience visuelle.

1. Pour créer des expériences supplémentaires, cliquez sur **[!UICONTROL Ajouter le ciblage d’expérience]**.

   ![Lien Ajouter un ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   La boîte de dialogue [!UICONTROL Ajouter une audience] s’affiche. Pour cibler une expérience sur une audience, sélectionnez l’audience avant d’ajouter l’expérience.

   La bibliothèque d’audiences contient les audiences qui ont été précédemment définies ainsi que les audiences courantes préconfigurées dans [!DNL Target]. Vous pouvez sélectionner une audience dans la bibliothèque ou [créer une audience](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Lors de la création d’une audience, vous pouvez sélectionner un emplacement et spécifier des paramètres pour cet emplacement. Sous [!UICONTROL Personnalisé] ([!UICONTROL Créer une audience] > [!UICONTROL Personnalisé]), sélectionnez l’emplacement, puis spécifiez les paramètres souhaités.

   >[!NOTE]
   >
   >Les audiences importées sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste des audiences et qu’elles datent de plus de dix minutes.

1. Sélectionnez une ou plusieurs audiences à cibler avec l’expérience, puis cliquez sur **[!UICONTROL Terminé]**.

   ![Expérience B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   L’expérience B s’affiche désormais dans l’illustration précédente et cette expérience est ciblée sur l’audience des visiteurs aux États-Unis.

1. Sélectionnez les éléments à modifier pour cette expérience et apportez les modifications souhaitées, comme expliqué à l’étape 1 ci-dessus.

1. Répétez les étapes précédentes pour créer d’autres expériences ciblées, si nécessaire.

1. Cliquez sur **[!UICONTROL Suivant]** lorsque vous avez terminé de concevoir vos expériences.

   Le diagramme des activités affiche :

   ![Diagramme de ciblage XT](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Vous pouvez diffuser une image à partir d’une source autre que votre page principale (par exemple, une image hébergée sur `akamai.net` et diffusée sur `adobe.com`). Les images hébergées ailleurs ne s’affichent pas dans la miniature de la page affichée dans le diagramme de flux.

1. (Conditionnel) Effectuez un glisser-déposer des paires d’audience et d’expérience lors de la création ou de la modification des activités [!UICONTROL Ciblage d’expérience] pour organiser les paires dans l’ordre souhaité.

   Les expériences des visiteurs sont évaluées dans l’ordre, du haut vers le bas.

   ![Déplacement d’expériences](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   Le [!UICONTROL ciblage d’expérience] suppose que l’ordre importe. Si un visiteur appartient à la première paire audience-expérience, la première expérience est diffusée.

   Supposons, par exemple, que vous ne soyez pas conscient que l’ordre importe lors de la création d’une activité [!UICONTROL Ciblage d’expérience]. Vous réalisez, par la suite, durant les tests, que les visiteurs que vous pensiez qualifiés pour les expériences B ou C sont en fait qualifiés pour l’expérience A. Cela peut être dû au fait que les audiences ne s’excluent pas mutuellement et ne sont pas dans le bon ordre (par exemple, expérience A = États-Unis, expérience B = San Francisco et expérience C = Californie). Dans ce scénario, tous les utilisateurs originaires des États-Unis peuvent bénéficier de l’expérience A, même s’ils se trouvent à San Francisco ou ailleurs en Californie. Vous pouvez réorganiser les paires d’audience et d’expérience du plus restrictif au moins restrictif (San Francisco > Californie > États-Unis) sans recréer l’activité entière.

   Si vous avez une audience [!UICONTROL Tous les visiteurs], assurez-vous qu’elle n’est pas la première du diagramme. Une expérience ciblée sur « [!UICONTROL Tous les visiteurs] » peut être utilisée comme dernière expérience dans l’activité [!UICONTROL Ciblage d’expérience] pour « attraper » les visiteurs qui n’ont participé à aucune autre expérience.

## Renommer ou modifier une expérience

Vous pouvez cliquer sur l’icône [!UICONTROL Modifier] (les points de suspension verticaux) d’une expérience dans une activité [!UICONTROL Ciblage d’expérience] et choisir parmi les options suivantes, si nécessaire :

* [!UICONTROL Renommer]
* [!UICONTROL Modifier]

![Options Renommer et Modifier](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Suppression d’une expérience

Sur la page **[!UICONTROL Expériences]** (première étape du workflow guidé en trois étapes), cliquez sur les points de suspension verticaux > **[!UICONTROL Supprimer]**.

![Suppression d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplication d’une expérience

Vous pouvez copier une expérience dans une activité de [!UICONTROL ciblage d’expérience] afin d’y apporter des modifications mineures sans avoir à recréer l’expérience entière.

Sur la page **[!UICONTROL Expériences]** (première étape du workflow guidé en trois étapes), cliquez sur les points de suspension verticaux > **[!UICONTROL Dupliquer]**.

![Duplication d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vidéos de formation :

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Des tests A/B au [!UICONTROL ciblage d’expérience]

Cette vidéo décrit comment booster les tests A/B avec le [!UICONTROL ciblage d’expérience] (XT).

* Décrivez le workflow guidé en trois étapes pour configurer une activité [!UICONTROL Ciblage d’expérience]
* Décrire comment diffuser du contenu spécifique à un emplacement auprès d’audiences situées dans différentes zones géographiques
* Décrire comment réorganiser les expériences afin de garantir que le bon contenu est diffusé à la bonne audience

>[!VIDEO](https://video.tv.adobe.com/v/38301?captions=fre_fr)

### Types d’activités (9:03)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target]. La section [!UICONTROL Ciblage d’expérience] est abordée à partir de 5 :15.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/29340?captions=fre_fr)

### Utilisation du [!UICONTROL compositeur d’expérience visuelle]

Cette vidéo fournit des informations sur l’utilisation des options [!UICONTROL Ciblage d’expérience] (VEC).

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/29229?captions=fre_fr)
