---
keywords: paramètres mbox.js avancés;client;domaine du serveur;x-domaine;niveau de compression;prise en charge de l’ID de session client;secureOnly;prise en charge de l’ID de PC client;transmettre la page;URL référente;niveau de trafic;durée du trafic;corps de la fonction mboxParameters();corps de la fonction mboxSupported();corps de la fonction mboxCookieDomain();code JavaScript supplémentaire;module externe SiteCatalyst;obtenir mbox.js sous la forme d’un fichier JavaScript à extraction automatique;scintillement;masquage du corps;masquer le corps
description: Informations relatives à la définition de plusieurs paramètres sur la page des paramètres mbox.js.
title: Configuration de mbox.js
uuid: e79c7af7-f8bd-4e2b-8e67-b04eddf0c65d
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Configuration de mbox.js{#configure-mbox-js}

Informations relatives à la définition de plusieurs paramètres sur la page des paramètres mbox.js.

Les paramètres par défaut de la bibliothèque de fonctions [!DNL mbox.js] répondent aux besoins de la plupart des clients [!DNL Target].

Si nécessaire, consultez le représentant de votre compte afin de modifier les paramètres [!DNL mbox.js].

Les méthodes suivantes sont disponibles :

## Client

Code client pour votre compte.

Lorsque vous affichez l’écran [!UICONTROL Configuration &gt; Mise en œuvre &gt; Modifier les paramètres de mbox.js], le client dans la partie supérieure est le code client de votre compte.

## Expiration

Le délai d’attente de la requête Target a expiré.

Sous [!UICONTROL Configuration &gt; Implémentation &gt; Modifier les paramètres mbox.js], le niveau de compression après expiration correspond au délai d’attente de votre requête Target. Cette valeur est définie par défaut sur 15 secondes, mais nous vous recommandons de la régler sur une valeur comprise entre 2 et 5 secondes.

## XDomain

Détermine si le navigateur définit les cookies dans votre domaine (cookies propriétaires), le domaine de Target ou les deux.

La modification de ce paramètre a un impact sur mbox.js et at.js.

## Niveau de compression

Détermine le niveau de compression du fichier de bibliothèque mbox.js. Un niveau de compression plus élevé réduit la durée de chargement des pages.

## Corps de la fonction mboxParameters()

Renvoie des paramètres supplémentaires à transmettre à chaque appel de mbox.

Par exemple :

return "test=123";

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

return "YOUR-DOMAIN";

## Code JavaScript supplémentaire

Inclut les scripts JavaScript supplémentaires à exécuter sur chaque page.

## Module externe SiteCatalyst

Active le module externe Analytics Target.

S’il est activé, le module externe Analytics génère le code de module externe dans mbox.js. Ceci envoie les informations de balise Analytics aux serveurs Target sous forme d’une demande de mbox sur chaque page balisée avec Analytics.

Notez que le module externe Analytics doit toujours être référencé sur la page.

## secureOnly

Indique si mbox.js doit utiliser le protocole HTTPS seulement ou s’il peut permuter entre les protocoles HTTP et HTTPS en fonction du protocole de la page. Ce paramètre avancé est défini par défaut sur false.