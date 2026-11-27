---
keywords: Ciblage d’expérience, Test de page de destination
description: Un sélecteur d’éléments est une expression CSS qui peut identifier un ou plusieurs éléments. Découvrez comment utiliser les sélecteurs d’éléments dans le compositeur d’expérience visuelle (VEC) d’Adobe [!DNL Target].
title: Puis-je utiliser des sélecteurs d’éléments dans le compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
TQID: 'https://experienceleague.adobe.com/sqvUyLFddt7HPHH62jwpOZmwTIMSg-hyLIUr8w-x7vg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 4%
---
# Sélecteurs d’éléments utilisés dans le [!UICONTROL compositeur d’expérience visuelle] {#vec-selectors}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez le fonctionnement des sélecteurs d’éléments dans le [!UICONTROL compositeur d’expérience visuelle] (VEC), comment choisir les sélecteurs utilisés et comment [!DNL Target] génère un sélecteur pour un élément.

>[!ENDSHADEBOX]

Un sélecteur d’éléments est une expression CSS qui peut identifier un ou plusieurs éléments. Des informations de base sur les sélecteurs CSS sont disponibles dans le document [Sélecteurs](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) sur le *[!DNL Mozilla Developer Network]* (MDN).

L’utilisation des classes d’éléments ou des identifiants d’élément est définie dans les préférences du compte. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Compositeur d’expérience visuelle]**, puis choisissez les sélecteurs CSS préférés :

* **[!UICONTROL Utiliser des ID d’élément]** : à désactiver si le même ID est utilisé pour plusieurs éléments ou si les ID d’élément peuvent changer au chargement de la page.
* **[!UICONTROL Utiliser des classes d’éléments]** : désactivez cette option si les classes d’éléments sur une page peuvent changer.
* **[!UICONTROL Utiliser des sélecteurs préférés]** : activez cette option pour utiliser des sélecteurs uniques dans le compositeur d’expérience visuelle afin d’identifier les zones clés du site web.

>[!NOTE]
>
>Les classes d’éléments sont disponibles en tant que sélecteurs dans les activités de **[!UICONTROL test A/B]**, **[!UICONTROL Automated Personalization]** et **[!UICONTROL test multivarié]**.

Pour plus d’informations sur l’utilisation des sélecteurs CSS et l’utilisation d’identifiants uniques, consultez [Bonnes pratiques et limites du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#vec-best-practices).

## Comment [!DNL Target] génère un sélecteur pour un élément {#generate-selector}

[!DNL Target] utilise un algorithme simple pour créer un sélecteur. La logique de génération est la suivante :

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

1. Si un élément contient un attribut de classe, [!DNL Target] tente d&#39;utiliser la première classe de toutes les classes présentes sur l&#39;élément.

   [!DNL Target] tente d&#39;analyser l&#39;élément parent jusqu&#39;à ce qu&#39;il trouve l&#39;élément `<HTML>` ou un élément avec un ID. Chaque fois qu’un élément contient un ID et que le sélecteur est calculé sur son enfant descendant, l’ID de cet élément contribue au sélecteur.

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

   Dans cet exemple, le sélecteur est `#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` (« > » indique l’enfant immédiat).

   `eq` donne l’index de l’élément qui a « tagName=UL » et la première classe `navigation`. Par conséquent, `index` est égal à 0. Pour plus d’informations, voir l’article [Selectors (Sélecteurs)](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) dans MDN.

1. Si un élément ne contient pas de classe, [!DNL Target] utilise `tagName` pour l’élément et parcourt l’élément parent jusqu’à ce que l’élément `<HTML>` ou un élément avec un ID soit trouvé.

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

   Le sélecteur est `#container` > `ul.navigation:eq(0)` > `li:nth-of-type(4)`.

Dans ce processus :

* Tout sélecteur CSS peut être utilisé, à condition qu’il identifie de manière unique un élément dans le DOM.
* L&#39;approche ci-dessus est celle utilisée par [!DNL Target]. [!DNL Target] ne rend pas obligatoire cette approche. N’importe quel sélecteur peut être ajouté, à condition qu’il identifie l’élément de manière unique.
* N’importe quel attribut peut être utilisé dans le sélecteur. Cet article utilise uniquement un nom de classe comme exemple.
