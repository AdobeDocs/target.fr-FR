---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;functions;function
description: Informations sur la fonction adobe.target.applyOffer(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
title: Informations sur la fonction adobe.target.applyOffer() pour la bibliothèque JavaScript at.js d’Adobe Target.
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 100%

---


# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

Cette fonction permet d’appliquer le contenu de la réponse.

>[!NOTE]
>
>`applyOffer` nécessite le paramètre `mbox`. Si le nom de mbox n’est pas spécifié, une erreur se produit.

Le paramètre options est obligatoire et possède la structure suivante :

| Clé | Type | Requis | Description |
|--- |--- |--- |--- |
| mbox | Chaîne | Oui | Nom de mbox<br> avec at.js 1.3.0 (et versions ultérieures), Target applique impérativement l’utilisation de la clé mbox. Cette clé était obligatoire par le passé, mais Target force désormais son application de manière à garantir sa validation et l’utilisation correcte de la fonction par les clients. |
| selector | Chaîne ou élément DOM | Non | Élément HTML ou sélecteur CSS utilisé pour identifier l’élément HTML dans lequel Target doit placer le contenu de l’offre. Si le sélecteur n’est pas fourni, Target suppose que l’élément HTML que nous devons utiliser est HTML HEAD. |
| offer | Tableau | Oui | Les actions d’un tableau devant être appliquées à l’élément. |

## Exemple {#section_D8D6A17B73DE4542937CDB687193A5CC}

L’exemple suivant illustre l’utilisation conjointe de `getOffer` et d’`applyOffer` :

```
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```
