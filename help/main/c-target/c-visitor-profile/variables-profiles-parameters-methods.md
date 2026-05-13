---
keywords: variables;profils;paramètres;profils intégrés;méthodes;variables d’url;profils géographiques;profils tiers;variables de mbox;variables de campagne;attributs du client
description: Affichez une liste de différents profils, variables et paramètres utiles dans les scripts de profil d’Adobe Target.
title: Dans quels profils, variables et paramètres est-il utilisé  [!DNL Target] ?
feature: Audiences
exl-id: 96ef9a56-fe76-428e-a164-c01829fdf45d
TQID: https://experienceleague.adobe.com/YMF4eXnu758kloK--c2mBzP-rwLBNRO2jLoV6s-P5JM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 699
ht-degree: 59%

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
| user.browserType | Renvoie le type de navigateur, par exemple, Safari, Chrome, etc. |
| user.header | Tous les profils `user.header` sont intégrés à partir des données de l’en-tête de la requête de mbox. |
| user.header(&#39;x-forwarded-for&#39;) | Adresse IP publique de la connexion réseau qu’utilise le visiteur.<br>Vous pouvez obtenir ceci de plusieurs façons, par exemple [whatismyip.com](https://www.whatismyip.com/). L’adresse IP n’est pas l’adresse NAT (adresse interne), commençant par 10., 192.168. ou 172.<br>Remarque : user.header(&#39;x-cluster-client-ip&#39;) a été abandonné. |
| user.header(&#39;host&#39;) | Nom d’hôte du site web |
| user.header(&#39;cookie&#39;) | Données de cookie du visiteur |
| user.header(&#39;user-agent&#39;) | Agent-utilisateur du navigateur des visiteurs |
| user.header(&#39;accept-language&#39;) | Langue du visiteur |
| user.header(&#39;accept-encoding&#39;) | Codage des caractères du visiteur |
| user.header(&#39;accept&#39;) | Codage de la langue et des caractères du visiteur |
| user.header(&#39;connection&#39;) | Connexion au serveur. Par exemple : keep-live |
| user.header(&#39;referrer&#39;) | URL du site web de la page active du visiteur. Ne fonctionne pas pour Internet Explorer. |
| user.getLocal(&#39;param_name&#39;); | Récupérez la valeur que vous avez définie à l’aide de `user.setLocal`. |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;) | Créez des valeurs de profil persistantes dans un script de profil. Ces valeurs persistent comme un script de profil, mais vous n’y avez accès que dans le script dans lequel il a été défini. |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | Attributs de profil persistants créés par le biais des scripts de profil. Fait également référence à des profils « système » tels que la géolocalisation, le nombre de visites, etc. |
| profile.get(&#39;param_name&#39;) | La méthode profile.get(&#39;param_name&#39;) est le moyen correct d&#39;obtenir un paramètre de profil à utiliser dans un script de profil. |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | Paramètres mbox devenus persistants en raison de leur préfixe profile.   |
| profile.browserTime | L’heure du navigateur local du visiteur. Pour l’heure du système, créez un nouvel objet de date dans le script du profil. |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| profile.mobile.isTablet | L’appareil visiteur est une tablette.<P>**REMARQUE** : ce profil remplace l’ancien navigateur obsolète de la catégorie d’audience iPad. Voir [Navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts) pour plus d’informations. |
| profile.mobile.isMobilePhone | L’appareil visiteur est un téléphone mobile.<P>**REMARQUE** : ce profil remplace l’ancien navigateur obsolète de la catégorie d’audience iPhone. Voir [Navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts) pour plus d’informations. |
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
| Paramètres automatiquement transmis avec chaque requête :<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |  |
| Paramètres transmis avec les mbox de commande :<ul><li>mbox.param(&#39;orderId’)</li><li>mbox.param(&#39;orderTotal’)</li><li>mbox.param(&#39;productPurchasedId’)</li></ul> |  |
| mbox3rdPartyId | Un paramètre mbox pour synchroniser un identifiant client au mboxPCID de la Target. Un identifiant client est l’identifiant que votre société utilise pour effectuer le suivi des visiteurs, comme un identifiant de logiciel de gestion de la relation client, un identifiant de membre, etc. Cet identifiant peut ensuite être utilisé pour ajouter des informations via les API de profil et [Attributs du client](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html){target=_blank}. |
| mboxPageValue | Dans chaque appel de mbox, une valeur est attribuée à la page. |
| mboxDebug | Utilisée uniquement pour les informations de débogage. Ajout à l’URL de la page où at.js le recherche. |
| mboxOverride.browserIp | Définit une zone géographique différente de l’emplacement réel afin que vous puissiez tester l’aspect d’un élément dans un autre emplacement.<br>**Remarque :** l’utilisation des paramètres mboxOverride doit être utilisée uniquement lors du test de l’activité, et non en production. L’utilisation de tout paramètre mboxOverride peut entraîner des incohérences avec la création de rapports lors de l’utilisation d’[Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Utilisez le [mode AQ d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md) pour vous assurer que l’activité fonctionne comme prévu avant de la transférer dans votre environnement de production. |

## Attributs du client {#section_62B4821EB6564FF4A14159A837AD4EDB}

Les attributs du client peuvent être référencés dans les scripts de profil, au format `crs.get('<Datasource Name>.<Attribute name>')`.

Ces attributs sont aussi disponibles sous forme de jetons dans les scripts de profil et directement dans les offres sans demander au préalable un script de profil. Le jeton doit se présenter sous la forme : `${crs.datasourceName.attributeName}`. Notez que les espaces dans le `datasourceName` doivent être supprimés de tout appel API.
