---
keywords: compositeur d’expérience visuelle;bonne utilisation du compositeur d’expérience visuelle;limites du compositeur d’expérience visuelle;avertissements concernant le compositeur d’expérience visuelle;bonnes pratiques pour vec;vec
description: Découvrez les bonnes pratiques pour que vos expériences fonctionnent comme prévu lors de l’utilisation du [!UICONTROL compositeur d’expérience visuelle] (VEC).
title: Quelles sont les bonnes pratiques et les limites du [!UICONTROL compositeur d’expérience visuelle] ?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
TQID: 'https://experienceleague.adobe.com/upZDSyuS9VqUmYskNXrlYazhwRHmZGBpSR-cR-qliRs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '2420'
ht-degree: 7%
---
# [!UICONTROL Bonnes pratiques et limites du compositeur d’expérience visuelle] {#vec-best-practices}

>[!BEGINSHADEBOX]

**Sur cette page :** découvrez les bonnes pratiques, les avertissements et les limites à connaître lors de la création d’expériences dans le **[!UICONTROL Compositeur d’expérience visuelle]** (VEC).

>[!ENDSHADEBOX]

Le respect de ces pratiques permet de créer des expériences dans le [!DNL Adobe Target] **[!UICONTROL compositeur d’expérience visuelle]** (VEC) comme prévu. Les avertissements et les limitations décrivent les comportements qui peuvent provoquer des problèmes courants. En conséquence, les connaître permet d’éviter les problèmes et de maintenir les performances.

## Bonnes pratiques {#best-practices}

Les pratiques suivantes s’appliquent lors de l’utilisation du compositeur d’expérience visuelle.

### Activer le [!UICONTROL compositeur d’expérience amélioré] {#enable-eec}

Le **[!UICONTROL compositeur d’expérience amélioré]** peut être activé au niveau du compte, ce qui l’active pour toutes les activités créées dans le compte, ou au niveau de chaque activité.

* **Niveau du compte :** Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Compositeur d’expérience visuelle]**, puis activez le bouton (bascule) **[!UICONTROL Activer le compositeur d’expérience amélioré]** en position Activé.
* **Niveau d’activité :** lors de la création d’une activité dans le **[!UICONTROL compositeur d’expérience visuelle]**, cliquez sur **[!UICONTROL Configurer]** > **[!UICONTROL Diffusion de page]**, puis activez le bouton (bascule) **[!UICONTROL Activer le compositeur d’expérience amélioré]** sur la position Activé.

### Mise en page et chargement

+++ Placez la référence at.js en haut de la section `<head>` de la page.

Si le **[!UICONTROL service d’API visiteur]** est également utilisé, placez le script de l’API visiteur au-dessus d’at.js.

+++

+++ Placez sur la liste autorisée les adresses IP si le [!UICONTROL compositeur d’expérience amélioré] ne se charge pas sur les pages sécurisées du site.

