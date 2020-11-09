---
keywords: mboxCreate;mboxcreate;mbox create;at.js;functions;function
description: Informations sur la fonction mboxCreate(mbox,params) pour la bibliothèque JavaScript at.js d’Adobe Target.
title: mboxCreate(mbox,params) - at.js 1.x
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

Exécute une requête et applique l’offre au DIV le plus proche avec le nom de la classe mboxDefault.

>[!NOTE]
>
>Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x.

Cette fonction est intégrée à [!DNL at.js] pour faciliter principalement la transition de [!DNL mbox.js] vers [!DNL at.js]. `adobe.target.getOffer()`, `adobe.target.applyOffer()` ou la directive angulaire sont de nouvelles options de remplacement de `mboxCreate()`.

## Exemple

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Remarques

La fonction `mboxCreate()` utilise désormais le point de terminaison « json » à la place du point de terminaison standard et est déclenchée de manière asynchrone. Pour cette raison :

* [Le débogage](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) est légèrement différent.
* Évitez du code d’offre qui requiert des appels de blocage synchrones,

   comme des offres qui définissent des variables JavaScript qui sont utilisées par le code du site ou d’autres mbox qui sont ajoutées ultérieurement à la page.

* Veillez à disposer d’un élément `<div class="mboxDefault"></div>`avant d’appeler `mboxCreate()`, car [!DNL at.js] ne l’ajoute pas automatiquement.

* Les fonctions `mboxCreate()` vides en haut de page ne sont pas recommandées en tant mbox globale.

   La mbox globale auto créée dans [!DNL at.js] est une meilleure solution, car elle est déclenchée à partir de `<head>`&lt; > et peut renvoyer du contenu plus tôt.