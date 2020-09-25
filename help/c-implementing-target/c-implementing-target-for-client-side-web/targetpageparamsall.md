---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;page params;page parameters;at.js;functions;function
description: Informations sur la fonction targetPageParamsAll() pour la bibliothèque JavaScript at.js d’Adobe Target.
title: targetPageParamsAll()
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 8789d750e9e0245d88d54a8d3fe342e5b2e616fc
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 87%

---


# targetPageParamsAll()

Cette méthode permet de joindre des paramètres à toutes les mbox à l’extérieur du code de demande.

Elle s’avère très utile pour inclure un même ensemble de paramètres dans plusieurs appels de mbox. La fonction doit être définie par le client. Elle doit renvoyer un tableau de paramètres qui sera transmis à toutes les demandes de mbox sur la page. This function can be defined before at.js is loaded or in **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

Vous pouvez transmettre des paramètres à target-global-mbox à l’aide de la fonction targetPageParamsAll() dans :

* Une liste délimitée par des esperluettes
* Un tableau
* Un objet JSON

## Exemples

Liste délimitée par des esperluettes (les valeurs doivent être codées dans l’URL) :

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Tableau (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

Objet JSON (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```
targetPageParamsAll = function() { 
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
