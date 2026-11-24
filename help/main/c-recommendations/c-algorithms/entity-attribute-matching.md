---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance des attributs d’entité
description: Découvrez comment filtrer dynamiquement dans [!DNL Target Recommendations] en comparant un groupe d’éléments potentiels à un élément spécifique avec lequel l’utilisateur a interagi.
title: Correspondance des attributs d’entité
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
TQID: 'https://experienceleague.adobe.com/2cBSfWXS96u7iumehPd7enxPjQcebkQCdSBSHWOUcJg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 5%
---
# Correspondance des attributs d’entité {#entity-attribute-matching}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment filtrer les recommandations de manière dynamique dans [!DNL Adobe Target Recommendations] en comparant un groupe d’éléments recommandés potentiels à un élément spécifique avec lequel le visiteur a interagi.

>[!ENDSHADEBOX]

**[!UICONTROL Correspondance des attributs d’entité]** recommande uniquement les éléments qui correspondent à un attribut d’un élément avec lequel le visiteur a interagi. Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Pour plus d’informations, voir [Utilisation de règles d’inclusion dynamiques et statiques](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Exemples de correspondance d’attributs d’entité

**[!UICONTROL La correspondance des attributs d&#39;entité]** ne peut recommander que les éléments qui correspondent, par exemple :

* Attribut de l’élément que le visiteur consulte actuellement
* L’élément que le visiteur a le plus récemment consulté
* L’article que le visiteur a acheté le plus récemment
* Élément que le visiteur a le plus consulté
* Élément stocké dans un attribut personnalisé dans le profil du visiteur

### Recommandation d’articles en fonction de la marque

Une fois les règles d’attribut d’entité créées, elles filtrent toutes les recommandations avec des attributs qui ne correspondent pas à la valeur d’entité transmise sur la page. La valeur `entity.brand` doit être diffusée dans la mbox sur les pages pour que ce processus fonctionne.

Avec ce type de règle d’inclusion dynamique, une seule règle de recommandation doit être spécifiée pour renvoyer les résultats de marque pertinents sur toutes les pages de marque, au lieu d’une collection ou d’un filtre statique pour chaque nom de marque.

Par exemple, lorsqu&#39;une page contenant un produit de marque A est affichée, la page définit la valeur du paramètre `entity.brand` sur « BrandA ». Sur une page de destination de marque, la mbox renvoie `entity.brand=brandA`.

![Exemple d&#39;appel Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

Les recommandations de la page contiennent alors uniquement des produits de marque A.

![Recommandations relatives à la marque A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Lorsqu&#39;une page de produit de marque B s&#39;affiche, la valeur `entity.brand` est réinitialisée sur « Marque B » et seuls les produits de marque B sont recommandés. De même, sur la page de destination de la marque B, seuls les produits de la marque B sont renvoyés.

![Recommandations relatives à la marque B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Intensification des ventes vers un produit plus cher

Pour inciter les visiteurs à envisager des articles plus chers et, par conséquent, plus rentables, les opérateurs « égal à » et « est compris entre » peuvent promouvoir des articles plus chers de la même catégorie et de la même marque. Par exemple, un retailer de chaussures de course peut promouvoir des chaussures de course plus coûteuses pour augmenter les ventes d’un visiteur qui envisage d’acheter des chaussures de course, comme dans l’exemple suivant :

![Ventes incitatives](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

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

Les filtres dynamiques et statiques peuvent être mélangés pour promouvoir les produits de marque privée. Par exemple, une société de fournitures de bureau peut promouvoir les cartouches de toner de la marque maison de l&#39;entreprise afin de générer une vente plus rentable pour un visiteur qui recherche du toner et des stylos de la marque maison de l&#39;entreprise pour un visiteur qui recherche des stylos, comme dans l&#39;exemple suivant :

![Marque Maison](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
