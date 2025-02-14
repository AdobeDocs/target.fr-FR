---
keywords: compositeur d’expérience visuelle;vec;wysiwyg
description: Découvrez les modifications introduites dans le Compositeur d’expérience visuelle (VEC) dans la version Adobe Target 25.2.1 (17 février 2025).
title: Quelles modifications ont été introduites dans le nouveau Compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 3aeac3344c2bbc2a44da80b5a359e55c9419b59b
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---

# [!UICONTROL Visual Experience Composer] changes

La version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique les différences entre les versions précédente et mise à jour du compositeur d’expérience visuelle.

>[!IMPORTANT]
>
>La [!UICONTROL Visual Editing Composer] mise à jour nécessite l’extension [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponible sur Chrome Web Store.

Le compositeur d’expérience visuelle s’affiche lorsque vous créez ou modifiez une activité existante.

![Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## Modifications majeures apportées au compositeur d’expérience visuelle

Les sections suivantes expliquent les modifications majeures apportées au VEC mis à jour par rapport à la version précédente.

### panneau [!UICONTROL Experiences]

Comme dans la version précédente, le panneau [!UICONTROL Experiences] reste sur le côté gauche du compositeur d’expérience visuelle. Impossible de réduire le panneau [!UICONTROL Experiences].

![ Panneau Expériences ](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Vous pouvez créer, renommer ou supprimer des expériences à l’aide du panneau [!UICONTROL Experiences]. Cliquez sur l’icône **[!UICONTROL Add]** ( ![icône Ajouter](/help/main/assets/icons/Add.svg) ) pour ajouter une nouvelle expérience. Cliquez sur l’icône [!UICONTROL More Actions] ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) pour dupliquer, supprimer ou rediriger une expérience.

### Panneau [!UICONTROL Components] (nouveau)

Vous pouvez ajouter plusieurs composants à votre page web et les modifier selon vos besoins à l’aide du nouveau panneau [!UICONTROL Components].

![ Panneau Composants ](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Pour ajouter un nouveau composant, faites-le glisser depuis le panneau Composants à insérer sur un élément de page existant dans la zone de travail de conception. Choisissez ensuite d’insérer le composant avant ou après l’élément sélectionné.

Par rapport à la version précédente du compositeur d’expérience visuelle, vous ne pouvez pas remplacer un élément sélectionné par un composant.

### panneau [!UICONTROL Modifications]

Pour ouvrir le panneau [!UICONTROL Modifications], cliquez sur l’icône [!UICONTROL Show Modifications] ( ![Afficher le panneau Modifications](/help/main/assets/icons/History.svg) ) dans le panneau [!UICONTROL Components]. Le panneau [!UICONTROL Modifications] a changé de position du côté droit au côté gauche de la zone de travail de modification.

![Panneau Modifications](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

Le panneau [!UICONTROL Modifications] affiche toutes les modifications apportées à votre page dans le [!UICONTROL Visual Experience Composer] (VEC) et vous permet d’effectuer des modifications supplémentaires (comme le sélecteur CSS, la mbox et le code personnalisé).

Cliquez sur l’icône [!UICONTROL More Options] ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) pour ajouter une modification, supprimer toutes les modifications ou supprimer toutes les modifications non valides. Cliquez sur [!UICONTROL Select] pour effectuer des opérations en bloc : [!UICONTROL Apply to All Pages] ou [!UICONTROL Delete].

### Panneau [!UICONTROL Properties] (nouveau)

Le nouveau panneau [!UICONTROL Properties] vous permet de modifier les propriétés des éléments sélectionnés de la page, qu’il s’agisse d’éléments HTML ou d’objets spécifiques à [!DNL Target], tels que des recommandations ou des offres.

![Panneau Propriétés](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Cliquez sur les icônes en haut du panneau pour modifier le code d’HTML ou supprimer, dupliquer ou masquer des éléments. Les modifications s’affichent dans le panneau [!UICONTROL Modifications].

Le panneau [!UICONTROL Properties] est réductible dans le rail de droite. Cliquez sur l’icône [!UICONTROL Show/Hide Properties] ( ![icône Propriétés](/help/main/assets/icons/Propertie.svg) ) à droite du panneau pour réduire ou afficher le panneau [!UICONTROL Properties].

### Paramètres/configuration de l’activité

Cliquez sur l’icône [!UICONTROL Configure] ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ) affichée en haut de la zone de travail de conception pour afficher le menu des propriétés de l’activité.

![Options de configuration des activités](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Les différentes options vous permettent d’activer ou de désactiver les activités à plusieurs pages ou à audiences multiples, d’attribuer des propriétés (fonctionnalité de [[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)) ou de modifier les règles de diffusion de page.

La position et la fonctionnalité sont similaires à celles de l’interface utilisateur du compositeur d’expérience visuelle précédente.

### Modes [!UICONTROL Design]/[!UICONTROL Browse]

Utilisez les boutons (bascule) [!UICONTROL Design]/[!UICONTROL Browse] affichés au-dessus de la zone de travail de conception pour basculer entre le mode de conception et le mode de navigation.

![Boutons bascule Conception et navigation](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Utilisez le mode [!UICONTROL Browse] pour parcourir votre site et sélectionner la vue ou la page à mettre à jour. Revenez au mode [!UICONTROL Design] pour ajouter ou modifier vos modifications.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Vous pouvez annuler les modifications effectuées en cliquant sur l’icône [!UICONTROL Undo] ( ![Icône Annuler](/help/main/assets/icons/Undo.svg) ).

![Icône Annuler dans le VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Pour rétablir une action, développez le groupe de boutons Annuler/[!UICONTROL Redo] et choisissez [!UICONTROL Redo].

### Zone de travail [!UICONTROL Design]

La zone de travail [!UICONTROL Design] vous permet de sélectionner des fenêtres d’affichage, notamment les options d’ajustement à l’écran, les [!UICONTROL Desktop], les [!UICONTROL Tablet], les [!UICONTROL Mobile Landscape] et les [!UICONTROL Mobile Portrait]. Par défaut, la zone de travail s’affiche sur la page à l’écran avec les fenêtres d’affichage définies dans la section [ Administration ](/help/main/administrating-target/visual-experience-composer-set-up.md).

![Options de fenêtre d’affichage](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

Le compositeur d’expérience visuelle mis à jour vous permet également d’effectuer un zoom avant ou arrière en cliquant sur l’icône appropriée ( ![icône de zoom avant](/help/main/assets/icons/ZoomIn.svg) ou ![icône de zoom arrière](/help/main/assets/icons/ZoomOut.svg) ).

## Illustration visuelle montrant les modifications de l’interface utilisateur

L’illustration suivante présente les modifications de haut niveau de l’interface utilisateur apportées au VEC mis à jour. La partie supérieure de l’illustration présente l’interface utilisateur du compositeur d’expérience visuelle mise à jour et la partie inférieure l’interface utilisateur précédente. Les flèches indiquent l’endroit où divers éléments ont été déplacés.

(Cliquez sur l’image pour la développer sur toute la largeur du navigateur.)

![Comparaison du compositeur d’expérience visuelle - nouveau par rapport à l’interface utilisateur précédente](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}
