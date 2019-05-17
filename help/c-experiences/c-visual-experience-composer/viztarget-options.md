---
description: Lorsque vous cliquez sur un élément de page dans le compositeur d'expérience visuelle, un menu affiche les options disponibles pour ce type d'élément.
keywords: options du compositeur d’expérience visuelle;options du compositeur d’expérience;options du compositeur;modifier le texte;modifier le code html;modifier le texte/code html;modifier la couleur d’arrière-plan;couleur d’arrière-plan;insérer un élément;modifier un lien;lien;lien du compositeur d’expérience visuelle;modifier la classe css;classe css;permuter l’offre;permutation de l’offre;permuter l’image;permutation d’image;supprimer un élément;suppression d’un élément;masquer un élément;masquage d’un élément;réorganiser;déplacer un élément;redimensionner un élément;redimensionnement d’un élément;élément;étendre la sélection;accéder à ce lien;accéder au lien;accès au lien;accéder;annuler;rétablir;annuler/rétablir
seo-description: Lorsque vous cliquez sur un élément de page dans le compositeur d'expérience visuelle d'Adobe Target, un menu affiche les options disponibles pour ce type d'élément.
seo-title: Options du compositeur d'expérience visuelle d'Adobe Target
solution: Target
title: Options du compositeur d’expérience visuelle
topic: Standard
uuid: efd672ae-c684-455f-8ec1-0efcfe1e9534
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Options du compositeur d’expérience visuelle{#visual-experience-composer-options}

Lorsque vous cliquez sur un élément de page dans le compositeur d&#39;expérience visuelle, un menu affiche les options disponibles pour ce type d&#39;élément. En outre, un chemin DOM s&#39;affiche au bas de la page, ce qui vous permet de naviguer facilement dans la structure de la page.

## Options du compositeur d&#39;expérience visuelle

Les différentes actions du compositeur d&#39;expérience visuelle (VEC) sont des options de menu appropriées pour rendre votre travail plus rapide et plus efficace :

![Menu Options du compositeur d&#39;expérience visuelle](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>Les options disponibles dépendent du type d’activité que vous êtes en train de modifier.

### Modifier 

Les options disponibles sont les suivantes :

#### Texte/Code HTML {#edit-text-html}

Permet de modifier le code HTML de l’élément (texte d’une zone de texte, bouton ou lien, par exemple).

En plus du code HTML, vous pouvez modifier et insérer du code JavaScript personnalisé.

Plusieurs options de mise en forme de texte enrichi sont disponibles lors de l’édition de texte et de code HTML pour les activités [!UICONTROL A/B] et de [!UICONTROL ciblage d’expérience]. Vous pouvez choisir une police, sélectionner un style de police, modifier l’alignement du texte et accéder à d’autres options de mise en forme de texte standard. Lors de la modification de code HTML, vous pouvez basculer entre l’affichage du code et l’affichage de texte enrichi du code HTML.

Les balises HTML 5 suivantes peuvent être imbriquées :

| Baliser | Balises imbriquées autorisées |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

#### Couleur d’arrière-plan

Utilisez le sélecteur de couleurs pour sélectionner ou définir une couleur d’arrière-plan. Vous pouvez sélectionner un échantillon de couleur et l’ajuster à l’aide des valeurs RVB ou des codes couleur hexadécimaux. La croix rouge dans le sélecteur de couleurs rend l’arrière-plan transparent.

**Remarque :** Cette option n’est pas disponible pour les éléments avec des images d’arrière-plan.

#### Styles

Utilisez le panneau [!UICONTROL Styles] pour afficher ou modifier la valeur des styles existants pour l&#39;élément sélectionné. Vous pouvez également ajouter d&#39;autres styles.

Pour accéder au panneau [!UICONTROL Styles] , cliquez sur un élément de page dans le compositeur d&#39;expérience visuelle, puis cliquez **[!UICONTROL sur Edition]** &gt; **[!UICONTROL Styles]**.

Le panneau [!UICONTROL Styles] s&#39;affiche sur le côté droit du compositeur d&#39;expérience visuelle. Le panneau contient une liste de styles qui vous permet de modifier ou d&#39;ajouter à l&#39;élément sélectionné. Un éditeur CSS en temps réel permet d&#39;afficher les modifications et d&#39;ajouter des styles si vous maîtrisez l&#39;utilisation de feuilles de style en cascade (CSS) ou si vous recevez du code de votre développeur.

![Panneau Styles](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

Lorsque vous appliquez des styles différents, vous pouvez toujours annuler vos modifications en cliquant sur l&#39;icône [!UICONTROL Rétablir] qui s&#39;affiche dans le coin supérieur droit du panneau [!UICONTROL Styles] après avoir apporté une modification à n&#39;importe quelle section. Notez que le fait de cliquer sur l&#39;icône [!UICONTROL Rétablir] rétablit toutes les modifications dans le panneau de la section active.

Développez chaque section pour modifier ou ajouter des styles, comme expliqué ci-dessous. Pour enregistrer vos modifications, cliquez sur l&#39;icône Précédent dans la partie supérieure du panneau pour revenir à l&#39;affichage principal du panneau, puis cliquez **[!UICONTROL sur Enregistrer]**.

Notez que les points bleus du panneau principal et en regard de chaque option des différents panneaux de section indiquent que vous avez apporté des modifications aux styles correspondants. Cela vous facilite la révision des modifications avant de cliquer [!UICONTROL sur Enregistrer].

>[!NOTE]
>
>Les actions rapides pour les modifications de mise en page, la couleur d&#39;arrière-plan, le redimensionnement et le déplacement sont également disponibles sous forme d&#39;actions distinctes dans le menu Compositeur d&#39;expérience visuelle. Vous pouvez utiliser ces options comme des actions distinctes ou utiliser le menu Styles, comme expliqué ici.

* **Typographie**

   Modifiez la typographie d&#39;un élément. Les modifications apportées à la typographie sont rapides et faciles à réaliser.

   Bien que l&#39;éditeur de texte enrichi (Modifier le texte/HTML) soit disponible pour affiner - réglage, les actions rapides permettant d&#39;apporter des modifications à l&#39;élément entier sont disponibles via cette option. Si vous souhaitez appliquer des modifications de typographie à une partie seulement du texte (et non au texte intégral), utilisez l&#39;éditeur [de texte enrichi](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

   Vous pouvez modifier les styles de typographie suivants :

   * Taille de police
   * Poids de police
   * Style de police
   * Couleur (spécifiez le code couleur ou utilisez le sélecteur de couleurs)
   * Espacement des mots
   * Hauteur de ligne
   * Alignement du texte

* **Marge**

   Modifiez la marge de l&#39;élément sélectionné. Vous pouvez modifier les marges gauche, droite, inférieure et supérieure.

   Cliquez sur l&#39;icône déroulante pour chaque marge pour choisir parmi les options suivantes :

   * Automatique
   * Valeur (faire glisser le curseur pour définir la marge ou spécifier le nombre de pixels pour chaque marge)
   Marge prend en charge les valeurs positives et négatives.

   Target prend également en charge les autres unités de taille, telles que rem, pc, em, etc. Pour plus d&#39;informations sur ces unités, voir [Feuilles de style Web et astuces CSS](https://www.w3.org/Style/Examples/007/units.en.html).

* **Remplissage**

   Modifiez le remplissage de l&#39;élément sélectionné. Vous pouvez modifier les marges gauche, droite, inférieure et supérieure.

   Faites glisser le curseur pour définir le remplissage ou spécifier le nombre de pixels pour le remplissage.

   Le remplissage prend en charge les échelles de largeur à partir de 0.

   Target prend également en charge [les autres unités de taille](https://www.w3.org/Style/Examples/007/units.en.html), telles que rem, pc, em, etc.

* **Bordure**

   Cliquez sur les icônes de bordure en haut du panneau pour modifier la bordure de l&#39;élément sélectionné.

   Vous pouvez modifier les styles suivants pour chaque bordure (en haut, à droite, en bas et à gauche) :

   * Style de bordure (aucun, masqué, pointillé, tirets, plein ou double)
   * Couleur de bordure (spécifiez le code couleur ou utilisez le sélecteur de couleurs)
   * Largeur de la bordure (faites glisser le curseur pour sélectionner une largeur de bordure ou spécifiez la largeur en pixels).
   La bordure prend en charge les échelles de largeur à partir de 0.

   Target prend également en charge [les autres unités de taille](https://www.w3.org/Style/Examples/007/units.en.html), telles que rem, pc, em, etc.

* **Position**

   Déplace l&#39;élément sélectionné de sa position actuelle. Vous pouvez modifier la position supérieure, inférieure, gauche, droite et [z](https://www.w3schools.com/cssref/pr_pos_z-index.asp) de l&#39;élément.

   Cliquez sur la [!UICONTROL liste] déroulante Statique pour choisir l&#39;une des options de position suivantes :

   * Statique
   * Relatif
   * Absolu 
   * Attractif
   * Fixe
   Cliquez sur l&#39;icône déroulante pour chaque position pour choisir parmi les options suivantes :

   * Automatique
   * Valeur (faire glisser le curseur pour positionner l&#39;élément ou spécifier le nombre de pixels que vous souhaitez déplacer)
   La position prend en charge les valeurs positives et négatives.

   Target prend également en charge [les autres unités de taille](https://www.w3.org/Style/Examples/007/units.en.html), telles que rem, pc, em, etc.

* **Taille**

   Modifie la largeur et la hauteur de l&#39;élément sélectionné.

   Cliquez sur l&#39;icône déroulante en regard [!UICONTROL de Largeur] et [!UICONTROL de hauteur] pour choisir parmi les options suivantes :

   * Automatique
   * Valeur (faire glisser le curseur pour dimensionner l&#39;élément ou spécifier le nombre de pixels pour chaque dimension)

* **Filtrer**

   Faites glisser le curseur pour chaque option de filtre ou indiquez le pourcentage souhaité :

   * Sépia
   * Contraste
   * Luminosité
   * Grayscale
   * Flou
   * Opacité
   * Invert
   * Rotation de la teinte
   * Saturer

* **Editeur CSS**

   L&#39;éditeur CSS en temps réel vous permet d&#39;afficher les modifications et d&#39;ajouter des styles si vous maîtrisez l&#39;utilisation de feuilles de style en cascade (CSS) ou si vous recevez du code de votre développeur.

   L&#39;éditeur CSS affiche toutes les modifications que vous apportez dans le panneau Styles. Comme illustré ci-dessous, la taille de police, la bordure supérieure et la taille de l&#39;image ont été modifiées :

   ![Editeur CSS avec modifications](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   Notez les points bleus en regard des options [!UICONTROL Typographie], [!UICONTROL Bordure et][!UICONTROL Taille] de l&#39;illustration précédente. Ces points indiquent que vous avez apporté des modifications à ces sections. Si vous ouvrez ces panneaux de section, les points bleus s&#39;affichent en regard des options spécifiques que vous avez modifiées.

   Vous pouvez saisir votre propre code si le style souhaité n&#39;est pas disponible par défaut dans [!UICONTROL les styles].

   N&#39;oubliez pas que l&#39;éditeur CSS affiche les détails de la session en cours uniquement. Si vous enregistrez les modifications puis rouvrez l&#39;éditeur, les détails de la modification précédente ne s&#39;affichent pas dans l&#39;éditeur, même si vous sélectionnez de nouveau le même élément.

   >[!Important]
   >
   >Vous pouvez appliquer une image d&#39;arrière-plan à l&#39;aide de l&#39;éditeur CSS, mais cela peut entraîner un scintillement. Testez les modifications avant le déploiement.

#### Classe CSS

Permet de spécifier la classe CSS prédéfinie utilisée pour l’élément. Si plusieurs éléments sont sélectionnés, séparez plusieurs classes CSS par un espace.

Disponible pour les activités de [!UICONTROL test A/B], de [!UICONTROL Personnalisation automatisée] et de [!UICONTROL test multivarié].

#### Lien

Permet de modifier l’URL d’un lien.

Utilisez Modifier un lien pour mettre à jour le sélecteur afin qu’il pointe vers le même élément d’image. Cependant, le renvoi vers un élément d’image différent n’est pas pris en charge. Pour renvoyer vers un élément d’image différent, supprimez l’action d’origine dans l’éditeur de code et utilisez le [!UICONTROL compositeur d’expérience visuelle] pour appliquer l’action sur l’autre élément d’image.

### Insérer avant

Les options disponibles sont les suivantes :

#### Image, HTML et texte

Ajoutez n’importe quel élément à votre page en plus de la modification du contenu existant. Ajoutez du texte, du code, des listes et plus afin de créer des expériences entièrement différentes à tester.

Sélectionnez un élément sur la page, puis cliquez sur [!UICONTROL Insérer avant] et choisissez si vous souhaitez insérer une image, du code HTML ou du texte. L’élément inséré s’affiche avant l’élément sélectionné.

Le comportement de l’élément inséré dépend de la structure de votre page, de votre CSS et d’autres options de configuration de page. Un code HTML valide est requis pour faire apparaître votre page correctement. Testez toujours votre page après l’insertion d’un élément afin de vous assurer qu’il apparaît comme prévu.

[!UICONTROL Recommendations] prend en charge [!UICONTROL l’insertion avant] le contenu des balises DIV, SECTION et ARTICLE.

**Remarque :** L’insertion d’une image requiert que [!DNL Adobe Scene7 Publishing System] soit activé afin que vous ayez accès à la bibliothèque d’images.

#### Recommandation

Incluez des recommandations dans le test A/B (y compris l’Affectation automatique et le Ciblage automatique) et les activités de Ciblage d’expérience (XT). Pour plus d’informations, voir [Recommendations en tant qu’offre](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragment d’expérience

Insérez des fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation. Pour plus d’informations, voir [Fragments d’expérience AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Insérer après

Les options disponibles sont les suivantes :

#### Image, HTML et texte

Ajoutez n’importe quel élément à votre page en plus de la modification du contenu existant. Ajoutez du texte, du code, des listes et plus afin de créer des expériences entièrement différentes à tester.

Sélectionnez un élément sur la page, puis cliquez sur [!UICONTROL Insérer après] et choisissez si vous souhaitez insérer une image, du code HTML ou du texte. L’élément inséré s’affiche après l’élément sélectionné.

Le comportement de l’élément inséré dépend de la structure de votre page, de votre CSS et d’autres options de configuration de page. Un code HTML valide est requis pour faire apparaître votre page correctement. Testez toujours votre page après l’insertion d’un élément afin de vous assurer qu’il apparaît comme prévu.

[!UICONTROL Recommendations] prend en charge [!UICONTROL Insertion après] le contenu des balises DIV, SECTION et ARTICLE.

**Remarque :** L’insertion d’une image requiert que [!DNL Adobe Scene7 Publishing System] soit activé afin que vous ayez accès à la bibliothèque d’images.

#### Recommandation

Incluez des recommandations dans le test A/B (y compris l’Affectation automatique et le Ciblage automatique) et les activités de Ciblage d’expérience (XT). Pour plus d’informations, voir [Recommendations en tant qu’offre](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragment d’expérience

Insérez des fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation. Pour plus d&#39;informations, voir [Fragments d’expérience AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Remplacer par

Les options disponibles sont les suivantes :

#### Image

Permet de sélectionner une autre image dans la bibliothèque de contenu. Les images disponibles pour la permutation incluent les images téléchargées dans le dossier de ressources Experience Cloud ou dans la bibliothèque de contenu de Target.

À la création initiale de l’activité, l’URL affichée est différente de l’URL utilisée pour la diffusion. Lors de la synchronisation des activités, cette URL est mise à jour vers une URL de production Scene7.

Par exemple, l’URL initiale peut se présenter comme suit :

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Après la synchronisation des activités, l’URL de diffusion se présentera plutôt comme suit :

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Les recommandations prennent en charge le remplacement par des balises DIV, SECTION et ARTICLE.

**Remarque :** La permutation d’images requiert un compte Adobe Scene7 Publishing System.

#### Offre HTML

Permet de sélectionner une autre offre dans la [!UICONTROL Bibliothèque de contenu].

**Remarque :** Les offres HTML sont stockées sur les serveurs [!DNL Target].

La taille d’une offre HTML peut aller jusqu’à 256 Ko.

#### Recommandation

Incluez des recommandations dans le test A/B (y compris l’Affectation automatique et le Ciblage automatique) et les activités de Ciblage d’expérience (XT). Pour plus d’informations, voir [Recommendations en tant qu’offre](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragment d’expérience

Insérez des fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation. Pour plus d’informations, voir [Fragments d’expérience AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Mise en page

Les options disponibles sont les suivantes :

#### Réorganiser

Permet de faire glisser l&#39;élément vers un autre emplacement au sein du même élément parent ou dans une balise DIV. Les autres éléments changent de place afin de libérer de l’espace pour l’élément déplacé.

**Remarque :** Le suivi des clics ne fonctionne pas sur les éléments réorganisés.

#### Redimensionner

Permet de redimensionner un élément sur votre page. Lorsque vous sélectionnez l’option [!UICONTROL Redimensionner], une poignée apparaît dans le coin inférieur droit de l’élément, que vous pouvez faire glisser pour le redimensionner. Maintenez la touche Maj enfoncée pour conserver les proportions.

**Remarque :** Il n’est pas possible de redimensionner les éléments insérés.

#### Déplacer 

Permet de déplacer des éléments sur votre page. Contrairement à l’option [!UICONTROL Réorganiser], [!UICONTROL Déplacer] ne déplace pas d’autres éléments afin de libérer de l’espace pour l’élément déplacé. Utilisez les touches fléchées pour affiner le déplacement. (Amélioration prévue : un moyen de s’assurer que les éléments déplacés ne sont pas masqués derrière d’autres éléments.)

Dans certains cas, par exemple lorsqu’un élément doit rester dans son élément parent en raison d’une restriction CSS, vous ne pouvez pas déplacer l’élément en dehors de son parent.

#### Masquer

Permet de masquer l’élément. L’espace blanc est conservé, mais le contenu est supprimé.

#### Supprimer

Permet de supprimer un élément. L’espace blanc derrière l’image est supprimé et l’espace où se trouve l’élément est réduit.

**Remarque :** Cette option ne permet pas de supprimer les éléments d’une mbox « classique » (mbox créée dans une campagne Target Classic).

### Développer la section

Permet de sélectionner l’élément parent en plus de l’élément initialement sélectionné. Lorsque vous sélectionnez un élément parent, tous les enfants de cet élément sont automatiquement sélectionnés. Vous pouvez étendre plusieurs fois la sélection.

### Naviguer jusqu&#39;au lien

Permet d’ouvrir la destination du lien.

### Annuler/rétablir

Permet d’annuler les modifications apportées à vos activités durant une session de modification. Vous pouvez également rétablir les modifications précédemment annulées.

## Navigation dans les éléments à l&#39;aide du chemin DOM {#dom-path}

Lorsque vous cliquez sur un élément de la page, le menu des options du compositeur d&#39;expérience visuelle s&#39;affiche. En outre, lorsque vous cliquez sur un élément, le chemin DOM correspondant s&#39;affiche au bas de la page.

![Chemin DOM](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Vous pouvez utiliser le chemin DOM pour afficher rapidement les informations sur l&#39;élément sélectionné (type, ID et classe) et monter ou descendre le chemin DOM pour sélectionner l&#39;élément souhaité.

Lorsque vous passez la souris sur le chemin DOM, une zone bleue met en surbrillance l&#39;élément correspondant dans le compositeur d&#39;expérience visuelle. Lorsque vous cliquez sur l&#39;élément, une zone orange met en surbrillance l&#39;élément et le menu des options du compositeur d&#39;expérience visuelle s&#39;affiche, comme expliqué ci-dessus.

Vous pouvez facilement accéder à n&#39;importe quel élément parent, frère ou enfant du compositeur d&#39;expérience visuelle à l&#39;aide du chemin DOM.

La fonction Chemin DOM est également disponible lorsque vous définissez le suivi des [clics](/help/c-activities/r-success-metrics/click-tracking.md).