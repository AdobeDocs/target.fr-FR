---
keywords: entités ; attributs d’entité ; transférer des informations à Recommandations ; données de comportement ; compteur de données ; définir une URL relative ; afficher le niveau de stock ; définir le prix ; définir la marge bénéficiaire ; attributs personnalisés
description: Découvrez comment utiliser les attributs d’entité pour transmettre des informations sur les produits ou contenus à [!DNL Target] Recommendations.
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
title: Comment Utiliser Les Attributs D’Entité ?
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
TQID: 'https://experienceleague.adobe.com/GXQOxQxTV0vTYsWy9Ky9wPNEqoRSAhIA5zlBd4Cr4Ec'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 28%
---
# Attributs d’entité {#entity-attributes}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez quels attributs d&#39;entité transmettent des informations sur le produit ou le contenu à [!DNL Adobe Target Recommendations] et comment les définir.

>[!ENDSHADEBOX]

Utilisez les attributs d&#39;entité pour transmettre des informations sur le produit ou le contenu à [!DNL Adobe Target Recommendations], où elles peuvent être affichées dans des conceptions et utilisées dans des règles d&#39;inclusion, des collections et des exclusions. Les entités sont les éléments que vous souhaitez recommander, tels que les produits, le contenu (articles, diaporamas, images, films et émissions télévisées), les offres d’emploi, les restaurants, etc. [!DNL Recommendations] envoie le `productId` ou le `productPurchasedId` (appelé `entity.id` dans le code) qui est utilisé dans les algorithmes.

Tenez compte des points suivants :

* `entity.id` doit correspondre au `productPurchasedId` envoyé à la page de confirmation de commande et au `productId` utilisé dans les rapports de produit [!DNL Adobe Analytics].
* Les valeurs d’attribut d’entité que vous transmettez à [!DNL Recommendations] expirent après 61 jours. Adobe vous recommande de transmettre la dernière valeur de chaque attribut d&#39;entité à [!DNL Recommendations] au moins une fois par mois pour chaque élément de votre catalogue.

