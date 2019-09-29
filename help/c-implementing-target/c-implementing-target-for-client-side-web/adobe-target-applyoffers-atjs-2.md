---
description: 'Informations sur la fonction adobe.target.applyOffers() pour at.js. '
keywords: adobe.target.applyOffers;applyOffers;applyoffers;apply offers;at.js;fonctions;fonction
seo-description: Informations sur la fonction adobe.target.applyOffers(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
seo-title: Informations sur la fonction adobe.target.applyOffers(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
solution: Target
subtopic: Prise en main
title: adobe.target.applyOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# adobe.target.applyOffers(options) - at.js 2.x

Cette fonction vous permet d’appliquer plusieurs offres récupérées par `adobe.target.getOffers()`.

>[!NOTE]
>
>Cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*.

| Clé | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| selector | Chaîne | Non | Élément HTML ou sélecteur CSS utilisé pour identifier l’élément HTML dans lequel [!DNL Target] doit placer le contenu de l’offre. Si le sélecteur n’est pas fourni, [!DNL Target] suppose que l’élément HTML que nous devons utiliser est HTML HEAD. |
| Réponse | Objet | Oui | Objet réponse de `getOffers()`.<br>Voir Requêtes ci-dessous. |

## Réponse

| Nom du champ | Description |
| --- | --- |
| réponse &gt; prérécupérer &gt; vues &gt; options &gt; contenu | Notez que le contenu de l’« option » n’est pas bien défini et dépend directement de la structure du type/modèle d’option. |
| réponse &gt; prérécupérer &gt; vues &gt; options &gt; type | Type d’option. Reflète le type de champ « contenu ». Le type pris en charge est Actions. |
| réponse &gt; prérécupérer &gt; vues &gt; état | Jeton d’état d’affichage opaque qui doit être transféré avec une notification d’affichage pour la vue |
| réponse &gt; prérécupérer &gt; vues &gt; options &gt; jetonsderéponse | Contient le mappage de `responseTokens` qui a été collecté lorsque l’option actuelle était en cours de traitement. |
| réponse &gt; prérécupérer &gt; vues &gt; analytics &gt; charge utile | Charge utile Analytics pour l’intégration côté client qui doit être envoyée à Analytics après l’application de la vue. |
| réponse &gt; prérécupérer &gt; vues &gt; trace | Objet contenant toutes les données de suivi pour l’appel de prérécupération par affichage.<br>L’objet trace comprend également une version pour la trace.<br>L’objet trace comprend également des détails sur la vue actuelle. |
| réponse &gt; prérécupérer &gt; vues &gt; options &gt; jetonDévénement | La journalisation d’événements est effectuée par option. Pour chaque option appliquée, le jeton d’événement correspondant doit être ajouté à la liste des jetons de notification. Notez qu’une vue est composée de plusieurs options. Si toutes les options ont été appliquées et affichées, toutes `eventTokens` doivent être incluses dans la notification. |
| réponse &gt; prérécupérer &gt; vues &gt; nom | Nom d’affichage lisible. |
| réponse &gt; prérécupérer &gt; vues &gt; mesures | Mesures de création de rapports qui doivent être regardées, puis notifiées [!DNL Target]. Actuellement, il suffit de cliquer sur Mesure pour afficher la mesure. Si un clic sur l’élément se produit, les informations appropriées `eventTokens` doivent être collectées et une notification doit être envoyée. |
| réponse &gt; prérécupérer &gt; vues &gt; clé | Clé ou empreinte digitale qui identifie la vue. |
| réponse &gt; prérécupérer &gt; vues &gt; id | ID de la vue. |
| réponse &gt; notifications &gt; id | Identifiant de notification. |
| réponse &gt; notifications &gt; événements &gt; type | Type de notification, du clic ou de l’affichage. |
| réponse &gt; notifications &gt; événements &gt; trace | Trace de l’événement de notification. |
| réponse &gt; notifications &gt; événements &gt; jeton | Jeton envoyé avec l’événement de notification. |
| réponse &gt; notifications &gt; événements &gt; horodatage | Horodatage envoyé avec l’événement de notification. |
| réponse &gt; notifications &gt; événements &gt; erreurCode | Si la notification a échoué, le code indique la raison de l’échec. |
| réponse &gt; notifications &gt; événements | Événements consignés ou non répertoriés pour la notification actuelle. |
| réponse &gt; notifications | Indique les notifications enregistrées ou non. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; trace | Objet contenant toutes les données de suivi pour la requête de mbox individuelle. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; jetons de réponse | Contient le mappage `responseTokens` pour l’exécution spécifique de la requête de mbox. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; option &gt; contenu | Notez que le contenu de l’« option » n’est pas bien défini et dépend directement de la structure du type/modèle d’option. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; option &gt; type | Type d’option. Reflète le type de champ « contenu ». Les types pris en charge sont les suivants : html, redirect, JSON et dynamique. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; options | Option de réponse. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; mesures &gt; eventtoken | Jeton d’événement de clic. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; mesures &gt; type | "click" |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; mesures | Contient la liste des mesures `clickThrough`. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; mbox | Nom de la mbox. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; index | Indique que la réponse est destinée à la mbox avec cet index de la requête. |
| réponse &gt; exécuter &gt; mbox &gt; mbox &gt; analytics &gt; charge | Charge Analytics pour l’intégration côté client, qui doit être envoyée à Analytics après l’application de la mbox. (Voir la section Campagnes compatibles avec A4T). |
| réponse &gt; exécuter &gt; mbox | Liste des mbox exécutées. |
| réponse &gt; exécuter &gt; pageLoad &gt; options &gt; contenu | Notez que le contenu de l’« option » n’est pas bien défini et dépend directement de la structure du type/modèle d’option. |
| réponse &gt; exécuter &gt; pageLoad &gt; options &gt; type | Type d’option. Reflète le type de champ « contenu ». Les types pris en charge sont : html, rediriger, JSON, dynamique et actions. |
| réponse &gt; exécuter &gt; pageLoad &gt; options | Options qui ne sont pas regroupées par affichage (target-global-mbox + options issues d’activités dont les vues ne sont pas regroupées par affichage). |
| réponse &gt; exécuter &gt; pageLoad &gt; mesures | Cliquez sur les mesures qui n’ont pas été définies pour appartenir à une vue spécifique. |
| réponse &gt; exécuter &gt; pageLoad &gt; suivi | Objet contenant toutes les données de suivi pour la requête pageLoad. |
| réponse &gt; exécuter &gt; pageLoad &gt; analytics &gt; charge | Charge Analytics pour l’intégration côté client, qui doit être envoyée à Analytics après application du contenu de chargement de la page. (Voir la section Campagnes compatibles avec A4T). |

## Exemple appel applyOffers()

```
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

```
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
