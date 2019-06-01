---
description: 'Informations sur la fonction adobe. target. getoffers (options) pour at. js. '
keywords: adobe.target.notification;élément;sélecteur;notification;extension
seo-description: Informations sur la fonction adobe. target. getoffers (options) pour la bibliothèque JavaScript d'Adobe Target at. js.
seo-title: Informations sur la fonction adobe. target. getoffers (options) pour la bibliothèque JavaScript d'Adobe Target at. js.
solution: Target
subtopic: Prise en main
title: adobe.target.getOffer(options).
topic: Standard
translation-type: tm+mt
source-git-commit: cc7dc21321816e7f71b67e31abc0855184a285c6

---


# adobe. target. getoffers (options) - at. js 2. x

Cette fonction permet de récupérer plusieurs offres en transmettant plusieurs mbox. De plus, plusieurs offres peuvent être extraites pour toutes les vues des activités actives.

>[!NOTE]
>
>Cette fonction a été introduite avec at. js 2. x. Cette fonction n&#39;est pas disponible pour at. js version 1.*x*.

| Clé | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| IdConsommateur | Chaîne | Non | La valeur par défaut est la mbox globale du client si elle n&#39;est pas fournie. Cette clé sert à générer l’identifiant de données supplémentaire utilisé pour l’intégration A4T. |
| events | Objet | Oui | Consultez les requêtes ci-dessous. |
| timeout | Nombre | Non | Délai d’attente de requête. Si cette valeur n’est pas spécifiée, c&#39;est le délai d’attente par défaut d’at.js qui sera utilisé. |

## Demande

