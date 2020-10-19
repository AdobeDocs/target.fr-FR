---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: Filtrez dynamiquement dans Adobe Target en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel l’utilisateur a interagi.
title: Filtrer par correspondance d’attributs d’entité dans les règles d’inclusion dynamique dans Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 0%

---


# ![Correspondance d&#39;attribut d&#39;entité PREMIUM](/help/assets/premium.png)

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

Par exemple, ne recommander que les éléments qui correspondent à la marque de l’élément actif, comme dans l’exemple suivant :

Si la mbox d’un Landing page de marque est renvoyée `entity.brand=Nike`, seuls les produits Nike sont renvoyés et affichés sur cette page. De même, sur le Landing page Marque pour Adidas, seuls les produits Adidas sont renvoyés. Avec ce type de règle d’inclusion dynamique, l’utilisateur ne doit spécifier qu’une seule règle de recommandation qui renvoie des résultats de marque pertinents sur toutes les pages de la marque plutôt que de spécifier une collection ou un filtre statique pour correspondre à chaque nom de marque.

Notez que vous devez diffuser la `entity.brand` mbox sur ces landings page pour que cela fonctionne.

## Exemples de correspondance d’attributs d’entité

[!UICONTROL La Correspondance] d’attributs d’entité vous permet de recommander uniquement les éléments qui correspondent, par exemple :

* Attribut de l’élément actuellement affiché par l’utilisateur
* Article consulté le plus récemment par l’utilisateur
* Article acheté le plus récemment par l&#39;utilisateur
* L&#39;article que l&#39;utilisateur a le plus souvent consulté
* Élément stocké dans un attribut personnalisé du profil visiteur

### Éléments recommandés en fonction de la marque

Une fois les règles d’attribut d’entité créées, elles filtrent toutes les recommandations avec des attributs qui ne correspondent pas à la valeur d’entité transmise sur la page.

L’exemple suivant montre les recommandations correspondant à la marque de produit affichée sur la page :

Lorsque vous visitez une page qui comporte un produit Nike, la page définit la valeur du `entity.brand` paramètre sur &quot;Nike&quot;.

![Exemple d’appel de Cible](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

Dans les recommandations de la page, vous verrez uniquement les produits Nike.

![Recommandations de Nike](/help/c-recommendations/c-algorithms/assets/nike.png)

Si vous vue ensuite une page de produits Adidas, la `entity.brand` valeur sera réinitialisée sur &quot;Adidas&quot; et les produits Adidas recommandés sur les pages de produits Adidas s’afficheront.

![Recommandations supplémentaires](/help/c-recommendations/c-algorithms/assets/adidas.png)

### Mise à niveau vers un produit plus cher

Supposons que vous soyez un détaillant de vêtements et que vous souhaitiez encourager les utilisateurs à envisager des articles plus chers et donc plus rentables. Vous pouvez utiliser les opérateurs &quot;égal à&quot; et &quot;est compris entre&quot; pour promouvoir des articles plus chers provenant de la même catégorie et de la même marque. Par exemple, un détaillant de chaussures de sport peut promouvoir des chaussures de sport plus chères afin d’augmenter la vente d’un visiteur qui recherche des chaussures de sport, comme dans l’exemple de code suivant :

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

Vous pouvez mélanger des filtres dynamiques et statiques pour promouvoir des produits de marque privée. Par exemple, une société d&#39;approvisionnement de bureau peut promouvoir les cartouches de toner de la marque de la maison de la société pour générer une vente plus rentable pour un visiteur qui examine le toner — et promouvoir les stylos de la marque de la maison de la société pour générer une vente plus rentable pour un visiteur qui regarde les stylos, comme dans l&#39;exemple de code suivant :

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
