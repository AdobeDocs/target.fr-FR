---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
description: Informations sur la fonction adobe.target.trackEvent(options) pour la bibliothèque JavaScript at.js d’Adobe Target.
title: adobe.target.trackEvent(options)
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 78%

---


# adobe.target.trackEvent(options)

Cette fonction déclenche une demande pour signaler les actions de l’utilisateur, telles que les clics et les conversions. Elle ne déclenche pas la diffusion d’activités dans le cadre de la réponse.

Ces appels de mbox de suivi d’événement peuvent servir à définir des mesures dans les activités. Pour plus d’informations, voir [Mesures de succès](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) et [Suivi des conversions](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

Voici les détails de l’API :

| Clé | Type | Requis | Description |
|--- |--- |--- |--- |
| mbox | Chaîne | Oui | Mbox <br>**nameNote**: Si un appel trackEvent() est déclenché avec un nom de mbox qui s’est déjà déclenché sur la page, le SDID de trackEvent() est réinitialisé et sera différent des appels de Cible sur la page. Cependant, le déclenchement d’un appel trackEvent() avec un nom de mbox différent permet de conserver le SDID de l’appel trackEvent() cohérent avec les appels Page Load Request/triggerView() sur la page. |
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