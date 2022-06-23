---
keywords: at.js;navigateur user agent;user agent;client hints;user-agent
description: Découvrez comment  [!DNL Adobe Target]  utilise user-agent et les Client Hints pour qualifier les visiteurs pour la segmentation et la personnalisation.
title: User agent et Client Hints
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: 3c64945eb1898457a9d6a3e7bbfa64420bf1250a
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 96%

---

# User-agent et Client Hints

[!DNL Adobe Target] utilise user-agent pour qualifier les visiteurs pour la segmentation et la personnalisation.

>[!NOTE]
>
>Les informations contenues dans cet article s’appliquent à [at.js version 2.9.0](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) (ou ultérieure).


Chaque fois qu’un navigateur web envoie une requête à un serveur, des informations sur le navigateur et l’environnement dans lequel il s’exécute sont incluses dans l’en-tête de la requête. Depuis les tous premiers jours d’Internet, ces données se sont agglomérées en une seule chaîne appelée user-agent.

Le texte suivant est un échantillon user-agent d’un ordinateur Mac OS X utilisant un navigateur Safari :

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

À partir de ce user-agent, le serveur recevant la demande peut discerner les informations suivantes à propos du navigateur et du système d’exploitation :

| Informations | Détails |
| --- | --- |
| Nom du logiciel | Chrome |
| Version du logiciel | 101 |
| Version complète du logiciel | 101.0.4951.41 |
| Nom du moteur de rendu | AppleWebKit |
| Version du moteur de rendu | 537.36 |
| Système d’exploitation | Android |
| Version du système d’exploitation | Android 12 (Snow Cone) |
| Périphérique | SM-S908E (Samsung Galaxy S22 Ultra) |

Au fil des ans, la quantité d’informations sur le navigateur et l’appareil utilisé incluses dans la chaîne user-agent a augmenté.

## Cas d’utilisation de User-Agent

Les User-agents ont longtemps été utilisés pour fournir aux équipes de marketing et de développement des informations importantes sur la façon dont les navigateurs, les systèmes d’exploitation et les appareils affichent le contenu du site, et sur la manière dont les utilisateurs interagissent avec les sites web. Les User-agents sont également utilisés pour bloquer les spams et filtrer les bots qui explorent les sites à diverses fins supplémentaires.

Cependant, au cours des dernières années, certains propriétaires de site et vendeurs marketing ont utilisé user-agent avec d’autres informations incluses dans les en-têtes de requête pour créer des empreintes numériques qui peuvent être utilisées pour identifier les utilisateurs à leur insu. Malgré l’objectif important que remplit user-agent pour les propriétaires de site, les développeurs de navigateur ont décidé de modifier la manière dont les user-agents fonctionnent afin de limiter les éventuels problèmes de confidentialité pour les visiteurs du site.

User-Agent Client Hints est la solution apportée par les développeurs. Les Client Hints permettent toujours aux sites de collecter les informations nécessaires sur le navigateur, le système d’exploitation et l’appareil utilisé, tout en offrant une protection accrue contre les méthodes de suivi secrètes, telles que l’empreinte numérique.

## Client hints

Les User-Agent Client Hints permettent aux propriétaires de site web d’accéder aux mêmes informations que celles disponibles dans user-agent, mais de manière plus respectueuse de la vie privée. Lorsque les navigateurs modernes envoient un user-agent à un serveur web, user-agent complet est envoyé à chaque requête, même si ce dernier n’est pas requis. Les Client Hints, en revanche, appliquent un modèle dans lequel le serveur doit demander au navigateur les informations supplémentaires qu’il souhaite connaître sur le client. Lors de la réception de cette requête, le navigateur peut appliquer ses propres politiques ou sa propre configuration utilisateur pour déterminer les données renvoyées. Au lieu d’exposer l’ensemble de user-agent par défaut sur toutes les requêtes, l’accès est désormais géré de manière explicite et auditable.

User-Agent Client Hints est disponible dans Chrome depuis la version 89. Les versions récentes des navigateurs Chromium, tels que Microsoft Edge, Opera, Brave, Chrome Android, Opera Android et Samsung Internet prennent également en charge l’API Client Hints.

Les Client Hints contenus dans les en-têtes de la première requête envoyée par le navigateur à un serveur web contiennent la marque du navigateur, la version majeure du navigateur et un indicateur indiquant si le client est un appareil mobile. Chaque élément de données possède sa propre valeur d’en-tête, plutôt que de les regrouper en une seule chaîne user-agent, comme illustré dans l’échantillon suivant :

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

L’échantillon suivant est user-agent pour le même navigateur :

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

Bien que les informations soient similaires, la première requête au serveur inclue des Client Hints qui contiennent uniquement un sous-ensemble de ce qui est disponible dans la chaîne user-agent. La requête ne contient pas: l’architecture du système d’exploitation, la version complète du système d’exploitation, le nom du moteur de rendu, la version du moteur de rendu et la version complète du navigateur. Cependant, pour les prochaines requêtes, l’API Client Hints permet aux serveurs web de demander des détails supplémentaires à entropie élevée sur l’appareil. Lorsque ces valeurs à entropie élevée sont demandées, en fonction de la politique du navigateur ou des paramètres utilisateur, la réponse du navigateur peut inclure ces informations.

L’exemple suivant est un objet JSON renvoyé par l’API Client Hints lorsque des valeurs à entropie élevée sont demandées :

