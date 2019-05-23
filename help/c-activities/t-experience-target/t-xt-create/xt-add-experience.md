---
description: Le compositeur d’expérience fournit une interface visuelle pour la modification des expériences de votre page.
keywords: créer une expérience;création d’une expérience;priorité;audience;expérience;compositeur d’expérience visuelle
seo-description: Le compositeur d’expérience fournit une interface visuelle pour la modification des expériences de votre page.
seo-title: Création d’une expérience
solution: Target
title: Création d’une expérience
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: b1dd50db873cb9a7cdca976366171ddf0c02d156

---


# Création d’une expérience{#create-experience}

Le compositeur d’expérience fournit une interface visuelle pour la modification des expériences de votre page.

Pour plus d’informations sur les expériences, voir [Expériences](../../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Cliquez sur **[!UICONTROL Ajouter une expérience]**.

   >[!NOTE]
   >
   >Si vous ciblez une expérience vers une audience, vous devez sélectionner l’audience avant de pouvoir ajouter une expérience. Un message s’affiche pour vous rappeler de sélectionner l’audience.

1. A l’invite, saisissez l’URL de l’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Continuer]**.

   Le compositeur d’expérience (voir [Expériences](../../../c-experiences/experiences.md#concept_1D011219034B492BB03C08B3BB80E3F0)) ouvre la page spécifiée dans vos Préférences de compte. Pour afficher une autre page, cliquez sur l’icône Globe et entrez l’URL dans la zone Sélectionner une URL du Compositeur visuel d’expérience, puis cliquez sur **[!UICONTROL Continuer]**. Si vous avez saisi l’URL d’un site qui ne contient pas le code JavaScript de Target Standard, vous ne pouvez pas sélectionner d’éléments de page.

   Par défaut, le compositeur d’expérience visuelle n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez choisir de désactiver JavaScript si vous souhaitez pouvoir modifier ces éléments à l’aide du compositeur d’expérience visuelle.

   >[!NOTE]
   >
   >Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.

1. Sélectionnez les éléments que vous souhaitez modifier et apportez les modifications de votre choix.

   Lorsque vous pointez sur les éléments de votre page, ils sont mis en surbrillance. Vous pouvez modifier un élément en surbrillance à l’aide du Compositeur visuel d’expérience.

   Si vous créez une mbox sur la page à l’aide de Target Classic (anciennement Test&amp;Target), celle-ci apparaît comme un élément qui indique le nom de la mbox et qui peut être modifié comme tout autre élément.

   Pour obtenir la liste des actions pouvant être exécutées sur un élément de la page affichée pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Si vous publiez une image provenant d’une source autre que votre page principale (une image hébergée sur akamai.net et publiée sur dell.com, par exemple), cette image ne s’affiche pas dans la miniature de la page dans le diagramme de flux.

1. Cliquez sur le bouton représentant une coche lorsque vous avez terminé de concevoir l’expérience.

   Le diagramme des activités affiche :

   ![](assets/xt_diagram.png)

   S’il s’agit de contenu interdomaines, les miniatures peuvent ne pas s’afficher correctement et être remplacées par des icônes.
1. Créez d’autres expériences, selon les besoins.

   >[!NOTE]
   >
   >Vous pouvez glisser des paires audience / expérience lors de la création ou de la modification d’activités de ciblage d’expérience afin d’organiser les paires dans l’ordre souhaité. Les expériences des visiteurs seront évaluées dans l’ordre, du haut vers le bas.

   ![](assets/move_experiences.jpg)

   Le ciblage d’expérience présume que l’ordre est important. Si un visiteur appartient à la première paire audience/expérience, la première expérience est diffusée.

   Par exemple, supposons que vous ne sachiez pas que l’ordre est important lors de la création d’une activité de ciblage d’expérience. Vous réalisez, par la suite, durant les tests, que les visiteurs que vous pensiez qualifiés pour les expériences B ou C sont en fait qualifiés pour l’expérience A. Cela peut être dû au fait que les audiences ne s’excluent pas mutuellement et ne sont pas dans le bon ordre (par exemple, expérience A = États-Unis, expérience B = San Francisco et expérience C = Californie). Dans ce scénario, tous les utilisateurs des États-Unis sont qualifiés pour l’expérience A, même s’ils sont situés à San Francisco ou ailleurs en Californie. Vous pouvez réorganiser les paires audience/expérience de la plus restrictive à la moins restrictive (San Francisco &gt; Californie &gt; États-Unis) sans recréer toute l’activité.

## Modification du nom, modification ou suppression d’une expérience

Vous pouvez cliquer sur l’icône Modifier (trois points alignés verticalement) d’une expérience dans une activité de test A/B ou de ciblage d’expérience (XT) et choisir l’une des options suivantes, selon vos besoins :

* Renommer
* Modifier 
* Supprimer

![](assets/experience_edit.png)

Cliquez ensuite sur **[!UICONTROL Continuer]**.

## Duplication d’une expérience

Vous pouvez désormais copier une expérience dans une activité de ciblage d’expérience (XT) afin d’y apporter des changements mineurs, sans devoir la recréer de zéro.

Sur la page **[!UICONTROL Expériences]** (la première étape du processus assisté en trois étapes), cliquez sur les trois points alignés verticalement &gt; **[!UICONTROL Dupliquer]**.

![](assets/duplicate_experience.png)

## Vidéo de formation : utilisation du compositeur d’expérience visuelle

La vidéo ci-après fournit des informations sur l’utilisation des options du compositeur d’expérience visuelle.

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/17399)