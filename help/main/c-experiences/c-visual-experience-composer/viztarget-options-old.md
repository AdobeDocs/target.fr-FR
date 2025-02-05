---
keywords: options du compositeur d’expérience visuelle;options du compositeur d’expérience;options d’expérience;modifier le texte;modifier le html;modifier le texte/html;modifier la couleur d’arrière-plan;insérer un élément;modifier le lien;lien du compositeur d’expérience visuelle;modifier la classe css;modifier la classe css;permuter l’offre;permuter l’image;permuter l’image;supprimer l’élément;supprimer l’élément;masquer l’élément;réorganiser;déplacer l’élément;redimensionner l’élément;redimensionner l’élément;développer la sélection;naviguer vers ce lien;naviguer;lien;annuler;annuler;rétablir;événements personnalisés;composants web;décision d’offre;offer decisioning
description: Explorez les options disponibles dans le  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).
title: Comment utiliser les options du [!UICONTROL Visual Experience Composer] (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '2667'
ht-degree: 55%

---

# Options du compositeur d’expérience visuelle

Lorsque vous cliquez sur un élément de page dans le [!UICONTROL Visual Experience Composer] d’[!DNL Adobe Target] (VEC), un menu affiche les options disponibles pour ce type d’élément. En outre, un chemin d’accès DOM s’affiche au bas de la page, ce qui vous permet de naviguer facilement dans la structure de la page.

Les différentes actions [!UICONTROL Visual Experience Composer] (VEC) sont regroupées dans des options de menu appropriées pour rendre votre tâche plus rapide et plus efficace :

![Menu Options du VEC](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>Les options disponibles dépendent du type d’activité que vous créez ou modifiez.

## [!UICONTROL Edit]

Les options disponibles sont les suivantes :

### [!UICONTROL Text/HTML] {#edit-text-html}

Permet de modifier le code HTML de l’élément (texte d’une zone de texte, bouton ou lien, par exemple).

En plus du code HTML, vous pouvez modifier et insérer du code JavaScript personnalisé.

Plusieurs options de mise en forme de texte enrichi sont disponibles lors de la modification de texte et de l’HTML pour les activités de [!UICONTROL A/B] et de [!UICONTROL Experience Targeting]. Vous pouvez choisir une police, sélectionner un style de police, modifier l’alignement du texte et accéder à d’autres options de mise en forme de texte standard. Lors de la modification de code HTML, vous pouvez basculer entre l’affichage du code et l’affichage de texte enrichi du code HTML.

Les balises HTML 5 suivantes peuvent être imbriquées :

| Baliser | Balises imbriquées autorisées |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

Utilisez le sélecteur de couleurs pour sélectionner ou définir une couleur d’arrière-plan. Vous pouvez sélectionner un échantillon de couleur et l’ajuster à l’aide des valeurs RVB ou des codes couleur hexadécimaux. La croix rouge dans le sélecteur de couleurs rend l’arrière-plan transparent.

**Remarque :** Cette option n’est pas disponible pour les éléments avec des images d’arrière-plan.

### [!UICONTROL Styles] {#styles}

Utilisez le panneau [!UICONTROL Styles] pour afficher ou modifier la valeur des styles existants pour l’élément sélectionné. Vous pouvez également ajouter d’autres styles.

Pour accéder au panneau [!UICONTROL Styles], cliquez sur un élément de page dans le VEC, puis cliquez sur **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

Le panneau [!UICONTROL Styles] s’affiche sur le côté droit du compositeur d’expérience visuelle. Le panneau contient une liste de styles qui vous permet de modifier ou d’ajouter à l’élément sélectionné. Un éditeur CSS en temps réel permet d’afficher les modifications et d’ajouter des styles si vous maîtrisez l’utilisation de feuilles de style en cascade (CSS) ou si vous recevez du code de votre développeur.

![Panneau Styles](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

Lorsque vous appliquez différents styles, vous pouvez toujours annuler vos modifications en cliquant sur l’icône [!UICONTROL Revert] qui s’affiche dans le coin supérieur droit du panneau [!UICONTROL Styles] après avoir modifié une section. Cliquer sur l’icône [!UICONTROL Revert] annule toutes les modifications dans le panneau de la section active.

Développez chaque section pour modifier ou ajouter des styles, comme expliqué ci-dessous. Pour enregistrer vos modifications, cliquez sur l’icône [!UICONTROL Back] en haut du panneau pour revenir à l’affichage principal du panneau, puis cliquez sur **[!UICONTROL Save]**.

Des points bleus sur le panneau principal et en regard de chaque option sur les différents panneaux de section indiquent que vous avez modifié les styles correspondants. Cet indicateur visuel vous permet de passer facilement en revue vos modifications avant de cliquer sur [!UICONTROL Save].

>[!NOTE]
>
>Les actions rapides pour les modifications de mise en page, la couleur d’arrière-plan, le redimensionnement et le déplacement sont également disponibles sous forme d’actions distinctes dans le menu VEC. Ces options peuvent être utilisées comme des actions distinctes ou vous pouvez utiliser le menu Styles , comme expliqué ici.

* **[!UICONTROL Background]**

  Modification de la couleur et de l’image d’arrière-plan.

   * Couleur (spécifiez le code couleur ou utilisez le sélecteur de couleurs)
   * Image (sélectionnez une image dans le sélecteur d’images)
   * Source de l’image (spécification d’une URL externe)
   * Pièce jointe
      * Cliquez sur la liste déroulante supérieure pour sélectionner scroll (défilement), fixed (fixe) ou local
      * Cliquez sur la liste déroulante inférieure pour sélectionner repeat (répétition), repeat-x (répétition-x), repeat-y (répétition-y), no-repeat (pas de répétition), space (espace) ou round (rond).
   * Clip
      * Cliquez sur la liste déroulante supérieure pour sélectionner border-box(zone de bordure), padding-box (zone de remplissage), content-box (zone de contenu) ou text (texte).
      * Cliquez sur la liste déroulante inférieure pour sélectionner auto audio (audio automatique) ou audio

* **[!UICONTROL Typography]**

  Modification de la typographie d’un élément. Les modifications apportées à la typographie sont rapides et faciles à réaliser.

  Bien que l’éditeur de texte enrichi (Modifier le texte/l’HTML) soit disponible pour les réglages précis, les actions rapides permettant de modifier l’élément entier sont disponibles via cette option. Si vous souhaitez appliquer des modifications de typographie à une partie seulement du texte (et non au texte intégral), utilisez l’éditeur [de texte enrichi](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

  Vous pouvez modifier les styles de typographie suivants :

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] (spécifiez le code couleur ou utilisez le sélecteur de couleurs)
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Modification de la marge de l’élément sélectionné. Vous pouvez modifier les marges gauche, droite, inférieure et supérieure.

  Cliquez sur l’icône déroulante pour chaque marge pour choisir parmi les options suivantes :

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (faites glisser le curseur pour définir la marge ou spécifiez le nombre de pixels pour chaque marge)

  La marge prend en charge les valeurs positives et négatives.

  Target prend également en charge d’autres unités de taille, telles que rem, pc, em. Pour plus d’informations sur ces unités, voir [Conseils et astuces CSS pour les feuilles de style web](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Modification du remplissage de l’élément sélectionné. Vous pouvez modifier le remplissage gauche, droit, inférieur et supérieur.

  Faites glisser le curseur pour définir le remplissage ou spécifier le nombre de pixels pour le remplissage.

  Le remplissage prend en charge les échelles de largeur à partir de 0.

  Target prend également en charge [d’autres unités de taille](https://www.w3.org/Style/Examples/007/units.en.html) telles que rem, pc, em.

* **[!UICONTROL Border]**

  Cliquer sur les icônes de bordure en haut du panneau pour modifier la bordure de l’élément sélectionné.

  Vous pouvez modifier les styles suivants pour chaque bordure (en haut, à droite, en bas et à gauche) :

   * [!UICONTROL Border style] (aucune, masquée, pointillée, tirée, pleine ou double)
   * [!UICONTROL Border color] (spécifiez le code couleur ou utilisez le sélecteur de couleurs)
   * [!UICONTROL Border width] (faites glisser le curseur pour sélectionner une largeur de bordure ou spécifiez la largeur en pixels)

  La bordure prend en charge les échelles de largeur à partir de 0.

  Target prend également en charge [d’autres unités de taille](https://www.w3.org/Style/Examples/007/units.en.html) telles que rem, pc, em.

* **[!UICONTROL Position]**

  Déplacement de l’élément sélectionné depuis sa position actuelle. Vous pouvez modifier la position en haut, en bas, à gauche, à droite et [index Z](https://www.w3schools.com/cssref/pr_pos_z-index.asp) de l’élément.

  Cliquez sur la liste déroulante [!UICONTROL Static] pour effectuer un choix parmi les options de position suivantes :

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

  Cliquez sur l’icône déroulante pour chaque position pour choisir parmi les options suivantes :

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (faites glisser le curseur pour positionner l’élément ou indiquez le nombre de pixels à déplacer)

  La position prend en charge les valeurs positives et négatives.

  Target prend également en charge [d’autres unités de taille](https://www.w3.org/Style/Examples/007/units.en.html) telles que rem, pc, em.

* **[!UICONTROL Size]**

  Modification de la largeur et de la hauteur de l’élément sélectionné.

  Cliquez sur l’icône déroulante en regard de [!UICONTROL Width] et [!UICONTROL Height] pour choisir parmi les options suivantes :

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (faites glisser le curseur pour dimensionner l’élément ou indiquez le nombre de pixels pour chaque dimension)

* **[!UICONTROL Filter]**

  Faites glisser le curseur pour chaque option de filtre ou indiquez le pourcentage souhaité :

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

  L’éditeur CSS en temps réel vous permet d’afficher les modifications et d’ajouter des styles si vous maîtrisez l’utilisation de feuilles de style en cascade (CSS) ou si vous recevez du code de votre développeur.

  L’éditeur CSS affiche toutes les modifications que vous apportez dans le panneau Styles. Comme illustré ci-dessous, la taille de police, la bordure supérieure et la taille de l’image ont été modifiées :

  ![Éditeur CSS avec modifications](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Remarquez les points bleus en regard des options [!UICONTROL Typography], [!UICONTROL Border] et [!UICONTROL Size] dans l’illustration précédente. Ces points indiquent que vous avez modifié ces sections. Si vous ouvrez ces panneaux de section, les points bleus s’affichent à côté des options spécifiques que vous avez modifiées.

  Vous pouvez saisir votre propre code si le style souhaité n’est pas disponible par défaut dans le [!UICONTROL Styles].

  L’éditeur CSS affiche uniquement les détails de la session en cours. Si vous enregistrez les modifications puis rouvrez l’éditeur, les détails de la modification précédente ne s’affichent pas dans l’éditeur, même si vous sélectionnez de nouveau le même élément.

  >[!IMPORTANT]
  >
  >Vous pouvez appliquer une image d’arrière-plan à l’aide de l’éditeur CSS, mais cela peut entraîner un scintillement. Testez les modifications avant le déploiement.

### [!UICONTROL CSS Class]

Permet de spécifier la classe CSS prédéfinie utilisée pour l’élément. Si plusieurs éléments sont sélectionnés, séparez plusieurs classes CSS par un espace.

Disponible pour les activités [!UICONTROL A/B], [!UICONTROL Automated Personalization] et [!UICONTROL Multivariate Test].

### [!UICONTROL Link]

Permet de modifier l’URL d’un lien.

Utilisez Modifier un lien pour mettre à jour le sélecteur afin qu’il pointe vers le même élément d’image. Cependant, le renvoi vers un élément d’image différent n’est pas pris en charge. Pour créer un lien vers un autre élément d’image, supprimez l’action d’origine de l’éditeur de code et utilisez l’[!UICONTROL Visual Experience Composer] pour appliquer l’action à l’autre élément d’image.

## [!UICONTROL Insert Before]

Les options disponibles sont les suivantes :

### [!UICONTROL Offer Decision]

Ajoutez une [offre créée dans [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} pour présenter la meilleure offre et la meilleure expérience à vos clients à l’aide de l’offer decisioning.

**Remarque :** cette option est disponible lors de la modification ou de la création d’activités [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) manuelles ou [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) uniquement. Cette option n’est pas disponible pour les autres types d’activités.

Pour plus d’informations, voir [Utilisation des décisions d’offre](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML] et [!UICONTROL Text]

Ajoutez n’importe quel élément à votre page en plus de la modification du contenu existant. Ajoutez du texte, du code, des listes et plus afin de créer des expériences entièrement différentes à tester.

Sélectionnez un élément sur la page, puis cliquez sur [!UICONTROL Insert Before] et choisissez d’insérer une image, un HTML ou du texte. L’élément inséré s’affiche avant l’élément sélectionné.

Le comportement de l’élément inséré dépend de la structure de votre page, de votre CSS et d’autres options de configuration de page. Un code HTML valide est requis pour faire apparaître votre page correctement. Testez toujours votre page après l’insertion d’un élément afin de vous assurer qu’il apparaît comme prévu.

[!UICONTROL Recommendations] prend [!UICONTROL Insert Before] en charge le contenu des balises DIV, SECTION et ARTICLE.

**Remarque :** L’insertion d’une image requiert que [!DNL Adobe Scene7 Publishing System] soit activé afin que vous ayez accès à la bibliothèque d’images.

### Recommandation

Incluez des recommandations dans le test A/B (y compris l’Affectation automatique et le Ciblage automatique) et les activités de Ciblage d’expérience (XT). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insérez des fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation. Pour plus d’informations, voir [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

Les options disponibles sont les suivantes :

### [!UICONTROL Offer Decision]

Ajoutez une [offre créée dans [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} pour présenter la meilleure offre et la meilleure expérience à vos clients à l’aide de l’offer decisioning.

**Remarque :** cette option est disponible lors de la modification ou de la création d’activités [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) manuelles ou [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) uniquement. Cette option n’est pas disponible pour les autres types d’activités.

Pour plus d’informations, voir [Utilisation des décisions d’offre](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML] et [!UICONTROL Text]

Ajoutez n’importe quel élément à votre page en plus de la modification du contenu existant. Ajoutez du texte, du code, des listes et plus afin de créer des expériences entièrement différentes à tester.

Sélectionnez un élément sur la page, puis cliquez sur [!UICONTROL Insert After] et choisissez d’insérer une image, un HTML ou du texte. L’élément inséré s’affiche après l’élément sélectionné.

Le comportement de l’élément inséré dépend de la structure de votre page, de votre CSS et d’autres options de configuration de page. Un code HTML valide est requis pour faire apparaître votre page correctement. Testez toujours votre page après l’insertion d’un élément afin de vous assurer qu’il apparaît comme prévu.

[!UICONTROL Recommendations] prend [!UICONTROL Insert After] en charge le contenu des balises DIV, SECTION et ARTICLE.

**Remarque :** L’insertion d’une image requiert que [!DNL Adobe Scene7 Publishing System] soit activé afin que vous ayez accès à la bibliothèque d’images.

### Recommandation

Incluez des recommandations dans le test A/B (y compris l’Affectation automatique et le Ciblage automatique) et les activités de Ciblage d’expérience (XT). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insérez des fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation. Pour plus d’informations, voir [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

Les options disponibles sont les suivantes :

### [!UICONTROL Offer Decision]

Ajoutez une [offre créée dans [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} pour présenter la meilleure offre et la meilleure expérience à vos clients à l’aide de l’offer decisioning.

**Remarque :** cette option est disponible lors de la modification ou de la création d’activités [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) manuelles ou [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) uniquement. Cette option n’est pas disponible pour les autres types d’activités.

Pour plus d’informations, voir [Utilisation des décisions d’offre](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Permet de sélectionner une autre image dans la bibliothèque de contenu. Les images disponibles pour la permutation incluent les images téléchargées dans le dossier de ressources Experience Cloud ou dans la bibliothèque de contenu de Target.

À la création initiale de l’activité, l’URL affichée est différente de l’URL utilisée pour la diffusion. Lors de la synchronisation des activités, cette URL est mise à jour vers une URL de production Scene7.

Par exemple, l’URL initiale peut se présenter comme suit :

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Après la synchronisation des activités, l’URL de diffusion se présentera plutôt comme suit :

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations prend en charge le remplacement par des balises DIV, SECTION et ARTICLE.

**Remarque :** La permutation d’images requiert un compte Adobe Scene7 Publishing System.

### [!UICONTROL HTML Offer]

Sélectionnez une autre offre dans la [!UICONTROL Content Library].

**Remarque :** Les offres HTML sont stockées sur les serveurs [!DNL Target].

Une offre d’HTML peut aller jusqu’à 256 Ko.

### Recommandation

Incluez des recommandations dans le test A/B (y compris l’Affectation automatique et le Ciblage automatique) et les activités de Ciblage d’expérience (XT). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insérez des fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation. Pour plus d’informations, voir [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

Les options disponibles sont les suivantes :

### [!UICONTROL Rearrange]

Permet de faire glisser l’élément vers un autre emplacement au sein du même élément parent ou dans une balise DIV. Les autres éléments changent de place afin de libérer de l’espace pour l’élément déplacé.

**Remarque** : le suivi des clics ne fonctionne pas sur les éléments réorganisés.

Actuellement, certaines actions du compositeur d’expérience visuelle, telles que [!UICONTROL Rearrange] et [!UICONTROL Move], supposent que les éléments frères des éléments parents source et de destination sont complètement chargés. Si le chargement différé se produit sous les éléments DOM parents (source ou destination), ces actions du compositeur d’expérience visuelle peuvent provoquer un comportement incohérent. Nous travaillons sur une approche plus fiable pour que les actions du compositeur d’expérience visuelle fonctionnent dans les éléments DOM chargés en différé. Comme solution temporaire, vous pouvez utiliser [!UICONTROL Custom Code] dans ces scénarios pour effectuer le rendu de vos expériences.

### [!UICONTROL Resize]

Permet de redimensionner un élément sur votre page. Lorsque vous sélectionnez [!UICONTROL Resize], une poignée s’affiche dans le coin inférieur droit de l’élément et vous permet de faire glisser ce coin pour le redimensionner. Maintenez la touche Maj enfoncée pour conserver les proportions.

**Remarque :** Il n’est pas possible de redimensionner les éléments insérés.

### [!UICONTROL Move] {#move}

Permet de déplacer des éléments sur votre page. Contrairement à l’option [!UICONTROL Rearrange] , [!UICONTROL Move] ne déplace pas les autres éléments pour libérer de l’espace pour l’élément déplacé. Utilisez les touches fléchées pour affiner le déplacement. (Amélioration prévue : prise en charge pour s’assurer que les éléments déplacés ne sont pas masqués derrière d’autres éléments.)

Dans certains cas, par exemple lorsqu’une restriction CSS exige qu’un élément reste à l’intérieur de son élément parent, vous ne pouvez pas déplacer l’élément en dehors de son parent. Un élément ne peut pas être déplacé en dehors d’un conteneur possédant la propriété CSS suivante : `overflow: hidden`.

Consultez [!UICONTROL Rearrange]-dessus pour plus d’informations sur le comportement incohérent des actions [!UICONTROL Move] et [!UICONTROL Rearrange] en raison du chargement différé des éléments DOM.

### [!UICONTROL Hide]

Permet de masquer l’élément. L’espace blanc est conservé, mais le contenu est supprimé.

### [!UICONTROL Remove]

Permet de supprimer un élément. L’espace blanc derrière l’image est supprimé et l’espace où se trouve l’élément est réduit.

**Remarque :** Cette option ne permet pas de supprimer les éléments d’une mbox « classique » (mbox créée dans une campagne Target Classic).

## [!UICONTROL Expand Section]

Permet de sélectionner l’élément parent en plus de l’élément initialement sélectionné. Lorsque vous sélectionnez un élément parent, tous les enfants de cet élément sont automatiquement sélectionnés. Vous pouvez étendre plusieurs fois la sélection.

## [!UICONTROL Navigate to Link]

Permet d’ouvrir la destination du lien.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Permet d’annuler les modifications apportées à vos activités durant une session de modification. Vous pouvez également rétablir les modifications précédemment annulées.

## Considérations {#considerations}

* Si une offre contient du contenu HTML, voir « Comment at.js effectue le rendu des offres avec du contenu HTML » dans [Fonctionnement d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} pour plus d’informations.

## Prise en charge des éléments personnalisés {#custom}

Le compositeur d’expérience visuelle prend en charge les [composants web](https://developer.mozilla.org/fr/docs/Web/Web_Components) pour vous permettre de créer et de tester des expériences et des offres personnalisées sur des éléments personnalisés et sur des éléments au sein d’éléments personnalisés. Cette fonctionnalité est disponible dans le compositeur d’expérience visuelle pour tous les types d’activité [!DNL Target].

>[!NOTE]
>
>La prise en charge du compositeur d’expérience visuelle pour les éléments personnalisés est prise en charge dans [at.js version](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} 2.7.0 (ou ultérieure){target=_blank}. Assurez-vous que la version requise est déployée sur votre site web. Si vous utilisez l’extension d’assistance [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), la version requise d’at.js doit également être déployée. Les options du compositeur d’expérience visuelle décrites ci-dessus ne sont pas visibles et peuvent être utilisées avec des versions d’at.js non prises en charge.
>
>La prise en charge du VEC pour les éléments personnalisés n’est actuellement pas prise en charge avec le [SDK Web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

La plupart des actions du compositeur d’expérience visuelle sont prises en charge sur les événements personnalisés et dans les événements personnalisés, avec les exceptions suivantes :

Les actions suivantes ne sont pas disponibles sur les éléments personnalisés :

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

L’action suivante n’est pas disponible dans les éléments personnalisés :

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## Navigation dans les éléments à l’aide du chemin d’accès DOM {#dom-path}

Lorsque vous cliquez sur un élément de la page, le menu des options du VEC s’affiche. En outre, lorsque vous cliquez sur un élément, le chemin d’accès DOM correspondant s’affiche au bas de la page.

![Chemin d’accès DOM](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Vous pouvez utiliser le chemin d’accès DOM pour afficher rapidement les informations sur l’élément sélectionné (type, ID et classe). Vous pouvez monter ou descendre le chemin d’accès DOM pour sélectionner l’élément souhaité.

Lorsque vous passez la souris sur le chemin d’accès DOM, une zone bleue met en surbrillance l’élément correspondant dans le VEC. Lorsque vous cliquez sur l’élément, une zone orange met en surbrillance l’élément et le menu des options du VEC s’affiche, comme expliqué ci-dessus.

Vous pouvez facilement accéder à n’importe quel élément parent, frère ou enfant du VEC à l’aide du chemin d’accès DOM.

La fonction Chemin d’accès DOM est également disponible lorsque vous définissez le [suivi des clics](/help/main/c-activities/r-success-metrics/click-tracking.md).
