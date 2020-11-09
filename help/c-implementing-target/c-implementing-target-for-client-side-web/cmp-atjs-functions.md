---
keywords: at.js;functions;javascript library
description: Liste des fonctions pouvant être utilisées avec la bibliothèque JavaScript at.js dans Adobe Target.
title: Fonctions d’Adobe Target at.js
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 100%

---


# Fonctions d’at.js{#at-js-functions}

Liste des fonctions pouvant être utilisées avec la bibliothèque JavaScript d’Adobe Target at.js. Cliquez sur les liens de la colonne Fonction pour plus d’informations et d’exemples.

| Fonction | Détails |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | Cette fonction déclenche une demande pour obtenir une offre Target. Utilisez avec `adobe.target.applyOffer()` pour traiter la réponse ou utilisez votre propre gestion de succès. |
| [adobe.target.getOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at.js 2.x) | Cette fonction permet de récupérer plusieurs offres en transmettant plusieurs mbox. De plus, plusieurs offres peuvent être extraites pour toutes les vues des activités actives.<br>**Remarque :** cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*. |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | Cette fonction permet d’appliquer le contenu de la réponse. |
| [adobe.target.applyOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at.js 2.x) | Cette fonction vous permet d’appliquer plusieurs offres récupérées par adobe.target.getOffers().<br>**Remarque :** cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*. |
| [adobe.target.triggerView (viewName, options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at.js 2.x) | Cette fonction peut être appelée à chaque chargement d’une nouvelle page ou lorsqu’un composant fait l’objet d’un nouveau rendu sur une page.<br> Cette fonction doit être implémentée pour les applications monopages (SPA) afin d’utiliser le compositeur d’expérience visuelle (VEC) pour créer des activités de tests A/B et de ciblage d’expérience (XT). |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | Cette fonction déclenche une demande pour signaler les actions de l’utilisateur, telles que les clics et les conversions. Elle ne déclenche pas la diffusion d’activités dans le cadre de la réponse. |
| [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at.js 1.x) | Exécute une requête et applique l’offre au DIV le plus proche avec le nom de la classe mboxDefault.<br>**Remarque :** Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x. |
| [mboxDefine(options) and mboxUpdate(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at.js 1.x) | Définissent et mettent à jour une mbox.<br>**Remarque :** Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x. |
| [targetGlobalSettings(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Vous pouvez remplacer les paramètres de la Bibliothèque at.js en utilisant `targetGlobalSettings()` au lieu de configurer les paramètres dans l’interface utilisateur de Target Standard / Premium, ou d’utiliser des API REST.<ul><li>Fournisseurs de données : ce paramètre permet aux clients de collecter des données auprès de fournisseurs de données tiers tels que Demandbase, BlueKai ou des services personnalisés, et de les transmettre à Target sous forme de paramètres mbox dans la requête globale mbox.</li></ul> |
| [targetPageParams(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | Cette méthode permet de joindre des paramètres à la mbox globale depuis l’extérieur du code de demande. |
| [targetPageParamsAll(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | Cette méthode permet de joindre des paramètres à toutes les mbox à l’extérieur du code de demande. |
| [registerExtension(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at.js 1.x) | Propose une méthode standard pour enregistrer une extension spécifique.<br>**Remarque :** Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x. |
| [événements personnalisés at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | Les événements personnalisés at.js indiquent quand une requête ou une offre de mbox échoue ou réussit. |
| [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)<br>(at.js 2.1.0) | Cette fonction envoie une notification à Target Edge lorsqu’une expérience est générée sans utiliser `adobe.target.applyOffer()` ou `adobe.target.applyOffers()`.<br>**Remarque** : Cette fonction a été introduite dans at.js 2.1.0 et sera disponible pour toutes les versions ultérieures à 2.1.0. |

