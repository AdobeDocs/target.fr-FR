---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;fonctions;fonction
description: Utilisez la fonction adobe.target.applyOffer() pour l’Adobe [!DNL Target] Bibliothèque JavaScript at.js pour appliquer le contenu de la réponse.
title: Comment utiliser la fonction adobe.target.applyOffer() ?
feature: at.js
role: Developer
exl-id: d230d48f-0d6c-4f55-96a0-681dd31e8d16
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 73%

---

# adobe.target.applyOffer(options)

Cette fonction permet d’appliquer le contenu de la réponse avec [!DNL Adobe Target].

>[!NOTE]
>
>`applyOffer` nécessite le paramètre `mbox`. Si le nom de mbox n’est pas spécifié, une erreur se produit.

Le paramètre options est obligatoire et possède la structure suivante :

| Clé | Type | Requis | Description |
|--- |--- |--- |--- |
| mbox | Chaîne | Oui | Nom de mbox<br> avec at.js 1.3.0 (et versions ultérieures), Target applique impérativement l’utilisation de la clé mbox. Cette clé était obligatoire par le passé, mais Target force désormais son application de manière à garantir sa validation et l’utilisation correcte de la fonction par les clients. |
| selector | Chaîne ou élément DOM | Non | Élément HTML ou sélecteur CSS utilisé pour identifier l’élément HTML dans lequel Target doit placer le contenu de l’offre. Si le sélecteur n’est pas fourni, Target suppose que l’élément de HTML doit utiliser l’HEAD de HTML. |
| Offre | Tableau | Oui | Les actions d’un tableau devant être appliquées à l’élément. |

## Exemple {#section_D8D6A17B73DE4542937CDB687193A5CC}

L’exemple suivant illustre l’utilisation conjointe de `getOffer` et d’`applyOffer` :

```javascript
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
