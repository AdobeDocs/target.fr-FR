---
keywords: compositeur d’expérience visuelle;bonne utilisation du compositeur d’expérience visuelle;limites du compositeur d’expérience visuelle;avertissements concernant le compositeur d’expérience visuelle;bonnes pratiques pour vec;vec
description: Découvrez les bonnes pratiques pour que vos expériences fonctionnent comme prévu lors de l’utilisation du [!UICONTROL Visual Experience Composer] (VEC).
title: Quelles sont [!UICONTROL Visual Experience Composer] bonnes pratiques et les limites ?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: d94dad7795ef024feb19234c2a20423b074ea768
workflow-type: tm+mt
source-wordcount: '2534'
ht-degree: 80%

---

# [!UICONTROL Visual Experience Composer] des bonnes pratiques et des limites

Respectez les bonnes pratiques pour que vos expériences produisent les résultats escomptés. Il existe également d’autres conseils et restrictions que vous devez connaître lors de l’utilisation du [!UICONTROL Visual Experience Composer] (VEC) dans [!DNL Adobe Target].

## Bonnes pratiques {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

Voici les bonnes pratiques à appliquer lors de l’utilisation du compositeur d’expérience visuelle :

### Placez la référence at.js en haut de la section `<head>` de votre page.

Si vous utilisez également le service d’API visiteur, placez le script de l’API visiteur au-dessus d’at.js.

### Vous pouvez activer le compositeur d’expérience avancé au niveau du compte (activé pour toutes les activités créées dans le compte) ou au niveau de chaque activité.

Pour activer le compositeur d’expérience avancé au niveau du compte, cliquez sur [!UICONTROL Administration > Visual Experience Composer], puis activez le bouton (bascule) sur la position Activé .

Pour activer le compositeur d’expérience avancé au niveau de l’activité lors de la création d’une activité dans le compositeur d’expérience visuelle, cliquez sur [!UICONTROL Configure > URL], puis activez le bouton (bascule) sur la position Activé.

### Vous pouvez placer sur la liste autorisée certaines adresses IP si le compositeur d’expérience visuelle amélioré ne se charge pas sur les pages sécurisées de votre site.

Les problèmes de chargement du compositeur d’expérience visuelle amélioré peuvent être résolus en plaçant sur la liste autorisée les adresses IP suivantes. Ces adresses IP sont destinées au serveur Adobe utilisé pour le proxy du compositeur d’expérience avancé. Elles ne sont requises que pour la modification des activités. Placer sur la liste autorisée Les visiteurs et visiteuses de votre site n’ont pas besoin de ces adresses IP.

États-Unis : 52.55.99.45, 54.80.158.92 et 54.204.197.253

Europe, Moyen-Orient et Afrique (EMEA) : 52.51.238.221, 52.210.199.44 et 54.72.56.50

Asie-Pacifique : 52.193.67.35, 54.199.198.109 et 54.199.241.57

### Utiliser des identifiants uniques pour les éléments de niveau supérieur et pour tout autre élément qui serait un bon candidat pour le test/ciblage.

Tout élément se trouvant immédiatement dans l’élément de corps doit avoir un ID unique. Si de nouveaux éléments sont injectés dans le corps et que le code se déplace, au moins les éléments parents sont dotés d’un moyen plus facile pour les reconnaître.

Adobe Target ne requiert pas d’identifiants mais l’utilisation de ces derniers accroît la fiabilité des expériences créées avec le compositeur d’expérience. Target utilise des sélecteurs CSS pour modifier le contenu lorsque l’expérience est fournie. Lorsque vous modifiez une expérience, le compositeur d’expérience visuelle ancre le sélecteur correspondant à l’ancêtre le plus proche avec un attribut d’identifiant non nul à l’élément HTML en cours de modification. En conséquence, il n’est pas conseillé d’utiliser un mécanisme, notamment les bibliothèques JavaScript, qui définit ou modifie les attributs d’identifiant HTML. Bien que ces identifiants puissent être disponibles pour le compositeur d’expérience Target pour une création d’activités, si JavaScript modifie les identifiants, celui qui a été utilisé lorsque l’expérience a été créée ne sera peut-être pas disponible lorsque l’expérience s’exécute. Si un identifiant n’est pas disponible, le sélecteur ancré à l’identifiant échoue.

