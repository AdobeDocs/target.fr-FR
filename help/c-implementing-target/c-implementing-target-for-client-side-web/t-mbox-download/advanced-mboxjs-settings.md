---
keywords: paramètres mbox.js avancés;client;domaine du serveur;x-domaine;niveau de compression;prise en charge de l’ID de session client;secureOnly;prise en charge de l’ID de PC client;transmettre la page;URL référente;niveau de trafic;durée du trafic;corps de la fonction mboxParameters();corps de la fonction mboxSupported();corps de la fonction mboxCookieDomain();code JavaScript supplémentaire;module externe SiteCatalyst;obtenir mbox.js sous la forme d’un fichier JavaScript à extraction automatique;scintillement;masquage du corps;masquer le corps
description: Découvrez l’implémentation héritée du fichier mbox.js d’Adobe Target. Migration vers le Adobe Experience Platform Web SDK (AEP Web SDK) ou vers la dernière version d’at.js.
title: Comment configurer la bibliothèque mbox.js de Cible ?
feature: at.js
role: Developer
exl-id: 17821e60-2692-49af-a225-764bd1b6aec1
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 71%

---

# Configuration de mbox.js

Informations relatives à la définition de plusieurs paramètres sur la page des paramètres mbox.js.

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : A compter du 31 mars 2021, la bibliothèque mbox.js  [!DNL Adobe Target] ne sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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
