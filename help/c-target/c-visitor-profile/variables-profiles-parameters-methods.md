---
keywords: variables;profiles;parameters;built in profiles;methods;url variables;geo profiles;third party profiles;mbox variables;campaign variables;customer attributes
description: Cette page répertorie les profils, les variables et les paramètres utiles dans les scripts de profil.
title: Glossaire des profils et variables
topic: Standard
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
translation-type: tm+mt
source-git-commit: 6586d49118ff5a598b699dfb9f5a23ef9da4cce7

---


# Glossaire des profils et variables{#profile-and-variable-glossary}

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
| user.header('x-cluster-client-ip') | Adresse IP publique de la connexion réseau qu’utilise le visiteur.<br>Vous pouvez la récupérer de différentes façons, par exemple avec [whatismyip.com](https://www.whatismyip.com/). L’adresse IP n’est pas l’adresse NAT (adresse interne), qui commence par 10., 192.168. ou 172. |
| user.header('host') | Nom d’hôte du site web |
| user.header('cookie') | Données de cookie du visiteur |
| user.header('user-agent') | Agent-utilisateur du navigateur des visiteurs |
| user.header('accept-language') | Langue du visiteur |
| user.header('accept-encoding') | Codage des caractères du visiteur |
| user.header('accept') | Codage de la langue et des caractères du visiteur |
| user.header('connection') | Connexion au serveur. Par exemple : keep-live |
| user.header('referrer') | URL du site web de la page active du visiteur. Ne fonctionne pas pour Internet Explorer. |
| user.getLocal('param_name','value'); |  |
| user.setLocal('param_name','value'); |  |
| user.get('param_name') |  |
| user.parameter | Attributs de profil persistants créés par le biais des scripts de profil. Cela fait aussi référence aux profils « système » comme la géolocalisation, le compte de visites, etc. |
| profile.get('param_name') | La méthode profile.get('param_name') est la méthode appropriée pour obtenir un paramètre de profil à utiliser dans un script de profil. |
| profile.param('param_name'); |  |
| profile.parameter('parameter_name'); | Paramètres mbox devenus persistants en raison de leur préfixe profile. préfixe. |
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
| mbox.param('param_name') |  |
| Paramètres automatiquement transmis avec chaque requête :<ul><li>mbox.param('browserHeight')</li><li>mbox.param('browserTimeOffset')</li><li>mbox.param('browserWidth')</li><li>mbox.param('colorDepth')</li><li>mbox.param('mboxXDomain')</li><li>mbox.param('mboxTime')</li><li>mbox.param('screenHeight')</li><li>mbox.param('screenWidth')</li></ul> |
| Paramètres transmis avec les mbox de commande :<ul><li>mbox.param('orderId’)</li><li>mbox.param('orderTotal’)</li><li>mbox.param('productPurchasedId’)</li></ul> |
| mbox3rdPartyId | Un paramètre mbox pour synchroniser un identifiant client au mboxPCID de la Target. Un identifiant client est l’identifiant que votre société utilise pour effectuer le suivi des visiteurs, comme un identifiant de logiciel de gestion de la relation client, un identifiant de membre, etc. Cet identifiant peut ensuite être utilisé pour ajouter des informations par le biais des API de profil et des [Attributs du client](/help/c-target/c-visitor-profile/working-with-customer-attributes.md). |
| mboxPageValue | Dans chaque appel de mbox, une valeur est attribuée à la page. |
| mboxDebug | Utilisée uniquement pour les informations de débogage. Ajoutée à l’URL de la page lorsque mbox.js la recherche. |
| mboxOverride.browserIp | Définit un autre lieu géographique que le lieu actuel afin que vous puissiez tester à quoi ressemblerait un élément particulier dans un autre lieu.<br>**Remarque :** Les paramètres mboxOverride doivent être utilisés pour tester l’activité et non en production. L’utilisation de tout paramètre mboxOverride peut entraîner des incohérences avec la création de rapports lors de l’utilisation d’[Analytics pour Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Utilisez le [mode AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md) pour vous assurer que l’activité fonctionne comme prévu avant de la transférer dans votre environnement de production. |

## Attributs du client {#section_62B4821EB6564FF4A14159A837AD4EDB}

Les attributs du client peuvent être référencés dans les scripts de profil, au format `crs.get('<Datasource Name>.<Attribute name>')`.

Ces attributs sont aussi disponibles sous forme de jetons dans les scripts de profil et directement dans les offres sans demander au préalable un script de profil. Le jeton doit être au format suivant : `${crs.datasourceName.attributeName}`. Notez que les espaces de la `datasourceName` section doivent être supprimés de tout appel d’API.