| Nom du champ | Obligatoire ? | Limites | Description |
| --- | --- | --- | --- |
| Requête &gt; id | Non |  | Un de `tntId`, `thirdPartyId`ou `marketingCloudVisitorId` est obligatoire. |
| Requête &gt; ID &gt; IDtiers | Non | Taille maximale = 128 |  |  |
| Request &gt; experiencecloud | Non |  |  |
| Request &gt; experiencecloud &gt; analytics | Non |  | Intégration d&#39;Adobe Analytics |
| Requête &gt; experiencecloud &gt; analytics &gt; journalisation | Non | Les éléments suivants doivent être implémentés sur la page :<ul><li>Service d’identification des visiteurs</li><li>Appmeasurement. js</li></ul> | Les valeurs suivantes sont prises en charge :<br>**client_ side**: Lorsqu&#39;elle est spécifiée, une charge d&#39;analyse est renvoyée à l&#39;appelant qui doit être utilisé pour l&#39;envoi à Adobe Analytics via l&#39;API d&#39;insertion de données.<br>**côté serveur**: Il s&#39;agit de la valeur par défaut dans laquelle l&#39;arrière-plan de Target et Analytics utilise le SDID pour regrouper les appels ensemble à des fins de création de rapports. |
| Requête &gt; prérécupérer | Non |  |  |
| Requête &gt; prérécupérer &gt; vues | Non | Nombre maximal 50<br>Nom non vide<br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=` 5000<br>Le nom ne doit pas commencer par le « profil »<br>Noms non autorisés : « Orderid », « ordertotal », « productpurchasedid » | Transmettez les paramètres à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Requête &gt; Prérécupérer &gt; Affichages &gt; ParamètresProfile | Non | Nombre maximal 50<br>Nom non vide<br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=` 5000<br>Le nom ne doit pas commencer par « profil » | Transmettez les paramètres de profil à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Requête &gt; Prérécupérer &gt; Vues &gt; Produit | Non |  |  |
| Requête &gt; Prérécupérer &gt; Vues &gt; Produit -&gt; ID | Non | Taille maximale<br>non vide = 128 | Transmettez les ID de produit à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Requête &gt; Prérécupérer &gt; Vues &gt; Produit &gt; IDcatégorie | Non | Taille maximale<br>non vide = 128 | Transmettre les identifiants des catégories de produits à utiliser pour récupérer les vues pertinentes dans les activités. |
| Requête &gt; prérécupérer &gt; vues &gt; commande | Non |  |  |
| Requête &gt; prérécupérer &gt; vues &gt; commande &gt; id | Non | Longueur maximale = 250 | Transmettez les ID de commande à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Requête &gt; prérécupérer &gt; vues &gt; commande &gt; total | Non | Total `>=` 0 | Transmettez les totaux de la commande afin qu’ils soient utilisés pour récupérer les vues pertinentes dans les activités courantes. |
| Requête &gt; pré-récupérer &gt; vues &gt; commande &gt; références de produits achetés | Non | Pas de valeurs vides <br>Longueur maximale de chaque valeur 50<br>&gt;Concaténée et séparée par une virgule <br>Longueur totale des ID de produit `<=` 250 | Transmettez les ID de produit achetés à utiliser pour récupérer les vues pertinentes dans les activités actives. |
| Requête &gt; Exécuter | Non |  |  |
| Requête &gt; exécuter &gt; pageCharger | Non |  |  |
| Requête &gt; exécuter &gt; pageCharger &gt; paramètres | Non | Nombre maximal 50<br>Nom non vide <br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=` 5000<br>Nom ne doit pas commencer par « profil ».<br>Noms non autorisés : « ID de la commande », « Total de la commande », « ID du produit acheté » | Récupérez les offres avec des paramètres spécifiés lors du chargement de la page. |
| Demande &gt; Exécuter &gt; pageCharger &gt; profilParamètres | Non | Nombre maximum 50<br>Nom non vide <br>Longueur du nom `<=` 128<br>Longueur de la valeur `<=`256<br>Nom ne doit pas commencer par « profil » | Récupérez les offres avec des paramètres de profil spécifiés lors du chargement de la page. |
| Requête &gt; exécuter &gt; pageCharger &gt; produit | Non |  |  |
| Requête &gt; exécuter &gt; pageCharger &gt; produit -&gt; id | Non | Non vide <br>Taille maximale = 128 | Récupérez les offres avec des ID de produit spécifiés lors du chargement de la page. |
| Requête &gt; exécuter &gt; pageCharger &gt; produit &gt; identifiant de catégorie | Non | Non vide <br>&gt;Taille maximale = 128 | Récupérez les offres avec des identifiants de catégorie de produits spécifiés lors du chargement de la page. |
| Requête &gt; exécuter &gt; pageCharger&gt; commande | Non |  |  |
| Requête &gt; exécuter &gt; pageCharger&gt; commande &gt; id | Non | Longueur maximale = 250 | Récupérez les offres avec des ID de commande spécifiés lors du chargement de la page. |
| Requête &gt; exécuter &gt; pageCharger &gt; commande &gt; Total | Non | `>=` 0 | Récupérez les offres avec des totaux de commande spécifiés lors du chargement de la page. |
| Requête &gt; exécuter &gt; pageCharger &gt; commande &gt; Ids des produits achetés | Non | Aucune valeur à blanc <br>Longueur maximale de chaque valeur 50<br>Concaténé et séparé par une virgule <br>Longueur totale des ID de produit `<=` 250 | Récupérez les offres avec des ID de produit achetés, spécifiés lors du chargement de la page. |
| Requête &gt; exécuter &gt; mbox | Non | Taille maximale = 50<br>Pas d&#39;éléments nuls |  |
| Requête &gt; exécuter &gt; mbox &gt; mbox | Oui | Non vide<br>Suffixe no &#39;-clicked&#39; <br>Taille maximale = 250<br>Caractères autorisés : `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Nom de la mbox. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; index | Oui | Non nul<br>Unique<br>`>=` 0 | Notez que l’index ne représente pas l’ordre dans lequel les mbox seront traitées. Comme dans une page web comportant plusieurs mbox régionales, l’ordre dans lequel ils seront traités ne peut pas être spécifié. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; paramètres | Non | Compte maximum = 50<br>Nom non vide<br>Longueur de nom`<=` 128<br>Longueur de valeur `<=` 5 000<br>Le nom ne doit pas commencer par « profil ».<br>Noms non autorisés : « Orderid », « ordertotal », « productpurchasedid » | Récupérez les offres pour une mbox donnée avec les paramètres spécifiés. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; Paramètresprofile | Non | Compte maximum = 50<br>Nom non vide<br>Longueur de nom`<=` 128<br>Longueur de valeur `<=`256<br>Le nom ne doit pas commencer par « profil ». | Récupérez les offres pour une mbox donnée avec les paramètres de profil spécifiés. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; produit | Non |  |  |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; produit &gt; id | Non | Non vide <br>Taille maximale = 128 | Récupérez les offres pour une mbox donnée avec les ID de produit spécifiés. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; produit &gt; idcatégorie | Non | Non vide<br>Taille maximale = 128 | Récupérez les offres pour une mbox donnée avec les identifiants de catégorie de produits spécifiés. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; commande | Non |  |  |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; commande &gt; id | Non | Longueur maximale = 250 | Récupérez les offres pour une mbox donnée avec les ID de commande spécifiés. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; commande &gt; Total | Non | `>=` 0 | Récupérez les offres pour une mbox donnée avec les totaux de commande spécifiés. |
| Requête &gt; exécuter &gt; mbox &gt; mbox &gt; commande &gt; Idsproduitsachetés | Non | Pas de valeur vide<br>Longueur maximale de chaque valeur = 50<br>Concaténation et séparation par une virgule<br>Longueur totale des identifiants de produit `<=` 250 | Récupérez les offres pour une mbox donnée avec l’ordre spécifié des ID de produit achetés. |

