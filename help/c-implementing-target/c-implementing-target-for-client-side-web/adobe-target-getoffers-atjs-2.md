---
keywords: adobe.target.getOffers;getOffers;getoffers;get offers;at.js;fonctions;fonction
description: Utilisez la fonction adobe.target.getOffers() et ses options pour l’Adobe [!DNL Target] at.js library to fire requests to get multiple [!DNL Target] offres. (at.js 2.x)
title: Comment utiliser la fonction adobe.target.getOffers() ?
feature: at.js
role: Developer
exl-id: ed5f06c8-d837-4ea1-a857-c6c46424aa1f
source-git-commit: 40173370840d1bcc8582bf7bec51e5ef8b1ae53b
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 69%

---

# adobe.target.getOffers() - at.js 2.x

Cette fonction permet de récupérer plusieurs offres en transmettant plusieurs mbox. De plus, plusieurs offres peuvent être extraites pour toutes les vues des activités actives.

>[!NOTE]
>
>Cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*.

| Clé | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| `consumerId` | Chaîne | Non | La valeur par défaut est la mbox globale du client si elle n’est pas fournie. Cette clé est utilisée pour générer l’ID de données supplémentaire (SDID) utilisé pour l’intégration A4T.<br>Lors de l’utilisation de `getOffers()`, chaque appel génère un nouveau SDID. Si vous disposez de plusieurs requêtes de mbox sur la même page et que vous souhaitez conserver le SDID (afin qu’il corresponde au SDID de target-global-mbox et au SDID Adobe Analytics), utilisez la variable `consumerId` .<br>If `getOffers()` comprend trois mbox (nommées &quot;mbox1&quot;, &quot;mbox2&quot; et &quot;mbox3&quot;), à savoir : `consumerId: "mbox1, mbox2, mbox3"` dans le `getOffers()` appelez . |
| `decisioningMethod` | Chaîne | Non | &quot;côté serveur&quot;, &quot;sur appareil&quot;, &quot;hybride&quot; |
| `request` | Objet | Oui | Consultez les requêtes ci-dessous. |
| `timeout` | Nombre | Non | Délai d’attente de requête. Si cette valeur n’est pas spécifiée, c’est le délai d’attente par défaut d’at.js qui sera utilisé. |

## Demande

>[!NOTE]
>
>Consultez la [Documentation de l’API de diffusion](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) pour plus d’informations sur les types acceptables pour tous les champs répertoriés ci-dessous.

