---
keywords: règles d’inclusion ; critères d’inclusion ; recommandations ; promotion ; promotions ; filtrage dynamique ; dynamique ; correspondance d’attribut d’entité
description: Découvrez comment filtrer dynamiquement dans Adobe Target en comparant un groupe d’éléments potentiels à un élément spécifique avec lequel l’utilisateur a interagi.
title: Comment puis-je filtrer par correspondance d’attributs d’entité dans les Activités Recommendations ?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# ![Correspondance d&#39;attribut ](/help/assets/premium.png) PREMIUMEntity

Filtrez dynamiquement dans [!DNL Adobe Target] [!DNL Recommendations] en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel l’utilisateur a interagi.

>[!NOTE]
>
>Le [processus de création et d&#39;utilisation des règles d&#39;inclusion](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) pour les critères et les promotions est similaire, tout comme les cas d&#39;utilisation et les exemples.

Par exemple, ne recommander que les éléments qui correspondent à la marque de l’élément actif, comme dans l’exemple suivant :

Si la mbox d’un Landing page de marque renvoie `entity.brand=brandA`, seuls les produits de marque A sont renvoyés et affichés sur cette page. De même, sur le Landing page Marque pour la Marque B, seuls les produits Marque B sont renvoyés. Avec ce type de règle d’inclusion dynamique, l’utilisateur ne doit spécifier qu’une seule règle de recommandation qui renvoie des résultats de marque pertinents sur toutes les pages de la marque plutôt que de spécifier une collection ou un filtre statique pour correspondre à chaque nom de marque.

Notez que vous devez diffuser le `entity.brand` dans la mbox sur ces landings page pour que cela fonctionne.

## Exemples de correspondance d’attributs d’entité

[!UICONTROL La ] correspondance des attributs d’entité vous permet de recommander uniquement les éléments qui correspondent, par exemple :

* Attribut de l’élément actuellement affiché par l’utilisateur
* Article consulté le plus récemment par l’utilisateur
* Article acheté le plus récemment par l&#39;utilisateur
* L&#39;article que l&#39;utilisateur a le plus souvent consulté
* Élément stocké dans un attribut personnalisé du profil visiteur

### Éléments recommandés en fonction de la marque

Une fois les règles d’attribut d’entité créées, elles filtrent toutes les recommandations avec des attributs qui ne correspondent pas à la valeur d’entité transmise sur la page.

L’exemple suivant montre les recommandations correspondant à la marque de produit affichée sur la page :

Lorsque vous visitez une page qui comporte un produit Marque A, la page définit la valeur du paramètre `entity.brand` sur &quot;MarqueA&quot;.

![Exemple d’appel de Cible](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

Dans les recommandations de la page, vous verrez uniquement les produits de la marque A.

![Recommandations de marque A](/help/c-recommendations/c-algorithms/assets/brandA.png)

Si vous vue ensuite une page de produit de la marque B, la valeur `entity.brand` sera réinitialisée sur &quot;MarqueB&quot; et les produits de la marque B recommandés sur les pages de produits de la marque B s’afficheront.

![Recommandations de marque B](/help/c-recommendations/c-algorithms/assets/brandB.png)

### Mise à niveau vers un produit plus cher

Supposons que vous soyez un détaillant de vêtements et que vous souhaitiez encourager les utilisateurs à envisager des articles plus chers et donc plus rentables. Vous pouvez utiliser les opérateurs &quot;égal à&quot; et &quot;est compris entre&quot; pour promouvoir des articles plus chers provenant de la même catégorie et de la même marque. Par exemple, un détaillant de chaussures de sport peut promouvoir des chaussures de sport plus chères afin d’augmenter la vente d’un visiteur qui recherche des chaussures de sport, comme dans l’exemple suivant :

![Mise à niveau](/help/c-recommendations/c-algorithms/assets/upsell.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### Promotion de produits de marque privée

Vous pouvez mélanger des filtres dynamiques et statiques pour promouvoir des produits de marque privée. Par exemple, une société d&#39;approvisionnement de bureau peut promouvoir les cartouches de toner de la marque de la maison de la société afin de générer une vente plus rentable pour un visiteur qui examine le toner — et promouvoir les stylos de la marque de la maison de la société pour générer une vente plus rentable pour un visiteur qui regarde les stylos, comme dans l&#39;exemple suivant :

![Marque maison](/help/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
