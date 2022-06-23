---
keywords: paramètres de mbox globale;targetPageParams;chaîne de requête;tableau;json;dtm
description: Découvrez comment utiliser la fonction targetPageParams pour transmettre des informations de ciblage ou de contexte supplémentaires à l’Adobe [!DNL Target] mbox globale.
title: Comment puis-je transférer des paramètres à une mbox globale ?
feature: at.js
role: Developer
exl-id: 37d143af-83a8-48fd-91eb-58f21f8c7b94
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 63%

---

# Transfert de paramètres à une mbox globale

Le JavaScript `targetPageParams` sert à transférer des paramètres à la mbox globale dans [!DNL Adobe Target]. Cette fonction est requise dans les scénarios où des informations supplémentaires de ciblage/contexte doivent être transférées dans [!DNL Target].

Par exemple, dans une [!DNL Recommendations] activité, utilisez les paramètres pour représenter le produit ou la catégorie en cours de consultation.

Le code permettant d’appeler la fonction JavaScript doit être placé avant la mbox globale sur la page, que la mbox globale soit déclenchée dans le cadre d’at.js ou qu’elle soit incluse manuellement dans le code de page.

>[!NOTE]
>
>Si vous souhaitez ajouter des paramètres à toutes les mbox de la page, et pas seulement à la mbox globale, utilisez la variable [targetPageParamsAll()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/) fonction .

Vous pouvez transférer des paramètres à `target-global-mbox` à l’aide de la fonction `targetPageParams()` de l’une des façons suivantes :

* Un tableau
* Un objet JSON
* Une liste délimitée par des esperluettes

Utilisez ces trois méthodes pour vérifier que les paramètres sont transférés correctement. Vous pouvez également être en mesure de vérifier le transfert des paramètres en utilisant le [Débogueur d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).

Vous devez définir la fonction JavaScript avant d’ajouter la mbox globale à la page. Le nom doit être `targetPageParams`.

## Chaîne de requête

```
p1=v1&p2=v2&p3=hello%20world
```

* Nom : `targetPageParams`
* Valeur de renvoi : des paramètres délimités « &amp; » avec des valeurs de paramètre codées en URL

   Exemple :

   Dans cet exemple, p3 a la valeur `hello world`, qui est codée en URL.

Vous trouvez ci-dessous un exemple présentant à quoi pourrait ressembler le code pour la page :

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
          return "p1=v1&p2=v2&p3=hello%20world";
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

Cet exemple envoie les données suivantes dans le bord de mbox :

* p1=v1
* p2=v2
* p3=hello world

## Tableau

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 
```

Il n’est pas nécessaire que les valeurs soient encodées en URL. Par exemple, si une valeur comporte un espace, il n’est pas nécessaire d’encoder l’espace.

Cet exemple envoie les données suivantes dans le bord de mbox :

* a=1
* b=2
* c=hello world

## JSON

JSON est un moyen puissant de transférer des paramètres. Target utilise les clés d’objet JSON pour aplanir des structures compliquées en simples paramètres.

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 
```

Il n’est pas nécessaire que les valeurs soient encodées en URL. Par exemple, « San Francisco » ne nécessite pas d’espace pour être encodé. Un espace suffit.

Cet exemple envoie les données suivantes dans le bord de mbox :

* a=1
* b=2
* `profile.memberStatus`=Gold
* `profile.country.city`=San Francisco
