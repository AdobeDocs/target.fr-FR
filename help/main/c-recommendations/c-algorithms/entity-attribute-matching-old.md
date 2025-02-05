---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance des attributs d’entité
description: Découvrez comment filtrer dynamiquement dans Adobe [!DNL Target] Recommendations en comparant un groupe d’éléments potentiels à un élément spécifique avec lequel l’utilisateur a interagi.
title: Comment filtrer par correspondance d’attributs d’entité dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Correspondance des attributs d’entité

Filtrez de manière dynamique dans [!DNL Adobe Target] [!DNL Recommendations] en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel l’utilisateur a interagi.

>[!NOTE]
>
>Le [processus de création et d’utilisation des règles d’inclusion](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) pour les critères et les promotions est similaire, ainsi que les cas d’utilisation et les exemples.

Par exemple, recommandez uniquement les éléments qui correspondent à la marque de l’élément actif, comme dans l’exemple suivant :

Si la mbox d’une page de destination de marque renvoie la valeur `entity.brand=brandA`, seuls les produits de la marque A sont renvoyés et affichés sur cette page. De même, sur la page de destination de la marque B, seuls les produits de la marque B sont renvoyés. Avec ce type de règle d’inclusion dynamique, l’utilisateur n’a qu’à spécifier une seule règle de recommandation qui renvoie les résultats de marque pertinents sur toutes les pages de marque, plutôt que de spécifier une collection ou un filtre statique pour correspondre à chaque nom de marque.

Pour que cela fonctionne, vous devez diffuser le `entity.brand` dans la mbox sur ces pages de destination.

## Exemples de correspondance d’attributs d’entité

[!UICONTROL Entity Attribute Matching] vous permet de recommander uniquement les éléments qui correspondent, par exemple :

* Attribut de l’élément que l’utilisateur consulte actuellement
* Élément que l’utilisateur a consulté le plus récemment
* L&#39;article que l&#39;utilisateur a acheté le plus récemment
* Élément que l’utilisateur a le plus consulté.
* Élément stocké dans un attribut personnalisé dans le profil du visiteur

### Recommandation d’articles en fonction de la marque

Une fois vos règles d’attributs d’entité créées, elles filtrent toutes les recommandations dont les attributs ne correspondent pas à la valeur d’entité transmise sur la page.

L’exemple suivant illustre des recommandations correspondant à la marque du produit affichée sur la page :

Lorsque vous consultez une page qui contient un produit de marque A, la page définit la valeur du paramètre `entity.brand` sur « BrandA ».

![Exemple d’appel Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

Dans les recommandations de la page, vous verrez uniquement les produits de la marque A.

![Recommandations relatives à la marque A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Si vous affichez ensuite une page de produit de la marque B, la valeur `entity.brand` est réinitialisée sur « Marque B » et les produits de la marque B recommandés apparaissent sur les pages de produits de la marque B.

![Recommandations relatives à la marque B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Intensification des ventes vers un produit plus cher

Supposons que vous soyez un détaillant de vêtements et que vous souhaitiez encourager les utilisateurs à envisager des articles plus chers et, par conséquent, plus rentables. Vous pouvez utiliser les opérateurs « est égal à » et « est compris entre » pour promouvoir des articles plus chers appartenant à la même catégorie et à la même marque. Par exemple, un détaillant de chaussures de course peut faire la promotion de chaussures de course plus coûteuses afin d’augmenter les ventes de chaussures de course à un visiteur, comme dans l’exemple suivant :

![Vente incitative](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

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

### Promouvoir les produits de marque privée

Vous pouvez combiner des filtres dynamiques et statiques pour promouvoir les produits de marque privée. Par exemple, une entreprise de fournitures de bureau peut promouvoir les cartouches de toner de la marque maison de l&#39;entreprise pour générer une vente plus rentable pour un visiteur qui cherche du toner — et promouvoir des stylos de la marque maison de l&#39;entreprise pour générer une vente plus rentable pour un visiteur qui cherche des stylos, comme dans l&#39;exemple suivant :

![Marque House](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
