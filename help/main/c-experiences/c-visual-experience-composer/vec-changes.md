---
keywords: compositeur d’expérience visuelle;vec;wysiwyg
description: Découvrez les modifications introduites dans le Compositeur d’expérience visuelle (VEC) dans la version Adobe Target 25.2.1 (17 février 2025).
title: Quelles modifications ont été introduites dans le nouveau Compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 2dabda04aabe720b28e31033052e2076e78d1376
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] changes

La version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique les différences entre les versions précédente et mise à jour du compositeur d’expérience visuelle.

>[!IMPORTANT]
>
>La [!UICONTROL Visual Editing Composer] mise à jour nécessite l’extension [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponible dans la [!DNL Chrome Web Store].

Le compositeur d’expérience visuelle s’affiche lorsque vous créez ou modifiez une activité existante.

![Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Modifications majeures apportées au compositeur d’expérience visuelle

Les sections suivantes expliquent les modifications majeures apportées au VEC mis à jour par rapport à la version précédente.

### rail [!UICONTROL Experiences]

Comme dans la version précédente, le rail [!UICONTROL Experiences] reste sur le côté gauche du compositeur d’expérience visuelle. Impossible de réduire le rail [!UICONTROL Experiences].

![Rail Expériences](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Vous pouvez créer, renommer ou supprimer des expériences à l’aide du rail de [!UICONTROL Experiences]. Cliquez sur l’icône **[!UICONTROL Add]** ( ![icône Ajouter](/help/main/assets/icons/Add.svg) ) pour ajouter une nouvelle expérience. Cliquez sur l’icône [!UICONTROL More Actions] ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) pour dupliquer, supprimer ou rediriger une expérience.

### rail [!UICONTROL Components] (nouveau)

Vous pouvez ajouter plusieurs composants à votre page web et les modifier selon vos besoins à l’aide du nouveau rail de [!UICONTROL Components].

![Rail Composants](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Pour ajouter un nouveau composant, sélectionnez le composant de votre choix dans le rail de [!UICONTROL Components], passez la souris sur un élément existant de la page, puis choisissez d’insérer le composant avant ou après l’élément sélectionné.

>[!NOTE]
>
>Si le rail [!UICONTROL Modifications] s’affiche dans cette zone à la place du rail [!UICONTROL Components], cliquez sur l’icône **[!UICONTROL Show Components]** ( ![icône Afficher les composants](/help/main/assets/icons/Add.svg) ). L’icône [!UICONTROL Show Components] ( ![icône Afficher les composants](/help/main/assets/icons/Add.svg) ) et l’icône [!UICONTROL Show Modifications] ( ![rail Afficher les modifications](/help/main/assets/icons/History.svg) ) servent de bascule pour afficher les options appropriées.
>
>Pour réduire le rail de [!UICONTROL Components] et agrandir la zone de travail de [!UICONTROL Design], alors que le rail de [!UICONTROL Components] est ouvert, cliquez sur l’icône ( ![icône Afficher les composants](/help/main/assets/icons/Add.svg) ).

### rail [!UICONTROL Modifications]

Pour ouvrir le rail [!UICONTROL Modifications], cliquez sur l’icône [!UICONTROL Show Modifications] ( ![Afficher le rail Modifications](/help/main/assets/icons/History.svg) ) dans le rail [!UICONTROL Components]. Le rail de [!UICONTROL Modifications] a changé de position du côté droit au côté gauche de la zone de travail de modification.

![Rail Modifications](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>L’icône [!UICONTROL Show Components] ( ![icône Afficher les composants](/help/main/assets/icons/Add.svg) ) et l’icône [!UICONTROL Show Modifications] ( ![rail Afficher les modifications](/help/main/assets/icons/History.svg) ) servent de bascule pour afficher les options appropriées.
>
>Pour réduire le rail de [!UICONTROL Modifications] et agrandir la zone de travail de [!UICONTROL Design], alors que le rail de [!UICONTROL Modifications] est ouvert, cliquez sur l’icône [!UICONTROL Show Modifications] ( ![Afficher le rail des modifications](/help/main/assets/icons/History.svg) ).

Le rail [!UICONTROL Modifications] affiche toutes les modifications apportées à votre page dans le VEC et vous permet d’effectuer des modifications supplémentaires (comme le sélecteur CSS, la mbox et le code personnalisé).

Cliquez sur l’icône [!UICONTROL More Options] ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) pour ajouter une modification, supprimer toutes les modifications ou supprimer toutes les modifications non valides. Cliquez sur [!UICONTROL Select] pour effectuer des opérations en bloc : [!UICONTROL Apply to All Pages] ou [!UICONTROL Delete].

Pour afficher à nouveau le rail [!UICONTROL Modifications], cliquez sur l’icône [!UICONTROL Hide Modifications] ( ![Afficher le rail Modifications](/help/main/assets/icons/History.svg) ) dans le rail [!UICONTROL Modifications].

### rail [!UICONTROL Properties] (nouveau)

Le rail [!UICONTROL Properties] vous permet de modifier les propriétés des éléments sélectionnés sur la page, qu’il s’agisse d’éléments HTML ou d’objets spécifiques à [!DNL Target], tels que des recommandations ou des offres.

![Rail Propriétés](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Cliquez sur les icônes en haut du rail pour modifier le code d’HTML ou supprimer, dupliquer ou masquer des éléments. Les modifications s’affichent dans le rail de [!UICONTROL Modifications].

![Icônes de propriété](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

Le rail [!UICONTROL Properties] est réductible dans le rail de droite. Cliquez sur l’icône [!UICONTROL Show/Hide Properties] ( ![icône Propriétés](/help/main/assets/icons/Propertie.svg) ) à droite du rail pour réduire ou afficher le rail [!UICONTROL Properties].

### Paramètres/configuration de l’activité

Cliquez sur l’icône [!UICONTROL Configure] ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ) affichée en haut de la zone de travail de conception pour afficher le menu des propriétés de l’activité.

![Options de configuration des activités](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Les différentes options vous permettent d’attribuer des propriétés, de modifier les règles de diffusion des pages, de spécifier les préférences du site, d’ajouter des pages supplémentaires et d’activer ou de désactiver les activités à plusieurs pages ou à plusieurs audiences. L’affectation de [!UICONTROL Properties] est une fonctionnalité [[!DNL Target Premium]](/help/main/c-intro/intro.md#premium).

La position et la fonctionnalité sont similaires à celles de l’interface utilisateur du compositeur d’expérience visuelle précédente.

### Modes [!UICONTROL Design]/[!UICONTROL Browse]

Utilisez les boutons (bascule) [!UICONTROL Design]/[!UICONTROL Browse] affichés en haut du rail de [!UICONTROL Properties] pour basculer entre le mode de conception et le mode de navigation.

![Boutons bascule Conception et navigation](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Utilisez le mode [!UICONTROL Browse] pour parcourir votre site et sélectionner la vue ou la page à mettre à jour. Revenez au mode [!UICONTROL Design] pour ajouter ou modifier vos modifications.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Vous pouvez annuler les modifications effectuées en cliquant sur l’icône [!UICONTROL Undo] ( ![Icône Annuler](/help/main/assets/icons/Undo.svg) ).

![Icône Annuler dans le VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Pour rétablir une action, développez le groupe de boutons Annuler/[!UICONTROL Redo] et choisissez [!UICONTROL Redo].

### Zone de travail [!UICONTROL Design]

La zone de travail [!UICONTROL Design] vous permet de sélectionner des fenêtres d’affichage, notamment les options d’ajustement à l’écran, les [!UICONTROL Desktop], les [!UICONTROL Tablet], les [!UICONTROL Mobile Landscape] et les [!UICONTROL Mobile Portrait].

![Options de fenêtre d’affichage](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

Le compositeur d’expérience visuelle mis à jour vous permet également d’effectuer un zoom avant ou arrière en cliquant sur l’icône appropriée ( ![icône de zoom avant](/help/main/assets/icons/ZoomIn.svg) ou ![icône de zoom arrière](/help/main/assets/icons/ZoomOut.svg) ).

## Illustration visuelle montrant les modifications de l’interface utilisateur

L’illustration suivante présente les modifications de haut niveau de l’interface utilisateur apportées au VEC mis à jour. La partie supérieure de l’illustration présente l’interface utilisateur du compositeur d’expérience visuelle mise à jour et la partie inférieure l’interface utilisateur précédente. Les flèches indiquent l’endroit où divers éléments ont été déplacés.

(Cliquez sur l’image pour la développer sur toute la largeur du navigateur.)

![Comparaison du compositeur d’expérience visuelle - nouveau par rapport à l’interface utilisateur précédente](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

## Informations supplémentaires sur l’interface utilisateur mise à jour

* [[!DNL Target Standard/Premium] Notes de mise à jour de la version 25.2.1 (17 février 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour [!UICONTROL Activities], [!UICONTROL Recommendations] et le [!UICONTROL Visual Experience Composer] (VEC).

* Notes de mise à jour de la version [[!DNL Target Standard/Premium] 25.1.1 (9 janvier 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour le [!UICONTROL Offers Library].

* [Présentation de l [!DNL Target] interface utilisateur &#x200B;](/help/main/c-intro/understand-the-target-ui.md) : fournit un bref aperçu pour vous familiariser avec les [!DNL Target] et fournit des liens vers des informations plus détaillées et des instructions détaillées.

* [[!UICONTROL Visual Experience Composer] modifications &#x200B;](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) : la version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2025) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique les différences entre les versions héritées et mises à jour du compositeur d’expérience visuelle.

* [[!UICONTROL Visual Experience Composer] options &#x200B;](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) : cet article explique l’interface utilisateur du compositeur d’expérience visuelle mise à jour et ses options.

* [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md) : cette FAQ aborde les questions courantes sur la nouvelle interface utilisateur [!DNL Target] et le nouveau [!UICONTROL Visual Experience Composer] (VEC), y compris les modifications de navigation, les emplacements de fonctionnalités et l’obsolescence du bouton (bascule) de version temporaire de l’interface utilisateur. Que vous soyez spécialiste du marketing, développeur ou administrateur, cette FAQ vous aide à effectuer une transition en douceur et à tirer le meilleur parti de l’interface utilisateur mise à jour.