---
description: 'Informations sur la fonction adobe.target.sendNotifications(options) pour at.js. '
keywords: adobe.target.sendNotifications;sendNotifications;sendnotifications;send notifications;notifications;at.js;fonctions;fonction
seo-description: Informations sur la fonction adobe.target.sendNotifications(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
seo-title: Informations sur la fonction adobe.target.sendNotifications(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
solution: Target
subtopic: Prise en main
title: adobe.target.sendNotifications(options)
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# adobe.target.sendNotifications(options)

Cette fonction envoie une notification à Target Edge lorsqu’une expérience est générée sans utiliser `adobe.target.applyOffer()` ou `adobe.target.applyOffers()`.

>[!NOTE]
>
>Cette fonction a été introduite dans at.js 2.1.0 et sera disponible pour toutes les versions ultérieures à 2.1.0.

| Clé | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| consumerId | Chaîne | Non | La valeur par défaut est la mbox globale du client si elle n’est pas fournie. Cette clé sert à générer l’identifiant de données supplémentaire utilisé pour l’intégration A4T. |
| Demande | Objet | Oui | Consultez les requêtes ci-dessous. |
| timeout | Nombre | Non | Délai d’attente de requête. Si cette valeur n’est pas spécifiée, c’est le délai d’attente par défaut d’at.js qui sera utilisé. |

## Demande

| Nom du champ | Type | Obligatoire ? | Limite | Description |
| --- | --- | --- | --- | --- |
| Request &gt; notifications | Tableau d’objets | Oui |  | Notifications pour le contenu affiché, les sélecteurs cliqués et/ou les affichages ou mbox consultés. |
| Request &gt; notifications &gt; address | Objet | Non |  |  |
| Request &gt; notifications &gt; address &gt; url | Chaîne | Non |  | URL à partir de laquelle la notification a été déclenchée. |
| Request &gt; notifications &gt; address &gt; referringUrl | Chaîne | Non |  | URL de référence à partir de laquelle la notification a été déclenchée. |
| Request &gt; notifications &gt; parameters | Objet | Non | Les noms suivants ne sont pas autorisés pour les paramètres :<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tenez compte des points suivants :<ul><li>Limite de 50 paramètres max.</li><li>Le nom du paramètre ne doit pas être vide.</li><li>Longueur de paramètre 128 max.</li><li>Le nom du paramètre ne doit pas commencer par « profile ».</li><li>Longueur de la valeur du paramètre 5 000 max.</li></ul> |  |
| Request &gt; notifications &gt; profileParameters | Objet | Non | Les noms suivants ne sont pas autorisés pour les paramètres :<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tenez compte des points suivants :<ul><li>Limite de 50 paramètres max.</li><li>Le nom du paramètre ne doit pas être vide.</li><li>Longueur de paramètre 128 max.</li><li>Le nom du paramètre ne doit pas commencer par « profile ».</li><li>Longueur de la valeur du paramètre 5 000 max.</li></ul> |  |
| Request &gt; notifications &gt; order | Objet | Non |  | Objet décrivant les détails de la commande. |
| Request &gt; notifications &gt; order &gt; id | Chaîne | Non | `<=` 250 caractères. | ID de commande. |
| Request &gt; notifications &gt; order &gt; total | Chaîne | Non | `>=` 0 | Total de la commande. |
| Request &gt; notifications &gt; order &gt; purchasedProductIds | Tableau de chaîne | Non | <ul><li>Aucune valeur vide n’est autorisée.</li><li>Longueur de chaque id de produit 50 max.</li><li>Les ID de produit, séparés par des virgules et concaténées, ne doivent pas dépasser 250.</li></ul> | ID des produits commandés. |
| Request &gt; notifications &gt; product | Objet | Non |  |  |
| Request &gt; notifications &gt; product &gt; id | Chaîne | Non | `<=` 128 caractères ; ne peut pas être vide. | ID de produit. |
| Request &gt; notifications &gt; product &gt; categoryId | Chaîne | Non | `<=` 128 caractères ; ne peut pas être vide. | ID de catégorie |
| Request &gt; notifications &gt; id | Chaîne | Oui | `<=` 200 caractères. | L’ID de notification est renvoyé en réponse et indique que la notification a bien été traitée. |
| Request &gt; notifications &gt; impressionId | Chaîne | Non | `<= 128` caractères. | L’ID d’impression est utilisé pour associer (lier) la notification actuelle à une notification précédente ou à une demande d’exécution. Au cas où ces deux requêtes correspondent, la deuxième requête et les requêtes suivantes ne généreront pas de nouvelle impression pour l’activité ou l’expérience. |
| Request &gt; notifications &gt; type | Chaîne | Oui | « click » ou « display » est pris en charge. | Type de notification. |
| Request &gt; notifications &gt; timestamp | Nombre`<int64>` | Oui |  | Horodatage de la notification en millisecondes écoulées depuis l’époque UNIX considérée. |
| Request &gt; notifications &gt; tokens | Tableau de chaîne | Oui |  | Liste des jetons pour le contenu affiché ou les sélecteurs cliqués, en fonction du type de notification. |
| Request &gt; notifications &gt; mbox | Objet | Non |  | Notifications pour la mbox. |
| Request &gt; notifications &gt; mbox &gt; name | Chaîne | Non | Aucune valeur vide n’est autorisée.<br>Caractères autorisés : Voir la remarque ci-dessous. | nom de mbox. |
| Request &gt; notifications &gt; mbox &gt; state | Chaîne | Non |  | jeton d’état de mbox. |
| Request &gt; notifications &gt; view | Objet | Non |  |  |
| Request &gt; notifications &gt; view &gt; id | Entier `<int64>` | Non |  | Id de la vue. ID affecté à la vue lorsque la vue a été créée via l’API d’affichage. |
| Request &gt; notifications &gt; view &gt; name | Chaîne | Non | `<= 128` caractères. | Nom de la vue. |
| Request &gt; notifications &gt; view &gt; key | Chaîne | Non | `<=` 512 caractères. | Clé de la vue. Clé qui a été définie avec la vue via l’API. |
| Request &gt; notifications &gt; view &gt; state | Chaîne | Non |  | jeton d’état de la vue. |

**Remarque** : Les caractères suivants sont autorisés pour `Request > notifications > mbox > name` :

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## Appel sendNotifications() après le rendu des mbox prérécupérées

```
function createTokens(options) {
  return options.map(e => e.eventToken);
}

function createNotification(mbox, type, tokens) {
  const id = 11111; // here we should use a random ID like UUID
  const timestamp = Date.now();
  const { name, state, parameters, profileParameters, order, product } = mbox;
  const result = {
    id,
    type,
    timestamp,
    parameters,
    profileParameters,
    order,
    product
  };

  result.mbox = { name, state };
  result.tokens = tokens;

  return result;
}

adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "a1-serverside-ab"
        }
      ]
    }
  }
})
.then(response => {
  const mboxes = response.prefetch.mboxes;
  const notifications = mboxes.map(mbox => {
    const type = "display";
    const tokens = createTokens(mbox.options);

    return createNotification(mbox, type, tokens);
  });
  
  adobe.target.sendNotifications({
    request: { notifications }
  });
})
```

>[!NOTE]
>
>Si vous utilisez Adobe Analytics, `getOffers()` avec prérécupération uniquement et `sendNotifications()`, la requête Analytics doit être déclenchée après l’exécution de `sendNotifications()`. Cela permet de garantir que le SDID généré par `sendNotifications()` correspondra au SDID envoyé à Analytics et Target.