---
keywords: compositeur d’expérience visuelle;bonne utilisation du compositeur d’expérience visuelle;limites du compositeur d’expérience visuelle;avertissements concernant le compositeur d’expérience visuelle;bonnes pratiques pour vec;vec
description: Découvrez les bonnes pratiques pour que vos expériences fonctionnent comme prévu lors de l’utilisation du [!UICONTROL Visual Experience Composer] (VEC).
title: Quelles sont [!UICONTROL Visual Experience Composer] bonnes pratiques et les limites ?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: 8c62a0e976ce075d07e1f80018c7ad7fac240eea
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 50%

---

# [!UICONTROL Visual Experience Composer] des bonnes pratiques et des limites

Pour vous assurer que vos expériences fonctionnent comme prévu, suivez les bonnes pratiques lors de l’utilisation du [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC). Tenez compte des conseils clés et des limites afin d’optimiser les performances et d’éviter les problèmes courants.

## Bonnes pratiques {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

Voici les bonnes pratiques à appliquer lors de l’utilisation du compositeur d’expérience visuelle :

### Placez la référence at.js en haut de la section `<head>` de votre page.

+++Afficher les détails
Si vous utilisez également le [!UICONTROL Visitor API Service] , placez le script de l’API visiteur au-dessus d’at.js.

+++

### Vous pouvez activer le [!UICONTROL Enhanced Experience Composer] au niveau du compte (activé pour toutes les activités créées dans le compte) ou au niveau de chaque activité.

+++Afficher les détails
Pour activer le [!UICONTROL Enhanced Experience Composer] au niveau du compte, cliquez sur [!UICONTROL [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]], puis activez le bouton d’activation de la [!UICONTROL Enable Enhanced Experience Composer].

Pour activer le [!UICONTROL Enhanced Experience Composer] au niveau de l’activité lors de la création d’une activité dans le [!UICONTROL Visual Experience Composer], cliquez sur [!UICONTROL Configure > [!UICONTROL Page Delivery]], puis activez le bouton [!UICONTROL Enable Enhanced Experience Composer] sur Activé.

+++

### Vous pouvez placer sur la liste autorisée certaines adresses IP si le [!UICONTROL Enhanced Experience Composer] ne se charge pas sur des pages sécurisées de votre site.

+++Afficher les détails
Placer sur la liste autorisée Les problèmes de chargement de l’[!UICONTROL Enhanced Experience Composer] peuvent être résolus en GRANT les adresses IP suivantes. Ces adresses IP sont destinées aux serveurs [!DNL Adobe] utilisés pour le proxy [!UICONTROL Enhanced Experience Composer]. Elles ne sont requises que pour la modification des activités. Placer sur la liste autorisée Les visiteurs et visiteuses de votre site n’ont pas besoin de ces adresses IP.

Pour plus d’informations, voir [L’EEC ne charge pas d’URL d’assurance qualité interne non accessible sur les adresses IP publiques](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) dans *Résolution des problèmes liés au Enhanced Experience Composer*.

+++

### Utiliser des identifiants uniques pour les éléments de niveau supérieur et pour tout autre élément qui serait un bon candidat pour le test/ciblage.

+++Détails
Tout élément se trouvant immédiatement dans l’élément de corps doit avoir un ID unique. Si de nouveaux éléments sont injectés dans le corps et que le code se déplace, au moins les éléments parents sont dotés d’un moyen plus facile pour les reconnaître.

[!DNL Target] ne nécessite pas d’identifiants, mais leur utilisation accroît la fiabilité des expériences créées avec le compositeur d’expérience. [!DNL Target] utilise des sélecteurs CSS pour modifier le contenu lors de la diffusion de l’expérience. Lorsque vous modifiez une expérience, le [!UICONTROL Visual Experience Composer] ancre le sélecteur à l’ancêtre le plus proche avec un attribut d’ID non nul sur l’élément HTML en cours de modification. En conséquence, il n’est pas conseillé d’utiliser un mécanisme, notamment les bibliothèques JavaScript, qui définit ou modifie les attributs d’identifiant HTML. Bien que ces identifiants puissent être disponibles pour le compositeur d’expérience [!DNL Target] pour la création d’activités, si JavaScript modifie les identifiants, l’identifiant utilisé lors de la création de l’expérience peut ne pas être disponible lors de l’exécution de l’expérience. Si un identifiant n’est pas disponible, le sélecteur ancré à l’identifiant échoue.

