---
keywords: registerExtension;registerextension;register extension;at.js;fonctions;fonction;clientCode;serverDomain;globalMboxName;globalMboxAutoCreate;délai d’expiration
description: Utilisation de la fonction registerExtension() pour l’Adobe [!DNL Target] Bibliothèque JavaScript at.js pour enregistrer une extension spécifique. (at.js 1.x)
title: Comment utiliser la fonction registerExtension() ?
feature: at.js
role: Developer
exl-id: 7f0898b4-ddd5-425c-99dc-94f9b30f8ba7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 90%

---

# registerExtension () - at.js 1.x

Propose une méthode standard pour enregistrer une extension spécifique.

>[!NOTE]
>
>Cette fonction est disponible pour at.js versions 1.*x* uniquement. Cette fonction a été abandonnée avec la version d’at.js 2.x. Cette fonction renvoie le contenu par défaut s’il est utilisé avec at.js 2.x.

Le paramètre options est obligatoire et possède la structure suivante :

| Clé | Type | Requis | Description |
|--- |--- |--- |--- |
| name | Chaîne | Oui | Nom de l’extension. |
| modules | Tableau[Chaîne] | Oui | Tableau de chaînes représentant les noms de modules demandés. |
| s’inscrire | Fonction | Oui | Fonction utilisée pour initialiser et créer l’extension. Cette fonction reçoit les arguments sur la base du tableau de modules. |

Remarques :

* Si l’un des paramètres n’est pas fourni, une exception est déclenchée.
* Si le tableau de modules est vide, une exception est déclenchée.

Pour en savoir plus et consulter des exemples sur la manière d’utiliser `registerExtension`, visitez la page [Extensions Target atjs d’Adobe Experience Cloud](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions) sur GitHub.

## Méthodes de module Paramètres {#section_8501CDD4B0624FA2B10532C98C5F4328}

| Clé | Type | Description |
|--- |--- |--- |
| clientCode | Chaîne | Code client |
| serverDomain | Chaîne | Domaine du serveur Edge |
| globalMboxName | Chaîne | Nom de la mbox globale Target |
| globalMboxAutoCreate | Booléen | Indique si la création automatique est activée ou non. |
| timeout | Nombre | Délai d’attente de requête |

## Méthodes de module Enregistreur {#section_10AF62B49AEF48F981E950D26E176138}

| Clé | Type | Description |
|--- |--- |--- |
| log | Fonction | Enregistre la liste de variables des arguments dans la console du navigateur, le cas échéant. Cette fonction est activée uniquement lorsque `mboxDebug=true` est passé à l’URL. |
| error | Fonction | Enregistre la liste de variables des arguments dans la console du navigateur. Cette fonction est activée uniquement en cas d’erreurs importantes, comme le délai d’expiration réseau atteint, un nœud HTML introuvable, etc. |
