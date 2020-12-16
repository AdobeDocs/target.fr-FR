---
keywords: adobe.target.applyOffers;applyOffers;applyoffers;apply offers;at.js;functions;function
description: Informations sur la fonction adobe.target.applyOffers(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
title: adobe.target.applyOffers(options) - at.js 2.x
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 95%

---


# adobe.cible.applyOffers(options) - at.js 2.x

Cette fonction vous permet d’appliquer plusieurs offres récupérées par `adobe.target.getOffers()`.

>[!NOTE]
>
>Cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*.

| Clé | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| selector | Chaîne | Non | Élément HTML ou sélecteur CSS utilisé pour identifier l’élément HTML dans lequel [!DNL Target] doit placer le contenu de l’offre. Si aucun sélecteur n’est fourni, [!DNL Target] suppose que l’élément HTML à utiliser est HEAD HTML. |
| Réponse | Objet | Oui | Objet réponse de `getOffers()`.<br>Voir Requêtes ci-dessous. |

## Réponse

>[!NOTE]
>
>Consultez la [documentation de l&#39;API de Diffusion](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) pour plus d&#39;informations sur les types acceptables pour tous les champs répertoriés ci-dessous.

| Nom du champ | Description |
| --- | --- |
| réponse > prérécupérer > vues > options > contenu | Notez que le contenu de l’« option » n’est pas bien défini et dépend directement de la structure du type/modèle d’option. |
| réponse > prérécupérer > vues > options > type | Type d’option. Reflète le type de champ « contenu ». Le type pris en charge est Actions. |
| réponse > prérécupérer > vues > état | Jeton d’état d’affichage opaque qui doit être transféré avec une notification d’affichage pour la vue |
| réponse > prérécupérer > vues > options > jetonsderéponse | Contient le mappage de `responseTokens` qui a été collecté lorsque l’option actuelle était en cours de traitement. |
| réponse > prérécupérer > vues > analytics > charge utile | Charge utile Analytics pour l’intégration côté client qui doit être envoyée à Analytics après l’application de la vue. |
| réponse > prérécupérer > vues > trace | Objet contenant toutes les données de suivi pour l’appel de prérécupération par affichage.<br>L’objet trace comprend également une version pour la trace.<br>L’objet trace comprend également des détails sur la vue actuelle. |
| réponse > prérécupérer > vues > options > jetonDévénement | La journalisation d’événements est effectuée par option. Pour chaque option appliquée, le jeton d’événement correspondant doit être ajouté à la liste des jetons de notification. Notez qu’une vue est composée de plusieurs options. Si toutes les options ont été appliquées et affichées, toutes `eventTokens` doivent être incluses dans la notification. |
| réponse > prérécupérer > vues > nom | Nom d’affichage lisible. |
| réponse > prérécupérer > vues > mesures | Mesures de création de rapports qui doivent être regardées, puis notifiées [!DNL Target]. Actuellement, il suffit de cliquer sur Mesure pour afficher la mesure. Si un clic sur l’élément se produit, les informations appropriées `eventTokens` doivent être collectées et une notification doit être envoyée. |
| réponse > prérécupérer > vues > clé | Clé ou empreinte digitale qui identifie la vue. |
| réponse > prérécupérer > vues > id | ID de la vue. |
| réponse > notifications > id | Identifiant de notification. |
| réponse > notifications > événements > type | Type de notification, du clic ou de l’affichage. |
| réponse > notifications > événements > trace | Trace de l’événement de notification. |
| réponse > notifications > événements > jeton | Jeton envoyé avec l’événement de notification. |
| réponse > notifications > événements > horodatage | Horodatage envoyé avec l’événement de notification. |
| réponse > notifications > événements > erreurCode | Si la notification a échoué, le code indique la raison de l’échec. |
| réponse > notifications > événements | Événements consignés ou non répertoriés pour la notification actuelle. |
| réponse > notifications | Indique les notifications enregistrées ou non. |
| réponse > exécuter > mbox > mbox > trace | Objet contenant toutes les données de suivi pour la requête de mbox individuelle. |
| réponse > exécuter > mbox > mbox > jetons de réponse | Contient le mappage `responseTokens` pour l’exécution spécifique de la requête de mbox. |
| réponse > exécuter > mbox > mbox > option > contenu | Notez que le contenu de l’« option » n’est pas bien défini et dépend directement de la structure du type/modèle d’option. |
| réponse > exécuter > mbox > mbox > option > type | Type d’option. Reflète le type de champ « contenu ». Les types pris en charge sont les suivants : html, redirect, JSON et dynamique. |
| réponse > exécuter > mbox > mbox > options | Option de réponse. |
| réponse > exécuter > mbox > mbox > mesures > eventtoken | Jeton d’événement de clic. |
| réponse > exécuter > mbox > mbox > mesures > type | &quot;click&quot; |
| réponse > exécuter > mbox > mbox > mesures | Contient la liste des mesures `clickThrough`. |
| réponse > exécuter > mbox > mbox > mbox | Nom de la mbox. |
| réponse > exécuter > mbox > mbox > index | Indique que la réponse est destinée à la mbox avec cet index de la requête. |
| réponse > exécuter > mbox > mbox > analytics > charge | Charge Analytics pour l’intégration côté client, qui doit être envoyée à Analytics après l’application de la mbox. (Voir la section Campagnes compatibles avec A4T). |
| réponse > exécuter > mbox | Liste des mbox exécutées. |
| réponse > exécuter > pageLoad > options > contenu | Notez que le contenu de l’« option » n’est pas bien défini et dépend directement de la structure du type/modèle d’option. |
| réponse > exécuter > pageLoad > options > type | Type d’option. Reflète le type de champ « contenu ». Les types pris en charge sont : html, rediriger, JSON, dynamique et actions. |
| réponse > exécuter > pageLoad > options | Options qui ne sont pas regroupées par affichage (target-global-mbox + options issues d’activités dont les vues ne sont pas regroupées par affichage). |
| réponse > exécuter > pageLoad > mesures | Cliquez sur les mesures qui n’ont pas été définies pour appartenir à une vue spécifique. |
| réponse > exécuter > pageLoad > suivi | Objet contenant toutes les données de suivi pour la requête pageLoad. |
| réponse > exécuter > pageLoad > analytics > charge | Charge Analytics pour l’intégration côté client, qui doit être envoyée à Analytics après application du contenu de chargement de la page. (Voir la section Campagnes compatibles avec A4T). |

## Exemple appel applyOffers()

```javascript
adobe.target.applyOffers({response:{
  "execute": {
    "pageLoad": {
      "options": [{
        "type": "html",
        "content": "page-load"
      },
      {
        "type": "actions",
        "content": [{
          "type": "setHtml",
          "content": "<h1>Container 1</h1>",
          "selector": "#container1",
          "cssSelector": "#container1"
        },
        {
          "type": "setHtml",
          "content": "<h3>Container 3</h3>",
          "selector": "#container3",
          "cssSelector": "#container3"
        }]
      }],
 
 
      "metrics": [{
        "type": "click",
        "selector": "#container1",
        "eventToken": "page-load-click-metric" 
      }]
    }
  }
}});
```

## Exemple d’appel de Promesse chaînée avec `getOffers()` et `applyOffers()`, car ces fonctions sont basées sur Promesse

```javascript
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