### Nommer les classes CSS afin qu’elles soient facilement identifiables.

Lors de la modification de classes CSS dans le compositeur d’expérience visuelle, il est utile de rendre les classes faciles à identifier en utilisant des noms de classe descriptifs. Cela permet de garantir que vous modifiez les classes CSS appropriées et que vos pages s’affichent comme prévu.

Ne pas utiliser la propriété CSS `!important` lors du masquage ou de la suppression d’éléments.

Si la propriété CSS 1!important1 est présente, les modifications effectuées par target.js au cours de la diffusion seront remplacées par les règles CSS du site.

### Éviter d’utiliser des tables HTML pour les dispositions de pages.

Target Standard et Premium utilisent JavaScript pour mettre en forme une page. Il est difficile de modifier les dispositions basées sur des tables avec JavaScript. En outre, les dispositions basées sur des tables peuvent ne pas s’afficher de la même manière dans tous les navigateurs. Pour de meilleurs résultats, utilisez CSS pour créer les dispositions de page.

### Réduisez l’utilisation des iFrames.

Il est de bonne pratique de minimiser l’utilisation des iFrames afin de simplifier la gestion des pages et des tests. Le compositeur d’expérience visuelle peut appliquer des actions dans un iFrame mais certaines actions, telles que le redimensionnement, ne fonctionnent pas correctement. Il est difficile de gérer et de redimensionner des pages qui utilisent plusieurs iFrames. De ce fait, le test de pages lourdes en iFrame peut générer des problèmes.

### Tenter d’organiser toutes les modifications du DOM dynamique dès que possible une fois que le DOM est prêt.

Si vos modifications ne procèdent pas à l’application avant l’application d’expérience par target.js, la diffusion du contenu pourrait être interrompue. Cela ne se produit qu’en cas de modification du DOM dans la hiérarchie de l’élément ciblé.

### Utiliser uniquement du texte brut ou une balise d’image dans les éléments d’ancre.

`<a>Anchor Text</a>`

OU

`<a href=""> <img src=""> </img> </a>`

### Éviter les éléments de niveau bloc dans un élément inséré.

Les éléments de niveau bloc ne doivent pas être utilisés dans des éléments insérés tels que ancre, span, etc. Une telle utilisation provoquerait la perte de la hauteur et de la largeur des éléments insérés. De ce fait, l’outil de superposition du compositeur d’expérience visuelle ne fonctionnerait pas comme vous l’attendez.

### Ne pas utiliser la balise de base dans votre site web pour résoudre les URL et les liens.

Le compositeur d’expérience visuelle manipule le site web en arrière-plan, à l’aide d’un serveur proxy qui a mis à jour les liens. Si vous ajoutez une balise de base, les URL utilisées par le serveur proxy sont à nouveau résolues par le navigateur et apparaissent rompues.

### L’utilisation de l’option Modifier HTML pour manipuler la structure DOM peut rompre les sélecteurs.

Par exemple, si vous avez entrepris deux actions :

* Ajout d’une classe à l’élément 1
* Modification du code HTML pour l’élément 1

Chaque modification crée un nouvel élément dans le compositeur d’expérience visuelle. La deuxième action modifiant l’élément 1, si vous supprimez l’élément 1, la deuxième action n’a plus rien à modifier, la modification ne fonctionne donc plus.

En d’autres termes, si vous ajoutez un élément avec du texte, puis, dans une action distincte, vous modifiez cet élément avec un texte différent, l’éditeur de code affiche les deux actions comme des éléments distincts. Lorsque vous avez modifié l’élément, vous avez créé un nouvel élément qui modifie l’élément d’origine que vous avez créé, contenant le texte modifié. Si vous supprimez alors l’élément d’origine, le texte modifié ne sera pas en mesure de trouver l’élément qui a été modifié et ne s’affichera pas. Le deuxième élément reste dans la liste des éléments mais il n’affecte pas la page car l’élément qu’il modifie n’existe plus.

