---
description: 'Informations sur la fonction adobe.target.getOffers() pour at.js. '
keywords: adobe.target.getOffers;getOffers;getoffers;get offers;at.js;fonctions;fonction
seo-description: Informations sur la fonction adobe.target.getOffers(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
seo-title: Informations sur la fonction adobe.target.getOffers() pour la bibliothèque JavaScript at.js d’Adobe Target.
solution: Target
subtopic: Prise en main
title: adobe.target.getOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: 104de769c2f545a8ce2f3346497810dc3a8933dd

---


# adobe.target.getOffers(options) - at.js 2.x

Cette fonction permet de récupérer plusieurs offres en transmettant plusieurs mbox. De plus, plusieurs offres peuvent être extraites pour toutes les vues des activités actives.

>[!NOTE]
>
>Cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*.

| Clé | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| consumerId | Chaîne | Non | La valeur par défaut est la mbox globale du client si elle n’est pas fournie. Cette clé sert à générer l’identifiant de données supplémentaire utilisé pour l’intégration A4T. Cette clé est une chaîne unique par visiteur. |
| events | Objet | Oui | Consultez les requêtes ci-dessous. |
| timeout | Nombre | Non | Délai d’attente de requête. Si cette valeur n’est pas spécifiée, c’est le délai d’attente par défaut d’at.js qui sera utilisé. |

## Demande

| Nom du champ | Obligatoire ? | Limites | Description |
| --- | --- | --- | --- |
| request &gt; id | Non |  | Un de `tntId`, `thirdPartyId`ou `marketingCloudVisitorId` est obligatoire. |
| Request &gt; id &gt; thirdPartyId | Non | Taille maximale = 128 |  |  |
| Request &gt; experienceCloud | Non |  |  |
| Request &gt; experienceCloud &gt; analytics | Non |  | Intégration d’Adobe Analytics |
| Request &gt; experienceCloud &gt; analytics &gt; logging | Non | Les éléments suivants doivent être implémentés sur la page :<ul><li>Service d’identification des visiteurs</li><li>Appmeasurement.js</li></ul> | Les valeurs suivantes sont prises en charge :<br>**client_ side** : Lorsqu’elle est spécifiée, une charge d’analyse est renvoyée à l’appelant qui doit être utilisée pour l’envoi à Adobe Analytics via l’API d’insertion de données.<br>**Server_side** : Il s’agit de la valeur par défaut dans laquelle le backend de Target et d’Analytics utilise le SDID pour regrouper les appels à des fins de génération de rapports. |
| Request &gt; prefetch | Non |  |  |
| Request &gt; prefetch &gt; views | Non | Nombre maximal 50<br>Nom non vide<br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=` 5000<br>Le nom ne doit pas commencer par le « profil »<br>Noms non autorisés : « Orderid », « ordertotal », « productpurchasedid » | Transmettez les paramètres à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request &gt; prefetch &gt; views &gt; profileParameters | Non | Nombre maximal 50<br>Nom non vide<br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=` 5000<br>Le nom ne doit pas commencer par « profil » | Transmettez les paramètres de profil à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request &gt; prefetch &gt; views &gt; product | Non |  |  |
| Request &gt; prefetch &gt; views &gt; product -&gt; id | Non | Taille maximale<br>non vide = 128 | Transmettez les ID de produit à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request &gt; prefetch &gt; views &gt; product &gt; categoryId | Non | Taille maximale<br>non vide = 128 | Transmettre les identifiants des catégories de produits à utiliser pour récupérer les vues pertinentes dans les activités. |
| Request &gt; prefetch &gt; views &gt; order | Non |  |  |
| Request &gt; prefetch &gt; views &gt; order &gt; id | Non | Longueur maximale = 250 | Transmettez les ID de commande à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request &gt; prefetch &gt; views &gt; order &gt; total | Non | Total `>=` 0 | Transmettez les totaux de la commande afin qu’ils soient utilisés pour récupérer les vues pertinentes dans les activités courantes. |
| Request &gt; prefetch &gt; views &gt; order &gt; purchasedProductIds | Non | Pas de valeurs vides <br>Longueur maximale de chaque valeur 50<br>&gt;Concaténée et séparée par une virgule <br>Longueur totale des ID de produit `<=` 250 | Transmettez les ID de produit achetés à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Request &gt; execute | Non |  |  |
| Request &gt; execute &gt; pageLoad | Non |  |  |
| Request &gt; execute &gt; pageLoad &gt; parameters | Non | Nombre maximal 50<br>Nom non vide <br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=` 5000<br>Nom ne doit pas commencer par « profil ».<br>Noms non autorisés : « ID de la commande », « Total de la commande », « ID du produit acheté » | Récupérez les offres avec des paramètres spécifiés lors du chargement de la page. |
| Request &gt; execute &gt; pageLoad &gt; profileParameters | Non | Nombre maximum 50<br>Nom non vide <br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=`256<br>Nom ne doit pas commencer par « profil » | Récupérez les offres avec des paramètres de profil spécifiés lors du chargement de la page. |
| Request &gt; execute &gt; pageLoad &gt; product | Non |  |  |
| Request &gt; execute &gt; pageLoad &gt; product -&gt; id | Non | Non vide <br>Taille maximale = 128 | Récupérez les offres avec des ID de produit spécifiés lors du chargement de la page. |
| Request &gt; execute &gt; pageLoad &gt; product &gt; categoryId | Non | Non vide <br>&gt;Taille maximale = 128 | Récupérez les offres avec des identifiants de catégorie de produits spécifiés lors du chargement de la page. |
| Request &gt; execute &gt; pageLoad &gt; order | Non |  |  |
| Request &gt; execute &gt; pageLoad &gt; order &gt; id | Non | Longueur maximale = 250 | Récupérez les offres avec des ID de commande spécifiés lors du chargement de la page. |
| Request &gt; execute &gt; pageLoad &gt; order &gt; total | Non | `>=` 0 | Récupérez les offres avec des totaux de commande spécifiés lors du chargement de la page. |
| Request &gt; execute &gt; pageLoad &gt; order &gt; purchasedProductIds | Non | Aucune valeur à blanc <br>Longueur maximale de chaque valeur 50<br>Concaténé et séparé par une virgule <br>Longueur totale des ID de produit `<=` 250 | Récupérez les offres avec des ID de produit achetés, spécifiés lors du chargement de la page. |
| Request &gt; execute &gt; mboxes | Non | Taille maximale = 50<br>Pas d’éléments nuls |  |
| Request &gt; execute &gt; mboxes&gt;mbox | Oui | Non vide<br>Suffixe no ’-clicked’ <br>Taille maximale = 250<br>Caractères autorisés : `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Nom de la mbox. |
| Request &gt; execute &gt; mboxes&gt;mbox&gt;index | Oui | Non nul<br>Unique<br>`>=` 0 | Notez que l’index ne représente pas l’ordre dans lequel les mbox seront traitées. Comme dans une page web comportant plusieurs mbox régionales, l’ordre dans lequel ils seront traités ne peut pas être spécifié. |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; parameters | Non | Compte maximum = 50<br>Nom non vide<br>Longueur de nom`<=` 128<br>Longueur de valeur `<=` 5 000<br>Le nom ne doit pas commencer par « profil ».<br>Noms non autorisés : « Orderid », « ordertotal », « productpurchasedid » | Récupérez les offres pour une mbox donnée avec les paramètres spécifiés. |
| Request &gt; execute &gt; mboxes&gt;mbox&gt;profileParameters | Non | Compte maximum = 50<br>Nom non vide<br>Longueur de nom`<=` 128<br>Longueur de valeur `<=`256<br>Le nom ne doit pas commencer par « profil ». | Récupérez les offres pour une mbox donnée avec les paramètres de profil spécifiés. |
| Request &gt; execute &gt; mboxes&gt;mbox &gt; product | Non |  |  |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; id | Non | Non vide <br>Taille maximale = 128 | Récupérez les offres pour une mbox donnée avec les ID de produit spécifiés. |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; categoryId | Non | Non vide<br>Taille maximale = 128 | Récupérez les offres pour une mbox donnée avec les identifiants de catégorie de produits spécifiés. |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; order | Non |  |  |
| Request &gt; execute &gt; mboxes&gt;mbox &gt; order &gt; id | Non | Longueur maximale = 250 | Récupérez les offres pour une mbox donnée avec les ID de commande spécifiés. |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; total | Non | `>=` 0 | Récupérez les offres pour une mbox donnée avec les totaux de commande spécifiés. |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; purchasedProductIds | Non | Pas de valeur vide<br>Longueur maximale de chaque valeur = 50<br>Concaténation et séparation par une virgule<br>Longueur totale des identifiants de produit `<=` 250 | Récupérez les offres pour une mbox donnée avec l’ordre spécifié des ID de produit achetés. |

## Appel de `getOffers()` pour toutes les vues

```
adobe.target.getOffers({
    request: {
      prefetch: {
        views: [{}]
    }
  }
});
```

## Appel de `getOffers()` pour récupérer les dernières vues avec les paramètres transmis et les paramètres de profil

```
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

## Appel de `getOffers()` pour récupérer les mbox avec des paramètres et des paramètres de profil transmis.

```
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

```
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

```
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

La charge utile peut ensuite être transférée à Adobe Analytics via l’API [d’insertion de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)données.

## Récupération et génération des données de plusieurs mbox via getOffers() et applyOffers() {#multiple}

at.js 2.x vous permet de récupérer plusieurs mbox via l’`getOffers()`API. Vous pouvez également récupérer des données pour plusieurs mbox, puis utiliser `applyOffers()` pour effectuer le rendu des données à différents emplacements identifiés par un sélecteur CSS.

L’exemple suivant illustre une page HTML simple avec at.js 2.x implémentée :

```
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

```
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

* mbox1 &gt; Sélecteur CSS #container1
* mbox2 &gt; Sélecteur CSS #container2
* mbox3 &gt; Sélecteur CSS #container3

Cet exemple utilise la variable count pour construire les sélecteurs CSS. Dans un scénario réel, vous pouvez utiliser un mappage différent entre le sélecteur CSS et la mbox.

Notez que cet exemple utilise `prefetch > mboxes`, mais vous pouvez également utiliser `execute > mboxes`. Vérifiez que si vous utilisez la prérécupération dans `getOffers()`, vous devez également utiliser la prérécupération dans l’appel de `applyOffers()`.
