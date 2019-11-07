---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;param. de page;paramètres de page;at.js;fonctions;fonction
description: Informations sur la fonction targetPageParamsAll() pour la bibliothèque JavaScript at.js d’Adobe Target.
title: Informations sur la fonction targetPageParamsAll() pour la bibliothèque JavaScript at.js d’Adobe Target.
subtopic: Prise en main
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# targetPageParamsAll()

Cette méthode permet de joindre des paramètres à toutes les mbox à l’extérieur du code de demande.

Elle s’avère très utile pour inclure un même ensemble de paramètres dans plusieurs appels de mbox. La fonction doit être définie par le client. Elle doit renvoyer un tableau de paramètres qui sera transmis à toutes les demandes de mbox sur la page. Cette fonction peut être définie avant le chargement du fichier at.js ou dans **[!UICONTROL Configuration]** &gt; **[!UICONTROL Mise en œuvre]** &gt; **[!UICONTROL Modifier les paramètres at.js]** &gt; **[!UICONTROL Paramètres des codes]** &gt; **[!UICONTROL En-tête de bibliothèque]**.

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