Voir [Sélecteurs d’éléments utilisés dans le compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)

### Utilisez des balises `<b>` et `<i>` lors de la mise en forme d’éléments de texte avec l’éditeur de texte enrichi.

* Pour mettre le texte en gras, utilisez `<b>` plutôt que `<strong>`.
* Pour mettre le texte en italique, utilisez `<i>` plutôt que `<em>`.

Les balises `<strong>` et `<em>` pourraient engendrer des résultats inattendus.

### Soyez attentif lors de la suppression des champs de formulaire.

Certains champs de formulaire peuvent être obligatoires pour la soumission. La suppression de ces champs de formulaire peut avoir un impact sur les soumissions.

### N’incluez pas de `mboxCreate` dans les scripts.

Du fait que `mboxCreate` utilise `document.write`, il n’est pas recommandé d’inclure `mboxCreate` dans les scripts. À la place, utilisez `mboxDefine` et `mboxUpdate` dans le même objectif.

### Ne pas mettre à jour un extrait de code HTML à l’aide de Target Standard s’il requiert du code JavaScript pour son initialisation.

Lorsqu’une action (Modifier HTML) est exécutée sur des composants de page (par ex. curseurs, carrousels, etc.), la diffusion peut apparaître rompue. Le compositeur d’expérience visuelle exécute l’action après que le composant de page a été instancié par JavaScript.

Cependant, lorsque le contenu de la page est diffusé aux visiteurs, l’action est appliquée avant l’instanciation du composant. De ce fait, la fonctionnalité de ce composant peut ou non être rompue lors de la diffusion. La fonctionnalité dépend de la nature du script utilisé sur cette page pour définir le composant.

Si vous testez la diffusion et que le composant fonctionne la première fois, il n’est pas garanti qu’il continue de fonctionner. Il peut y avoir (ou non) une situation de concurrence.

* En cas de situation de concurrence, la diffusion fonctionnera par intermittence.
* S’il n’existe pas de situation de concurrence, la diffusion fonctionnera toujours.

Testez plusieurs fois votre page pour vous assurer que la diffusion fonctionne comme prévu.

### Ne pas utiliser une balise de base dans votre site web pour résoudre les URL et les liens.

Lorsque vous utilisez le compositeur d’expérience avancé, le site web est manipulé en arrière-plan par un serveur proxy qui met à jour toutes les URL des liens pour qu’elles fonctionnent dans le proxy. Si vous ajoutez une balise de base, toutes ces URL sont résolues par le navigateur et apparaissent rompues.

### Le texte important du site qui est susceptible d’être utilisé pour le ciblage doit être conservé en code HTML à l’intérieur d’un élément.

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

Dans cet exemple, tout l’élément d’ancre est sélectionné dans le compositeur d’expérience visuelle, ce qui peut nuire aux autres éléments si un ciblage est effectué.

### N’utilisez pas de variables `top` ou `self` dans le code JavaScript.

Lorsque le compositeur d’expérience amélioré est activé, la valeur des variables top et self est mise à jour pour désactiver l’iframe. Utilisez un en-tête X-Frame-Options pour ajouter des iFrames au lieu de code JavaScript personnalisé.

### Toujours tester votre site web si des paramètres sont ajoutés au chargement de la page.

Par exemple, pour ouvrir www.abc.com, les paramètres d’URL suivants sont ajoutés :

`www.abc.com?mboxEdit=1&mboxDisable=1`

Ces paramètres permettent d’effectuer des modifications dans les iFrames.

Assurez-vous que votre site web charge comme prévu après l’ajout de ce type de paramètres.

### S’assurer que votre page s’ouvre comme prévu dans un iFrame.

Désactivez les techniques d’iFrame sur votre site web et vérifiez qu’il s’ouvre comme prévu dans un iFrame sur une page factice. Par exemple :

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

## Avertissements {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Tenez compte des avertissements suivants lors de l’utilisation de l’[!UICONTROL Visual Experience Composer] pour concevoir votre activité.

### La fonctionnalité Déplacer ne prend pas en charge l’index z.