Le fait de Placer sur la liste autorisée les adresses IP des serveurs [!DNL Adobe] utilisés pour le proxy **[!UICONTROL Enhanced Experience Composer]** résout les problèmes de chargement. Ces adresses IP ne sont requises que pour la modification d’activités. Les visiteurs et visiteuses du site n’en ont pas besoin. Les adresses IP sont répertoriées dans [L’EEC ne chargera pas d’URL d’assurance qualité interne non accessible sur une adresse IP publique](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#eec-ip-addresses) dans *Résolution des problèmes liés au compositeur d’expérience amélioré*.

+++

+++ N’utilisez pas la balise de base dans le site web pour résoudre les URL et les liens.

Le compositeur d’expérience visuelle, y compris le **[!UICONTROL compositeur d’expérience amélioré]**, manipule le site web en arrière-plan par le biais d’un serveur proxy qui met à jour toutes les URL de lien pour les faire fonctionner dans le proxy. Si une balise de base est ajoutée, le navigateur résout à nouveau ces URL afin qu’elles apparaissent endommagées.

+++

+++ N’utilisez pas les variables `top` ou `self` dans le code JavaScript.

Lorsque le **[!UICONTROL compositeur d’expérience amélioré]** est activé, les valeurs des variables `top` et `self` sont mises à jour afin de désactiver le contournement d’iframe. Utilisez un en-tête X-Frame-Options pour ajouter le démantèlement d’iframe au lieu du code JavaScript personnalisé.

+++

+++ Testez toujours le site web si des paramètres sont ajoutés au chargement de la page.

Par exemple, les paramètres d’URL suivants sont utilisés pour ouvrir `www.abc.com` en vue de le modifier dans un iframe :

`www.abc.com?mboxEdit=1&mboxDisable=1`

Assurez-vous que le site web se charge comme prévu après l’ajout de paramètres tels que ceux-ci.

+++

+++ Assurez-vous que la page s’ouvre comme prévu dans un iframe.

Désactivez les techniques de suppression d’iframe sur le site web et vérifiez si le site web s’ouvre comme prévu dans un iframe sur une page factice. Par exemple :

```html
<!DOCTYPE html>
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

### Balisage de page

+++ Utilisez des identifiants uniques pour les éléments de niveau supérieur et pour tous les autres éléments qui constituent de bons candidats de test ou de ciblage.

Tout ce qui se trouve immédiatement à l’intérieur de l’élément de corps doit avoir un identifiant unique, de sorte qu’au moins les éléments parents soient faciles à reconnaître lorsque de nouveaux éléments sont injectés dans le corps et que le code se déplace.

[!DNL Target] ne nécessite pas d’identifiants, mais les identifiants augmentent la fiabilité des expériences créées avec le compositeur d’expérience. [!DNL Target] utilise des sélecteurs CSS pour modifier le contenu lors de la diffusion de l’expérience. Lorsqu’une expérience est modifiée, le **[!UICONTROL compositeur d’expérience visuelle]** ancre le sélecteur à l’ancêtre le plus proche de l’élément HTML modifié dont l’attribut d’ID n’est pas nul. Il n’est donc pas recommandé d’utiliser un mécanisme, y compris les bibliothèques JavaScript, qui définit ou modifie les attributs d’HTML ID. Ces identifiants peuvent être disponibles pour le compositeur d’expérience lors de la création de l’activité, mais si JavaScript les modifie, les identifiants utilisés lors de la création peuvent ne pas être disponibles lors de l’exécution de l’expérience. Si aucun identifiant n’est disponible, le sélecteur ancré à cet identifiant échoue.

+++

+++ Utilisez des noms de classe CSS descriptifs.

Les noms de classe descriptifs permettent d’identifier facilement les classes lorsque des classes CSS sont modifiées dans le **[!UICONTROL compositeur d’expérience visuelle]**. Cela permet de s’assurer que les classes CSS appropriées sont modifiées et que les pages s’affichent comme prévu.

+++

+++ N’utilisez pas la propriété CSS `!important` lors du masquage ou de la suppression d’éléments.

Si la propriété CSS `!important` est présente, les règles CSS du site remplacent les modifications apportées par `target.js` lors de la diffusion.

+++

+++ Évitez les tableaux HTML pour les mises en page.

[!DNL Target] utilise JavaScript pour formater une page et les dispositions basées sur des tableaux sont difficiles à modifier avec JavaScript. Les dispositions basées sur des tableaux peuvent également ne pas s’afficher de la même manière dans tous les navigateurs. Pour de meilleurs résultats, utilisez CSS pour créer les dispositions de page.

+++

+++ Réduisez l’utilisation des iFrames.

Réduire les iFrames simplifie la gestion des pages et des tests. Le **[!UICONTROL compositeur d’expérience visuelle]** peut appliquer certaines actions dans un iFrame, mais certaines actions, telles que le redimensionnement, ne fonctionnent pas correctement. Les pages qui utilisent plusieurs iFrames sont difficiles à gérer et à redimensionner, de sorte que tester des pages riches en iFrames peut créer des problèmes.

+++

+++ Utilisez uniquement du texte brut ou une balise d’image dans les éléments d’ancrage.

Un élément d’ancrage contient du texte brut :

`<a>Anchor Text</a>`

ou une balise d’image :

`<a href=""> <img src=""> </img> </a>`

+++

+++ Éviter les éléments de niveau bloc dans un élément inséré.

Les éléments au niveau du bloc ne doivent pas être utilisés dans les éléments intégrés, tels que les éléments d’ancrage et d’étendue. Cela entraîne une perte de hauteur et de largeur des éléments intégrés. Il se peut donc que l’outil de recouvrement du **[!UICONTROL compositeur d’expérience visuelle]** ne fonctionne pas comme prévu.

+++

+++ Soyez attentif lors de la suppression des champs de formulaire.

Certains champs de formulaire peuvent être obligatoires pour l’envoi. Leur suppression peut donc avoir une incidence sur les envois.

+++

+++ Conservez le texte important pouvant être utilisé à des fins de ciblage dans le code HTML au sein d’un élément .

Par exemple, le texte Panier ne peut pas être ciblé dans le VEC si le code est similaire à ce qui suit :

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart">
   <img alt="Shopping Cart" src="/images/ico-cart.gif"></img>
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

### Edition et diffusion

+++ Organisez toutes les modifications DOM dynamiques dès que possible après que le DOM sera prêt.

Si les modifications ne s’appliquent pas avant que `target.js` n’applique l’expérience, la diffusion de contenu peut être interrompue. Cela ne se produit qu’en cas de modification du DOM dans la hiérarchie de l’élément ciblé.

+++

+++ L’utilisation de Modifier HTML pour manipuler la structure DOM peut interrompre les sélecteurs.

Par exemple, deux actions sont entreprises :

* Une classe est ajoutée à l’élément 1.
* L’HTML de l’élément 1 est modifiée.

Chaque modification crée un élément dans le compositeur d’expérience visuelle. La deuxième action modifie l’élément 1. Par conséquent, si l’élément 1 est supprimé, la deuxième action n’a plus rien à modifier et la modification ne fonctionne plus.

De même, si un élément est ajouté avec du texte et qu’une action distincte modifie ensuite cet élément avec un texte différent, l’éditeur de code affiche les deux actions sous la forme d’éléments distincts. L’édition crée un nouvel élément qui modifie l’élément d’origine et contient le texte modifié. Si l’élément d’origine est ensuite supprimé, le texte modifié ne trouve pas l’élément à modifier et ne s’affiche pas. Le deuxième élément reste dans la liste des éléments, mais il n’a aucun effet sur la page, car l’élément qu’il modifie n’existe plus.

Voir [Sélecteurs d’éléments utilisés dans le **[!UICONTROL compositeur d’expérience visuelle]**](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#vec-selectors).

+++

+++ Utilisez les balises `<b>` et `<i>` lors du style d’éléments de texte avec l’éditeur de texte enrichi.

* Pour mettre le texte en gras, utilisez `<b>` plutôt que `<strong>`.
* Pour mettre le texte en italique, utilisez `<i>` plutôt que `<em>`.

Les balises `<strong>` et `<em>` peuvent entraîner des résultats inattendus.

+++

+++ N’incluez pas `mboxCreate` dans les scripts.

`mboxCreate` utilise `document.write`, il n’est donc pas recommandé de l’inclure dans les scripts. Utilisez `mboxDefine` et `mboxUpdate` dans le même but.

+++

+++ Ne mettez pas à jour un fragment de code HTML avec [!DNL Target] si celui-ci nécessite du code JavaScript pour son initialisation.

Lorsqu’une action (Modifier HTML) est effectuée sur des composants de page tels que des curseurs et des carrousels, la diffusion peut sembler endommagée. Le compositeur d’expérience visuelle effectue l’action après l’instanciation du composant de page par JavaScript. Cependant, lorsque le contenu de la page est diffusé aux visiteurs, l’action est appliquée avant l’instanciation du composant. Par conséquent, la fonctionnalité du composant peut être interrompue ou non au moment de la diffusion, selon le script qui définit le composant sur la page.

Un test de diffusion qui fonctionne la première fois ne garantit pas que la diffusion continuera à fonctionner, car une condition de concurrence peut exister :

* S’il existe une condition de concurrence, la diffusion fonctionne par intermittence.
* S’il n’existe aucune condition de concurrence, la diffusion fonctionne toujours.

Testez la page plusieurs fois pour vous assurer que la diffusion fonctionne comme prévu.

+++

## Avertissements {#caveats}

Les avertissements suivants s’appliquent lors de l’utilisation du **[!UICONTROL compositeur d’expérience visuelle]** pour concevoir une activité.

+++ La fonction [!UICONTROL Déplacer] ne prend pas en charge z-index.

Sans la fonctionnalité z-index, un élément déplacé ne peut pas être placé au-dessus d’un autre élément. Pour plus d’informations, voir [Limites](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

+++

+++ La réorganisation des éléments affecte le suivi des clics.

Si un élément marqué pour le suivi des clics est réorganisé, les chemins des éléments réorganisés changent. Par conséquent, les clics sont suivis sur l’élément à l’emplacement où se trouvait l’élément d’origine avant sa réorganisation.

Cela se produit, car le code qui diffuse le contenu de l’activité et le code qui suit les clics sont inclus dans un élément de code qui est diffusé à la page. Si une autre page est accessible et que le suivi des clics y est configuré, les deux éléments de code sont envoyés à cette page. Si la page de suivi des clics présente une structure de page similaire à celle de la page sur laquelle s’exécute le test, le contenu du test peut également s’afficher sur la page de suivi des clics.

+++

+++ L&#39;insertion d&#39;un élément peut ne pas fonctionner dans un `<div>` qui est une mbox.

Si une mbox contient une offre et qu’elle est implémentée de manière incorrecte, un élément inséré peut apparaître sous la forme `insertBefore` et non sous la forme `insertAfter`.

+++

+++ Lors de la modification d’un élément parent et d’un élément enfant, modifiez d’abord le parent.

Si une action d’image est permutée sur un élément et que le texte ou l’HTML de son élément parent est ensuite modifié, des problèmes de diffusion peuvent se produire. Le meilleur processus consiste à modifier l’élément parent avant de permuter l’image sur l’élément enfant.

+++

+++ Ne sélectionnez pas un élément de page qui inclut une mbox comme élément enfant.

Par exemple, si la page contient le code suivant :

```html
<div>
  <div class="mboxDefault" >
  </div>
  <script>mboxCreate('myMbox');
</script>
</div>
```

La balise div externe ne doit pas être sélectionnée dans une expérience, car la mbox codée en dur dans la page effectue toujours un appel à [!DNL Target] et reçoit une réponse. Cette réponse interfère avec la réponse prévue pour l’élément de page plus grand.

+++

+++ Les adresses IP du proxy peuvent être bloquées dans l’environnement du client.

Si le **[!UICONTROL compositeur d’expérience amélioré]** est utilisé sur un site non actif, tel qu’un environnement d’évaluation, des dépassements de délai et des erreurs d’accès refusé peuvent se produire si le site bloque les adresses IP du proxy.

+++

## Limites {#section_F33C2EA27F2E417AA036BC199DD6C721}

Les restrictions suivantes s’appliquent lorsque vous utilisez le compositeur d’expérience visuelle.

### Exigences de page

+++ Gérez la compatibilité du VEC avec les modifications de la politique d’extension [!DNL Chrome].

Dans le cadre des politiques de manifeste [V3 mises à jour dans Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}, les extensions ne peuvent plus modifier le DOM d’origine avant que le navigateur ne l’analyse. Par conséquent, certains scripts de sécurité, tels que les implémentations qui démolissent un iframe, peuvent bloquer le chargement des pages dans le VEC.

Pour garantir la compatibilité, désactivez ces scripts de manière conditionnelle lorsque la page est chargée dans l’iframe [!DNL Target]. Vous pouvez le faire en toute sécurité en vérifiant la présence de l’objet `window.adobeVecExtension`, que [!DNL Target] injecte pendant le chargement du VEC.

Les fragments de code suivants sont des exemples de code qui démolissent un iframe et peuvent empêcher le chargement d’une page web dans le VEC :

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

Une simple vérification peut vérifier si une page web est incorporée dans [!DNL Target]. Le fragment de code ressemble à ceci :

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

+++ Les pages doivent accepter les paramètres d’URL pour que le compositeur d’expérience visuelle fonctionne.

Certains sites suppriment tous les paramètres d’URL de leurs pages, mais le compositeur d’expérience visuelle requiert ces paramètres.

+++

+++ Lorsqu’un script est utilisé dans le cadre d’HTML, déclarez toutes les variables et fonctions accessibles de l’extérieur sous l’espace de noms de fenêtre.

Le script est exécuté dans la portée de `target.js` après le chargement de la page. Par conséquent, toute variable ou fonction déclarée localement n’est pas accessible de l’extérieur du bloc de script.

*Incorrect :*

```html
<script>
  var myVar = 123;
  function myFunc() {
    //
  }
</script>
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

+++ L’action `customCode` dans le VEC ne fonctionne pas avec [!DNL Internet Explorer] 8.

`target.js` ne prend pas en charge cette action dans IE8 en raison des limitations d’IE8 lors de la gestion du contenu du script. Pour pallier ce problème, si la page contient jQuery et que jQuery est exposé globalement sur l’objet de fenêtre, `target.js` peut exécuter l’action `customCode`. Assurez-vous que `window.jQuery` et `window.jQuery.fn.prepend` sont définis.

+++

### Réorganisation des mbox et

**Un élément ne peut pas être déplacé en dehors d&#39;un conteneur suivi d&#39;une propriété CSS.**

+++ L&#39;élément [!UICONTROL Button] ne peut pas être sélectionné pour la réorganisation.

Les éléments **[!UICONTROL Button]** ne peuvent pas être sélectionnés directement pour la réorganisation. Pour permettre le réarrangement, placez les boutons dans un conteneur plus grand.

+++

+++ Ne réorganisez pas et ne déplacez pas le même élément.

Si un élément a été déplacé vers un autre emplacement et que le conteneur parent est ensuite sélectionné pour réorganiser les éléments enfants, l’élément déplacé n’est pas affecté et reste à son emplacement actuel. La réorganisation peut ne pas apparaître comme vous le souhaitez.

+++

+++ Seules les offres de permutation sont disponibles sur les mbox.

Les actions telles que **[!UICONTROL Modifier la classe]** et **[!UICONTROL Réorganiser]** ne sont pas autorisées dans une mbox.

+++

### Images

+++ L’action [!UICONTROL Modifier l’image] ne fonctionne pas sur une image d’un carrousel.

Par exemple, si la page contient un carrousel avec six images et qu’une image doit être permutée avec la deuxième image du carrousel, l’action **[!UICONTROL Modifier l’image]** ne fonctionne pas.

Pour pallier ce problème, sélectionnez le conteneur parent et utilisez l’action **[!UICONTROL Modifier HTML]** pour modifier l’HTML du carrousel et mettre à jour la source d’image de l’image souhaitée.

+++

+++ Les images ne peuvent pas être redimensionnées dans une mbox.

Si une image est permutée dans un élément de mbox, puis redimensionnée en fonction de la taille de l’élément de mbox, le redimensionnement n’est pas autorisé.

+++

+++ Une fois une image permutée, l’action [!UICONTROL Modifier] ne peut pas être sélectionnée.

Une fois l’image permutée, l’URL Scene7 ne peut pas être modifiée.

+++

+++ L’insertion d’une image à partir de la bibliothèque [!UICONTROL Content] (Scene7) et la modification de l’HTML rompt l’URL de l’image.

Ajoutez un élément d’ancrage dans la balise div `customHeaderMessage` avec un texte factice :

```html
<a href="#">
<span> Dummy text </span>
</a>
```

Sélectionnez cette balise div à l’aide de l’action **[!UICONTROL Insérer l’élément]** pour insérer une image en tant que frère du texte factice.

Une fois l’image insérée, le code se présente comme suit :

```html
<a href="#">
<span> Dummy text </span>
<img src=""> This is inserted Image. </img>
</a>
```

Supprimez l’élément span de texte de remplissage.

+++

### Suivi des clics et contenu externe

+++ Le suivi des clics ne fonctionne pas pour les éléments d’ancre qui contiennent des éléments autres que du texte brut ou des balises d’image.

Par exemple, le suivi des clics ne fonctionne pas si l’élément contient du code JavaScript.

+++

+++ Le suivi des clics est uniquement pris en charge sur la page sur laquelle les expériences sont créées ou sur la page de redirection.

Bien que le mode **[!UICONTROL Parcourir]** soit disponible pour le suivi des clics dans le VEC, le mode **[!UICONTROL Parcourir]** ne peut pas être utilisé pour ajouter le suivi des clics sur une page.

+++

+++ Les éléments HTML avec une source externe ne peuvent pas être modifiés.

Par exemple : balises vidéo, audio, intégré, iFrames et images.

+++
