---
keywords: entités ; attributs d’entité ; transférer des informations à Recommendations ; données de comportement ; compteur de données ; définir une URL relative ; afficher le niveau de stock ; définir le prix ; définir la marge bénéficiaire ; attributs personnalisés
description: Découvrez comment utiliser les attributs d’entité pour transmettre des informations sur les produits ou le contenu à  [!DNL Target] Recommendations.
title: Comment utiliser les attributs d’entité ?
feature: Recommandations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 55%

---

# ![PREMIUM](/help/assets/premium.png) Attributs d’entité

Utilisez les attributs d&#39;entité pour transmettre des informations sur les produits ou le contenu à [!DNL Adobe Target Recommendations].

Les entités font référence aux éléments que vous voulez recommander. Les entités peuvent inclure des produits, du contenu (articles, diaporamas, images, films et émissions de télévision), des listes d’emplois, des restaurants, etc.

[!DNL Recommendations] envoie le  `productId` ou  `productPurchasedId` (appelé  `entity.id` dans le code) utilisé dans les algorithmes.

Tenez compte des points suivants :

* `entity.id` doit correspondre à la page de confirmation de commande  `productPurchasedId` envoyée et à la page  `productId` utilisée dans les rapports  [!DNL Adobe Analytics] de produit.
* Les valeurs d’attribut d’entité que vous transmettez à [!DNL Recommendations] expirent après 61 jours. Adobe vous recommande de transmettre la dernière valeur de chaque attribut d’entité à [!DNL Recommendations] au moins une fois par mois pour chaque élément de votre catalogue.

La plupart des paramètres prédéfinis acceptent une seule valeur, les nouvelles valeurs remplaçant les anciennes. Le paramètre `categoryId` peut accepter une liste de valeurs délimitées par des virgules pour chaque catégorie contenant ce produit. Les nouvelles valeurs `categoryId` n’écrasent pas les valeurs existantes, mais sont ajoutées lors de la mise à jour de l’entité (250 caractères maximum).

En général, la mbox d’affichage d’informations ressemble à l’exemple suivant si vous utilisez at.js 1.** xwith  `mboxCreate`. Tous les attributs de paramètre d’entité sont sensibles à la casse.

>[!NOTE]
>
>Si vous utilisez at.js 2.*x*,  `mboxCreate` (comme utilisé dans l’exemple suivant) n’est plus pris en charge. Pour transmettre des informations sur le produit ou le contenu à [!DNL Recommendations] à l’aide d’at.js 2.*x*, utilisez  [targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md). Pour un exemple, voir [Planification et mise en oeuvre de Recommendations](/help/c-recommendations/plan-implement.md).

```javascript
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

Les valeurs `entity.id` doivent *ne pas* contenir de barres obliques, d&#39;esperluettes, de points d&#39;interrogation, de symboles de pourcentage, de virgules ou d&#39;autres caractères de ponctuation qui nécessitent un codage URL lorsqu&#39;elles sont transmises dans un appel d&#39;API REST. Les tirets et les traits de soulignement sont autorisés. Le fait d’inclure des signes de ponctuation non autorisés dans une valeur `entity.id` entraîne l’échec de certaines fonctionnalités de [!DNL Recommendations].

Exemple : `'entity.id=67833'`

### entity.name

Une seule valeur uniquement.

Nom du produit affiché sur le site web lorsque ce produit est recommandé.

Exemple : `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

Prend en charge plusieurs valeurs (liste délimitée par des virgules).

Catégorie de la page en cours. entity.categoryID peut inclure plusieurs catégories, telles qu’une sous-sous-section &quot;cardigans&quot; (par exemple, femmes, femmes:pulls, femmes:pulls:pulls:cardigans). Plusieurs catégories doivent être séparées par des virgules.

La valeur `categoryId` est limitée à 250 caractères.

>[!NOTE]
>
>Pour afficher une recommandation basée sur une catégorie dans une page [!UICONTROL Catégorie], seule une `categoryId` peut être transférée à la mbox utilisée pour afficher cette recommandation spécifique. La valeur de `categoryId` doit correspondre exactement à la valeur de `entity.categoryId` transmise sur la page [!UICONTROL Détail du produit].

Exemples :