En raison de l’absence de fonctionnalité d’index z, l’élément déplacé ne peut pas être déplacé au-dessus d’un autre élément. Pour plus d’informations, voir [Limites](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

### La réorganisation des éléments affecte le suivi des clics.

Si un élément marqué pour le suivi des clics est réorganisé, les chemins d’accès des éléments réorganisés sont modifiés. De ce fait, l’élément à l’emplacement où l’élément d’origine se trouvait avant la réorganisation est celui dont les clics sont suivis.

Cela se produit car le code de diffusion du contenu d’activité ainsi que le code de suivi des clics sont inclus dans un fragment de code qui est diffusé sur la page. Si vous naviguez sur une page différente et configurez le suivi des clics, le code du contenu d’activité et le code de suivi des clics sont diffusés sur cette page. Si la page de suivi des clics comporte une structure de page similaire dans laquelle le test est exécuté, alors le contenu du test peut également apparaître sur la page de suivi des clics.

### L’insertion d’un élément peut ne pas fonctionner dans un `<div>` qui est une mbox.

Si une mbox contient une offre, l’insertion d’un élément peut apparaître en tant que insertBefore au lieu de insertAfter si le mbox n’est pas implémenté correctement.

### Lors de la modification simultanée d’un élément parent et d’un élément enfant, modifiez d’abord le parent.

Si vous permutez une action d’image sur un élément puis modifiez le texte ou le code HTML sur son élément parent, des problèmes de diffusion peuvent survenir. Le meilleur processus consiste à modifier l’élément parent avant de permuter l’image sur l’élément enfant.

### Impossible de sélectionner un élément de page qui inclut une mbox en tant qu’élément enfant.

Par exemple, si votre page comporte :

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

La balise div externe ne doit pas être sélectionnée dans une expérience car la mbox codée en dur dans la page effectue toujours un appel à Target et reçoit une réponse. Cette réponse interfère avec la réponse prévue pour l’élément de page plus grand.

### Les adresses IP du serveur proxy peuvent être bloquées dans les environnements des clients.

Si vous utilisez un compositeur d’expérience avancé comme site non actif, par exemple un environnement d’évaluation, vous pourrez constater des délais d’attente et des erreurs de refus d’accès si votre site bloque les RIP.

### Lors de l’ajout de plusieurs pages, le rail d’expérience et le rail de page sont ouverts simultanément. Cela entraîne une réduction de la largeur utilisable par le compositeur d’expérience visuelle pour afficher le site lors des optimisations. De ce fait, les sites reformatables peuvent commencer à s’afficher autrement que ce qui a été prévu dans l’espace réduit.

La méthode de contournement consiste à réduire le rail d’expérience et le rail de page en cliquant sur les icônes Chevron de gauche en haut de la page.

## Limites  {#section_F33C2EA27F2E417AA036BC199DD6C721}

Tenez compte des restrictions suivantes lorsque vous utilisez le compositeur d’expérience visuelle :

### Gestion de la compatibilité du VEC avec les modifications de la politique d’extension de Chrome. {#ext}

En raison des politiques de manifeste [V3 mises à jour dans Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}, les extensions ne peuvent plus modifier le DOM d’origine avant qu’il ne soit analysé par le navigateur. Par conséquent, certains scripts de sécurité, tels que les implémentations qui démolissent un iframe, peuvent bloquer le chargement des pages dans le compositeur d’expérience visuelle.

Pour garantir la compatibilité, ces scripts doivent être désactivés de manière conditionnelle lorsque la page est chargée dans l’iframe [!DNL Target]. Ce processus peut être effectué en toute sécurité en vérifiant la présence de l’objet `window.adobeVecExtension`, qui est injecté par [!DNL Target] pendant le chargement du compositeur d’expérience visuelle.

Les fragments de code suivants sont des exemples de code qui démolissent un iframe et peuvent entraîner le non chargement de la page web dans le VEC :

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

Une simple vérification peut être utilisée pour vérifier si une page web est incorporée dans [!DNL Target]. Un fragment de code devrait ressembler à ceci :

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

### Vous ne pouvez pas déplacer un élément en dehors d’un conteneur suivi d’une propriété CSS.

Un élément ne peut pas être déplacé en dehors d’un conteneur qui est suivi par une propriété CSS.

### Vous ne pouvez pas sélectionner l’élément [!UICONTROL Button] pour réorganiser.

Les éléments [!UICONTROL Button] ne peuvent pas être sélectionnés directement pour la réorganisation. Pour activer la réorganisation, placez les boutons dans un conteneur plus grand.

### Seules les offres de permutation sont disponibles sur les mbox.

Les actions telles que Modifier la classe et Réorganiser ne sont pas autorisées dans une mbox.

### Vous ne devez pas réorganiser et déplacer le même élément.

Si un élément a été déplacé vers un autre emplacement et que vous sélectionnez le conteneur parent et tentez de réorganiser les éléments enfants, l’élément déplacé n’est pas affecté et reste où il se trouve. La réorganisation peut ne pas apparaître comme vous le souhaitez.

### L’action Permuter l’image ne fonctionne pas sur une image d’un carrousel.

Si, par exemple, votre page comporte un carrousel avec six images et que vous souhaitez permuter une image avec la deuxième image du carrousel, l’action Permuter l’image ne fonctionne pas.

La méthode de contournement consiste à sélectionner le conteneur parent et à utiliser l’action Modifier HTML pour modifier le code HTML du carrousel afin de mettre à jour la source d’image de l’image souhaitée.

### Les images ne peuvent pas être redimensionnées dans une mbox.

Si vous permutez une image dans un élément de mbox, puis tentez de redimensionner cette image selon la taille de l’élément de mbox, le redimensionnement n’est pas autorisé.

### Une fois que vous avez permuté une image, vous ne pouvez pas sélectionner l’action Modifier.

Une fois que vous avez permuté l’image, vous ne pouvez pas modifier l’URL de Scene7.

### Les éléments HTML comportant une source externe ne peuvent pas être modifiés.

Par exemple : vidéo, balises audio, élément incorporé, iFrames, images.

### Le suivi des clics ne fonctionne pas pour les éléments d’ancre qui contiennent des éléments autres que du texte brut ou des balises d’image.

Par exemple, le suivi des clics ne fonctionne pas si l’élément contient du code JavaScript.

### Pour que le compositeur d’expérience visuelle puisse fonctionner, les pages doivent accepter les paramètres d’URL.

Certains sites retirent les paramètres d’URL de leurs pages. Le compositeur d’expérience visuelle requiert toutefois ces paramètres.

### Lors de l’utilisation d’un script inclus dans du code HTML, toutes les variables et fonctions auxquelles l’accès se fait de l’extérieur doivent être déclarées sous l’espace de noms window.

Le script est exécuté dans les limites de target.js après le chargement de la page. Par conséquent, les variables ou fonctions qui sont déclarées localement ne sont pas accessibles depuis l’extérieur du bloc de script.

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

### L’insertion d’une image à partir de la bibliothèque de contenu (Scene7) et la modification de l’HTML rompent l’URL de l’image.

Ajoutez un élément d’ancre à l’intérieur de l’élément div « customHeaderMessage » avec du texte de remplissage :

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

Sélectionnez cet élément div à l’aide de l’action Insérer l’élément pour insérer une image en tant qu’élément frère de cet élément div de texte de remplissage.

Après l’insertion de l’image, vous obtenez ceci :

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Supprimez l’élément span de texte de remplissage.

### L’action customCode dans le VEC ne fonctionne pas avec Internet Explorer 8.

target.js ne prend pas en charge cette action dans IE8 en raison de limitations d’IE8 au niveau de la gestion des contenus de script. Si la page contient jQuery et est exposée globalement sur l’objet window, la méthode de contournement consiste à utiliser target.js pour diffuser l’action customCode. Assurez-vous que window.jQuery et window.jQuery.fn.prepend sont définis.

### Le suivi des clics est uniquement pris en charge sur la page sur laquelle les expériences sont créées ou sur la page de redirection.

Bien que le mode Parcourir soit disponible dans le compositeur d’expérience visuelle du suivi des clics, il ne peut pas être utilisé pour ajouter le suivi des clics à une page.
