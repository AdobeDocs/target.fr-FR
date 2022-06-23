---
keywords: at.js;fonctions;bibliothèque javascript
description: Affichez la liste des fonctions pouvant être utilisées avec les versions 1.x et 2.x de la bibliothèque JavaScript at.js dans Adobe Target.
title: Quelles fonctions puis-je utiliser avec at.js ?
feature: at.js
role: Developer
exl-id: a386e478-16f4-4bf6-9771-6b1e75f2e362
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 78%

---

# Fonctions d’at.js

Liste des fonctions pouvant être utilisées avec la bibliothèque JavaScript d’Adobe Target at.js. Cliquez sur les liens de la colonne Fonction pour plus d’informations et d’exemples.

| Fonction | Détails |
| --- | --- | 
| [adobe.target.getOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/) | Cette fonction déclenche une demande pour obtenir une offre Target. Utilisez avec `adobe.target.applyOffer()` pour traiter la réponse ou utilisez votre propre gestion de succès. |
| [adobe.target.getOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)<br>(at.js 2.x) | Cette fonction permet de récupérer plusieurs offres en transmettant plusieurs mbox. De plus, plusieurs offres peuvent être extraites pour toutes les vues des activités actives.<br>**Remarque :** cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*. |
| [adobe.target.applyOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/) | Cette fonction permet d’appliquer le contenu de la réponse. |
| [adobe.target.applyOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffers-atjs-2/)<br>(at.js 2.x) | Cette fonction vous permet d’appliquer plusieurs offres récupérées par adobe.target.getOffers().<br>**Remarque :** cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*. |
| [adobe.target.triggerView (viewName, options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/)<br>(at.js 2.x) | Cette fonction peut être appelée à chaque chargement d’une nouvelle page ou lorsqu’un composant fait l’objet d’un nouveau rendu sur une page.<br> Cette fonction doit être implémentée pour les applications monopages (SPA) afin d’utiliser le compositeur d’expérience visuelle (VEC) pour créer des activités de tests A/B et de ciblage d’expérience (XT). |
| [adobe.target.trackEvent(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-trackevent/) | Cette fonction déclenche une demande pour signaler les actions de l’utilisateur, telles que les clics et les conversions. Elle ne déclenche pas la diffusion d’activités dans le cadre de la réponse. |
| [mboxCreate(mbox,params)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxcreate-atjs/)<br>(at.js 1.x) | Exécute une requête et applique l’offre au DIV le plus proche avec le nom de la classe mboxDefault.<br>**Remarque :** Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x. |
| [mboxDefine(options) and mboxUpdate(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxdefine-mboxupdate-atjs-1x/)<br>(at.js 1.x) | Définissent et mettent à jour une mbox.<br>**Remarque :** Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x. |
| [targetGlobalSettings(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) | Vous pouvez remplacer les paramètres de la Bibliothèque at.js en utilisant `targetGlobalSettings()` au lieu de configurer les paramètres dans l’interface utilisateur de Target Standard / Premium, ou d’utiliser des API REST.<ul><li>Fournisseurs de données : ce paramètre permet aux clients de collecter des données auprès de fournisseurs de données tiers tels que Demandbase, BlueKai ou des services personnalisés, et de les transmettre à Target sous forme de paramètres mbox dans la requête globale mbox.</li></ul> |
| [targetPageParams(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparams/) | Cette méthode permet de joindre des paramètres à la mbox globale depuis l’extérieur du code de demande. |
| [targetPageParamsAll(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/) | Cette méthode permet de joindre des paramètres à toutes les mbox à l’extérieur du code de demande. |
| [registerExtension(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/registerextension-atjs-1x/)<br>(at.js 1.x) | Propose une méthode standard pour enregistrer une extension spécifique.<br>**Remarque :** Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x. |
| [événements personnalisés at.js](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/) | Les événements personnalisés at.js indiquent quand une requête ou une offre de mbox échoue ou réussit. |
| [adobe.target.sendNotifications(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-sendnotifications-atjs-21/)<br>(at.js 2.1.0) | Cette fonction envoie une notification à Target Edge lorsqu’une expérience est générée sans utiliser `adobe.target.applyOffer()` ou `adobe.target.applyOffers()`.<br>**Remarque** : Cette fonction a été introduite dans at.js 2.1.0 et sera disponible pour toutes les versions ultérieures à 2.1.0. |
