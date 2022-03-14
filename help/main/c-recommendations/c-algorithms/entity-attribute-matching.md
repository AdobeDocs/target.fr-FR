---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance des attributs d’entité
description: Découvrez comment filtrer dynamiquement dans Adobe [!DNL Target] Recommendations en comparant un groupe d’éléments potentiels à un élément spécifique avec lequel l’utilisateur a interagi.
title: Comment Filtrer Par Correspondance D’Attributs D’Entité Dans Les Activités Recommendations ?
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Correspondance des attributs d’entité

Filtrage dynamique dans [!DNL Adobe Target] [!DNL Recommendations] en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel l’utilisateur a interagi.

>[!NOTE]
>
>Le [processus de création et d’utilisation des règles d’inclusion](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) pour les critères et les promotions est similaire, tout comme les cas d’utilisation et les exemples.

Par exemple, recommandez uniquement des articles correspondant à la marque de l’article en cours, comme dans l’exemple suivant :

Si la mbox d’une page d’entrée de marque est renvoyée `entity.brand=brandA`, seuls les produits de la marque A sont renvoyés et affichés sur cette page. De même, sur la page d’entrée de la marque B, seuls les produits de la marque B sont renvoyés. Avec ce type de règle d’inclusion dynamique, l’utilisateur ne doit spécifier qu’une seule règle de recommandation qui renvoie les résultats pertinents de la marque sur toutes les pages de marque plutôt que de spécifier une collection ou un filtre statique pour correspondre à chaque nom de marque.

Notez que vous devez envoyer la variable `entity.brand` dans la mbox sur ces pages d’entrée pour que cela fonctionne.

## Exemples de correspondance des attributs d’entité

[!UICONTROL Correspondance des attributs d’entité] vous permet de recommander uniquement les éléments qui correspondent, par exemple :

* Attribut de l’élément que l’utilisateur consulte actuellement
* Article consulté le plus récemment par l’utilisateur
* Article acheté le plus récemment par l’utilisateur
* Article que l’utilisateur a consulté le plus souvent
* Article stocké dans un attribut personnalisé dans le profil du visiteur

### Éléments recommandés en fonction de la marque

Une fois vos règles d’attributs d’entité créées, elles filtrent toutes les recommandations avec des attributs qui ne correspondent pas à la valeur d’entité transmise sur la page.

L’exemple suivant montre les recommandations correspondant à la marque de produit affichée sur la page :

Lorsque vous visitez une page qui comprend un produit Marque A, la page définit la valeur de la variable `entity.brand` sur &quot;BrandA&quot;.

![Exemple d’appel Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

Dans les recommandations de la page, les produits de la marque A s’affichent uniquement.

![Recommandations de marque A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Si vous affichez ensuite une page de produit Marque B, la variable `entity.brand` La valeur sera réinitialisée sur &quot;BrandB&quot; et les produits de marque B recommandés sur les pages de produits de marque B s’affichent.

![Recommandations relatives à la marque B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Upgrade vers un produit plus cher

Supposons que vous soyez un détaillant de vêtements et que vous souhaitiez encourager les utilisateurs à envisager des articles plus chers et, par conséquent, plus rentables. Vous pouvez utiliser les opérateurs &quot;est égal à&quot; et &quot;est compris entre&quot; pour promouvoir des articles plus chers issus de la même catégorie et de la même marque. Par exemple, un détaillant de chaussures de course plus cher peut promouvoir des chaussures de course plus chères afin d’augmenter la vente à un visiteur qui recherche des chaussures de course, comme dans l’exemple suivant :

![Optimisation](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

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

Vous pouvez mélanger des filtres dynamiques et statiques pour promouvoir des produits de marque privée. Par exemple, une entreprise d’approvisionnement de bureau peut promouvoir les cartouches d’imprimantes de la marque maison de l’entreprise afin de générer une vente plus rentable pour un visiteur qui consulte l’encre — et promouvoir les stylos de la marque maison de l’entreprise pour générer une vente plus rentable pour un visiteur qui regarde les stylos, comme dans l’exemple suivant :

![Marque de la maison](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
