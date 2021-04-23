---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;param. de page;paramètres de page;at.js;fonctions;fonction
description: Utilisez la fonction targetPageParamsAll() de la bibliothèque JavaScript Adobe [!DNL Target] at.js pour associer des paramètres à toutes les mbox en dehors du code de requête.
title: Comment utiliser la fonction targetPageParamsAll() ?
feature: at.js
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 72%

---

# targetPageParamsAll()

Cette méthode permet de joindre des paramètres à toutes les mbox à l’extérieur du code de demande.

Elle s’avère très utile pour inclure un même ensemble de paramètres dans plusieurs appels de mbox. La fonction doit être définie par le client. Elle doit renvoyer un tableau de paramètres qui sera transmis à toutes les demandes de mbox sur la page. Cette fonction peut être définie avant le chargement du fichier at.js ou dans **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!UICONTROL Modifier]** > **[!UICONTROL Paramètres de code]** > **[!UICONTROL En-tête de bibliothèque]**.

Vous pouvez transmettre des paramètres à target-global-mbox à l’aide de la fonction targetPageParamsAll() dans :

* Une liste délimitée par des esperluettes
* Un tableau
* Un objet JSON

## Exemples

Liste délimitée par des esperluettes (les valeurs doivent être codées dans l’URL) :

```javascript
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Tableau (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```javascript
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

Objet JSON (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```javascript
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
