---
keywords: scintillement ; at.js ; mise en oeuvre ; asynchrone ; asynchrone ; synchrone ; synchrone
description: Découvrez comment at.js et Adobe [!DNL Target] empêchent le scintillement (le contenu par défaut s’affiche momentanément avant d’être remplacé par le contenu de l’activité) pendant le chargement de la page ou de l’application.
title: Comment at.js gère-t-il Flicker ?
feature: at.js
role: Developer
exl-id: f6c26973-e046-42ed-91db-95c8a4210a9d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 76%

---

# Gestion du scintillement par at.js

Informations sur la façon dont la bibliothèque JavaScript at.js de Target empêche le scintillement durant le chargement de la page ou de l’application.

Il y a scintillement lorsque du contenu par défaut est présenté temporairement aux visiteurs avant d’être remplacé par le contenu de l’activité. Ce phénomène peut déstabiliser les visiteurs et doit donc être évité.

## Utilisation d’une mbox globale créée automatiquement {#section_C502170D551C4F52AAFD8E82C41BB63A}

Lorsque vous activez la [Création automatique d’une Mbox globale](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13) lors de la configuration d’at.js, ce dernier gère le scintillement en modifiant le paramètre d’opacité au chargement de la page. Lorsque at.js charge, cela change le paramètre d’opacité du `<body>` sur « 0 », rendant la page initialement invisible pour les visiteurs. Lorsqu’une réponse de Target est reçue, ou si une erreur au niveau de la requête Target est détectée, at.js réinitialise le paramètre d’opacité sur 1. Ainsi, le visiteur ne voit la page qu’une fois le contenu de vos activités appliqué.

Si vous activez le paramètre lors de la configuration de at.js, at.js définit l’opacité du style HTML BODY sur 0. Après avoir reçu une réponse de Target, at.js réinitialise l’opacité de HTML BODY sur 1.

L’opacité définie sur 0 conserve le contenu de la page masqué pour empêcher le scintillement, mais le navigateur effectue toujours le rendu de la page et charge tous les éléments nécessaires tels que CSS, les images, etc.

Si l’opacité définie sur 0 ne fonctionne pas dans votre implémentation, vous pouvez également gérer le scintillement en personnalisant `bodyHiddenStyle` et en le définissant sur `body {visibility:hidden !important}`. Vous pouvez utiliser soit le corps de la valeur `{opacity:0 !important}`, soit `body {visibility:hidden !important}`, selon ce qui fonctionne le mieux pour votre situation spécifique.

L’illustration suivante présente les appels à Masquer/Afficher le corps dans at.js 1.*x* et at.js 2.x.

**at.js 2.x**

![Flux cible : demande de chargement de page at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

Pour plus d’informations sur le remplacement de `bodyHiddenStyle`, voir [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Gestion du scintillement lors du chargement asynchrone du fichier at.js

Le chargement d’at.js de manière asynchrone est un excellent moyen d’éviter de bloquer le rendu du navigateur. Cependant, cette technique peut entraîner un scintillement de la page web.

Vous pouvez éviter le scintillement en utilisant un fragment de code de pré-masquage qui sera visible une fois les éléments HTML pertinents personnalisés par [!DNL Target].

at.js peut être chargé de manière asynchrone, directement incorporé à la page ou via un gestionnaire de balises (lancement d’Adobe, gestionnaire dynamique de balises, etc.).

Si at.js est incorporé à la page, le fragment de code doit être ajouté avant de charger at.js. Si vous chargez at.js via un gestionnaire de balises, qui est également chargé de manière asynchrone, vous devez ajouter le fragment de code avant de charger le gestionnaire de balises. Si le gestionnaire de balises est chargé de manière synchrone, le script peut être inclus dans le gestionnaire de balises avant at.js.

Le fragment de code de pré-masquage se présente comme suit :

```
;(function(win, doc, style, timeout) {
  var STYLE_ID = 'at-body-style';

  function getParent() {
    return doc.getElementsByTagName('head')[0];
  }

  function addStyle(parent, id, def) {
    if (!parent) {
      return;
    }

    var style = doc.createElement('style');
    style.id = id;
    style.innerHTML = def;
    parent.appendChild(style);
  }

  function removeStyle(parent, id) {
    if (!parent) {
      return;
    }

    var style = doc.getElementById(id);

    if (!style) {
      return;
    }

    parent.removeChild(style);
  }

  addStyle(getParent(), STYLE_ID, style);
  setTimeout(function() {
    removeStyle(getParent(), STYLE_ID);
  }, timeout);
}(window, document, "body {opacity: 0 !important}", 3000));
```

Par défaut, le fragment de code masque préalablement l’ensemble HTML BODY. Dans certains cas, vous souhaitez uniquement masquer préalablement certains éléments HTML et non la totalité de la page. Vous pouvez y parvenir en personnalisant le paramètre de style. Il peut être remplacé par un élément qui masque préalablement seulement des régions spécifiques de la page.

Par exemple, vous disposez de deux régions identifiées par les ID container-1 et container-2, alors le style peut être remplacé par ce qui suit :

```
#container-1, #container-2 {opacity: 0 !important}
```

Au lieu de la valeur par défaut :

```
body {opacity: 0 !important}
```

## Gestion du scintillement dans at.js 2.x pour triggerView()

Lorsque vous utilisez `triggerView()` pour afficher du contenu ciblé dans votre SPA, la gestion du scintillement est fournie en dehors de la zone. Cela signifie que la logique de pré-masquage ne doit pas être ajoutée manuellement. À la place, at.js 2.x pré-masque l’emplacement de votre vue avant d’appliquer le contenu ciblé.

## Gérez le scintillement avec getOffer() et applyOffer().

Comme `getOffer()` et `applyOffer()` sont des API de bas niveau, il n’y a aucun contrôle de scintillement intégré. Vous pouvez transmettre un sélecteur ou un élément HTML sous la forme d’une option à `applyOffer()`. Dans ce cas, `applyOffer()` ajoute le contenu de l’activité à cet élément spécifique. Veillez toutefois à ce que l’élément soit correctement pré-masqué avant d’appeler `getOffer()` et `applyOffer()`.

```
document.documentElement.style.opacity = "0";
 
adobe.target.getOffer({
    mbox: 'target-global-mbox',
    success: function(offer) {
        adobe.target.applyOffer({
            mbox: 'target-global-mbox',
            offer: offer
        });
 
        document.documentElement.style.opacity = "1";
    },
    error: function() {
        document.documentElement.style.opacity = "1";        
    }
});
```

## Utilisation d’une mbox régionale avec mboxCreate() dans at.js 1.x (non pris en charge dans at.js 2.x)

Si vous utilisez une implémentation de mbox régionale, vous pouvez utiliser `mboxCreate()` avec votre page configurée comme suit :

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

Si vos pages sont correctement configurées, at.js gère le scintillement en activant/désactivant, suivant les besoins, la propriété de « visibilité » CSS de l’élément avec la classe mboxDefault.
