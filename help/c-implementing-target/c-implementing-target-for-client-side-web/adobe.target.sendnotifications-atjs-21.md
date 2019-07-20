---
description: 'Informations sur la fonction adobe. target. sendnotifications (options) pour at. js. '
seo-description: Informations sur la fonction adobe. target. sendnotifications (options) pour la bibliothèque JavaScript d'Adobe Target at. js.
seo-title: Informations sur la fonction adobe. target. sendnotifications (options) pour la bibliothèque JavaScript d'Adobe Target at. js.
solution: Target
subtopic: Prise en main
title: adobe. target. sendnotifications (options)
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# adobe. target. sendnotifications (options)

This function sends a notification to Target edge when an experience is rendered without using `adobe.target.applyOffer()` or `adobe.target.applyOffers()`.

>[!NOTE]
>
>Cette fonction a été introduite dans at. js 2.1.0 et sera disponible pour toutes les versions supérieures à 2.1.0.

| Clé | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| consumerId | Chaîne | Non | La valeur par défaut est la mbox globale du client si elle n’est pas fournie. Cette clé sert à générer l’identifiant de données supplémentaire utilisé pour l’intégration A4T. |
| Demande | Objet | Oui | Consultez les requêtes ci-dessous. |
| timeout | Nombre | Non | Délai d’attente de requête. Si cette valeur n’est pas spécifiée, c’est le délai d’attente par défaut d’at.js qui sera utilisé. |

## Demande

| Nom du champ | Type | Obligatoire ? | Limite | Description |
| --- | --- | --- | --- | --- |
| Requête &gt; Notifications | Tableau d'objets | Oui |  | Notifications pour le contenu affiché, les sélecteurs cliqués et/ou les affichages ou mbox consultés. |
| Requête &gt; notifications &gt; Adresse | Objet | Non |  |  |
| Request &gt; notifications &gt; address &gt; url | Chaîne | Non |  | URL à partir de laquelle la notification a été déclenchée. |
| Request &gt; notifications &gt; address &gt; referringurl | Chaîne | Non |  | URL de référence à partir de laquelle la notification a été déclenchée. |
| Requête &gt; notifications &gt; paramètres | Objet | Non | Les noms suivants ne sont pas autorisés pour les paramètres :<ul><li>orderId</li><li>orderTotal</li><li>Productpurchasedids</li></ul>Tenez compte des points suivants :<ul><li>Limite max. de 50 paramètres.</li><li>Le nom du paramètre ne doit pas être vide.</li><li>Nom du paramètre max 128.</li><li>Le nom du paramètre ne doit pas commencer par « profile ».  » »</li><li>Longueur de paramètre max 5000.</li></ul> |  |
| Request &gt; Notifications &gt; profileparameters | Objet | Non | Les noms suivants ne sont pas autorisés pour les paramètres :<ul><li>orderId</li><li>orderTotal</li><li>Productpurchasedids</li></ul>Tenez compte des points suivants :<ul><li>Limite max. de 50 paramètres.</li><li>Le nom du paramètre ne doit pas être vide.</li><li>Nom du paramètre max 128.</li><li>Le nom du paramètre ne doit pas commencer par « profile ».  » »</li><li>Longueur de paramètre max 5000.</li></ul> |  |
| Requête &gt; notifications &gt; commande | Objet | Non |  | Objet décrivant les détails de la commande. |
| Request &gt; notifications &gt; order &gt; id | Chaîne | Non | `<=` 250 caractères. | ID de commande. |
| Requête &gt; notifications &gt; commande &gt; Total | Chaîne | Non | `>=` 0 | Total de la commande. |
| Request &gt; Notifications &gt; order &gt; purchasedproductids | Tableau de chaîne | Non | <ul><li>Aucune valeur vide n'est autorisée.</li><li>Longueur max. de chaque produit 50.</li><li>Les ID de produit, séparés par des virgules et concaténées, ne doivent pas dépasser 250.</li></ul> | ID du produit Commande. |
| Request &gt; notifications &gt; product | Objet | Non |  |  |
| Request &gt; notifications &gt; product &gt; id | Chaîne | Non | `<=` 128 caractères ; ne peut pas être vide. | ID de produit. |
| Request &gt; notifications &gt; product &gt; categoryid | Chaîne | Non | `<=` 128 caractères ; ne peut pas être vide. | Identifiant de catégorie. |
| Request &gt; notifications &gt; id | Chaîne | Oui | `<=` 200 caractères. | L'ID de notification est renvoyé en réponse et indique que la notification a bien été traitée. |
| Request &gt; notifications &gt; impressionid | Chaîne | Non | `<= 128` caractères. | L'ID d'impression est utilisé pour associer (lier) la notification actuelle à une notification précédente ou à une demande d'exécution. Au cas où ces deux requêtes correspondent, le deuxième et les autres requêtes suivantes ne généreront pas une nouvelle impression pour l'activité ou l'expérience. |
| Requête &gt; notifications &gt; Type | Chaîne | Oui | « click » ou « display » est pris en charge. | Type de notification. |
| Requête &gt; notifications &gt; horodatage | Nombre`<int64>` | Oui |  | Horodatage de la notification en millisecondes écoulées depuis l'époque UNIX considérée. |
| Requête &gt; notifications &gt; jetons | Tableau de chaîne | Oui |  | Liste des jetons pour le contenu affiché ou les sélecteurs cliqués, en fonction du type de notification. |
| Requête &gt; notifications &gt; mbox | Objet | Non |  | Notifications pour la mbox. |
| Request &gt; notifications &gt; mbox &gt; name | Chaîne | Non | Aucune valeur vide n'est autorisée.<br>Caractères autorisés : Voir la remarque ci-dessous. | nom de mbox. |
| Request &gt; notifications &gt; mbox &gt; state | Chaîne | Non |  | jeton d'état de mbox. |
| Requête &gt; notifications &gt; Affichage | Objet | Non |  |  |
| Request &gt; notifications &gt; view &gt; id | Entier `<int64>` | Non |  | Afficher l'id. ID affecté à l'affichage lorsque la vue a été créée via l'API d'affichage. |
| Request &gt; notifications &gt; view &gt; name | Chaîne | Non | `<= 128` caractères. | Nom de la vue. |
| Request &gt; notifications &gt; view &gt; key | Chaîne | Non | `<=` 512 caractères. | Afficher la clé. Clé qui a été définie avec la vue via l'API. |
| Request &gt; notifications &gt; view &gt; state | Chaîne | Non |  | Afficher le jeton d'état. |

**Remarque**: Les caractères suivants sont autorisés `Request > notifications > mbox > name`pour :

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## Appel sendnotifications () après le rendu des mbox prefetched

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
>If you are using Adobe Analytics, `getOffers()` with prefetch only and `sendNotifications()`, the Analytics request must be fired after `sendNotifications()` is executed. The purpose of this is to ensure that the SDID generated by `sendNotifications()` will match the SDID sent to Analytics and Target.