---
description: 'Informations sur la fonction targetpageparams () pour at. js. '
keywords: adobe.target.notification;élément;sélecteur;notification;extension
seo-description: Informations sur la fonction targetpageparams () pour la bibliothèque JavaScript d'Adobe Target at. js.
seo-title: Informations sur la fonction targetpageparams () pour la bibliothèque JavaScript d'Adobe Target at. js.
solution: Target
subtopic: Prise en main
title: targetPageParams()
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

Cette méthode permet de joindre des paramètres à la mbox globale depuis l’extérieur du code de demande.

Elle s’avère très utile pour inclure un même ensemble de paramètres dans plusieurs appels de mbox. La fonction doit être définie par le client. Elle doit renvoyer un tableau de paramètres qui sera transmis uniquement à la demande de la mbox globale. Cette fonction peut être définie avant le chargement du fichier at.js ou dans **[!UICONTROL Configuration]** &gt; **[!UICONTROL Mise en œuvre]** &gt; **[!UICONTROL Modifier les paramètres at.js]** &gt; **[!UICONTROL Paramètres des codes]** &gt; **[!UICONTROL En-tête de bibliothèque]**.

Vous pouvez transmettre des paramètres à target-global-mbox à l’aide de la fonction `targetPageParams()` de n’importe quelle façon suivante :

* Une liste délimitée par des esperluettes
* Un tableau
* Un objet JSON

## Exemples

Liste délimitée par des esperluettes (les valeurs doivent être codées dans l’URL) :

```
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Tableau (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

Objet JSON (les valeurs n’ont pas besoin d’être codées dans l’URL) :

```
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
