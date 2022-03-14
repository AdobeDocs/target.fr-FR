---
keywords: adobe.target.getOffer;getOffer;getoffer;get offer;at.js;fonctions;fonction
description: Utilisez la fonction adobe.target.getOffer() et ses options pour l’Adobe [!DNL Target] bibliothèque at.js pour déclencher des demandes d’obtention d’un [!DNL Target] offre.
title: Comment utiliser la fonction adobe.target.getOffer() ?
feature: at.js
role: Developer
exl-id: 3448fdaa-b5f6-465d-8858-1dfe214bd8c4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 91%

---

# adobe.target.getOffer(options)

Cette fonction déclenche une demande pour obtenir une offre Target.

Utilisez avec `adobe.target.applyOffer()` pour traiter la réponse ou utilisez votre propre gestion de succès. Le paramètre options est obligatoire et possède la structure suivante :

| Clé | Type | Requis | Description |
|--- |--- |--- |--- |
| mbox | Chaîne | Oui | Nom de mbox |
| params | Objet | Non | Paramètres mBox. Objet de paires clé-valeur qui possède la structure suivante :<br>`{ "param1": "value1", "param2": "value2"}` |
| success | Fonction | Oui | Rappel à exécuter lors de l’obtention d’une réponse du serveur. La fonction de rappel de succès reçoit un seul paramètre qui représente un tableau des objets d’offre. Voici un exemple de rappel de succès :<br>`function handleSuccess(response){......}`<br>Pour plus d’informations, consultez les Réponses ci-dessous. |
| error | Fonction | Oui | Rappel à exécuter lors d’une erreur. Quelques cas sont considérés comme des erreurs :<ul><li>Le code d’état HTTP est différent de 200 OK.</li><li>La réponse ne peut pas être analysée. Par exemple, le code JSON a été mal créé ou du code HTML a été utilisé à la place de JSON.</li><li>La réponse contient la clé error. Par exemple, une exception a été levée à la périphérie car une demande n’a pas pu être correctement traitée. Un message d’erreur peut être généré lorsqu’une mbox est bloquée et qu’il est impossible de récupérer le contenu correspondant, etc. La fonction de rappel d’erreur reçoit deux paramètres : status et error. Voici un exemple de rappel d’erreur : `function handleError(status, error){......}`</li></ul>Pour plus d’informations, voir les réponses d’erreur ci-dessous. |
| timeout | Nombre | Non | Délai d’attente exprimé en secondes. Si cette valeur n’est pas spécifiée, le délai d’attente par défaut d’at.js est utilisé.<br>Le délai d’expiration par défaut peut être défini à partir de la variable [!DNL Target] IU sous [!UICONTROL Administration > Mise en oeuvre]. |

## Exemples {#section_97C2D2E03E6549BEA7F4873E3F5E4A0D}

Ajout de paramètres avec getOffer() et utilisation de applyOffer() pour la gestion de succès :

```javascript
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Ajout de paramètres et de paramètres de profil avec getOffer() et utilisation de applyOffer() pour la gestion de succès :

```javascript
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2, 
     "profile.age": 27, 
     "profile.gender": "male" 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Utilisation d’un délai d’attente personnalisé et d’une gestion de succès personnalisée avec getOffer() :

« YOUR_OWN_CUSTOM_HANDLING_FUNCTION » est un espace réservé pour une fonction définie par le client.

```javascript
adobe.target.getOffer({     
  "mbox": "target-global-mbox",   
  "success": function(offer) { 
    YOUR_OWN_CUSTOM_HANDLING_FUNCTION(offer);   
  }, 
  "error": function(status, error) {                 
    console.log('Error', status, error);   
  },   
  "timeout": 2000 
});
```

## Réponses {#section_CF9FD236EF794620BCBF84EB80160183}

Le paramètre de la réponse transféré au rappel de succès correspondra à un tableau d’actions. Une action est un objet qui a généralement le format suivant :

| Nom | Type | Description |
|--- |--- |--- |
| action | Chaîne | Type d’action à appliquer à l’élément identifié. |
| selector | Chaîne | Représente un sélecteur de fichier sizzle. |
| cssSelector | Chaîne | Sélecteur de modèle DOM natif, utilisé pour le prémasquage des éléments. |
| content | Chaîne | Le contenu à appliquer à l’élément identifié. |

## Exemple

```javascript
{ 
    "sessionId": "1444512212156-384616", 
    "tntId": "1444512212156-384616.17_35", 
    "offers": [{ 
        "plugins": ["<script type=\"text/javascript\">\r\n/*mboxHighlight+ (1of2) v1 ==> Response Plugin*/\r\nwindow.ttMETA=(typeof(window.ttMETA)!='undefined')?window.ttMETA:[];window.ttMETA.push({'mbox':'target-global-mbox','campaign':'at: redirect ootb','experience':'Experience B','offer':'/at_redirect_ootb/experiences/1/pages/0/1442082890250'});window.ttMBX=function(x){var mbxList=[];for(i=0;i<ttMETA.length;i++){if(ttMETA[i].mbox==x.getName()){mbxList.push(ttMETA[i])}}return mbxList[x.getId()]}\r\n</script>"], 
        "actions": { 
            "content": [{ 
                "passMboxSession": false, 
                "selector": "body", 
                "action": "redirect", 
                "url": "https://example.com/04.html", 
                "includeAllUrlParameters": true 
            }] 
        } 
    }] 
}
```

## Réponses d’erreur {#section_1ACCE79AF2CB4FA2AD1371EA06AF129F}

Les paramètres status et error transmis au rappel d’erreur possèdent le format suivant :

| Nom | Type | Description |
|--- |--- |--- |
| status | Chaîne | Représente l’état d’erreur. Ce paramètre peut avoir les valeurs suivantes :<ul><li>timeout : indique que la demande a expiré.</li><li>parseerror : indique que l’erreur n’a pas pu être analysée, par exemple, si nous recevons le code HTML ou un texte brut au lieu du code JSON.</li><li>error : indique une erreur générale, telle que la réception d’un état HTTP différent de 200 OK</li></ul> |
| error | Chaîne | Contient des données supplémentaires telles qu’un message d’exception ou tout autre élément utile pour la résolution des problèmes. |
