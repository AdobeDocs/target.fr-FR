---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders
description: Informations sur la fonction targetGlobalSettings() pour la bibliothèque JavaScript at.js d’Adobe Target.
title: Informations sur la fonction targetGlobalSettings() pour la bibliothèque JavaScript at.js d’Adobe Target.
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 73f2850baa2eb301b6366f0d89343d739edde004

---


# targetGlobalSettings()

Vous pouvez remplacer les paramètres de la bibliothèque at.js à l’aide de `targetGlobalSettings()`, au lieu de configurer les paramètres dans l’interface utilisateur de [!DNL Target] Standard/Premium, ou utiliser des API REST.

Dans certains cas d’utilisation, en particulier lorsque at.js est distribué via la [!DNL Dynamic Tag Management] (DTM), il se peut que vous souhaitiez remplacer certains des paramètres.

## Paramètres {#section_42C759AE9B524A43B8659018677224B8}

Vous pouvez remplacer les paramètres suivants :

| Paramètres | Type | Valeur par défaut | Description |
|--- |--- |--- |--- |
| serverState | Voir &quot;serverState&quot; ci-dessous. | Voir &quot;serverState&quot; ci-dessous. | Voir &quot;serverState&quot; ci-dessous. |
| clientCode | Chaîne | Valeur définie via l’interface utilisateur | Représente le code client |
| serverDomain | Chaîne | Valeur définie via l’interface utilisateur | Représente le serveur Target Edge |
| cookieDomain | Chaîne | Si possible, définissez la valeur sur le domaine de niveau supérieur | Représente le domaine utilisé lors de l’enregistrement de cookies |
| crossDomain | Chaîne | Valeur définie via l’interface utilisateur | Indique si le suivi interdomaine est activé ou non.<br>Les valeurs autorisées sont les suivantes :<ul><li>disabled</li><li>enabled</li><li>x-uniquement</li></ul> |
| timeout | Nombre | Valeur définie via l’interface utilisateur | Représente le délai d’expiration de la demande Target Edge |
| globalMboxAutoCreate | Booléen | Valeur définie via l’interface utilisateur | Indique si la demande de mbox globale doit être déclenchée ou non |
| visitorApiTimeout | Nombre | 2 000 ms = 2 s | Représente le délai d’expiration de la demande de l’API visiteur |
| enabled | Booléen | true | Lorsqu’elle est activée, une requête de  pour récupérer des expériences et la manipulation DOM pour générer les expériences est exécutée automatiquement. De plus, les appels de  peuvent être exécutés manuellement via `getOffer(s)` / `applyOffer(s)`<br>Lorsque la désactivation est activée, les demandes de  ne sont pas exécutées automatiquement ou manuellement. |
| pageLoadEnabled | Booléen | true | Lorsque cette option est activée, récupérez automatiquement les expériences qui doivent être renvoyées au chargement de la page. |
| viewsEnabled | Booléen | true | Lorsque cette option est activée, récupérez automatiquement les  qui doivent être renvoyées au chargement de la page. Les  sont pris en charge dans at.js 2.*x* uniquement |
| defaultContentHiddenStyle | Chaîne | visibility: hidden | Utilisé uniquement pour les mbox d’encapsulation qui font appel à des DIV avec le nom de classe « mboxDefault » et sont exécutées via `mboxCreate()`, `mboxUpdate()`, ou `mboxDefine()` () pour masquer le contenu par défaut |
| defaultContentVisibleStyle | Chaîne | visibility: visible | Utilisé uniquement pour les mbox d’encapsulation qui font appel à des DIV avec le nom de classe « mboxDefault » et sont exécutées via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` pour révéler l’offre appliquée (le cas échéant) ou le contenu par défaut |
| bodyHiddenStyle | Chaîne | body { opacity: 0 } | Utilisé uniquement lorsque `globalMboxAutocreate === true` pour minimiser les risques de scintillement.<br>Pour plus d’informations, voir [Gestion du scintillement par at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md). |
| bodyHidingEnabled | Booléen | true | Utilisé pour contrôler le scintillement lorsque `target-global-mbox` est utilisé pour diffuser des offres créées dans le composition d’expérience visuelle (également appelées offres visuelles) |
| imsOrgId | Chaîne | ID d’entreprise IMS | Représente l’ID d’entreprise IMS |
| secureOnly | Booléen | false | Indique si at.js doit utiliser le protocole HTTPS seulement ou s’il peut permuter entre les protocoles HTTP et HTTPS en fonction du protocole de la page. |
| overrideMboxEdgeServer | Booléen | vrai (vrai commençant par at.js version 1.6.2) | Indique s’il convient d’utiliser le domaine `<clientCode>.tt.omtrdc.net` ou le domaine `mboxedge<clusterNumber>.tt.omtrdc.net`.<br>Si cette valeur est définie sur vrai, le domaine `mboxedge<clusterNumber>.tt.omtrdc.net` sera enregistré dans un cookie. |
| overrideMboxEdgeServerTimeout | Nombre | 1 860 000 => 31 minutes | Indique la durée de vie du cookie qui contient la valeur `mboxedge<clusterNumber>.tt.omtrdc.net`. |
| optoutEnabled | Booléen | false | Indique si Target doit invoquer la fonction `isOptedOut()` de l’API visiteur. Fait partie de l’activation de Device Graph. |
| selectorsPollingTimeout | Nombre | 5 000 ms = 5 s | Dans at.js 0.9.6, Target présente ce nouveau paramètre qui peut être remplacé via `targetGlobalSettings`.<br>`selectorsPollingTimeout` représente la durée d’attente acceptable du client pour tous les éléments identifiés par les sélecteurs qui s’affichent sur la page.<br>Les activités créées via le compositeur d’expérience visuelle (VEC) comportent des offres qui contiennent des sélecteurs. |
| dataProviders | Voir la section Fournisseurs de données ci-dessous. | Voir la section Fournisseurs de données ci-dessous. | Voir la section Fournisseurs de données ci-dessous. |
| cspScriptNonce | Voir &quot;Politique de sécurité du contenu&quot; ci-dessous. | Voir &quot;Politique de sécurité du contenu&quot; ci-dessous. | Voir &quot;Politique de sécurité du contenu&quot; ci-dessous. |
| cspStyleNonce | Voir &quot;Politique de sécurité du contenu&quot; ci-dessous. | Voir &quot;Politique de sécurité du contenu&quot; ci-dessous. | Voir &quot;Politique de sécurité du contenu&quot; ci-dessous. |

## Utilisation {#section_9AD6FA3690364F7480C872CB55567FB0}

Cette fonction peut être définie avant le chargement du fichier at.js ou dans **[!UICONTROL Configuration]** > **[!UICONTROL Mise en œuvre]** > **[!UICONTROL Modifier les paramètres at.js]** > **[!UICONTROL Paramètres des codes]** > **[!UICONTROL En-tête de bibliothèque]**.

Le champ En-tête de bibliothèque vous permet de saisir du code JavaScript de forme libre. Le code de personnalisation doit être similaire au suivant :

```
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## Fournisseurs de données {#data-providers}

