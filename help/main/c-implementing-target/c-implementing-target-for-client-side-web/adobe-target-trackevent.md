---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;fonctions;fonction;preventDefault;preventdefault;prevent default
description: Utilisez la fonction adobe.target.trackEvent() pour l’Adobe [!DNL Target] bibliothèque JavaScript at.js pour déclencher une requête afin de signaler les actions de l’utilisateur, telles que les clics et les conversions sur votre site.
title: Comment utiliser la fonction adobe.target.trackEvent() ?
feature: at.js
role: Developer
exl-id: 36005236-ce18-4845-b4fb-e52056018bc7
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 64%

---

# adobe.target.trackEvent(options)

Cette fonction déclenche une demande pour signaler les actions de l’utilisateur, telles que les clics et les conversions. Elle ne déclenche pas la diffusion d’activités dans le cadre de la réponse.

Ces appels de mbox de suivi d’événement peuvent servir à définir des mesures dans les activités. Pour plus d’informations, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) et [Suivi des conversions](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}.

Voici les détails de l’API :

| Clé | Type | Requis | Description |
|--- |--- |--- |--- |
| mbox | Chaîne | Oui | Nom de mbox <br>**Remarque**: Si un appel trackEvent() est déclenché avec un nom de mbox qui a déjà été déclenché sur la page, le SDID de trackEvent() est réinitialisé et sera différent des appels Target sur la page. Toutefois, le déclenchement d’un appel trackEvent() avec un nom de mbox différent conserve le SDID de l’appel trackEvent() cohérent avec les appels de requête/triggerView() de chargement de page sur la page. |
| selector | Chaîne | Non | Sélecteurs CSS utilisés pour rechercher les éléments HTML. Les détecteurs d’événements sont attachés aux éléments trouvés.. |
| type | Chaîne | Non | Représente un type d’événement enregistré. Il peut s’agir d’événements HTML connus (click, mousedown, etc.) et d’événements HTML personnalisés. |
| preventDefault | Booléen | Non | Indique si `event.preventDefault()` () doit être utilisé dans le rappel des détecteurs d’événements. La valeur par défaut est false.<br>**Remarque**: Uniquement `form[submit]` et `a[click]` sont prises en charge. D’autres scénarios ne sont pas pris en charge pour des raisons de complexité et parce que le nombre de scénarios possibles est trop élevé. |
| params | Objet | Non | Paramètres mBox. Objet de paires clé-valeur qui possède la structure suivante :<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | Nombre | Non | Délai d’attente exprimé en secondes.<br>S’il n’est pas spécifié, la valeur par défaut est utilisée :<br>`...timeoutInSeconds: 0.15...}` |
| success | Fonction | Non | Fonction de rappel utilisée pour indiquer que l’événement a été signalé. |
| error | Fonction | Non | Fonction de rappel utilisée pour indiquer que l’événement n’a pas pu être signalé. |

## Exemple

```javascript
<a href="https://asite.com">click me!</a> 
```

plus le code JavaScript pour affecter `trackEvent` :

```javascript
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

Ou :

```javascript
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>Remarque : Si les champs obligatoires ne sont pas définis, aucune demande n’est exécutée et une erreur est générée.
