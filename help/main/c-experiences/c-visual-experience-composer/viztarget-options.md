---
keywords: options du compositeur d’expérience visuelle;options du compositeur d’expérience;options d’expérience;modifier le texte;modifier le html;modifier le texte/html;modifier la couleur d’arrière-plan;insérer un élément;modifier le lien;lien du compositeur d’expérience visuelle;modifier la classe css;modifier la classe css;permuter l’offre;permuter l’image;permuter l’image;supprimer l’élément;supprimer l’élément;masquer l’élément;réorganiser;déplacer l’élément;redimensionner l’élément;redimensionner l’élément;développer l’élément;élargir la sélection;naviguer sur le lien;naviguer;lien;annuler;lien;annuler;rétablir;annuler;annuler;annuler;annuler;annuler les événements personnalisés;événements personnalisés;événements personnalisés;composants web
description: Explorez les options disponibles dans le  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).
title: Comment utiliser les options du [!UICONTROL Visual Experience Composer] (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: b1bde455f686c34e7a5184868ce63db0b74e2af7
workflow-type: tm+mt
source-wordcount: '1998'
ht-degree: 8%

---

# Options du compositeur d’expérience visuelle

La version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique l’interface utilisateur mise à jour et ses options.

>[!TIP]
>
>Pour découvrir en quoi le compositeur d’expérience visuelle mis à jour diffère du compositeur d’expérience visuelle hérité, consultez [Modifications du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md).

>[!IMPORTANT]
>
>La [!UICONTROL Visual Editing Composer] mise à jour nécessite l’extension [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponible sur le [!DNL Chrome Web Store].

Le compositeur d’expérience visuelle s’affiche lorsque vous créez ou modifiez une activité existante.

![Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## Présentation de l’interface utilisateur du compositeur d’expérience visuelle

Les sections suivantes expliquent les options disponibles dans le VEC mis à jour pour une activité [!UICONTROL A/B Test]. Les options disponibles varient en fonction du type d’activité.

### rail [!UICONTROL Experiences]

Le rail [!UICONTROL Experiences] s’affiche dans le rail gauche du compositeur d’expérience visuelle.

![Rail Expériences](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Vous pouvez afficher, créer, renommer ou supprimer des expériences à l’aide du rail de [!UICONTROL Experiences].

Les options suivantes sont disponibles dans le rail de [!UICONTROL Experiences] :

* **Afficher une expérience** : pour afficher une expérience, cliquez sur l’expérience souhaitée pour l’afficher dans la zone de travail de [!UICONTROL Design].
* **Ajouter une expérience** : cliquez sur l’icône **[!UICONTROL Add]** ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ) pour ajouter une nouvelle expérience. Configurez la nouvelle expérience selon vos besoins.
* **Renommer une expérience** : cliquez sur l’icône **[!UICONTROL Rename]** ( ![Icône Renommer](/help/main/assets/icons/Rename.svg) ) pour afficher la boîte de dialogue [!UICONTROL Rename Experience]. Indiquez le nouveau nom, puis cliquez sur **[!UICONTROL Save]**.
* **Dupliquer, supprimer ou rediriger une expérience** : cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmall.svg) ), puis choisissez **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]** ou **[!UICONTROL Redirect to URL]**.

### Paramètres/configuration de l’activité {#settings}

Cliquez sur l’icône [!UICONTROL Configure] ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ) affichée en haut de la zone de travail [!UICONTROL Design] pour afficher le menu des propriétés de l’activité.

