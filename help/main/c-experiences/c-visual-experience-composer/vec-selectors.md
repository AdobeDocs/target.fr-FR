---
keywords: Ciblage d’expérience, Test de page de destination
description: Un sélecteur d’éléments est une expression CSS qui peut identifier un ou plusieurs éléments. Découvrez comment utiliser les sélecteurs d’éléments dans le compositeur  [!DNL Target] ’expérience visuelle (VEC) d’Adobe.
title: Puis-je utiliser des sélecteurs d’éléments dans le compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 31%

---

# Sélecteurs d’éléments utilisés dans le compositeur d’expérience visuelle

Un sélecteur d’éléments est une expression CSS qui peut identifier un ou plusieurs éléments.

Vous trouverez des informations de base sur les sélecteurs CSS dans le document [Sélecteurs](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) sur le *[!DNL Mozilla Developer Network]* (MDN).

Vous pouvez définir si vous utilisez l’élément classé ou les ID d’élément dans vos préférences de compte. Cliquez sur **[!UICONTROL Administration > Visual Experience Composer]**, puis choisissez vos sélecteurs CSS préférés.

* **Utiliser les ID d’élément** : à désactiver si le même ID est utilisé pour plusieurs éléments ou si les ID d’élément peuvent changer au chargement de la page.
* **Utiliser les classes d’éléments** : désactivez cette option si les classes d’éléments sur une page peuvent changer.
* **Utiliser les sélecteurs favoris** : activez cette option si vous souhaitez utiliser des sélecteurs uniques dans le compositeur d’expérience visuelle pour identifier les zones clés de votre site web.

>[!NOTE]
>
>Les classes d’éléments sont disponibles en tant que sélecteurs dans les activités [!UICONTROL A/B Test], [!UICONTROL Automated Personalization] et [!UICONTROL &#x200B; Multivariate Test].

Pour plus d’informations sur quand utiliser des sélecteurs CSS et quand utiliser des identifiants uniques, consultez les [Bonnes pratiques et limites du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6).

## Génération [!DNL Target]’un sélecteur pour un élément {#section_D89D954BCBFB486CA081BE183776A475}

[!DNL Target] utilise un algorithme simple pour créer un sélecteur. Voici une très brève explication de la logique de génération :

1. Si un élément possède un ID, par exemple `id="container"`, le sélecteur de l’élément est `#container`.

   Par exemple :

   ```html
   <div class="wrapper">
     <div id="container"> <!-- Selector is computed for this element -->
       <ul class="navigation">
         <li class="item active"> Home </li>
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

1. Si un élément contient un attribut de classe, [!DNL Target] tente d’exploiter la première classe de toutes les classes présentes sur l’élément.

   [!DNL Target] tente d’analyser l’élément parent jusqu’à ce qu’il trouve l’élément `<HTML>` ou un élément avec un ID. Chaque fois qu’un élément contient un ID et que le sélecteur est calculé sur son enfant descendant, l’ID de cet élément contribue au sélecteur.

   Par exemple :

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li class="item active"> Home </li> <!-- Selector is computed for this element -->
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

   Dans cet exemple :

   Sélecteur : `#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` (« > » indique l’enfant immédiat.)

   `eq` indique à l’index qu’il y a un élément qui comporte &quot;tagName=UL&quot; et que la première classe est `navigation`. Par conséquent, `index` est égal à 0. Pour plus d’informations, voir l’article [Selectors (Sélecteurs)](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) dans MDN.

1. Si un élément ne contient pas de classe, [!DNL Target] utilise `tagName` pour l’élément et parcourt l’élément parent jusqu’à ce que l’élément `<HTML>` ou un élément doté d’un ID soit trouvé.

   Par exemple :

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li> Home </li>
         <li> Men </li>
         <li class="active"> Women </li>
         <li> Kids </li><!-- Selector is computed for this element -->
       </ul>
     </div>
   </div>
   ```

   Sélecteur : `#container` > `ul.navigation(0)` > `li:nth-of-type(4)`.

Dans le processus ci-dessus :

* Vous pouvez utiliser n’importe quel sélecteur CSS tant qu’il identifie de manière unique un élément dans le DOM.
* L’approche ci-dessus est celle utilisée par [!DNL Target]. [!DNL Target] ne vous oblige pas à utiliser cette approche. Vous pouvez ajouter n’importe quel sélecteur tant que le point n° 1 est vrai.
* Vous pouvez utiliser n’importe quel attribut dans le sélecteur. Ce document utilise uniquement un nom de classe à titre d’exemple.