La plupart des paramètres prédéfinis n’acceptent qu’une seule valeur, les nouvelles valeurs remplaçant les anciennes. Le paramètre `categoryId` est l’exception (voir [entity.categoryId](#entity-category-id)).

En règle générale, la mbox des informations d’affichage ressemble à l’exemple suivant si vous utilisez at.js 1.*x* avec `mboxCreate`. Tous les attributs de paramètre d’entité sont sensibles à la casse.

Si vous utilisez at.js 2.*x*, `mboxCreate` (tel qu’utilisé dans l’exemple suivant) n’est plus pris en charge. Pour transmettre des informations sur le produit ou le contenu à [!DNL Recommendations] à l’aide d’at.js 2.*x*, utilisez [targetPageParams](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparams.html){target=_blank}. Pour obtenir un exemple, consultez [Planification et implémentation de Recommendations](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}.

+++ Exemple de mbox qui transmet des attributs d’entité

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

+++

>[!NOTE]
>
>Il est préférable d’utiliser des URL relatives pour `pageUrl` et `thumbnailUrl`, plutôt que des URL absolues, car les recommandations reçoivent les données envoyées de tous les environnements sur le site. L’utilisation d’URL relatives évite d’avoir à utiliser des liens codés en dur sur un serveur de développement ou de test.

Si la mbox se trouve sur une page de produit, vous pouvez inclure l’ID de produit et l’ID de catégorie. L’algorithme sélectionné détermine les affichages. L’identifiant du produit est utilisé pour les algorithmes d’affinité et l’identifiant de la catégorie, pour les algorithmes de catégorie.

## Variables disponibles

Le tableau suivant répertorie les variables disponibles. Les sous-sections situées après le tableau apportent des informations supplémentaires sur les variables qui en ont besoin.

| Variable | Valeurs | Description | Exemple |
|---|---|---|---|
| `entity.id` | Valeur unique uniquement. Requis. | Permet d’identifier le produit. Voir [entity.id](#entity-id). | `'entity.id=67833'` |
| `entity.name` | Valeur unique uniquement. | Nom du produit affiché sur le site Web lorsque le produit est recommandé. | `'entity.name=Giants& vs& Rockies& 5/12'` |
| `entity.categoryId` | À plusieurs valeurs (liste délimitée par des virgules). | Catégorie de la page active. Voir [entity.categoryId](#entity-category-id). | `'entity.categoryId=womens:sweaters'` |
| `entity.brand` | Valeur unique uniquement. | Affiche le nom de marque d’un élément. | `'entity.brand=brandxyz'` |
| `entity.pageUrl` | Valeur unique uniquement. | Définit l’URL relative de la page dans laquelle l’élément peut être acheté. | `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'` |
| `entity.thumbnailUrl` | Valeur unique uniquement. | Définit l’URL relative de l’image miniature qui s’affiche en même temps que l’élément. | `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'` |
| `entity.message` | Valeur unique uniquement. | Un message relatif au produit s’affiche dans la recommandation, par exemple « en solde » ou « soldes ». Ce message est plus détaillé que le nom du produit. Utilisez `entity.message` pour définir des informations supplémentaires à afficher avec le produit dans le modèle. | `'entity.message=Family&nbsp;special'` |
| `entity.inventory` | Valeur unique uniquement. Exige un nombre entier ou une valeur longue. | Affiche le niveau de stock de l’élément. Voir [entity.inventory](#entity-inventory). | `'entity.inventory=1'` |
| `entity.value` | Valeur unique uniquement. | Définit le prix ou la valeur de l’élément. Seul le format décimal est pris en charge (par exemple, 15,99). Le format de virgule (15,99) n’est pas pris en charge. | `'entity.value=15.99'` |
| `entity.margin` | Valeur unique uniquement. | Marge bénéficiaire ou autre valeur de l’élément. | `'entity.margin=1.00'` |
| `entity.`*custom* | À plusieurs valeurs (tableau JSON). | Variables personnalisées qui fournissent des informations supplémentaires sur l’élément. Voir [entité.*personnalisée*](#entity-custom). | `'entity.secondary=Rockies'` |
| `entity.event.detailsOnly` | Valeur unique uniquement. | Empêche un appel de mbox d’incrémenter les compteurs de données comportementales pour un algorithme. Voir [entity.event.detailsOnly](#entity-event-details-only). | `'entity.event.detailsOnly=true'` |

### entity.id {#entity-id}

L’identifiant alphanumérique doit être le même pour tous les [!DNL Adobe Experience Cloud] produits utilisés, y compris [!DNL Analytics], pour que les différents produits puissent reconnaître l’élément et partager des données à son sujet.

Les valeurs `entity.id` ne doivent *pas* contenir d’espaces, de barres obliques, d’esperluettes, de points d’interrogation, de symboles de pourcentage, de virgules ou d’autres caractères de ponctuation qui nécessitent un codage d’URL lors de leur transmission dans un appel API REST. Les tirets et les traits de soulignement sont autorisés. Le fait d’inclure des signes de ponctuation non autorisés dans une valeur `entity.id` entraîne l’échec de certaines fonctionnalités de [!DNL Recommendations].

### entity.categoryId {#entity-category-id}

La valeur `entity.categoryId` peut inclure plusieurs catégories, telles qu’une sous-sous-section de cardigans (par exemple, `womens`, `womens:sweaters`, `womens:sweaters:cardigans`). Plusieurs catégories doivent être séparées par des virgules. Les nouvelles valeurs `categoryId` ne remplacent pas les valeurs existantes, mais sont ajoutées lors de la mise à jour de l’entité. La valeur `categoryId` est limitée à 250 caractères.

>[!NOTE]
>
>Pour afficher une recommandation basée sur une catégorie dans une page **[!UICONTROL Catégorie]**, un seul élément `categoryId` peut être transmis dans la mbox utilisée pour afficher cette recommandation particulière. La valeur de `categoryId` doit correspondre exactement à la valeur de `entity.categoryId` transmise sur la page **[!UICONTROL Détails du produit]**.

Exemples :

* Exemple De Page De Détails Du Produit : `womens`, `womens:sweaters`, `womens:sweaters:cardigans`
* Exemple de pulls de page de catégorie : `womens:sweaters`
* Exemple de cardigans de page de catégorie : `womens:sweaters:cardigans`

Pour les recommandations basées sur des catégories, une virgule sépare la valeur de la catégorie. Toutes les valeurs séparées par des virgules deviennent des catégories. Vous pouvez également définir des sous-catégories en utilisant un autre séparateur, tel que les deux-points (:), pour séparer les sous-catégories au sein de la valeur de catégorie.

Par exemple, dans le code suivant, la catégorie Femmes est divisée en plusieurs sous-catégories :

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban', 'entity.thumbnailUrl=...', 'entity.message=...');
```

Pour la diffusion de mbox, le nom d’attribut le plus long est utilisé pour la clé. S’il existe un lien, le dernier attribut est utilisé. Dans l&#39;exemple ci-dessus, la clé de catégorie est `Womens:Outerwear:Jackets:Caban`.

### entity.inventory {#entity-inventory}

**Gestion des attributs d&#39;inventaire vides :** pour la diffusion, si vous avez une règle d&#39;inclusion, une règle de collection ou un paramètre de critère avec `entity.inventory` > 0 ou `entity.inventory` = 0 et que l&#39;inventaire du produit n&#39;est pas défini, [!DNL Target] évalue cette valeur sur TRUE et inclut les produits pour lesquels l&#39;inventaire n&#39;est pas défini. Par conséquent, les produits dont le stock n’est pas défini s’affichent dans les résultats de recommandation.

De même, si vous disposez d’une règle d’exclusion globale avec `entity.inventory` = 0 et que `entity.inventory`n’est pas définie, [!DNL Target] évalue cette règle à TRUE et exclut le produit.

>[!NOTE]
>
>**Problème connu :** La recherche de produit est incohérente avec la diffusion pour les attributs de valeur de stock qui ne sont pas définis. Par exemple, pour une règle avec `entity.inventory` = 0, la recherche de produits n’affiche pas les produits pour lesquels la valeur de stock n’est pas définie.

### entité.*personnalisée* {#entity-custom}

Vous pouvez définir jusqu’à 100 variables personnalisées. Pour chaque attribut personnalisé, vous pouvez spécifier un nom d’attribut non utilisé. Par exemple, vous pouvez créer un attribut personnalisé appelé `entity.genre` pour définir un livre ou un film. Un vendeur de billets peut créer des attributs pour un lieu d’événement pour un interprète secondaire, tel qu’une équipe visiteuse lors d’un événement sportif ou un acte d’ouverture dans un concert.

Restrictions :

* Vous ne pouvez pas utiliser de noms d’attributs d’entité prédéfinis pour les attributs d’entité personnalisés.
* L’attribut `entity.environment` est réservé par le système et ne peut pas être utilisé pour les attributs d’entité personnalisés. Les tentatives de transmission de `entity.environment` à l’aide de `targetPageParams`, d’un flux ou d’une API sont ignorées.

Exemples :

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Les attributs d’entité personnalisés prennent en charge plusieurs valeurs. Consultez les [Attributs d’entité personnalisés](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits) pour les limites de caractère et de valeur.

Exemple : `'entity.secondary=["band1",&nbsp;"band2"]'`

Les attributs d’entité personnalisés à plusieurs valeurs exigent des tableaux Json valides. Pour obtenir des informations de syntaxe correctes, voir [Attributs d&#39;entité personnalisés](/help/main/c-recommendations/c-products/custom-entity-attributes.md).

### entity.event.detailsOnly {#entity-event-details-only}

Utilisez ce paramètre pour empêcher un appel de mbox d’incrémenter des compteurs de données comportementaux pour un algorithme.

Dans les exemples suivants, le premier appel de mbox met à jour le catalogue et les données comportementales. Le deuxième appel de mbox met uniquement à jour le catalogue.

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york', 'entity.id = 123', 'entity.inventory = 4' )
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york', 'entity.id = 123', 'entity.inventory = 4', 'entity.event.detailsOnly=true' )
```
