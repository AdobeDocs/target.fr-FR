---
keywords: at.js;agent utilisateur du navigateur;agent utilisateur;conseils client;agent utilisateur
description: Découvrez comment [!DNL Adobe Target] utilise l’agent-utilisateur et les conseils au client pour qualifier les visiteurs pour la segmentation et la personnalisation.
title: Agent utilisateur et conseils client
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 3%

---

# Agent utilisateur et conseils client

[!DNL Adobe Target] utilise l’agent-utilisateur pour qualifier les visiteurs pour la segmentation et la personnalisation.

>[!NOTE]
>
>Les informations contenues dans cet article s&#39;appliquent à [at.js version 2.9.0](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) (ou version ultérieure).


Chaque fois qu’un navigateur web envoie une requête à un serveur, y compris dans l’en-tête de la requête, il y a des informations sur le navigateur et l’environnement dans lequel le navigateur s’exécute. Depuis les premiers jours d’Internet, ces données ont été agrégées dans une seule chaîne appelée user-agent.

Le texte suivant est un exemple d’agent-utilisateur d’un ordinateur Mac OS X utilisant un navigateur Safari :

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

À partir de cet agent-utilisateur, le serveur recevant la demande peut discerner les informations suivantes sur le navigateur et le système d’exploitation :

| Informations | Détails |
| --- | --- |
| Nom du logiciel | Chrome |
| Version logicielle | 101 |
| Version complète du logiciel | 101.0.4951.41 |
| Nom du moteur de mise en page | AppleWebKit |
| Version du moteur de mise en page | 537,36 |
| Système d’exploitation | Android    |
| Version du système d’exploitation | Android 12 (Snow Cone) |
| Périphérique | SM-S908E (Samsung Galaxy S22 Ultra) |

Au fil des ans, la quantité d’informations de navigateur et d’appareil incluses dans la chaîne user-agent a augmenté.

## Cas d’utilisation de l’agent utilisateur

Les agents utilisateur ont longtemps été utilisés pour fournir aux équipes de marketing et de développement des informations importantes sur la façon dont les navigateurs et les systèmes d’exploitation sont utilisés. Les appareils et affichent le contenu du site, ainsi que la manière dont les utilisateurs interagissent avec les sites web. Les agents utilisateur sont également utilisés pour bloquer les spams et filtrer les robots qui analysent les sites à diverses fins supplémentaires.

Cependant, au cours des dernières années, certains propriétaires de site et vendeurs marketing ont utilisé l’agent-utilisateur avec d’autres informations incluses dans les en-têtes de demande pour créer des empreintes digitales numériques qui peuvent être utilisées comme moyen d’identifier les utilisateurs à leur insu. Malgré l’objectif important que l’agent-utilisateur remplit pour les propriétaires de site, les développeurs de navigateur ont décidé d’apporter des modifications à la manière dont les agents-utilisateurs fonctionnent afin de limiter les éventuels problèmes de confidentialité pour les visiteurs du site.

Les conseils client User-Agent sont les solutions que les développeurs de navigateur ont développées. Les conseils aux clients permettent toujours aux sites de collecter les informations nécessaires sur le navigateur, le système d’exploitation et le périphérique, tout en offrant une protection accrue contre les méthodes de suivi secrètes, telles que l’empreinte digitale.

## Conseils client

Les conseils client User-Agent permettent aux propriétaires de site web d’accéder à une grande partie des mêmes informations disponibles dans l’agent-utilisateur, mais de manière plus respectueuse de la vie privée. Lorsque les navigateurs modernes envoient un agent-utilisateur à un serveur web, l’agent-utilisateur complet est envoyé à chaque demande, qu’elle soit requise ou non. Client Hints, en revanche, applique un modèle dans lequel le serveur doit demander au navigateur les informations supplémentaires qu’il souhaite connaître sur le client. Lors de la réception de cette requête, le navigateur peut appliquer ses propres stratégies ou sa propre configuration utilisateur pour déterminer les données renvoyées. Au lieu d’exposer l’ensemble de l’agent-utilisateur par défaut sur toutes les requêtes, l’accès est désormais géré de manière explicite et auditable.

Les conseils client User-Agent sont disponibles dans Chrome depuis la version 89. Les versions récentes des navigateurs Chromium, tels que Microsoft Edge, Opera, Brave, Chrome Android, Opera Android et Samsung Internet, prennent également en charge l’API Client Hints.

Client Les conseils contenus dans les en-têtes de la première requête envoyée par le navigateur à un serveur web contiennent la marque du navigateur, la version majeure du navigateur et un indicateur indiquant si le client est un appareil mobile. Chaque élément de données possède sa propre valeur d’en-tête, plutôt que d’être regroupé en une seule chaîne agent-utilisateur, comme illustré dans l’exemple suivant :

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

L’exemple suivant est l’agent-utilisateur pour le même navigateur :

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

Bien que les informations soient similaires, la première requête au serveur contient des conseils au client qui contiennent uniquement un sous-ensemble de ce qui est disponible dans la chaîne de l’agent-utilisateur. Il manque à la requête l’architecture du système d’exploitation, la version complète du système d’exploitation, le nom du moteur de mise en page, la version du moteur de mise en page et la version complète du navigateur. Cependant, lors de requêtes ultérieures, l’API Client Hints permet aux serveurs web de demander des détails supplémentaires à forte entropie sur l’appareil. Lorsque ces valeurs à forte entropie sont demandées, en fonction de la stratégie du navigateur ou des paramètres utilisateur, la réponse du navigateur peut inclure ces informations.