+++

### Nommer les classes CSS afin qu’elles soient facilement identifiables.

+++Détails
Lors de la modification de classes CSS dans le [!DNL Visual Experience Composer], il est utile de rendre les classes faciles à identifier à l’aide de noms de classe descriptifs. Cela permet de garantir que vous modifiez les classes CSS appropriées et que vos pages s’affichent comme prévu.

Ne pas utiliser la propriété CSS `!important` lors du masquage ou de la suppression d’éléments.

Si la propriété CSS `!important` est présente, les modifications apportées par `target.js` au cours de la diffusion sont remplacées par les règles CSS du site.

+++

### Éviter d’utiliser des tables HTML pour les dispositions de pages.

+++Détails
[!DNL Target] utilise JavaScript pour formater une page. Il est difficile de modifier les dispositions basées sur des tables avec JavaScript. En outre, les dispositions basées sur des tables peuvent ne pas s’afficher de la même manière dans tous les navigateurs. Pour de meilleurs résultats, utilisez CSS pour créer les dispositions de page.

+++

### Réduisez l’utilisation des iFrames.

+++Détails
Il est de bonne pratique de minimiser l’utilisation des iFrames afin de simplifier la gestion des pages et des tests. Le compositeur d’expérience visuelle peut appliquer certaines actions dans un iFrame, mais certaines actions, telles que le redimensionnement, ne fonctionnent pas correctement. Il est difficile de gérer et de redimensionner des pages qui utilisent plusieurs iFrames. De ce fait, le test de pages lourdes en iFrame peut générer des problèmes.

+++

### Tenter d’organiser toutes les modifications du DOM dynamique dès que possible une fois que le DOM est prêt.

+++Détails
Si vos modifications ne s’appliquent pas avant l’application d’expérience par `target.js`, la diffusion de contenu peut être interrompue. Cela ne se produit qu’en cas de modification du DOM dans la hiérarchie de l’élément ciblé.

+++

### Utiliser uniquement du texte brut ou une balise d’image dans les éléments d’ancre.

+++Détails
`<a>Anchor Text</a>`

OU

`<a href=""> <img src=""> </img> </a>`

+++

### Éviter les éléments de niveau bloc dans un élément inséré.

+++Détails
Les éléments au niveau du bloc ne doivent pas être utilisés dans les éléments intégrés, tels que l’ancrage, l’étendue, etc. Cela entraîne une perte de hauteur et de largeur des éléments intégrés, de sorte que l’outil de recouvrement de la [!UICONTROL Visual Experience Composer] risque de ne pas fonctionner comme prévu.

+++

### Ne pas utiliser la balise de base dans votre site web pour résoudre les URL et les liens.

+++Détails
Le compositeur d’expérience visuelle manipule le site web en arrière-plan, à l’aide d’un serveur proxy qui met à jour les liens. Si vous ajoutez une balise de base, les URL utilisées par le serveur proxy sont à nouveau résolues par le navigateur et apparaissent rompues.

+++

### L’utilisation de l’option Modifier HTML pour manipuler la structure DOM peut rompre les sélecteurs.

+++Détails
Par exemple, si vous avez entrepris deux actions :

* Ajout d’une classe à l’élément 1
* Modification du code HTML pour l’élément 1

Chaque modification crée un élément dans le compositeur d’expérience visuelle. La deuxième action modifiant l’élément 1, si vous supprimez l’élément 1, la deuxième action n’a plus rien à modifier, la modification ne fonctionne donc plus.

En d’autres termes, si vous ajoutez un élément avec du texte, puis, dans une action distincte, vous modifiez cet élément avec un texte différent, l’éditeur de code affiche les deux actions comme des éléments distincts. Lorsque vous avez modifié l’élément, vous avez créé un nouvel élément qui modifie l’élément d’origine que vous avez créé, contenant le texte modifié. Si vous supprimez alors l’élément d’origine, le texte modifié ne sera pas en mesure de trouver l’élément qui a été modifié et ne s’affichera pas. Le deuxième élément reste dans la liste des éléments mais il n’affecte pas la page car l’élément qu’il modifie n’existe plus.

