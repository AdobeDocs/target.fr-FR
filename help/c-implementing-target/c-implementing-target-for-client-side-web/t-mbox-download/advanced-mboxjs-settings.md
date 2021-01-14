---
keywords: advanced mbox.js settings;client;server domain;xdomain;compression level;client session id support;secureOnly;client pc id support;pass page;referring url;traffic level;traffic duration;mboxParameters() function body;mboxSupported() function body;mboxCookieDomain() function body;Extra JavaScript;SiteCatalyst plug-in;Get mbox.js as self-extracting JavaScript;flicker;body hiding;hide body
description: Informations relatives à la définition de plusieurs paramètres sur la page des paramètres mbox.js.
title: Configuration de mbox.js
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 91%

---


# Configuration de mbox.js

Informations relatives à la définition de plusieurs paramètres sur la page des paramètres mbox.js.

Les paramètres par défaut de la bibliothèque de fonctions [!DNL mbox.js] répondent aux besoins de la plupart des clients [!DNL Target].

Si nécessaire, consultez le représentant de votre compte afin de modifier les paramètres [!DNL mbox.js].

Les méthodes suivantes sont disponibles :

## Client

Code client pour votre compte.

Lors de l’affichage de [!UICONTROL Administration > Implémentation], le client en haut est le code client de votre compte.

## Expiration

Le délai d’attente de la requête Target a expiré.

Lors de l’affichage de [!UICONTROL Administration > Implémentation], le paramètre Délai d’expiration (secondes) correspond au délai d’expiration de la demande de Cible. Cette valeur est définie par défaut sur 15 secondes, mais nous vous recommandons de la régler sur une valeur comprise entre 2 et 5 secondes.

## XDomain

Détermine si le navigateur définit les cookies dans votre domaine (cookies propriétaires), le domaine de Target ou les deux.

La modification de ce paramètre a un impact sur mbox.js et at.js.

## Niveau de compression

Détermine le niveau de compression du fichier de bibliothèque mbox.js. Un niveau de compression plus élevé réduit la durée de chargement des pages.

## Corps de la fonction mboxParameters()

Renvoie des paramètres supplémentaires à transmettre à chaque appel de mbox.

Par exemple :

return &quot;test=123&quot;;

## Corps de la fonction mboxSupported()

Renvoie la valeur Faux pour exclure des utilisateurs spécifiques.

Par exemple :

return !navigator.userAgent.indexOf(’Safari’) != -1;

Les navigateurs suivants peuvent être acceptés ou exclus :

* IE 5.0 ou version supérieure (Windows)
* Netscape 5.0 ou version supérieure (Mac, Windows, Linux)
* Safari 1.2.4 ou version supérieure (Mac)
* Mozilla Firefox 1.0 ou version supérieure (Mac, Windows, Linux)

## Corps de la fonction mboxCookieDomain()

Renvoie une chaîne décrivant le domaine pour définir les cookies propriétaires.

Par exemple :

return &quot;YOUR-DOMAIN&quot;;

## Code JavaScript supplémentaire

Inclut les scripts JavaScript supplémentaires à exécuter sur chaque page.

## Module externe SiteCatalyst

Active le module externe Analytics Target.

S’il est activé, le module externe Analytics génère le code de module externe dans mbox.js. Ceci envoie les informations de balise Analytics aux serveurs Target sous forme d’une demande de mbox sur chaque page balisée avec Analytics.

Notez que le module externe Analytics doit toujours être référencé sur la page.

## secureOnly

Indique si mbox.js doit utiliser le protocole HTTPS seulement ou s’il peut permuter entre les protocoles HTTP et HTTPS en fonction du protocole de la page. Ce paramètre avancé est défini par défaut sur false.