L’exemple suivant est un objet JSON renvoyé par l’API Client Hints lorsque des valeurs à forte entropie sont demandées :

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

Les valeurs à forte entropie incluent plusieurs informations supplémentaires qui ne sont pas disponibles dans les informations de conseils client par défaut. Le tableau suivant contient des détails sur les données disponibles dans la requête par défaut par rapport aux informations User-Agent Client Hicks à entropie élevée.

| En-tête HTTP | JavaScript | Agent-utilisateur | Conseil client | Conseil client à forte entropie |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | marques | Oui | Oui | Non |
| Sec-CH-UA-Platform | plateforme | Oui | Oui | Non |
| Sec-CH-UA-Mobile | mobile | Oui | Oui | Non |
| Sec-CH-UA-Platform-Version | platformVersion | Oui | Non | Oui |
| Sec-CH-UA-Arch | Architecture | Oui | Non | Oui |
| Sec-CH-UA-Model | model | Oui | Non | Oui |
| Sec-CH-UA-Bitness | Bitness | Oui | Non | Oui |
| Sec-CH-UA-Full-Version-List | fullVersionList | Oui | Non | Oui |

## Migration vers les conseils client

Actuellement, les navigateurs basés sur Chromium continuent d’envoyer l’agent utilisateur avec des conseils client dans les en-têtes des demandes effectuées aux serveurs web. Toutefois, à partir d’avril 2022 et jusqu’à février 2023, la quantité de données contenue dans la chaîne agent-utilisateur sera réduite. D’autres navigateurs, tels que Safari et Firefox, continueront à utiliser la chaîne user-agent ; cependant, elles aussi réduiront la quantité d&#39;informations qu&#39;elles contiennent.

## [!DNL Target] Cas d’utilisation nécessitant des conseils de client

Les cas d’utilisation suivants dans Target nécessitent des conseils au client :

### Attributs d’audience

Si vous utilisez [!DNL Target] audiences et utiliser l’un des attributs d’audience suivants, [!DNL Target] nécessite que les conseils client effectuent la segmentation correcte :

* Navigateur
* Système d’exploitation
* Mobile

### Scripts de profil

Si vous utilisez des scripts de profil et référencez la variable `user.browser` (qui fait référence à l’agent-utilisateur), vous devrez peut-être mettre à jour le script de profil pour vérifier également un ou plusieurs conseils client. Vous pouvez accéder à l’un des conseils client à l’aide de la fonction `user.clientHint('sec-ch-ua-xxxxx')`. Le nom de l’en-tête de l’indicateur client doit être en minuscules.

L’exemple suivant montre comment détecter correctement un système d’exploitation Windows dans un script de profil :

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

Les sections suivantes présentent les en-têtes de conseils client et la sémantique d’utilisation de script de profil correspondante.

#### Sec-CH-UA

Entropy : Faible documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank} Attribut d’audience : Utilisation du script du profil du navigateur : `user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

Entropy : Documentation élevée : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank} Attribut d’audience : Exposé aux utilisateurs via des scripts de profil.
Utilisation des scripts de profil : `user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

Entropy : Documentation élevée : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank} Attribut d’audience : Exposé aux utilisateurs via des scripts de profil.
Utilisation des scripts de profil : `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

Entropy : Documentation élevée : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank} Attribut d’audience : Utilisation du script du profil du navigateur : `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

Entropy : Faible documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank} Attribut d’audience : Utilisation du script de profil mobile : `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

Entropy : Documentation élevée : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank} Attribut d’audience : Utilisation du script de profil mobile : `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

Entropy : Faible documentation : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank} Attribut d’audience : Système d’exploitation Utilisation des scripts de profil : `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

Entropy : Documentation élevée : [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank} Attribut d’audience : Exposé aux utilisateurs via des scripts de profil.
Utilisation des scripts de profil : `user.clientHint('sec-ch-ua-platform-version')`

## Comment transmettre des conseils au client à [!DNL Adobe Target]

Les sections suivantes contiennent des informations supplémentaires sur la manière de transmettre des conseils au client, en fonction de vos [!DNL Target] implémentation.

### at.js version 2.9.0 (ou ultérieure)

À compter d’at.js 2.9.0, les conseils client de l’agent utilisateur seront collectés automatiquement à partir du navigateur et envoyés à [!DNL Target] when `getOffer/getOffers()` est appelée. Par défaut, at.js collecte uniquement les conseils client &quot;Faible niveau d’entrée&quot;. Si vous effectuez une segmentation de l’audience ou utilisez des scripts de profil basés sur des données classées comme &quot;Haute entropie&quot; dans les sections précédentes, vous devez configurer at.js pour collecter les conseils client &quot;Haute entropie&quot; à partir du navigateur via `targetGlobalSettings`.

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### SDK côté serveur

Pour plus d’informations sur la manière de transmettre des conseils client via des SDK côté serveur, voir [Conseils au client](https://adobetarget-sdks.gitbook.io/docs/core-principles/audience-targeting#client-hints){target=_blank} dans la variable *SDK Adobe Target* documentation.
