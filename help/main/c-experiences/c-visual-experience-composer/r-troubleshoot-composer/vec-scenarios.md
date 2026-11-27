---
keywords: Recommandations
description: Explorez les scénarios courants qui montrent comment les modifications apportées à votre page dans le compositeur d’expérience visuelle (VEC) affectent la capacité d’Adobe Target à afficher une expérience.
title: Quels Sont Les Scénarios Courants De Modification D’Une Page ?
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
TQID: 'https://experienceleague.adobe.com/BI2SnUU5ilCf0auld15q1rpCrnLoPEwbe1fZO6G1quc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 4%
---
# Scénarios de modification d’une page {#vec-scenarios}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment les modifications apportées à une page en dehors de [!DNL Target] affectent la capacité de [!DNL Target] à afficher une expérience, à travers sept scénarios avec des exemples.

>[!ENDSHADEBOX]

Le sélecteur [!DNL Target] détermine l’emplacement d’affichage d’une expérience. Lorsqu’une page est modifiée en dehors de [!DNL Target], les modifications peuvent affecter la capacité de [!DNL Target] à trouver cet emplacement et à afficher l’expérience.

Le sélecteur fonctionne toujours avec une classe unique, qui n’est pas équivalente à un ID. Lorsqu’aucune classe n’est affectée à l’élément, le sélecteur comptabilise les frères précédents ayant le même nom de balise.

>[!NOTE]
>
>Les scénarios utilisent des éléments de liste comme exemples, mais les concepts s’appliquent à n’importe quel élément.

Le tableau suivant résume les scénarios. Dans chaque scénario, le sélecteur est `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`.

| Scénario | Action appliquée | Raison |
|---|---|---|
| Insérez un élément avec un nom de classe différent avant l’élément sélectionné | Oui | `li.women-section:eq(0)` n’est pas affecté |
| Insérer un élément avec le même nom de classe que l&#39;élément sélectionné | Non | Un nouvel élément prend la première position, ce qui rompt le sélecteur |
| Insérer un élément après l’élément sélectionné | Oui | Le nouvel élément est ajouté à la même position que l’élément parent |
| Supprimez l’élément qui précède immédiatement l’élément sélectionné | Oui | La classe de l’élément sélectionné n’est pas modifiée |
| Supprimez l’élément juste après l’élément sélectionné | Oui | La classe de l’élément sélectionné n’est pas modifiée |
| Supprimer l’élément sélectionné | Oui | L’élément a été supprimé. |
| Renommer la classe de l’élément sélectionné | Non | `class` est introuvable |

## Insérez un élément avec un nom de classe différent avant l’élément sélectionné

Un nouvel élément est inséré en tant que frère de l&#39;élément dans le sélecteur [!DNL Target]. Si la première classe de l’élément a été ajoutée par JavaScript, la diffusion échoue et l’action n’est pas appliquée.

**Élément inséré :**

```html
<li class="kids-section">Kids</li>
```

**Élément sélectionné :**

`<li class="women-section">Women</li>`

**Sélecteur :** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :** Le sélecteur fonctionne comme prévu, car `li.women-section:eq(0)` n’est pas affecté.

**Avant :**

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul>
</div>
```

**Après :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

## Insérer un élément avec le même nom de classe que l&#39;élément sélectionné

Une liste est insérée lorsqu&#39;un élément d&#39;une liste est sélectionné.

**Élément inséré :**

```html
<ul class="nav">
   <li class="item"> Sale </li>
   <li class="item"> Offers </li>
</ul>
```

**Élément sélectionné :**

`<li class="women-section">Women</li>`

**Sélecteur :** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :** Le sélecteur ne fonctionne pas. `ul.nav:eq(0)` pointe désormais vers un élément ajouté dynamiquement, qui n’est pas disponible. L’action n’est donc pas appliquée. L’ajout d’un élément de liste similaire avec la même classe, dynamiquement ou manuellement, après la création de l’activité, place un nouvel élément en première position, ce qui rompt le sélecteur.

**Avant :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

**Après (tentative) :**

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

## Insérer un élément après l’élément sélectionné

Une liste est insérée après l’élément de liste sélectionné.

**Élément inséré :**

```html
<ul class="nav">
   <li class="men-section"> Men Clothes</li>
   <li class="women-section"> Women Clothes</li>
</ul>
```

**Élément sélectionné :**

`<li class="women-section">Women Shoes</li>`

**Sélecteur :** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :** L’insertion d’une liste après la liste qui se termine par l’élément sélectionné fonctionne comme prévu. Le nouvel élément est ajouté à la même position que l&#39;élément sélectionné par rapport à l&#39;élément parent.

**Avant :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>       <li class="women-section">Women Shoes</li>
    </ul>
</div>
```

**Après :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>
        <li class="women-section">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## Supprimez l’élément qui précède immédiatement l’élément sélectionné

L’élément de liste avant la suppression de l’élément sélectionné.

**Élément supprimé :**

```html
<li class="men-section"> Men </li>
```

**Élément sélectionné :**

`<li class="women-section">Women</li>`

**Sélecteur :** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :** L&#39;élément a été supprimé, car la classe de l&#39;élément sélectionné n&#39;est pas modifiée.

**Avant :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Après :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Supprimez l’élément juste après l’élément sélectionné

L’élément de liste après la suppression de l’élément sélectionné.

**Élément supprimé :**

```html
<li class="kids-section">Kids</li>
```

**Élément sélectionné :**

`<li class="women-section">Women</li>`

**Sélecteur :** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :** L’élément a été supprimé avec succès, car la classe de l’élément sélectionné n’est pas modifiée et l’élément supprimé a une classe unique dans sa sous-arborescence parente.

**Avant :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Kids</li>
    </ul>
</div>
```

**Après :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Supprimer l’élément sélectionné

L’élément de liste sélectionné est supprimé.

**Élément supprimé :**

```html
<li class="women-section">Women</li>
```

**Élément sélectionné :**

`<li class="women-section">Women</li>`

**Sélecteur :** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :** L’élément a été supprimé.

**Avant :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Après :**

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## Renommer la classe de l’élément sélectionné

La classe de l’élément de liste sélectionné est modifiée.

**Élément modifié :**

```html
<li class="women-section">Women</li>
```

**Élément sélectionné :**

`<li class="women-section">Women</li>`

**Sélecteur :** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Résultat :** Impossible de renommer la classe, car `class` est introuvable.

**Avant :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Après (tentative) :**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div> 
```