Ce paramètre permet aux clients de collecter des données auprès de fournisseurs de données tiers tels que Demandbase, BlueKai ou des services personnalisés, et de les transmettre à Target sous forme de paramètres mbox dans la requête globale mbox. Cette fonction prend en charge la collecte des données en provenance de fournisseurs multiples via des requêtes synchrones et asynchrones. Cette approche permet de gérer aisément le scintillement du contenu de la page par défaut, tout en incluant des délais d’attente indépendants pour chaque fournisseur afin de limiter l’impact sur les performances de la page

>[!NOTE]
>
>La section Fournisseurs de données doit disposer du fichier [!DNL at.js] 1.3 ou d’une version ultérieure.

Les vidéos suivantes comprennent davantage d’informations :

| Vidéo | Description |
|--- |--- |
| [Utilisation des fournisseurs de données dans Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html) | L’option Fournisseurs de données est une fonctionnalité qui vous permet de transmettre facilement des données provenant de tiers à Target. Un tiers peut être un service météorologique, une plateforme de gestion des données, ou même votre propre service web. Vous pouvez ensuite utiliser ces données pour créer des audiences, cibler du contenu et enrichir le profil du visiteur. |
| [Implémenter les fournisseurs de données dans Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Détails de mise en œuvre et exemples d’utilisation de la fonctionnalité Fournisseurs de données d’Adobe Target pour récupérer les données de fournisseurs de données tiers et les transmettre dans la requête Target. |

Le paramètre `window.targetGlobalSettings.dataProviders` est un tableau de fournisseurs de données.

Chaque fournisseur de données présente la structure suivante :

| Clé | Type | Description |
|--- |--- |--- |
| name | Chaîne | Nom du fournisseur |
| version | Chaîne | Version du fournisseur. Cette clé sera utilisée pour l’évolution du fournisseur. |
| timeout | Nombre | Représente le délai d’attente du fournisseur dans le cas d’une requête réseau. Cette clé est facultative. |
| provider | Fonction | Fonction qui contient la logique de recherche des données de fournisseur.<br>La fonction comporte un seul paramètre requis : `callback`. Le paramètre callback est une fonction qui doit être appelée uniquement lorsque les données ont été recherchées avec succès ou qu’une erreur s’est produite.<br>Le paramètre callback appelle lui-même deux paramètres :<ul><li>error : indique qu’une erreur s’est produite. Si l’exécution est correcte, ce paramètre doit être défini sur la valeur Null.</li><li>params : objet JSON représentant les paramètres qui seront envoyés dans une requête Target.</li></ul> |

L’exemple suivant illustre l’exécution synchronisée par le fournisseur de données :

```
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

Une fois que at.js a traité `window.targetGlobalSettings.dataProviders`, la requête Target contient un nouveau paramètre : `t1=1`.

L’exemple suivant illustre la recherche des paramètres que vous souhaitez ajouter à la requête Target dans un service tiers tel que BlueKai, Demandbase, etc. :

```
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

Une fois que at.js a traité `window.targetGlobalSettings.dataProviders`, la requête Target contient des paramètres supplémentaires : `t1=1`, `t2=2` et `t3=3`.

L’exemple suivant fait appel à des fournisseurs de données pour collecter des données météorologiques depuis l’API et les envoyer sous forme de paramètres dans une requête Target. La requête Target contiendra des paramètres supplémentaires tels que `country` et `weatherCondition`.

```
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

Tenez compte de ce qui suit lors de l’exploitation du paramètre `dataProviders` :

* Si les fournisseurs de données ajoutés à `window.targetGlobalSettings.dataProviders` sont asynchrones, ils sont exécutés en parallèle. La requête d’API Visitor sera exécutée en parallèle avec des fonctions ajoutées à `window.targetGlobalSettings.dataProviders` afin de permettre un temps d’attente minimal.
* at.js ne tentera pas de mettre les données en cache. Si le fournisseur de données extrait les données en une seule fois, il doit s’assurer que les données sont mises en cache et que, lorsque la fonction du fournisseur est appelée, les données du cache sont envoyées pour le second appel.

## Content Security Policy {#content-security}

at.js 2.3.0+ prend en charge la définition d’nonces de la stratégie de sécurité de contenu sur les balises SCRIPT et STYLE ajoutées au DOM de la page lors de l’application de la  de fournie .

Les nonies SCRIPT et STYLE doivent être définies dans `targetGlobalSettings.cspScriptNonce` et `targetGlobalSettings.cspStyleNonce` proportionnellement, avant le chargement du fichier at.js 2.3.0+. Consultez un exemple ci-dessous :

```
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

Une fois les paramètres `cspScriptNonce` et `cspStyleNonce` spécifiés, at.js 2.3.0+ les définit comme des attributs nonce sur toutes les balises SCRIPT et STYLE qu’il ajoute au modèle DOM lors de l’application de  .

## serverState {#server-state}

`serverState` est un paramètre disponible dans at.js v2.2+ qui peut être utilisé pour optimiser les performances des pages lorsqu’une intégration hybride de  de est implémentée. L’intégration hybride signifie que vous utilisez at.js v2.2+ côté client et l’API de  de ou un kit SDK de côté serveur pour diffuser des expériences. `serverState` donne à at.js v2.2+ la possibilité d’appliquer des expériences directement à partir du contenu récupéré côté serveur et renvoyé au client dans le cadre de la page diffusée.

### Conditions préalables

Vous devez avoir une intégration hybride de [!DNL Target].

* **Côté** serveur :  Vous devez utiliser la nouvelle API [de](https://developers.adobetarget.com/api/delivery-api/) ou les SDK [de ](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **Côté** client : Vous devez utiliser [at.js version 2.2 ou ultérieure](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

### Exemples de code

Pour mieux comprendre comment cela fonctionne, reportez-vous aux exemples de code ci-dessous que vous trouverez sur votre serveur. Le code part du principe que vous utilisez le SDK [ Node.js du](https://github.com/adobe/target-nodejs-sdk).

```
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

Un exemple `serverState` d’objet JSON pour la prélecture  se présente comme suit :

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

Une fois la page chargée dans le navigateur, at.js applique tous les  de  à partir de [!DNL Target] immédiatement, sans déclencher d’appels réseau par rapport au `serverState` [!DNL Target] bord. En outre, at.js prémasque uniquement les éléments DOM pour lesquels des   sont disponibles dans le contenu récupéré côté serveur, ce qui a un impact positif sur les performances de chargement des pages et sur l’expérience utilisateur. [!DNL Target]

### Remarques importantes

Consider the following when using `serverState`:

* Actuellement, at.js v2.2 ne prend en charge que la diffusion d’expériences via serverState pour :

   * Les  créés par le compositeur d’expérience visuelle sont exécutés au chargement de la page.
   *  prérécupéré.

      Dans le cas des applications monopages utilisant des  [!DNL Target]`triggerView()` et dans l’API at.js, at.js v2.2 met en cache le contenu pour tous les  de prérécupérés côté serveur et l’applique dès que chaque `triggerView()`est déclenchée par le biais, une fois de plus, sans déclencher d’appels de récupération de contenu supplémentaires vers les.

   * **Remarque**:  Actuellement, les mbox récupérées côté serveur ne sont pas prises en charge dans `serverState`.

* Lorsque vous appliquez `serverState `, at.js prend en compte `pageLoadEnabled` et `viewsEnabled` les paramètres, par exemple, le de chargement de page  ne sera pas appliqué si le `pageLoadEnabled` paramètre est false.

   Pour activer ces paramètres, activez la bascule dans Configuration **[UICONTROL > Implémentation > Modifier les paramètres > Chargement de page activé]**.

   ![Paramètres d’activation du chargement de page](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

### Ressources supplémentaires

Pour en savoir plus sur le `serverState` fonctionnement, consultez les ressources suivantes :

* [Exemple de code](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Exemple d’application monopage avec `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