Voir [Sélecteurs d’éléments utilisés dans le [!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337).

+++

### Utilisez des balises `<b>` et `<i>` lors de la mise en forme d’éléments de texte avec l’éditeur de texte enrichi.

+++Détails
* Pour mettre le texte en gras, utilisez `<b>` plutôt que `<strong>`.
* Pour mettre le texte en italique, utilisez `<i>` plutôt que `<em>`.

Les balises `<strong>` et `<em>` pourraient engendrer des résultats inattendus.

+++

### Soyez attentif lors de la suppression des champs de formulaire.

+++Détails
Certains champs de formulaire peuvent être obligatoires pour la soumission. La suppression de ces champs de formulaire peut avoir un impact sur les soumissions.

+++

### N’incluez pas de `mboxCreate` dans les scripts.

+++Détails
Du fait que `mboxCreate` utilise `document.write`, il n’est pas recommandé d’inclure `mboxCreate` dans les scripts. À la place, utilisez `mboxDefine` et `mboxUpdate` dans le même objectif.

+++

### Ne mettez pas à jour un fragment de code HTML à l’aide de [!DNL Target] s’il nécessite du code JavaScript pour son initialisation.


+++Détails
Lorsqu’une action (Modifier HTML) est effectuée sur des composants de page (tels que des curseurs, des carrousels, etc.), la diffusion peut sembler endommagée. Le compositeur d’expérience visuelle effectue l’action une fois que le composant de page a été instancié par JavaScript.

Cependant, lorsque le contenu de la page est diffusé aux visiteurs, l’action est appliquée avant l’instanciation du composant. De ce fait, la fonctionnalité de ce composant peut ou non être rompue lors de la diffusion. La fonctionnalité dépend de la nature du script utilisé sur cette page pour définir le composant.

Si vous testez la diffusion et que le composant fonctionne la première fois, il n’est pas garanti qu’il continue de fonctionner. Il peut y avoir (ou non) une situation de concurrence.

* S’il existe une condition de concurrence, la diffusion fonctionne par intermittence.
* S’il n’existe aucune condition de concurrence, la diffusion fonctionne toujours.

Testez plusieurs fois votre page pour vous assurer que la diffusion fonctionne comme prévu.

+++

### Ne pas utiliser une balise de base dans votre site web pour résoudre les URL et les liens.

+++Détails
Lorsque vous utilisez le [!UICONTROL Enhanced Experience Composer], le site web est manipulé en arrière-plan par un serveur proxy qui met à jour toutes les URL de lien pour les faire fonctionner dans le proxy. Si vous ajoutez une balise de base, toutes ces URL sont résolues par le navigateur. Elles apparaissent donc endommagées.

+++

### Le texte important du site qui est susceptible d’être utilisé pour le ciblage doit être conservé en code HTML à l’intérieur d’un élément.

+++Détails
Par exemple, vous ne pouvez pas cibler le texte Panier dans le compositeur d’expérience visuelle si le code est le suivant :

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
   Shopping Cart: 
   <span id="HeaderCartQtyTotal">
      0 
  </span> 
  Items 
  <span id="HeaderCartPriceTotal"></span> 
</a>
```

Dans cet exemple, l’élément d’ancrage entier est sélectionné dans le compositeur d’expérience visuelle, ce qui a une incidence négative sur les autres éléments si le ciblage est effectué.

+++

### N’utilisez pas de variables `top` ou `self` dans le code JavaScript.

+++Détails
Lorsque le [!UICONTROL Enhanced Experience Composer] est activé, la valeur des variables top et self est mise à jour pour désactiver le démantèlement d’iframe. Utilisez un en-tête X-Frame-Options pour ajouter des iFrames au lieu de code JavaScript personnalisé.

+++

### Toujours tester votre site web si des paramètres sont ajoutés au chargement de la page.

+++Détails
Par exemple, pour ouvrir `www.abc.com`, les paramètres d’URL suivants sont utilisés :

`www.abc.com?mboxEdit=1&mboxDisable=1`

Ces paramètres permettent d’effectuer des modifications dans les iFrames.

Assurez-vous que votre site web charge comme prévu après l’ajout de ce type de paramètres.

+++

### S’assurer que votre page s’ouvre comme prévu dans un iFrame.

+++Détails
Désactivez les techniques de suppression d’iframe sur votre site web et vérifiez si le site web s’ouvre comme prévu dans un iframe sur une page factice. Par exemple :

```html
<!DOCTYPE 
<html> 
<html> 
<head> 
  <meta charset="utf-8"> 
  <meta name="viewport" content="width=device-width"> 
  <title>JS Bin</title> 
</head> 
<body> 
  <iframe src="https://www.homedepot.com"</iframe> 
</body> 
</html>
```

+++

## Avertissements {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Tenez compte des avertissements suivants lors de l’utilisation de l’[!UICONTROL Visual Experience Composer] pour concevoir votre activité.

### La fonction [!UICONTROL Move] ne prend pas en charge z-index.

+++Détails
En raison de l’absence de fonctionnalité d’index z, l’élément déplacé ne peut pas être déplacé au-dessus d’un autre élément. Pour plus d’informations, voir [Limites](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

+++

### La réorganisation des éléments affecte le suivi des clics.

+++Détails
Si un élément marqué pour le suivi des clics est réorganisé, les chemins d’accès des éléments réorganisés sont modifiés. De ce fait, l’élément à l’emplacement où l’élément d’origine se trouvait avant la réorganisation est celui dont les clics sont suivis.

Cela se produit car le code de diffusion du contenu d’activité ainsi que le code de suivi des clics sont inclus dans un fragment de code qui est diffusé sur la page. Si vous naviguez sur une page différente et configurez le suivi des clics, le code du contenu d’activité et le code de suivi des clics sont diffusés sur cette page. Si la page de suivi des clics comporte une structure de page similaire dans laquelle le test est exécuté, alors le contenu du test peut également apparaître sur la page de suivi des clics.

+++

### L’insertion d’un élément peut ne pas fonctionner dans un `<div>` qui est une mbox.

+++Détails
Si une mbox contient une offre, l’insertion d’un élément peut apparaître comme `insertBefore` et non comme `insertAfter`, si la mbox est implémentée de manière incorrecte.

+++

### Lors de la modification simultanée d’un élément parent et d’un élément enfant, modifiez d’abord le parent.

+++Détails
Si vous permutez une action d’image sur un élément puis modifiez le texte ou le code HTML sur son élément parent, des problèmes de diffusion peuvent survenir. Le meilleur processus consiste à modifier l’élément parent avant de permuter l’image sur l’élément enfant.

+++

### Impossible de sélectionner un élément de page qui inclut une mbox en tant qu’élément enfant.

+++Détails
Par exemple, si votre page comporte :

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

La balise div externe ne doit pas être sélectionnée dans une expérience, car la mbox codée en dur dans la page appelle toujours [!DNL Target] et reçoit une réponse. Cette réponse interfère avec la réponse prévue pour l’élément de page plus grand.

+++

### Les adresses IP du proxy peuvent être bloquées dans l’environnement des clients.

+++Détails
Si vous utilisez [!UICONTROL Enhanced Experienced Composer] sur un site non actif, tel qu’un environnement d’évaluation, vous pouvez voir des délais d’expiration et des erreurs d’accès refusé si votre site bloque les RIP.

+++

## Limites  {#section_F33C2EA27F2E417AA036BC199DD6C721}

Tenez compte des restrictions suivantes lorsque vous utilisez le compositeur d’expérience visuelle :

### Gestion de la compatibilité du VEC avec les modifications de la politique d’extension [!DNL Chrome]. {#ext}

+++Détails
En raison des politiques de manifeste [V3 mises à jour dans Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}, les extensions ne peuvent plus modifier le DOM d’origine avant qu’il ne soit analysé par le navigateur. Par conséquent, certains scripts de sécurité, tels que les implémentations qui démolissent un iframe, peuvent bloquer le chargement des pages dans le compositeur d’expérience visuelle.

Pour garantir la compatibilité, ces scripts doivent être désactivés de manière conditionnelle lorsque la page est chargée dans l’iframe [!DNL Target]. Ce processus peut être effectué en toute sécurité en vérifiant la présence de l’objet `window.adobeVecExtension`, qui est injecté par [!DNL Target] pendant le chargement du compositeur d’expérience visuelle.

Les fragments de code suivants sont des exemples de code qui démolissent un iframe et peuvent entraîner le non chargement de la page web dans le VEC :

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

Une simple vérification peut être utilisée pour vérifier si une page web est incorporée dans [!DNL Target]. Un fragment de code doit se présenter comme suit :

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### Vous ne pouvez pas déplacer un élément en dehors d’un conteneur suivi d’une propriété CSS.

+++Détails
Un élément ne peut pas être déplacé en dehors d’un conteneur qui est suivi par une propriété CSS.

+++

### Vous ne pouvez pas sélectionner l’élément [!UICONTROL Button] pour réorganiser.

+++Détails
Les éléments [!UICONTROL Button] ne peuvent pas être sélectionnés directement pour la réorganisation. Pour activer la réorganisation, placez les boutons dans un conteneur plus grand.

+++

### Seules les offres de permutation sont disponibles sur les mbox.

+++Détails
Les actions telles que [!UICONTROL Edit Class] et [!UICONTROL Rearrange] ne sont pas autorisées dans une mbox.

+++

### Vous ne devez pas réorganiser et déplacer le même élément.

+++Détails
Si un élément a été déplacé vers un autre emplacement et que vous sélectionnez le conteneur parent et tentez de réorganiser les éléments enfants, l’élément déplacé n’est pas affecté et reste où il se trouve. La réorganisation peut ne pas apparaître comme vous le souhaitez.

+++

### L’action [!UICONTROL Change Image] ne fonctionne pas sur une image d’un carrousel.

+++Détails
Si, par exemple, votre page contient un carrousel avec six images et que vous souhaitez permuter une image avec la deuxième image du carrousel, l’action [!UICONTROL Change Image] ne fonctionne pas.

La solution consiste à sélectionner le conteneur parent et à utiliser l’action [!UICONTROL Edit HTML] pour modifier l’HTML du carrousel afin de mettre à jour la source d’image de l’image souhaitée.

+++

### Les images ne peuvent pas être redimensionnées dans une mbox.

+++Détails
Si vous permutez une image dans un élément de mbox, puis tentez de redimensionner cette image selon la taille de l’élément de mbox, le redimensionnement n’est pas autorisé.

+++

### Après avoir permuté une image, vous ne pouvez pas sélectionner l’action [!UICONTROL Edit].

+++Détails
Une fois que vous avez permuté l’image, vous ne pouvez pas modifier l’URL de Scene7.

+++

### Les éléments HTML avec une source externe ne peuvent pas être modifiés.

+++Détails
Par exemple : vidéo, balises audio, élément incorporé, iFrames, images.

+++

### Le suivi des clics ne fonctionne pas pour les éléments d’ancre qui contiennent des éléments autres que du texte brut ou des balises d’image.

+++Détails
Par exemple, le suivi des clics ne fonctionne pas si l’élément contient du code JavaScript.

+++

### Les pages doivent accepter les paramètres d’URL pour que le compositeur d’expérience visuelle fonctionne.

+++Détails
Certains sites retirent les paramètres d’URL de leurs pages. Toutefois, le compositeur d’expérience visuelle requiert ces paramètres.

+++

### Lors de l’utilisation d’un script dans le cadre d’HTML, toutes les variables et fonctions accessibles de l’extérieur doivent être déclarées sous l’espace de noms window.

+++Détails
Le script est exécuté dans la portée de `target.js` après le chargement de la page. Par conséquent, les variables ou fonctions qui sont déclarées localement ne sont pas accessibles depuis l’extérieur du bloc de script.

*Incorrect :*

```html
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*Correct :*

```html
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

+++

### L’insertion d’une image à partir de la bibliothèque [!UICONTROL Content] (Scene7) et la modification de l’HTML rompent l’URL de l’image.

+++Détails
Ajoutez un élément d’ancre à l’intérieur de l’élément div « customHeaderMessage » avec du texte de remplissage :

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

Sélectionnez cette balise div à l’aide de l’action [!UICONTROL Insert Element] pour insérer une image comme sœur de cette balise div de texte factice.

Après l’insertion de l’image, vous obtenez ceci :

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Supprimez l’élément span de texte de remplissage.

+++

### L’action `customCode` dans le compositeur d’expérience visuelle ne fonctionne pas avec l’[!DNL Internet Explorer] 8.

+++Détails
En raison des limitations d’IE8 lors de la gestion du contenu du script, `target.js` ne prend pas en charge cette fonctionnalité dans IE8. Pour pallier ce problème, si la page contient jQuery et est exposée sur l’objet de fenêtre de manière globale, `target.js` pouvez utiliser l’action de `customCode`. Assurez-vous que `window.jQuery` et `window.jQuery.fn.prepend` sont définis.

+++

### Le suivi des clics est uniquement pris en charge sur la page sur laquelle les expériences sont créées ou sur la page de redirection.

+++Détails
Bien que [!UICONTROL Browse] mode soit disponible pour le suivi des clics dans le VEC, [!UICONTROL Browse] mode ne peut pas être utilisé pour ajouter le suivi des clics sur une page.

+++