| Nom du champ | Obligatoire ? | Limites | Description |
| --- | --- | --- | --- |
| request > id | Non |  | Un de `tntId`, `thirdPartyId`ou `marketingCloudVisitorId` est obligatoire. |
| Request > id > thirdPartyId | Non | Taille maximale = 128  |  |  |
| Request > experienceCloud | Non |  |  |
| Request > experienceCloud > analytics | Non |  | Intégration d’Adobe Analytics |
| Request > experienceCloud > analytics > logging | Non | Les éléments suivants doivent être implémentés sur la page :<ul><li>Service d’identification des visiteurs</li><li>Appmeasurement.js</li></ul> | Les valeurs suivantes sont prises en charge :<br>**client_ side** : Lorsqu’elle est spécifiée, une charge d’analyse est renvoyée à l’appelant qui doit être utilisée pour l’envoi à Adobe Analytics via l’API d’insertion de données.<br>**Server_side** : Il s’agit de la valeur par défaut dans laquelle le backend de Target et d’Analytics utilise le SDID pour regrouper les appels à des fins de génération de rapports. |
| Request > prefetch | Non |  |  |
| Request > prefetch > views | Non | Nombre maximum 50.<br>Nom non vide.<br>Longueur du nom `<=` 128.<br>Longueur de la valeur `<=` 5000.<br>Le nom ne doit pas commencer par &quot;profile&quot;.<br>Noms non autorisés : &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot;. | Transmettez les paramètres à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request > prefetch > views > profileParameters | Non | Le maximum compte 50.<br>Nom non vide.<br>Longueur du nom `<=` 128.<br>Longueur de la valeur `<=` 5000.<br>Accepte uniquement les valeurs de chaîne.<br>Le nom ne doit pas commencer par &quot;profile&quot;. | Transmettez les paramètres de profil à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request > prefetch > views > product | Non |  |  |
| Request > prefetch > views > product -> id | Non | Non vide.<br>taille maximale = 128. | Transmettez les ID de produit à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request > prefetch > views > product > categoryId | Non | Non vide.<br>taille maximale = 128. | Transmettre les identifiants des catégories de produits à utiliser pour récupérer les vues pertinentes dans les activités. |
| Request > prefetch > views > order | Non |  |  |
| Request > prefetch > views > order > id | Non | Longueur maximale = 250  | Transmettez les ID de commande à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request > prefetch > views > order > total | Non | Total `>=` 0  | Transmettez les totaux de la commande afin qu’ils soient utilisés pour récupérer les vues pertinentes dans les activités courantes. |
| Request > prefetch > views > order > purchasedProductIds | Non | Aucune valeur vide.<br>Longueur maximale de chaque valeur de 50.<br>Concaténé et séparé par une virgule.<br>Longueur totale des ID de produit `<=` 250. | Transmettez les ID de produit achetés à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request > execute | Non |  |  |
| Request > execute > pageLoad | Non |  |  |
| Request > execute > pageLoad > parameters | Non | Nombre maximum 50.<br>Nom non vide.<br>Longueur du nom `<=` 128.<br>Longueur de la valeur `<=` 5000.<br>Accepte uniquement les valeurs de chaîne.<br>Le nom ne doit pas commencer par &quot;profile&quot;.<br>Noms non autorisés : &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot;. | Récupérez les offres avec des paramètres spécifiés lors du chargement de la page. |
| Request > execute > pageLoad > profileParameters | Non | Nombre maximum 50.<br>Nom non vide.<br>Longueur du nom `<=` 128.<br>Longueur de la valeur `<=`256.<br>Le nom ne doit pas commencer par &quot;profile&quot;.<br>Accepte uniquement les valeurs de chaîne. | Récupérez les offres avec des paramètres de profil spécifiés lors du chargement de la page. |
| Request > execute > pageLoad > product | Non |  |  |
| Request > execute > pageLoad > product -> id | Non | Non vide.<br>Taille maximale = 128. | Récupérez les offres avec des ID de produit spécifiés lors du chargement de la page. |
| Request > execute > pageLoad > product > categoryId | Non | Non vide.<br>Taille maximale = 128. | Récupérez les offres avec des identifiants de catégorie de produits spécifiés lors du chargement de la page. |
| Request > execute > pageLoad > order | Non |  |  |
| Request > execute > pageLoad > order > id | Non | Longueur maximale = 250  | Récupérez les offres avec des ID de commande spécifiés lors du chargement de la page. |
| Request > execute > pageLoad > order > total | Non | `>=` 0  | Récupérez les offres avec des totaux de commande spécifiés lors du chargement de la page. |
| Request > execute > pageLoad > order > purchasedProductIds | Non | Aucune valeur vide.<br>Longueur maximale de chaque valeur de 50.<br>Concaténé et séparé par une virgule.<br>Longueur totale des ID de produit `<=` 250. | Récupérez les offres avec des ID de produit achetés, spécifiés lors du chargement de la page. |
| Request > execute > mboxes | Non | Taille maximale = 50.<br>Aucun élément nul. |  |
| Request > execute > mboxes>mbox | Oui | Non vide.<br>Aucun suffixe &quot;-clicked&quot;.<br>Taille maximale = 250.<br>Caractères autorisés : `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Nom de la mbox. |
| Request > execute > mboxes>mbox>index | Oui | Non nul.<br>Unique.<br>`>=` 0. | Notez que l’index ne représente pas l’ordre dans lequel les mbox seront traitées. Comme dans une page web comportant plusieurs mbox régionales, l’ordre dans lequel ils seront traités ne peut pas être spécifié. |
| Request > execute > mboxes > mbox > parameters | Non | Nombre maximal = 50.<br>Nom non vide.<br>Longueur du nom `<=` 128.<br>Accepte uniquement les valeurs de chaîne.<br>Longueur de la valeur `<=` 5000.<br>Le nom ne doit pas commencer par &quot;profile&quot;.<br>Noms non autorisés : &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot;. | Récupérez les offres pour une mbox donnée avec les paramètres spécifiés. |
| Request > execute > mboxes>mbox>profileParameters | Non | Nombre maximal = 50.<br>Nom non vide.<br>Longueur du nom `<=` 128.<br>Accepte uniquement les valeurs de chaîne.<br>Longueur de la valeur `<=`256.<br>Le nom ne doit pas commencer par &quot;profile&quot;. | Récupérez les offres pour une mbox donnée avec les paramètres de profil spécifiés. |
| Request > execute > mboxes>mbox > product | Non |  |  |
| Request > execute > mboxes > mbox > product > id | Non | Non vide.<br>Taille maximale = 128. | Récupérez les offres pour une mbox donnée avec les ID de produit spécifiés. |
| Request > execute > mboxes > mbox > product > categoryId | Non | Non vide.<br>Taille maximale = 128. | Récupérez les offres pour une mbox donnée avec les identifiants de catégorie de produits spécifiés. |
| Request > execute > mboxes > mbox > order | Non |  |  |
| Request > execute > mboxes>mbox > order > id | Non | Longueur maximale = 250  | Récupérez les offres pour une mbox donnée avec les ID de commande spécifiés. |
| Request > execute > mboxes > mbox > order > total | Non | `>=` 0  | Récupérez les offres pour une mbox donnée avec les totaux de commande spécifiés. |
| Request > execute > mboxes > mbox > order > purchasedProductIds | Non | Aucune valeur vide.<br>Longueur maximale de chaque valeur = 50.<br>Concaténé et séparé par une virgule.<br>Longueur totale des ID de produit `<=` 250. | Récupérez les offres pour une mbox donnée avec l’ordre spécifié des ID de produit achetés. |

## Appel de getOffers() pour toutes les vues

```javascript
adobe.target.getOffers({
    request: {
      prefetch: {
        views: [{}]
    }
  }
});
```

## Appelez getOffers() pour effectuer une prise de décision sur l’appareil

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
}); 
```

