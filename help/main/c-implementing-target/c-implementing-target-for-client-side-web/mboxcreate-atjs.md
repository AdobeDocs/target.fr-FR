---
keywords: mboxCreate;mboxcreate;mbox create;at.js;fonctions;fonction
description: Utilisation de la fonction mboxCreate() pour l’Adobe [!DNL Target] Bibliothèque JavaScript at.js pour appliquer les offres au DIV le plus proche avec le nom de classe mboxDefault . (at.js 1.x)
title: Comment utiliser la fonction mboxCreate() ?
feature: at.js
role: Developer
exl-id: 821ad97a-345a-4e56-9be6-ab1c7d3a651d
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 76%

---

# mboxCreate(mbox,params) - at.js 1.x

Exécute une requête et applique l’offre au DIV le plus proche avec le nom de la classe mboxDefault.

>[!NOTE]
>
>Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x.

Cette fonction est intégrée à [!DNL at.js] pour faciliter principalement la transition [!DNL mbox.js] (désormais obsolète) en [!DNL at.js]. `adobe.target.getOffer()`, `adobe.target.applyOffer()` ou la directive angulaire sont de nouvelles options de remplacement de `mboxCreate()`.

## Exemple

```javascript
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Remarques

La fonction `mboxCreate()` utilise désormais le point de terminaison « json » à la place du point de terminaison standard et est déclenchée de manière asynchrone. Pour cette raison :

* [Le débogage](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/target-debugging-atjs/) est légèrement différent.
* Évitez du code d’offre qui requiert des appels de blocage synchrones,

   comme des offres qui définissent des variables JavaScript qui sont utilisées par le code du site ou d’autres mbox qui sont ajoutées ultérieurement à la page.

* Veillez à disposer d’un élément `<div class="mboxDefault"></div>`avant d’appeler `mboxCreate()`, car [!DNL at.js] ne l’ajoute pas automatiquement.

* Les fonctions `mboxCreate()` vides en haut de page ne sont pas recommandées en tant mbox globale.

   La mbox globale auto créée dans [!DNL at.js] est une meilleure solution, car elle est déclenchée à partir de `<head>`&lt; > et peut renvoyer du contenu plus tôt.