![Options de configuration des activités](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Les options disponibles sont les suivantes :

* **[!UICONTROL Properties]** : attribuez des propriétés à l’activité ou supprimez des propriétés de l’activité. [!UICONTROL Properties] est une fonctionnalité ([[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)). Pour plus d’informations, voir [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).
* **[!UICONTROL Page Delivery]** : incluez la même expérience sur des pages similaires de votre site. Utilisez un modèle de page pour structurer vos pages, ou si vos pages contiennent des éléments similaires, pour tester des variations dans des éléments de page à structure similaire ou sur l’ensemble de votre domaine. Pour plus d’informations, voir [Inclure la même expérience sur des pages similaires](/help/main/c-experiences/c-visual-experience-composer/temtest.md).
* **[!UICONTROL Site Preferences]** : configurez les préférences de votre site pour spécifier comment [!DNL Target] génère les sélecteurs CSS. Pour plus d’informations, voir _Sélecteurs CSS_ dans [Configuration du [!UICONTROL Visual Experience Composer]](/help/main/administrating-target/visual-experience-composer-set-up.md).
* **Ajouter des pages supplémentaires** : ajoutez des pages supplémentaires à l’activité pour créer une activité multipage qui vous permet de créer une histoire sur plusieurs pages, avec une conception spécifique à chaque page. Pour plus d’informations, voir [Activité multipage](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md).
* **Audience unique** : utilisez une audience unique pour l’activité.
* **Audiences multiples** : attribuez plusieurs audiences à l’activité. Cliquez sur l’icône Ajouter des audiences ( ![icône Ajouter](/help/main/assets/icons/Add.svg) ), puis sélectionnez une ou plusieurs audiences dans la liste. Vous pouvez également [combiner des audiences](/help/main/c-target/combining-multiple-audiences.md) ou [créer une audience](/help/main/c-target/c-audiences/create-audience.md) à partir de la boîte de dialogue [!UICONTROL Add Audiences].

### Modes [!UICONTROL Design]/[!UICONTROL Browse]

Utilisez les boutons (bascule) [!UICONTROL Design]/[!UICONTROL Browse] affichés au-dessus de la zone de travail de conception pour basculer entre le mode de conception et le mode de navigation.

![Boutons bascule Conception et navigation](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Utilisez le mode [!UICONTROL Browse] pour parcourir votre site et sélectionner la vue ou la page à mettre à jour. Revenez au mode [!UICONTROL Design] pour ajouter ou modifier vos modifications.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Vous pouvez annuler les modifications effectuées en cliquant sur l’icône [!UICONTROL Undo] ( ![Icône Annuler](/help/main/assets/icons/Undo.svg) ).

![Icône Annuler dans le VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Pour rétablir une action, développez le groupe de boutons Annuler/[!UICONTROL Redo] et choisissez [!UICONTROL Redo].

### rail [!UICONTROL Components]

Vous pouvez ajouter plusieurs composants à votre page web et les modifier selon vos besoins à l’aide du nouveau rail de [!UICONTROL Components].

![Rail Composants](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

>[!NOTE]
>
>Si le rail [!UICONTROL Modifications] s’affiche dans cette zone à la place du rail [!UICONTROL Components], cliquez sur l’icône **[!UICONTROL Show Components]** ( ![icône Afficher les composants](/help/main/assets/icons/Add.svg) ). L’icône [!UICONTROL Show Components] ( ![icône Afficher les composants](/help/main/assets/icons/Add.svg) ) et l’icône [!UICONTROL Show Modifications] ( ![rail Afficher les modifications](/help/main/assets/icons/History.svg) ) servent de bascule pour afficher les options appropriées.

Pour ajouter un nouveau composant à une expérience :

1. Cliquez sur le composant de votre choix à ajouter pour le mettre en surbrillance.

   Les composants disponibles sont regroupés dans des conteneurs logiques :

   * [!UICONTROL Basic]
      * [!UICONTROL Divider]
      * [!UICONTROL HTML]
      * [!UICONTROL Image]
   * [!UICONTROL Text]
      * [!UICONTROL Heading]
      * [!UICONTROL Paragraph]
      * [!UICONTROL Link]
   * [!UICONTROL Dynamic]
      * [[!UICONTROL Recommendation]](/help/main/c-recommendations/recommendations-as-an-offer.md)
      * [[!UICONTROL Experience Fragment]](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)
      * [[!UICONTROL HTML Offer]](/help/main/c-experiences/c-manage-content/manage-content.md)

1. Faites glisser le composant sur un élément de page existant dans la zone de travail [!UICONTROL Design].
1. Choisissez de remplacer l’élément sélectionné ou d’insérer le composant avant ou après l’élément sélectionné.

### rail [!UICONTROL Modifications]

Pour ouvrir le rail [!UICONTROL Modifications], cliquez sur l’icône [!UICONTROL Show Modifications] ( ![Afficher le rail Modifications](/help/main/assets/icons/History.svg) ) dans le rail [!UICONTROL Components].

![Rail Modifications](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>L’icône [!UICONTROL Show Components] ( ![icône Afficher les composants](/help/main/assets/icons/Add.svg) ) et l’icône [!UICONTROL Show Modifications] ( ![rail Afficher les modifications](/help/main/assets/icons/History.svg) ) servent de bascule pour afficher les options appropriées.

Le rail [!UICONTROL Modifications] affiche toutes les modifications apportées à votre page dans le [!UICONTROL Visual Experience Composer] (VEC) et vous permet d’effectuer des modifications supplémentaires (comme le sélecteur CSS, la mbox et le code personnalisé).

Cliquez sur l’icône **[!UICONTROL More Options]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) dans l’en-tête du rail pour ajouter une modification, supprimer toutes les modifications ou supprimer toutes les modifications non valides. Cliquez sur [!UICONTROL Select] pour effectuer des opérations en bloc : [!UICONTROL Apply to All Pages] ou [!UICONTROL Delete].

Cliquez sur l’icône **[!UICONTROL More Options]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) en regard de chaque modification pour afficher ses informations, supprimer la modification ou l’appliquer à d’autres vues.

### Zone de travail [!UICONTROL Design]

La zone de travail [!UICONTROL Design] vous permet de sélectionner des fenêtres d’affichage, notamment les options d’ajustement à l’écran, les [!UICONTROL Desktop], les [!UICONTROL Tablet], les [!UICONTROL Mobile Landscape] et les [!UICONTROL Mobile Portrait]. Par défaut, la zone de travail s’affiche sur la page à l’écran avec les fenêtres d’affichage définies dans la section [ Administration ](/help/main/administrating-target/visual-experience-composer-set-up.md).

![Options de fenêtre d’affichage](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

Vous pouvez également effectuer un zoom avant ou arrière en cliquant sur l’icône appropriée ( ![Icône de zoom avant](/help/main/assets/icons/ZoomIn.svg) ou ![Icône de zoom arrière](/help/main/assets/icons/ZoomOut.svg) ).

Lorsque vous cliquez sur un élément de page dans la zone de travail de [!UICONTROL Design], un menu affiche les options disponibles pour ce type d’élément. En outre, un chemin d’accès DOM s’affiche au bas de la page, ce qui vous permet de naviguer facilement dans la structure de la page.

Les différentes actions [!UICONTROL Visual Experience Composer] (VEC) sont regroupées dans des options de menu appropriées pour rendre votre tâche plus rapide et plus efficace :

![Menu Options du VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-options.png)

>[!NOTE]
>
>Les options disponibles dépendent du type d’activité et de l’élément que vous créez ou modifiez. Pour plus d’informations sur la modification des images et des offres dans une activité [!UICONTROL A/B Test], consultez la section [Modifier les éléments à l’aide de la zone de travail [!UICONTROL Design]](#design) ci-dessous.

### rail [!UICONTROL Properties]

Le rail [!UICONTROL Properties] vous permet de modifier les propriétés des éléments sélectionnés sur la page, qu’il s’agisse d’éléments HTML ou d’objets spécifiques à [!DNL Target], tels que des recommandations ou des offres.

![Rail Propriétés](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Cliquez sur les icônes en haut du rail pour modifier le code d’HTML ou supprimer, dupliquer ou masquer des éléments. Les modifications s’affichent dans le rail de [!UICONTROL Modifications].

Le rail [!UICONTROL Properties] est réductible dans le rail de droite. Cliquez sur l’icône [!UICONTROL Show/Hide Properties] ( ![icône Propriétés](/help/main/assets/icons/Propertie.svg) ) à droite du rail pour réduire ou afficher le rail [!UICONTROL Properties].

## Modification des éléments à l’aide de la zone de travail [!UICONTROL Design] {#design}

Les sections suivantes vous montrent comment modifier des images et du texte dans la zone de travail [!UICONTROL Design]. La zone de travail de conception, ainsi que les rails Composants, Modifications et Propriétés vous fournissent des outils puissants pour vous permettre de créer facilement des expériences pour vos activités.

### Options d’image

Si vous cliquez sur une image dans une activité [!UICONTROL A/B Test], le compositeur d’expérience visuelle ressemble à l’illustration suivante :

![compositeur d’expérience visuelle avec image sélectionnée](/help/main/c-experiences/c-visual-experience-composer/assets/vec-image.png)

Sélectionnez des composants dans le cadre [!UICONTROL Components] sur le côté gauche pour insérer les éléments suivants :

* De base (séparateur, HTML, image).
* Texte (titre, paragraphe, lien).
* Dynamique ([recommandation](/help/main/c-recommendations/recommendations-as-an-offer.md), [fragment d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), offre HTML).

Le menu en haut de l’image vous permet d’effectuer les opérations suivantes :

* Insérez un lien ( ![Icône Insérer un lien](/help/main/assets/icons/Link.svg) ).
* Modifiez l’image ( ![Icône Choisir l’image](/help/main/assets/icons/Images.svg) ).
* Ajoutez une personnalisation ( ![icône Ajouter un Personalization](/help/main/assets/icons/PersonalizationField.svg) ).
* Supprimez l’image ( ![icône de suppression](/help/main/assets/icons/Delete.svg) ).

Le volet [!UICONTROL Properties] sur le côté droit permet de configurer plus en détail les propriétés de l’image.

Les icônes situées en haut du cadre permettent d’effectuer les opérations suivantes :

* Modifiez l’HTML ( ![Icône Insérer une HTML](/help/main/assets/icons/Code.svg) ). Consultez [Modifier HTML](#html) ci-dessous pour plus d’informations.
* Dupliquez l’image ( ![icône Dupliquer](/help/main/assets/icons/Code.svg) ).
* Supprimez l’image ( ![icône de suppression](/help/main/assets/icons/Delete.svg) ).
* Masquez l’image ( ![Icône Masquer](/help/main/assets/icons/VisibilityOff.svg) ).

Les options du cadre de droite permettent d’effectuer les opérations suivantes :

* Modifiez la classe CSS.
* Configurez les propriétés de l’image (source, titre, texte secondaire).
* Modifiez l’URL du lien.
* Configurez la taille de l’image (hauteur et largeur). Cliquez sur [!UICONTROL Show Advanced Options] pour configurer la taille minimale et maximale, la largeur, la hauteur, le débordement et l’ajustement de l’objet de l’image.
* Configurez la position de l’image sur votre page (absolue, fixe, relative, statique ou rémanente).
* Configurez l’espacement de l’élément, y compris la marge et la marge intérieure.
* Configurez les effets de l’élément (opacité). Cliquez sur [!UICONTROL Show Advanced Options] pour configurer les valeurs de sépia, niveaux de gris, contraste, luminosité et flou de l’image. Vous pouvez également inverser ou faire pivoter l’image.
* Configurez les styles intégrés de l’image.

### Options de texte

Si vous cliquez sur du texte dans une activité [!UICONTROL A/B Test], le compositeur d’expérience visuelle ressemble à l’illustration suivante :

![compositeur d’expérience visuelle avec texte sélectionné](/help/main/c-experiences/c-visual-experience-composer/assets/vec-text.png)

Sélectionnez des composants dans le cadre [!UICONTROL Components] sur le côté gauche pour insérer les éléments suivants :

* De base (séparateur, HTML, image).
* Texte (titre, paragraphe, lien).
* Dynamique ([recommandation](/help/main/c-recommendations/recommendations-as-an-offer.md), [fragment d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), offre HTML).

Cliquez sur l’icône [!UICONTROL Show Modifications] ( ![icône Afficher les modifications](/help/main/assets/icons/History.svg) ) pour afficher les modifications apportées à l’expérience.

Le menu situé en haut de l’élément de texte vous permet d’effectuer les opérations suivantes :

* Configurer les propriétés du texte (niveau d’en-tête, paragraphe, guillemet ou espace)
* Sélectionnez la couleur du texte ( ![icône Couleur du texte](/help/main/assets/icons/TextColor.svg) )
* Configurez les attributs du texte (gras, italique, souligné ou barré) ( ![icône Choisir les attributs de texte](/help/main/assets/icons/Text.svg) ).
* Configurer l’alignement du texte (gauche, centre, droite, justifier) (![icône Alignement du texte](/help/main/assets/icons/TextAlignCenter.svg) ).
* Insérez un lien ( ![Icône Insérer un lien](/help/main/assets/icons/Link.svg) ).
* Remplacez le contenu par une offre HTML, [fragment d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) ou [recommandation](/help/main/c-recommendations/recommendations-as-an-offer.md).
* Modifiez l’HTML ( ![Icône Insérer une HTML](/help/main/assets/icons/Code.svg) ).
* Ajoutez une personnalisation ( ![icône Ajouter un Personalization](/help/main/assets/icons/PersonalizationField.svg) ).
* Supprimez l’image ( ![icône de suppression](/help/main/assets/icons/Delete.svg) ).

Le rail [!UICONTROL Properties] sur le côté droit permet de configurer plus en détail les propriétés du texte.

Les icônes situées en haut du cadre permettent d’effectuer les opérations suivantes :

* Modifiez l’HTML ( ![Icône Insérer une HTML](/help/main/assets/icons/Code.svg) ). Consultez [Modifier HTML](#html) ci-dessous pour plus d’informations.
* Dupliquez le texte ( ![icône Dupliquer](/help/main/assets/icons/Code.svg) ).
* Supprimez le texte ( ![icône de suppression](/help/main/assets/icons/Delete.svg) ).
* Masquez le texte ( ![Icône Masquer](/help/main/assets/icons/VisibilityOff.svg) ).

Les options du cadre de droite permettent d’effectuer les opérations suivantes :

* Modifiez la classe CSS.
* Configurez la couleur et l’image d’arrière-plan du texte.
* Configurer la typographie du texte (style d’en-tête, taille de police, épaisseur de police, hauteur de ligne, alignement, couleur du texte, style de texte (gras, italique, souligné ou barré)).
* Configurez les listes, y compris les listes à puces, numérotées ou A, B, C.
* Choisissez la couleur de la bordure.
* Configurez la taille de la zone de texte (hauteur et largeur). Cliquez sur [!UICONTROL Show Advanced Options] pour configurer la taille minimale et maximale de la zone de texte, sa largeur, sa hauteur, son débordement et l’ajustement de l’objet.
* Configurez la position de la zone de texte sur la page (absolue, fixe, relative, statique ou rémanente) et définissez le nombre de pixels à partir du haut, de la droite, du bas et de la gauche.
* Configurez l’espacement de l’élément, y compris la marge et la marge intérieure.
* Configurez les effets de l’élément (opacité). Cliquez sur [!UICONTROL Show Advanced Options] pour configurer les valeurs de sépia, niveaux de gris, contraste, luminosité et flou de l’image. Vous pouvez également inverser ou faire pivoter le texte.
* Configurez les styles intégrés.

## Modifier HTML

En plus du code HTML, vous pouvez modifier et insérer du code JavaScript personnalisé.

Plusieurs options de formatage de texte enrichi sont disponibles lors de la modification de texte et dans HTML pour les activités de [!UICONTROL A/B] et de [!UICONTROL Experience Targeting]. Vous pouvez choisir une police, sélectionner un style de police, modifier l’alignement du texte et accéder à d’autres options de mise en forme de texte standard. Lors de la modification d’HTML, vous pouvez basculer entre l’affichage du code et l’affichage de modification riche d’HTML.

Les balises HTML 5 suivantes peuvent être imbriquées :

| Baliser | Balises imbriquées autorisées |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

## Navigation dans les éléments à l’aide du chemin d’accès DOM {#dom-path}

Lorsque vous cliquez sur un élément de la page, le menu des options du VEC s’affiche. En outre, lorsque vous cliquez sur un élément, le chemin d’accès DOM correspondant s’affiche au bas de la page.

![Chemin d’accès DOM](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path-refresh.png)

Si le chemin d’accès DOM n’apparaît pas, cliquez sur l’icône [!UICONTROL Show DOM] ( ![Afficher l’icône DOM](/help/main/assets/icons/LayersBringToFront.svg) ).

Vous pouvez utiliser le chemin d’accès DOM pour afficher rapidement les informations sur l’élément sélectionné (type, ID et classe). Vous pouvez monter ou descendre le chemin d’accès DOM pour sélectionner l’élément souhaité.

<!--When you hover over the DOM path, a blue box highlights the corresponding element in the VEC. When you click the element, an orange box highlights the element and the VEC options menu displays, as explained above.-->

Vous pouvez facilement accéder à n’importe quel élément parent, frère ou enfant du VEC à l’aide du chemin d’accès DOM.

La fonction Chemin d’accès DOM est également disponible lorsque vous définissez le [suivi des clics](/help/main/c-activities/r-success-metrics/click-tracking.md).

## Informations supplémentaires sur l’interface utilisateur mise à jour

* [[!DNL Target Standard/Premium] Notes de mise à jour de la version 25.2.1 (17 février 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour [!UICONTROL Activities], [!UICONTROL Recommendations] et le [!UICONTROL Visual Experience Composer] (VEC).

* Notes de mise à jour de la version [[!DNL Target Standard/Premium] 25.1.1 (9 janvier 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour le [!UICONTROL Offers Library].

* [Présentation de l [!DNL Target] interface utilisateur ](/help/main/c-intro/understand-the-target-ui.md) : fournit un bref aperçu pour vous familiariser avec les [!DNL Target] et fournit des liens vers des informations plus détaillées et des instructions détaillées.

* [[!UICONTROL Visual Experience Composer] modifications ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) : la version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique les différences entre les versions héritées et mises à jour du compositeur d’expérience visuelle.

* [[!UICONTROL Visual Experience Composer] options ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) : cet article explique l’interface utilisateur du compositeur d’expérience visuelle mise à jour et ses options.

* [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md) : cette FAQ aborde les questions courantes sur la nouvelle interface utilisateur [!DNL Target] et le nouveau [!UICONTROL Visual Experience Composer] (VEC), y compris les modifications de navigation, les emplacements de fonctionnalités et l’obsolescence du bouton (bascule) de version temporaire de l’interface utilisateur. Que vous soyez spécialiste du marketing, développeur ou administrateur, cette FAQ vous aide à effectuer une transition en douceur et à tirer le meilleur parti de l’interface utilisateur mise à jour.

<!--## [!UICONTROL Edit]

The following options are available:

### [!UICONTROL Text/HTML] {#edit-text-html}

Change the HTML code for the element, such as the text for a text area, button, or link.

In addition to HTML code, you can edit and inject custom JavaScript.

Several rich text formatting options are available when editing text and HTML for [!UICONTROL A/B] and [!UICONTROL Experience Targeting] activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML.

The following HTML5 tags can be nested:

|Tag|Allowed Nested Tags|
| --- | --- |
|`<a>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>`|
|`<ins>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`|
|`<del>`|`<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>`|
|`<label>`|`<p>`|

### [!UICONTROL Background Color]

Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent.

**Note:** This option is not available for an element where a background image is set. 

### [!UICONTROL Styles] {#styles}

Use the [!UICONTROL Styles] panel to view or edit the value of existing styles for the selected element. You can also add additional styling.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] panel displays on the right side of the VEC. The panel contains a list of styles that lets you edit or add to the selected element. A real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

![Styles panel](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

As you apply different styles, you can always revert your changes by clicking the [!UICONTROL Revert] icon that displays at the top-right corner of the [!UICONTROL Styles] panel after you change any section. Clicking the [!UICONTROL Revert] icon reverts all changes on the current section's panel.

Expand each section to edit or add styles, as explained below. To save your changes, click the [!UICONTROL Back] icon at the top of the panel to return to the panel's main display, then click **[!UICONTROL Save]**. 

Blue dots on the main panel and next to each option on the various section panels indicate that you have changed the corresponding styles. This visual indicator makes it easy for you to review your changes before clicking [!UICONTROL Save].

>[!NOTE]
>
>Quick actions for layout changes, background color, resizing, and move are also available as separate actions in the VEC menu. These options can be used as separate actions or you can use the Styles menu, as explained here.

* **[!UICONTROL Background]**

  Change the background color and image.

  * Color (specify the color code or use the color picker)
  * Image (select an image from the image picker)
  * Image source (specify an external URL)
  * Attachment
    * Click the top drop-down list to select scroll, fixed, or local
    * Click the bottom drop-down list to select repeat, repeat-x, repeat-y, no-repeat, space, or round
  * Clip
    * Click the top drop-down list to select border-box, padding-box, content-box, or text
    * Click the bottom drop-down list to select auto audio or audio

* **[!UICONTROL Typography]**

  Change the typography of an element. Typography edits are quick and easy. 

  Although the rich text editor (Edit Text/HTML) is available for fine tuning, quick actions to change the entire element is available via this option. If you want to apply typography changes to only a part of the text (not to the full text), use the [rich text editor](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md). 

  You can edit the following typography styles:

  * [!UICONTROL Font size]
  * [!UICONTROL Font weight]
  * [!UICONTROL Font style]
  * [!UICONTROL Color] (specify the color code or use the color picker)
  * [!UICONTROL Word spacing]
  * [!UICONTROL Line height]
  * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Change the margin for the selected element. You can change the left, right, bottom, and top margins.

  Click the drop-down icon for each margin to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to set the margin or specify the number of pixels for each margin)

  Margin supports positive and negative values.

  Target also supports other size units, such as rem, pc, em. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Change the padding for the selected element. You can change the left, right, bottom, and top padding.

  Drag the slider to set the padding or specify the number of pixels for padding.

  Padding supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Border]**

  Click the border icons at the top of the panel to change the selected element's border.

  You can edit the following styles for each border (top, right, bottom, and left):

  * [!UICONTROL Border style] (none, hidden, dotted, dashed, solid, or double)
  * [!UICONTROL Border color] (specify the color code or use the color picker)
  * [!UICONTROL Border width] (drag the slider to select a border width or specify the width in pixels)

  Border supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Position]**

  Move the selected element from its current position. You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

  Click the [!UICONTROL Static] drop-down list to choose from the following position options:

  * [!UICONTROL Static]
  * [!UICONTROL Relative]
  * [!UICONTROL Absolute]
  * [!UICONTROL Sticky]
  * [!UICONTROL Fixed]

  Click the drop-down icon for each position to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to position the element or specify the number of pixels you want to move the element)

  Position supports positive and negative values.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Size]**

  Change the selected element's width and height.

  Click the drop-down icon next to [!UICONTROL Width] and [!UICONTROL Height] to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to size the element or specify the number of pixels for each dimension)

* **[!UICONTROL Filter]**

  Drag the slider for each filter option or specify the desired percentage:

  * [!UICONTROL Sepia]
  * [!UICONTROL Contrast]
  * [!UICONTROL Brightness]
  * [!UICONTROL GrayScale]
  * [!UICONTROL Blur]
  * [!UICONTROL Opacity]
  * [!UICONTROL Invert]
  *[!UICONTROL  Hue-rotate]
  * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  The real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

  The CSS Editor displays any changes that you make in the Styles panel. As shown in the illustration below, the font size, top border, and image size have been changed:

  ![CSS editor with changes](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Notice the blue dots next to the [!UICONTROL Typography], [!UICONTROL Border], and [!UICONTROL Size] options in the preceding illustration. These dots indicate that you have changed these sections. If you open these section panels, blue dots display next to the specific options that you changed.

  You can type your own code if your desired style is not available by default in the [!UICONTROL Styles].

  The CSS Editor shows details for the current session only. If you save changes and then reopen the editor, details about your previous change do not display in the editor, even if you select the same element again.

  >[!IMPORTANT]
  >
  >You can apply a background image using the CSS Editor, but it might cause flicker. Test your changes before deployment.

### [!UICONTROL CSS Class]

Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space.

Available for [!UICONTROL A/B], [!UICONTROL Automated Personalization], and [!UICONTROL Multivariate Test] activities.

### [!UICONTROL Link]

Change the URL in the link.

Use Edit Link to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the [!UICONTROL Visual Experience Composer] to apply the action on the other image element.

## [!UICONTROL Insert Before]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=fr){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert Before] and choose whether you want to insert an image, HTML, or text. The inserted element appears before the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=fr){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert After] and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=fr){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target.

During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL.

For example, the initial URL might look like the following example:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

After activity syncing, the delivery URL might look like the following example:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations supports Replace With in DIV, SECTION, and ARTICLE tags.

**Note:** Swapping images requires an Adobe Scene7 Publishing System Account.

### [!UICONTROL HTML Offer]

Select a different offer from the [!UICONTROL Content Library].

**Note:** HTML Offers are stored on [!DNL Target] servers.

An HTML offer can be up to 256 KB.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

The following options are available:

### [!UICONTROL Rearrange]

Drag the element to another location inside the same parent element or DIV. Other elements shift location to make space for the rearranged element.

**Note**: Click-tracking does not work on rearranged items.

Currently, certain VEC actions, such as [!UICONTROL Rearrange] and [!UICONTROL Move], assume that the sibling elements of the source and destination parent elements are completely loaded. If lazy loading occurs under the parent DOM elements (source or destination), these VEC actions can cause inconsistent behavior. We are working on a more reliable approach to make VEC actions work in lazy-loaded DOM elements. As a temporary workaround, you can use [!UICONTROL Custom Code] in these scenarios to render your experiences.

### [!UICONTROL Resize]

Resize an element on your page. When you select [!UICONTROL Resize], a handle appears in the bottom-right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio.

**Note:** Inline elements cannot be resized.

### [!UICONTROL Move] {#move}

Move elements on your page. Unlike the [!UICONTROL Rearrange] option, [!UICONTROL Move] does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support to ensure moved elements are not hidden behind other elements.)

In certain situations, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. An element cannot be moved outside of a container that has following CSS property: `overflow: hidden`.

See [!UICONTROL Rearrange] above for more information about inconsistent behavior with the [!UICONTROL Move] and [!UICONTROL Rearrange] actions due to lazy loading of DOM elements.

### [!UICONTROL Hide]

Hide the element. The white space remains, but the content is removed.

### [!UICONTROL Remove]

Remove the element. The white space behind the image is removed and the space where the element was is collapsed.

**Note:** Items within a "classic" mbox (an mbox created within a Target Classic campaign) cannot be removed using this option.

## [!UICONTROL Expand Section]

Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times.

## [!UICONTROL Navigate to Link]

Open the destination of the link.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone.

## Considerations {#considerations}

* If an offer contains HTML content, see "How at.js renders offers with HTML content" in [How at.js works](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=fr){target=_blank} for more information.

## Custom element support {#custom}

The VEC supports [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) to let you create and test personalized experiences and offers on custom elements and on elements inside custom elements. This functionality is available in the VEC for all [!DNL Target] activity types.

>[!NOTE]
>
>VEC support for custom elements is supported in [at.js version](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} 2.7.0 (or later){target=_blank}. Ensure that your website has the required version deployed. If you are using the [Visual Experience Composer helper extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), it must also have the required version of at.js deployed. The VEC options described above are not visible and available for use with non-supported versions of at.js.
>
>VEC support for custom elements is currently not supported with the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

Most VEC actions are supported on custom events and inside custom events, with the following exceptions: 

The following actions are not available on custom elements:

* [!UICONTROL Edit]
  * [!UICONTROL Text/HTML]
  * [!UICONTROL Link]
  * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

The following action is not available inside custom elements:

* [!UICONTROL Layout]
  * [!UICONTROL Rearrange]-->
