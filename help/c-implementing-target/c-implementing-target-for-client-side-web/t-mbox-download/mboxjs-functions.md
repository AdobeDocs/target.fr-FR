---
description: Liste des fonctions de mbox.js à utiliser lors d’une implémentation avec mbox.js.
keywords: fonctions de mbox
seo-description: Liste des fonctions de mbox.js à utiliser lors d’une implémentation avec mbox.js.
seo-title: Fonctions de mbox.js
solution: Target
title: Fonctions de mbox.js
uuid: f503bc44-a664-4d09-82dc-80a1198ad9d0
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Fonctions de mbox.js{#mbox-js-functions}

Liste des fonctions de mbox.js à utiliser lors d’une implémentation avec mbox.js.

>[!NOTE]
>
>Si vous utilisez [!DNL at.js], ces méthodes ne s’appliquent pas.

| Méthode | Remarques |
|--- |--- |
| `mbox.getName()` |
| `mbox.getURL()` |
| `mbox.getDiv()` | Renvoie la balise div associée à la mbox (contenant le contenu par défaut ou une offre) |
| `mbox.getParameters()` | Un tableau de paramètres avec deux champs, nom et valeur |
| `mbox.setOnError()` | Exemple :<br>`mbox.setOnError(function() { alert(this.getName() +" had error"});` |
| `mbox.setMessage(message)` | Vous pouvez afficher le message dans la fenêtre de débogage. |
| `mboxCurrent.activate()` |
| `mboxCurrent.cancelTimeout()` |
| `mboxCurrent.finalize()` |
| `mboxCurrent.getDefaultDiv()` |
| `mboxCurrent.getDiv()` | Renvoie la balise div associée à la mbox (contenant le contenu par défaut ou une offre) |
| `mboxCurrent.getEventTimes()` |
| `mboxCurrent.getFetcher()` |
| `mboxCurrent.getId()` |
| `mboxCurrent.getImportName()` |
| `mboxCurrent.getName()` |
| `mboxCurrent.getOffer()` |
| `mboxCurrent.getParameters()` | Un tableau de paramètres avec deux champs : nom et valeur. |
| `mboxCurrent.getURL()` |
| `mboxCurrent.getURLBuilder()` |
| `mboxCurrent.hide()` |
| `mboxCurrent.isActivated`() |
| `mboxCurrent.load()` |
| `mboxCurrent.loaded()` |
| `mboxCurrent.setEventTime()` |
| `mboxCurrent.setFetcher()` |
| `mboxCurrent.setMessage()` |
| `mboxCurrent.setMessage(message)` | Affiche le message dans la fenêtre de débogage. |
| `mboxCurrent.setOffer()` |
| `mboxCurrent.setOnError()` | Exemple :<br>`mboxCurrent.setOnError(function(){ alert(this.getName() +" had error"});` |
| `mboxCurrent.setOnLoad()` | Exemple :<br>`mboxCurrent.setOnLoad(function(){alert(this.getName()+" loaded")});` |
| `mboxCurrent.show()` |
| `mboxCurrent.showContent()` |
| `mboxFactoryDefault.addOnLoad(action)` | L’action est appelée au chargement de la page. |
| `mboxFactoryDefault.getMboxes().each()` | Exemple :<br>`mboxFactoryDefault.getMboxes().each(function() { alert(mbox.getName()) };` |
| `mboxFactoryDefault.getMboxes().length()` |
| `mboxFactoryDefault.getPageId()` |
| `mboxFactoryDefault.getPCId().getId()` |
| `mboxFactoryDefault.getSessionId().getId()` |
| `mboxFactories.get('default').getSessionId()​.forceId("1276011116668");` |
| `mboxFactories.get('default').getPCId()​.forceId("1276011116668");` |
| `mboxFactoryDefault.create()` |
| `mboxFactoryDefault.disable()` |
| `mboxFactoryDefault.enable()` |
| `mboxFactoryDefault.get()` |
| `mboxFactoryDefault.getCookieManager()` |
| `mboxFactoryDefault.getDisableReason()` |
| `mboxFactoryDefault.getEllapsedTime()` |
| `mboxFactoryDefault.getEllapsedTimeUntil()` |
| `mboxFactoryDefault.getMboxes()` | Renvoie un `mboxList`. |
| `mboxFactoryDefault.getSignaler()` |
| `mboxFactoryDefault.getURLBuilder()` |
| `mboxFactoryDefault.isAdmin()` |
| `mboxFactoryDefault.isDomLoaded()` |
| `mboxFactoryDefault.isEnabled()` |
| `mboxFactoryDefault.isSupported()` |
| `mboxFactoryDefault.limitTraffic()` |
| `mboxFactoryDefault.update()` |
| `mboxFactoryDefault.getCookieManager()​.getCookie("name")//!= null) {` |
| `mboxFactoryDefault.getCookieManager()​.setCookie(_name,_value, _duration);` |