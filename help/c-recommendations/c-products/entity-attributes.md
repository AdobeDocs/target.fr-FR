---
keywords: entity;entity attributes;pass information to Recommendations;behavioral data;data counter;define relative URL;display inventory level;define price;define profit margin;custom attributes
description: Utilisez les attributs d’entité pour transmettre des informations sur les produits ou le contenu à Adobe Target Recommendations.
title: Attributs d’entité
feature: entities
uuid: 27672881-a79c-4271-9a61-defddb9a5249
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 88%

---


# ![PREMIUM](/help/assets/premium.png) Attributs d’entité{#entity-attributes}

Use entity attributes to pass product or content information to [!DNL Adobe Target Recommendations].

[!DNL Recommendations] envoie le ou `productId` (appelé `productPurchasedId` `entity.id` dans le code) utilisé dans les algorithmes.

>[!NOTE]
>
>* `entity.id` doit correspondre à la page `productPurchasedId` envoyée à la page de confirmation de commande et à la page `productId` utilisée dans les rapports de produits Adobe Analytics.
   >
   >
* Les valeurs d’attribut d’entité fournies expirent après 61 jours. Cela signifie que vous devez vous assurer que la dernière valeur de chaque attribut d’entité est transmise aux recommandations Target au moins une fois par mois pour chaque élément de votre catalogue.


La plupart des paramètres prédéfinis acceptent une seule valeur uniquement, les nouvelles valeurs remplaçant les anciennes. Le paramètre `categoryId` peut accepter une liste de valeurs délimitées par des virgules pour chaque catégorie contenant ce produit. Les nouvelles valeurs `categoryId` n’écrasent pas les valeurs existantes, mais sont ajoutées lors de la mise à jour de l’entité (250 caractères maximum).

En général, la mbox d’affichage d’informations peut ressembler à l’exemple suivant si vous utilisez at.js 1.*x* avec `mboxCreate`.

>[!NOTE]
>
>* Si vous utilisez at.js 2.*x*, `mboxCreate` (comme utilisé dans l’exemple suivant) n’est plus pris en charge. Pour transmettre des informations sur les produits ou le contenu à Recommendations à l’aide d’at.js 2.*x*, utilisez [targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md). Pour obtenir un exemple de ce processus, consultez [Planifier et mettre en oeuvre Recommendations](/help/c-recommendations/plan-implement.md).

>



Tous les attributs de paramètres d’entité sont sensibles aux majuscules.

```
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=/help/baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=/help/baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>Il est préférable d’utiliser des URL relatives pour `pageUrl` et `thumbnailUrl`, plutôt que des URL absolues, car les recommandations reçoivent les données envoyées de tous les environnements sur le site. L’utilisation d’URL relatives évite d’avoir à utiliser des liens codés en dur sur un serveur de développement ou de test.

Si la mbox se situe sur une page de produit, vous pouvez inclure l’identifiant du produit et l’identifiant de sa catégorie. L’algorithme sélectionné détermine ce qui s’affiche. L’identifiant du produit est utilisé pour les algorithmes d’affinité et l’identifiant de la catégorie, pour les algorithmes de catégorie.

## Variables disponibles

La liste ci-dessous décrit les variables disponibles.

### entity.id

Une seule valeur uniquement.

Ce paramètre obligatoire identifie le produit. Cet ID alphanumérique doit être le même dans tous les produits [!DNL Adobe Experience Cloud] utilisés, y compris [!DNL Analytics], pour que les différents produits reconnaissent l’élément et partagent les données le concernant.

Les valeurs de `entity.id` ne doivent pas contenir de barres obliques, d’esperluettes, de points d’interrogation, de symboles de pourcentage, de virgules ou d’autres caractères de ponctuation nécessitant le codage d’URL lors de leur passage dans un appel d’API REST. Les tirets et les caractères de soulignement sont autorisés. Le fait d’inclure des signes de ponctuation non autorisés dans une valeur `entity.id` entraîne l’échec de certaines fonctionnalités de [!DNL Recommendations].

Exemple : `'entity.id=67833'`

### entity.name

Une seule valeur uniquement.

Nom du produit affiché sur le site web lorsque ce produit est recommandé.

Exemple : `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

Prend en charge plusieurs valeurs (liste délimitée par des virgules).

Catégorie de la page en cours. Plusieurs catégories peuvent être incluses, tels que la sous-section secondaire « cardigans » (à savoir : womens, womens:sweaters, womens:sweaters:cardigans). S’il existe plusieurs catégories, elles doivent être séparées par des virgules.

`categoryId`est limitée à 250 caractères.

>[!NOTE]
>
>Pour afficher une recommandation basée sur une catégorie dans une page [!UICONTROL Catégorie], seule une `categoryId` peut être transférée à la mbox utilisée pour afficher cette recommandation spécifique. La valeur de `categoryId` doit correspondre exactement à la valeur de `entity.categoryId` transmise sur la page [!UICONTROL Détail du produit].

Exemples :

