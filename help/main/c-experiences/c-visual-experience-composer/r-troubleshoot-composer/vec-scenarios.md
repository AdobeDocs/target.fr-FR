---
keywords: Recommendations
description: Explorez les scénarios courants qui montrent comment les modifications apportées à votre page dans le compositeur d’expérience visuelle (VEC) affectent la capacité d’affichage d’une expérience dans Adobe Target.
title: Quels Sont Les Scénarios De Modification De Page Courants ?
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 90%

---

# Scénarios de modification d’une page

Les scénarios de cette rubrique montrent comment les modifications apportées à votre page affectent la capacité Adobe Target à afficher une expérience.

Le sélecteur de Target détermine où afficher une expérience. Si une page est modifiée en dehors de Target, les modifications affectent la capacité de Target à afficher l’expérience.

Lors de l’utilisation du sélecteur, la classe unique n’est pas équivalente à l’identifiant. Le sélecteur fonctionne systématiquement avec une classe unique. Si aucune classe n’est affectée à l’élément, le sélecteur calcule le nombre de frères antérieurs qui sont dotés du même nom de balise.

>[!NOTE]
>
>Bien que ces scénarios utilisent des éléments de liste comme exemples, les concepts s’appliquent à tout élément.

## Scénario : insertion d’un élément avec un nom de classe différent avant l’élément sélectionné {#section_298F661F72384F6AB957D5885A99D822}

Dans cet exemple, un nouvel élément est inséré en tant que frère de l’élément dans le sélecteur de Target.

Il est possible que la première classe présente sur l’élément puisse être ajoutée par JavaScript. Dans ce cas, la diffusion échoue et l’action n’est pas appliquée.

**Élément inséré :**

```html
<li class="kids-section">Kids</li>
```

**Sélectionné :**

`<li class="women-section">Women</li>`

Sélecteur : `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :**

Le sélecteur fonctionne comme prévu car `li.women-section:eq(0)` n’est pas affecté.

Avant :

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul> 
</div>
```

Après :

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

## Scénario : insertion d’un élément avec le même nom de classe en tant qu’élément sélectionné {#section_0969B88C2F154E648D9969C8C85EF55A}

Dans ce scénario, une tentative est réalisée d’insérer une liste lorsqu’un élément d’une liste est sélectionné.

**Élément inséré :**

```html
<ul class="nav"> 
   <li class="item"> Sale </li> 
   <li> class="item"> Offers </li> 
</ul>
```

**Sélectionné :**

`<li class="women-section">Women</li>`

Sélecteur : `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :**

Le sélecteur ne fonctionne pas car `ul.nav:eq(0)` fournit un élément ajouté dynamiquement. L’élément ne sera pas disponible et l’action n’est pas appliquée. Lorsqu’un élément de liste similaire doté de la même classe est ajouté dynamiquement ou manuellement après la création d’une activité, un nouvel élément au niveau de la première position est créé. Cela arrête le sélecteur.

Avant :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

Après (tentative) :

```html
<div id="wrap">
     <ul class="nav">
        <li class="item"> Sale</li>
        <li> class="item"> Offers</li>
     </ul>
     <ul class="nav">
       <li class="men-section"> Men</li>
       <li class="women-section">Women</li>
    </ul>
</div>
```

## Scénario : insertion d’un élément après l’élément sélectionné {#section_15B07B84BEE94ED39D85BBBE0733E170}

Dans ce scénario, un élément de liste est inséré après l’élément sélectionné.

**Élément inséré :**

```html
<ul class="nav"> 
   <li class="men-section"> Men Clothes</li> 
   <li class="women-section"> Women Clothes</li> 
</ul>
```

**Sélectionné :**

`<li class="women-section">Women Shoes</li>`

Sélecteur : `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :**

Dans ce cas, l’insertion d’une liste après la fin de la liste avec l’élément de liste sélectionné fonctionne comme prévu. Le nouvel élément est ajouté à la même position que l’élément sélectionné par rapport à l’élément parent.

Avant :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>       <li class="women">Women Shoes</li>
    </ul>
</div>
```

Après :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>
        <li class="women">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## Scénario : suppression de l’élément précédent immédiatement un autre élément {#section_F193674F04F84AA593EAA1137C880EBA}

Dans ce scénario, l’élément de liste précédent l’élément sélectionné est supprimé.

**Élément supprimé :**

```html
<li class="men-section"> Men </li>
```

**Sélectionné :**

`<li class="women-section">Women</li>`

Sélecteur : `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :**

L’élément est supprimé avec succès car la classe de l’élément sélectionné n’est pas modifiée.

Avant :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Après :

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Scénario : suppression de l’élément suivant immédiatement un autre élément {#section_F83B51BE54924FB58679D512DAF1EBB2}

Dans ce scénario, l’élément de liste suivant l’élément sélectionné est supprimé.

**Élément supprimé :**

```html
<li class="kids-section">Kids</li>
```

**Sélectionné :**

`<li class="women-section">Women</li>`

Sélecteur : `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :**

L’élément est supprimé avec succès car la classe de l’élément sélectionné n’est pas modifiée. L’élément supprimé inclut une classe unique au sein de la sous-arborescence parente.

Avant :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Women</li>
    </ul>
</div>
```

Après :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Scénario : suppression de l’élément sélectionné {#section_1989CF1E2C344CC5963084ED83C18F9C}

Dans ce scénario, l’élément de liste sélectionné est supprimé.

**Élément supprimé :**

```html
<li class="women-shoes">Women</li>
```

**Sélectionné :**

`<li class="women-shoes">Women</li>`

Sélecteur : `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :**

L’élément est bien supprimé.

Avant :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

Après :

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## Scénario : renommer la classe de l’élément sélectionné {#section_79D244C588BA452DB8E433D82B7F63EA}

Dans ce scénario, la classe de l’élément de liste sélectionné est modifiée.

**Élément modifié :**

```html
<li class="women-section">Women</li>
```

**Sélectionné :**

`<li class="women-section">Women</li>`

Sélecteur : `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :**

Il est impossible de renommer la classe de l’élément car `class` est introuvable.

Avant :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Après (tentative) :

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```
