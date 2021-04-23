---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;param. de page;paramètres de page;at.js;fonctions;fonction
description: Utilisez la fonction targetPageParams() de la bibliothèque JavaScript Adobe [!DNL Target] at.js pour associer des paramètres à la mbox globale en dehors du code de requête.
title: Comment utiliser la fonction targetPageParams() ?
feature: at.js
role: Developer
exl-id: 0772b400-626c-45d8-a4b5-a12691978cf3
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---

# targetPageParams()

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