## Appelez getOffers() pour récupérer les dernières vues avec les paramètres transmis et les paramètres de profil.

```javascript
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## Appelez getOffers() pour récupérer les mbox avec des paramètres et des paramètres de profil transmis.

```javascript
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## Appel getOffers() pour récupérer la charge utile Analytics du côté client

```javascript
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**Réponse** :

```javascript
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

La payload peut ensuite être transmise à Adobe Analytics via le [API d’insertion de données](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Récupération et génération des données de plusieurs mbox via getOffers() et applyOffers() {#multiple}

at.js 2.x vous permet de récupérer plusieurs mbox via l’`getOffers()`API. Vous pouvez également récupérer des données pour plusieurs mbox, puis utiliser `applyOffers()` pour effectuer le rendu des données à différents emplacements identifiés par un sélecteur CSS.

L’exemple suivant illustre une page HTML simple avec at.js 2.x implémentée :

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

Supposons que vous ayez trois conteneurs que vous souhaitez modifier via le contenu reçu [!DNL Target]. Vous pouvez créer une requête unique pour trois mbox dans lesquelles chaque mbox comporte du contenu à rendre dans le conteneur correspondant.

Le code de requête et de rendu peut ressembler à l’exemple suivant :

```javascript
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

Dans la section `request > prefetch > mboxes`, il existe trois mbox différentes. Si la requête a réussi, vous recevez la réponse pour chaque mbox de `response > prefetch > mboxes`. Après avoir reçu les réponses et les emplacements à utiliser pour le rendu, vous pouvez invoquer `applyOffers()` pour obtenir le rendu du contenu récupéré dans [!DNL Target]. Dans cet exemple, nous avons le mappage suivant :

* mbox1 > Sélecteur CSS #container1
* mbox2 > Sélecteur CSS #container2
* mbox3 > Sélecteur CSS #container3

Cet exemple utilise la variable count pour construire les sélecteurs CSS. Dans un scénario réel, vous pouvez utiliser un mappage différent entre le sélecteur CSS et la mbox.

Notez que cet exemple utilise `prefetch > mboxes`, mais vous pouvez également utiliser `execute > mboxes`. Vérifiez que si vous utilisez la prérécupération dans `getOffers()`, vous devez également utiliser la prérécupération dans l’appel de `applyOffers()`.

## Appelez getOffers() pour effectuer un événement pageLoad.

L’exemple suivant montre comment effectuer un événement pageLoad à l’aide de getOffers() avec at.js 2.*x*

```javascript
adobe.target.getOffers({
    request: {
        execute: {
            pageLoad: {
                parameters: {}
            }
        }
    }
});
```