* Exemple de page Détail du produit : womens, womens:sweaters, womens:sweaters:cardigans
* Exemple de page Catégorie Pulls : womens:sweaters
* Exemple de page Catégorie Gilets : womens:sweaters:cardigans

Pour les recommandations selon les catégories, une virgule est utilisée pour séparer les valeurs de catégories. Toutes les valeurs séparées par des virgules deviennent des catégories. Vous pouvez également définir des sous-catégories en utilisant un autre séparateur, tel que les deux-points (:), pour séparer les sous-catégories au sein de la valeur de catégorie.

Par exemple, dans le code suivant, la catégorie Womens est divisée en plusieurs sous-catégories :

```
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

Pour la diffusion de mbox, le nom d’attribut le plus long est utilisé pour la clé. S’il existe un lien, le dernier attribut est utilisé. Dans l’exemple ci-dessous, la clé de catégorie est Womens:Outerwear:Jackets:Caban.

### entity.brand

Une seule valeur uniquement.

Affiche le nom de marque d’un élément.

Exemple : `'entity.brand=brandxyz'`

### entity.pageUrl

Une seule valeur uniquement.

Définit l’URL relative de la page dans laquelle l’élément peut être acheté.

Exemple : `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### entity.thumbnailUrl

Une seule valeur uniquement.

Définit l’URL relative de l’image miniature qui s’affiche en même temps que l’élément.

Exemple : `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### entity.message

Une seule valeur uniquement.

Un message relatif au produit s’affiche dans la recommandation, par exemple « en solde » ou « soldes ». Ce message est plus détaillé que le nom du produit. Utilisez-le pour définir des informations supplémentaires à afficher avec le produit dans le modèle..

Exemple : `'entity.message=Family&nbsp;special'`

### entity.inventory

Une seule valeur uniquement. Exige un nombre entier ou une valeur longue.

Affiche le niveau de stock de l’élément.

Exemple : `'entity.inventory=1'`

**Traitement d’attribut d’inventaire vide :** pour la livraison, si vous avez une règle d’inclusion, une règle de collecte ou un paramètre de critère avec `entity.inventory` > 0 ou `entity.inventory`= 0 et que l’inventaire du produit n’est pas défini, [!DNL Target] l’évalue sur la valeur True et inclut les produits dont l’inventaire n’est pas défini. Cette opération a été effectuée par défaut afin que les produits dont l’inventaire n’est pas défini apparaissent dans les résultats de la recommandation.

De même, si vous disposez d’une règle d’exclusion globale avec `entity.inventory` = 0 et que `entity.inventory`n’est pas définie, [!DNL Target] évalue cette règle à TRUE et exclut le produit.

**Problème connu** : la recherche de produit est incohérente avec la livraison pour les attributs de valeur d’inventaire non définis. Par exemple, pour une règle de `entity.inventory` = 0, la recherche de produit n’affichera pas les produits dont la valeur d’inventaire n’est pas définie.

### entity.value

Une seule valeur uniquement.

Définit le prix ou la valeur de l’élément.

Exemple : `'entity.value=15.99'`

### entity.margin

Une seule valeur uniquement.

Marge bénéficiaire ou autre valeur de l’élément.

Exemple : `'entity.margin=1.00'`

### entity.*custom*

Prend en charge plusieurs valeurs (tableau JSON).

Définissez jusqu’à 100 variables personnalisées donnant d’autres informations sur l’élément. Pour chaque attribut personnalisé, vous pouvez spécifier un nom d’attribut non utilisé. Par exemple, vous pouvez créer un attribut personnalisé appelé `entity.genre` pour définir un livre ou un film. Ou, un vendeur de billets peut créer des attributs pour le lieu d’un événement pour un interprète secondaire ; par exemple, pour une équipe en déplacement dans le cas d’un événement sportif ou une première partie dans le cas d’un concert.

Restrictions :

* Vous ne pouvez pas utiliser de noms d’attributs d’entité prédéfinis pour les attributs d’entité personnalisés.
* L’attribut entity.environment est réservé par le système et ne peut pas être utilisé pour les attributs d’entité personnalisés. Toute tentative de transférer entity.environment à l’aide de targetPageParams, d’un flux ou d’une API sera ignorée.

Exemples :

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Les attributs d’entité personnalisés prennent en charge plusieurs valeurs. Consultez les [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md#limits) pour les limites de caractère et de valeur.

Exemple : `'entity.secondary=["band1",&nbsp;"band2"]'`

>[!NOTE]
>
>Les attributs d’entité personnalisés à plusieurs valeurs exigent des tableaux Json valides. Pour obtenir des informations de syntaxe correctes, voir Attributs d’entité personnalisés.

### entity.event.detailsOnly

Une seule valeur uniquement.

Utilisé pour empêcher un appel mbox d’incrémenter les compteurs de données de comportement pour un algorithme.

Exemple : `'entity.event.detailsOnly=true'`

Dans les exemples ci-dessous, le premier appel mbox mettra à jour le catalogue et les données de comportement. Le deuxième appel mbox mettra à jour le catalogue uniquement.

```
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

## Rubriques connexes :

* [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
