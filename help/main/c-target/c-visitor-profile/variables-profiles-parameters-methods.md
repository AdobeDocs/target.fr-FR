---
keywords: variables;profils;paramètres;profils intégrés;méthodes;variables d’url;profils géographiques;profils tiers;variables de mbox;variables de campagne;attributs du client
description: Affichez la liste des différents profils, variables et paramètres utiles dans les scripts de profil dans Adobe Target.
title: Quels profils, variables et paramètres sont utilisés dans Target ?
feature: Audiences
exl-id: 96ef9a56-fe76-428e-a164-c01829fdf45d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 86%

---

# Glossaire des profils et variables

Cette page répertorie les profils, les variables et les paramètres utiles dans les scripts de profil.

## Profils intégrés {#section_2B694370003C4F8E8E29E0B2F6E52045}

| Profil | Remarques |
|--- |--- |
| user.activeActivities<br>user.activeCampaigns | Renvoie l’ID de toutes les campagnes et activités auxquelles participe l’utilisateur, même s’il n’a pas interagi avec une campagne ou activité au cours de la présente session. |
| user.pcId |  |
| user.sessionId |  |
| user.categoryAffinity |  |
| user.categoryAffinities | Renvoi d’un tableau des affinités renseignées par un visiteur. |
| user.isFirstSession |  |
| user.isNewSession |  |
| user.daysSinceLastVisit |  |
| user.browser | L’agent-utilisateur |
| user.header | Tous les profils `user.header` sont intégrés à partir des données de l’en-tête de la requête de mbox. |
| user.header(&#39;x-transfer-for&#39;) | Adresse IP publique de la connexion réseau qu’utilise le visiteur.<br>Vous pouvez la récupérer de différentes façons, par exemple avec [whatismyip.com](https://www.whatismyip.com/). L’adresse IP n’est pas l’adresse NAT (adresse interne), qui commence par 10., 192.168. ou 172.<br>Remarque : user.header(&#39;x-cluster-client-ip&#39;) a été abandonné. |
| user.header(&#39;host&#39;) | Nom d’hôte du site web |
| user.header(&#39;cookie&#39;) | Données de cookie du visiteur |
| user.header(&#39;user-agent&#39;) | Agent-utilisateur du navigateur des visiteurs |
| user.header(&#39;accept-language&#39;) | Langue du visiteur |
| user.header(&#39;accept-encoding&#39;) | Codage des caractères du visiteur |
| user.header(&#39;accept&#39;) | Codage de la langue et des caractères du visiteur |
| user.header(&#39;connection&#39;) | Connexion au serveur. Par exemple : keep-live |
| user.header(&#39;referrer&#39;) | URL du site web de la page active du visiteur. Ne fonctionne pas pour Internet Explorer. |
| user.getLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | Attributs de profil persistants créés par le biais des scripts de profil. Cela fait aussi référence aux profils « système » comme la géolocalisation, le compte de visites, etc. |
| profile.get(&#39;param_name&#39;) | La méthode profile.get(&#39;param_name&#39;) constitue la méthode correcte pour obtenir un paramètre de profil à utiliser dans un script de profil. |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | Paramètres mbox devenus persistants en raison de leur préfixe profile. prefix. |
| profile.browserTime | L’heure du navigateur local du visiteur. Pour l’heure du système, créez un nouvel objet de date dans le script du profil. |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| parameter= | Terme générique pour les valeurs additionnelles transmises par une mbox, généralement des paires nom/valeur. Non persistantes sauf si elles y sont forcées avec `profile.parameter` ou `user.parameter`. |

## Variables d’URL {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## Profils de géociblage et d’opérateur de téléphonie mobile {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## Variables de mbox {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| Variable | Remarques |
|--- |--- |
| `mbox.name` |  |
| mbox.param(&#39;param_name&#39;) |  |
| Paramètres automatiquement transmis avec chaque requête :<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |
| Paramètres transmis avec les mbox de commande :<ul><li>mbox.param(&#39;orderId’)</li><li>mbox.param(&#39;orderTotal’)</li><li>mbox.param(&#39;productPurchasedId’)</li></ul> |
| mbox3rdPartyId | Un paramètre mbox pour synchroniser un identifiant client au mboxPCID de la Target. Un identifiant client est l’identifiant que votre société utilise pour effectuer le suivi des visiteurs, comme un identifiant de logiciel de gestion de la relation client, un identifiant de membre, etc. Cet identifiant peut ensuite être utilisé pour ajouter des informations par le biais des API de profil et des [Attributs du client](/help/main/c-target/c-visitor-profile/working-with-customer-attributes.md). |
| mboxPageValue | Dans chaque appel de mbox, une valeur est attribuée à la page. |
| mboxDebug | Utilisée uniquement pour les informations de débogage. Ajout à l’URL de la page où at.js la recherche. |
| mboxOverride.browserIp | Définit un autre lieu géographique que le lieu actuel afin que vous puissiez tester à quoi ressemblerait un élément particulier dans un autre lieu.<br>**Remarque :** Les paramètres mboxOverride doivent être utilisés pour tester l’activité et non en production. L’utilisation de tout paramètre mboxOverride peut entraîner des incohérences avec la création de rapports lors de l’utilisation d’[Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Utilisez le [mode AQ d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md) pour vous assurer que l’activité fonctionne comme prévu avant de la transférer dans votre environnement de production. |

## Attributs du client {#section_62B4821EB6564FF4A14159A837AD4EDB}

Les attributs du client peuvent être référencés dans les scripts de profil, au format `crs.get('<Datasource Name>.<Attribute name>')`.

Ces attributs sont aussi disponibles sous forme de jetons dans les scripts de profil et directement dans les offres sans demander au préalable un script de profil. Le jeton doit être au format suivant : `${crs.datasourceName.attributeName}`. Notez que les espaces dans la variable `datasourceName` doit être supprimé de tout appel API.
