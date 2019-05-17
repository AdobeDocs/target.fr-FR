---
description: Liste des fonctions pouvant être utilisées avec at.js.
keywords: adobe.target.notification;élément;sélecteur;notification;extension
seo-description: Liste des fonctions pouvant être utilisées avec la bibliothèque JavaScript at.js dans Adobe Target.
seo-title: Fonctions d’Adobe Target at.js
solution: Target
subtopic: Prise en main
title: Fonctions d’at.js
topic: Standard
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Fonctions d’at.js{#at-js-functions}

Liste des fonctions pouvant être utilisées avec la bibliothèque JavaScript d’Adobe Target at.js. Cliquez sur les liens de la colonne Fonction pour plus d&#39;informations et d&#39;exemples.

| Fonction | Détails |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | Cette fonction déclenche une demande pour obtenir une offre Target. Utilisez avec `adobe.target.applyOffer()` pour traiter la réponse ou utilisez votre propre gestion de succès. |
| [adobe. target. getoffers (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at. js 2. x) | Cette fonction permet de récupérer plusieurs offres en transmettant plusieurs mbox. De plus, plusieurs offres peuvent être extraites pour toutes les vues des activités actives.<br>**Remarque :** Cette fonction a été introduite avec at. js 2. x. Cette fonction n&#39;est pas disponible pour at. js version 1.*x*. |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | Cette fonction permet d’appliquer le contenu de la réponse. |
| [adobe. target. applyoffers (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at. js 2. x) | Cette fonction vous permet d&#39;appliquer plusieurs offres récupérées par adobe. target. getoffers ().<br>**Remarque :** Cette fonction a été introduite avec at. js 2. x. Cette fonction n&#39;est pas disponible pour at. js version 1.*x*. |
| [adobe. target. triggerview (viewname, options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at. js 2. x) | Cette fonction peut être appelée à chaque chargement d’une nouvelle page ou lorsqu’un composant fait l&#39;objet d&#39;un nouveau rendu sur une page.<br> Cette fonction doit être implémentée pour les applications d&#39;une seule page (SPAS) afin d&#39;utiliser le compositeur d&#39;expérience visuelle pour créer des activités de tests A/B et de ciblage d&#39;expérience. |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | Cette fonction déclenche une demande pour signaler les actions de l’utilisateur, telles que les clics et les conversions. Elle ne déclenche pas la diffusion d’activités dans le cadre de la réponse. |
| [Mboxcreate (mbox, params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at. js 1. x) | Exécute une requête et applique l’offre au DIV le plus proche avec le nom de la classe mboxDefault.<br>**Remarque :** Cette fonction est disponible pour at. js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version at. js 2. x. Cette fonction renvoie le contenu par défaut s&#39;il est utilisé avec at. js 2. x. |
| [Mboxdefine (options) et mboxupdate (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at. js 1. x) | Définissent et mettent à jour une mbox.<br>**Remarque :** Cette fonction est disponible pour at. js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version at. js 2. x. Cette fonction renvoie le contenu par défaut s&#39;il est utilisé avec at. js 2. x. |
| [Targetglobalsettings (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Vous pouvez remplacer les paramètres dans la bibliothèque at. js plutôt que `targetGlobalSettings()`de configurer les paramètres dans l&#39;interface utilisateur de Target Standard/Premium ou en utilisant des API REST.<ul><li>Fournisseurs de données : Ce paramètre permet aux clients de collecter des données auprès de fournisseurs de données tiers, tels que Demandbase, bluekai et les services personnalisés, et transfère les données à Target en tant que paramètres de mbox dans la demande de mbox globale.</li></ul> |
| [Targetpageparams (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | Cette méthode permet de joindre des paramètres à la mbox globale depuis l’extérieur du code de demande. |
| [Targetpageparamsall (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | Cette méthode permet de joindre des paramètres à toutes les mbox à l’extérieur du code de demande. |
| [Registerextension (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at. js 1. x) | Propose une méthode standard pour enregistrer une extension spécifique.<br>**Remarque :** Cette fonction est disponible pour at. js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version at. js 2. x. Cette fonction renvoie le contenu par défaut s&#39;il est utilisé avec at. js 2. x. |
| [événements personnalisés at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | Les événements personnalisés at. js indiquent quand une requête ou une offre de mbox réussit ou échoue. |
