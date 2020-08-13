---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
description: Informations sur la fonction adobe.target.trackEvent(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
title: Informations sur la fonction adobe.target.trackEvent(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%

---


# adobe.target.trackEvent(options)

Cette fonction déclenche une demande pour signaler les actions de l’utilisateur, telles que les clics et les conversions. Elle ne déclenche pas la diffusion d’activités dans le cadre de la réponse.

Ces appels de mbox de suivi d’événement peuvent servir à définir des mesures dans les activités. Pour plus d’informations, voir [Mesures de succès](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) et [Suivi des conversions](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

Voici les détails de l’API :

| Clé | Type | Requis | Description |
|--- |--- |--- |--- |
| mbox | Chaîne | Oui | Nom de mbox |
| selector | Chaîne | Non | Sélecteurs CSS utilisés pour rechercher les éléments HTML. Les détecteurs d’événements sont attachés aux éléments trouvés.. |
| type | Chaîne | Non | Représente un type d’événement enregistré. Il peut s’agir d’événements HTML connus (click, mousedown, etc.) et d’événements HTML personnalisés. |
| preventDefault | Booléen | Non | Indique si `event.preventDefault()` () doit être utilisé dans le rappel des détecteurs d’événements. La valeur par défaut est false.<br>**Remarque :** Seuls `form[submit] and `par[clic] sont pris en charge. D’autres scénarios ne sont pas pris en charge pour des raisons de complexité et parce que le nombre de scénarios possibles est trop élevé. |
| params | Objet | Non | Paramètres mBox. Objet de paires clé-valeur qui possède la structure suivante :<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | Nombre | Non | Délai d’attente exprimé en secondes.<br>S’il n’est pas spécifié, la valeur par défaut est utilisée :<br>`...timeoutInSeconds: 0.15...}` |
| success | Fonction | Non | Fonction de rappel utilisée pour indiquer que l’événement a été signalé. |
| error | Fonction | Non | Fonction de rappel utilisée pour indiquer que l’événement n’a pas pu être signalé. |

## Exemple

```
<a href="https://asite.com">click me!</a> 
```

plus le code JavaScript pour affecter `trackEvent` :

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

Ou :

```
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