* Exemple de page Détail du produit : womens, womens:sweaters, womens:sweaters:cardigans
* Exemple de page Catégorie Pulls : womens:sweaters
* Exemple de page Catégorie Gilets : womens:sweaters:cardigans

Pour les recommandations basées sur des catégories, une virgule sépare la valeur de la catégorie. Toutes les valeurs séparées par des virgules deviennent des catégories. Vous pouvez également définir des sous-catégories en utilisant un autre séparateur, tel que les deux-points (:), pour séparer les sous-catégories au sein de la valeur de catégorie.

Par exemple, dans le code suivant, la catégorie des femmes est divisée en plusieurs sous-catégories :

```javascript
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

Un message relatif au produit s’affiche dans la recommandation, par exemple « en solde » ou « soldes ». Ce message est plus détaillé que le nom du produit. Utilisez entity.message pour définir des informations supplémentaires à afficher avec le produit dans le modèle.

Exemple : `'entity.message=Family&nbsp;special'`

### entity.inventory

Une seule valeur uniquement. Exige un nombre entier ou une valeur longue.

Affiche le niveau de stock de l’élément.

Exemple : `'entity.inventory=1'`

**Gestion des attributs d&#39;inventaire vide :** Pour la diffusion, si vous avez défini une règle d&#39;inclusion, une règle de collecte ou un paramètre de critère avec  `entity.inventory` > 0 ou  `entity.inventory` = 0 et que le stock n&#39;est pas défini,  [!DNL Target] cette valeur est évaluée sur TRUE et inclut les produits pour lesquels le stock n&#39;est pas défini. Par conséquent, les produits dont le stock n’est pas défini s’affichent dans les résultats des recommandations.

De même, si vous disposez d’une règle d’exclusion globale avec `entity.inventory` = 0 et que `entity.inventory`n’est pas définie, [!DNL Target] évalue cette règle à TRUE et exclut le produit.

**Problème connu : la recherche de** produits est incompatible avec la diffusion des attributs de valeur de stock qui ne sont pas définis. Par exemple, pour une règle avec `entity.inventory` = 0, la recherche de produits n’affiche pas les produits pour lesquels la valeur de stock n’est pas définie.

### entity.value

Une seule valeur uniquement.

Définit le prix ou la valeur de l’élément.

Exemple : `'entity.value=15.99'`

entity.value ne prend en charge que le format décimal (par exemple, 15.99). Le format de virgule (15,99) n’est pas pris en charge.

### entity.margin

Une seule valeur uniquement.

Marge bénéficiaire ou autre valeur de l’élément.

Exemple : `'entity.margin=1.00'`

### entity.*custom*

Prend en charge plusieurs valeurs (tableau JSON).

Définissez jusqu’à 100 variables personnalisées donnant d’autres informations sur l’élément. Pour chaque attribut personnalisé, vous pouvez spécifier un nom d’attribut non utilisé. Par exemple, vous pouvez créer un attribut personnalisé appelé `entity.genre` pour définir un livre ou un film. Un vendeur de billets peut créer des attributs pour un lieu de événement pour un interprète secondaire, par exemple une équipe en déplacement dans un événement sportif ou une première partie dans un concert.

Restrictions :

* Vous ne pouvez pas utiliser de noms d’attributs d’entité prédéfinis pour les attributs d’entité personnalisés.
* L’attribut entity.environment est réservé par le système et ne peut pas être utilisé pour les attributs d’entité personnalisés. Les tentatives de transmettre entity.environnement à l’aide de targetPageParams, de flux ou d’API sont ignorées.

Exemples :

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Les attributs d’entité personnalisés prennent en charge plusieurs valeurs. Consultez les [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md#limits) pour les limites de caractère et de valeur.

Exemple : `'entity.secondary=["band1",&nbsp;"band2"]'`

Les attributs d’entité personnalisés à plusieurs valeurs exigent des tableaux Json valides. Pour obtenir des informations de syntaxe correctes, voir [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md).

### entity.event.detailsOnly

Une seule valeur uniquement.

Utilisé pour empêcher un appel mbox d’incrémenter les compteurs de données de comportement pour un algorithme.

Exemple : `'entity.event.detailsOnly=true'`

Dans les exemples ci-dessous, le premier appel de mbox met à jour le catalogue et les données comportementales. Le second appel de mbox met à jour uniquement le catalogue.

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

>[!MORELIKETHIS]
>
>* [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)