## Appel de `getOffers()` pour toutes les vues

```
adobe.target.getOffers({
    prefetch: {
      views: []
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

## Appel getoffers () pour récupérer la charge utile Analytics du côté client

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

**Réponse**:

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

La charge utile peut ensuite être transmise à Adobe Analytics via l&#39;API d&#39;insertion [de données](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Récupérer et générer les données de plusieurs mbox via getoffers () et applyoffers () {#multiple}

at. js 2. x vous permet de récupérer plusieurs mbox via l&#39; `getOffers()` API. Vous pouvez également récupérer des données pour plusieurs mbox, puis les utiliser `applyOffers()` pour effectuer le rendu des données à différents emplacements identifiés par un sélecteur CSS.

L&#39;exemple suivant illustre une page HTML simple avec at. js 2. x implémentée :

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

Supposons que vous ayez trois conteneurs que vous souhaitez modifier via [!DNL Target]le contenu reçu. Vous pouvez créer une requête unique pour trois mbox dans lesquelles chaque mbox comporte du contenu à rendre dans le conteneur correspondant.

Le code de demande et de rendu peut ressembler à l&#39;exemple suivant :

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

Dans la `request > prefetch > mboxes` section, il existe trois mbox différentes. Si la requête a réussi, vous recevez la réponse de `response > prefetch > mboxes`chaque mbox. Après avoir reçu les réponses et les emplacements à utiliser pour le rendu, vous pouvez lancer `applyOffers()` le rendu du contenu récupéré [!DNL Target]. Dans cet exemple, nous avons le mappage suivant :

* mbox 1 &gt; Sélecteur CSS # container 1
* mbox 2 &gt; Sélecteur CSS # container 2
* mbox 3 &gt; Sélecteur CSS # container 3

Cet exemple utilise la variable count pour construire les sélecteurs CSS. Dans un scénario réel, vous pouvez utiliser un mappage différent entre le sélecteur CSS et la mbox.

Notez que cet exemple utilise `prefetch > mboxes`, mais vous pouvez également utiliser `execute > mboxes`. Vérifiez que si vous utilisez la prérécupération, `getOffers()`vous devez également utiliser la prélecture dans l&#39; `applyOffers()` appel.
