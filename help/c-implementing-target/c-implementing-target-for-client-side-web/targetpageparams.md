---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;param. de page;paramètres de page;at.js;fonctions;fonction
description: Utilisez la fonction targetPageParams() de la bibliothèque JavaScript Adobe Target at.js pour associer des paramètres à la mbox globale en dehors du code de requête.
title: Comment utiliser la fonction targetPageParams() ?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

Cette méthode permet de joindre des paramètres à la mbox globale depuis l’extérieur du code de demande.

Elle s’avère très utile pour inclure un même ensemble de paramètres dans plusieurs appels de mbox. La fonction doit être définie par le client. Elle doit renvoyer un tableau de paramètres qui sera transmis uniquement à la demande de la mbox globale. Cette fonction peut être définie avant le chargement du fichier at.js ou dans **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!UICONTROL Modifier]** > **[!UICONTROL En-tête de bibliothèque]**.

Vous pouvez transmettre des paramètres à target-global-mbox à l’aide de la fonction `targetPageParams()` de n’importe quelle façon suivante :

* Une liste délimitée par des esperluettes
* Un tableau
* Un objet JSON

## Exemples

Liste délimitée par des esperluettes (les valeurs doivent être codées dans l’URL) :

```javascript
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Tableau (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```javascript
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

Objet JSON (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```javascript
targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```