```
{ 

    "architecture":"x86", 
    "bitness":"64", 
    "brands":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100" 
        } 
    ], 
    "fullVersionList":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99.0.0.0" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100.0.4896.127" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100.0.4896.127" 
        } 
    ], 
    "mobile":false, 
    "model":"", 
    "platformVersion":"12.2.1" 
} 
```

Les valeurs à entropie élevée incluent plusieurs informations supplémentaires qui ne sont pas disponibles dans les informations par défaut du Client Hints. Le tableau suivant détaille les données disponibles dans la requête par défaut par rapport à celles disponibles dans les informations User-Agent Client Hints à entropie élevée.

| En-tête HTTP | JavaScript | User-agent | Client hint | Client hint à entropie élevée |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | brands | Oui | Oui | Non |
| Sec-CH-UA-Platform | plateforme | Oui | Oui | Non |
| Sec-CH-UA-Mobile | mobile | Oui | Oui | Non |
| Sec-CH-UA-Platform-Version | platformVersion | Oui | Non | Oui |
| Sec-CH-UA-Arch | architecture | Oui | Non | Oui |
| Sec-CH-UA-Model | model | Oui | Non | Oui |
| Sec-CH-UA-Bitness | Bitness | Oui | Non | Oui |
| Sec-CH-UA-Full-Version-List | fullVersionList | Oui | Non | Oui |

## Migration vers Client Hints

Actuellement, les navigateurs basés sur Chromium continuent d’envoyer user-agent
 avec les Client Hints dans les en-têtes des requêtes effectuées aux serveurs web. Toutefois, la quantité de données contenue dans la chaîne user-agent sera réduite entre avril 2022 et février 2023. D’autres navigateurs, tels que Safari et Firefox, continueront à utiliser la chaîne user-agent, mais ils réduiront eux aussi la quantité d’informations qu’elles contiennent.

## Cas d’utilisation de [!DNL Target] nécessitant des Client Hints

Les cas d’utilisation suivants dans Target nécessitent des Client Hints :

### Attributs d’audience

Si vous utilisez les audiences [!DNL Target] et utilisez l’un des attributs d’audience suivants, [!DNL Target] requière que la segmentation correcte soit effectuée par les Client Hints :

* Navigateur
* Système d’exploitation
* Mobile

### Scripts de profil

Si vous utilisez des scripts de profil et référencez l’attribut `user.browser` (qui fait référence à user-agent), vous devrez peut-être mettre à jour le script de profil pour vérifier également un ou plusieurs Client Hints. Vous pouvez accéder à l’un des Client Hints à l’aide de la fonction `user.clientHint('sec-ch-ua-xxxxx')`. Le nom de l’en-tête du Client Hint doit être en minuscules.

L’exemple suivant montre comment détecter correctement un système d’exploitation Windows dans un script de profil :

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

Les sections suivantes présentent les en-têtes de Client Hints et la sémantique d’utilisation du script de profil correspondant.

#### Sec-CH-UA

Entropie : faible
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA?lang=fr) {target=_blank}
Attribut d’audience : navigateur
Utilisation du script du profil : `user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

Entropie : élevée
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch?lang=fr) {target=_blank}
Attribut d’audience : exposé aux utilisateurs via des scripts de profil.
Utilisation du script de profil : `user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

Entropie : élevée
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness?lang=fr) {target=_blank}
Attribut d’audience : exposé aux utilisateurs via des scripts de profil.
Utilisation du script de profil : `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

Entropie : élevée
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List?lang=fr) {target=_blank}
Attribut d’audience : navigateur
Utilisation du script du profil : `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

Entropie : faible
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile?lang=fr) {target=_blank}
Attribut d’audience : mobile
Utilisation du script du profil : `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

Entropie : élevée
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model?lang=fr) {target=_blank}
Attribut d’audience : mobile
Utilisation du script du profil : `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

Entropie : faible
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform?lang=fr) {target=_blank}
Attribut d’audience : système d’exploitation
Utilisation du script du profil : `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

Entropie : élevée
Documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version?lang=fr) {target=_blank}
Attribut d’audience : exposé aux utilisateurs via des scripts de profil.
Utilisation du script de profil : `user.clientHint('sec-ch-ua-platform-version')`

## Comment transmettre des Client Hints à [!DNL Adobe Target]

Les sections suivantes contiennent des informations supplémentaires sur la manière de transmettre des Client Hints, en fonction de votre implémentation de [!DNL Target].

### at.js version 2.9.0 (ou ultérieure)

À compter d’at.js version 2.9.0, les User Agent Client Hints seront collectés automatiquement à partir du navigateur et envoyés à [!DNL Target] lorsque `getOffer/getOffers()` est appelé. Par défaut, at.js collecte uniquement les Client Hints « à entropie faible ». Si vous effectuez une segmentation de l’audience ou utilisez des scripts de profil basés sur des données dites « à entropie élevée » des sections précédentes, vous devez configurer at.js pour collecter les Client Hints « à entropie élevée » à partir du navigateur via `targetGlobalSettings`.

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### SDK côté serveur

Pour plus d’informations sur la manière de transmettre des conseils client via des SDK côté serveur, voir [Conseils au client](https://developer.adobe.com/target/implement/server-side/sdk-guides/core-principles/audience-targeting/){target=_blank} sous *Ciblage d’audience* dans le *SDK Adobe Target* documentation.
