---
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
description: La fonction JavaScript targetPageParams est utilisée pour transférer des paramètres à la mbox globale. Cela est nécessaire dans tout scénario où des informations de ciblage/contexte supplémentaires doivent être transmises à Adobe Target.
title: Transfert de paramètres à une mbox globale
feature: null
translation-type: tm+mt
source-git-commit: 5c7ab4af3d4290ef8fa53ed51ed1c2e8336e02f9
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 70%

---


# Transfert de paramètres à une mbox globale{#pass-parameters-to-a-global-mbox}

The JavaScript `targetPageParams` function is used to pass parameters to the global mbox in [!DNL Adobe Target]. Cette fonction est requise dans les scénarios où des informations supplémentaires de ciblage/contexte doivent être transférées dans [!DNL Target].

For example, in a [!DNL Recommendations] activity, use the parameters to represent the current product or category that is being viewed.

Le code permettant d’appeler la fonction JavaScript doit précéder la mbox globale sur la page, que la mbox globale soit déclenchée dans le cadre d’at.js ou soit incluse manuellement dans le code de page.

>[!NOTE]
>
>If you want to add parameters to all mboxes on the page, not just to the global mbox, use the [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) function.

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
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
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
* `profile.memberStatus`=Or
* `profile.country.city`=San Francisco