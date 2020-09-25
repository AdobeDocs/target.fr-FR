---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: Informations sur la fonction targetGlobalSettings() pour la bibliothèque JavaScript at.js d’Adobe Target.
title: targetGlobalSettings()
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 8789d750e9e0245d88d54a8d3fe342e5b2e616fc
workflow-type: tm+mt
source-wordcount: '1674'
ht-degree: 38%

---


# targetGlobalSettings()

Vous pouvez remplacer les paramètres de la bibliothèque at.js à l’aide de `targetGlobalSettings()`, au lieu de configurer les paramètres dans l’interface utilisateur de [!DNL Target] Standard/Premium, ou utiliser des API REST.

Dans certains cas d’utilisation, en particulier lorsque at.js est distribué via la [!DNL Dynamic Tag Management] (DTM), il se peut que vous souhaitiez remplacer certains des paramètres.

## Paramètres {#section_42C759AE9B524A43B8659018677224B8}

Vous pouvez remplacer les paramètres suivants :

### bodyHiddenStyle

* **Type** : String
* **Valeur** par défaut : body { opacity: 0 }
* **Description**: Utilisé uniquement `globalMboxAutocreate === true` pour minimiser les risques de scintillement.

   Pour plus d’informations, voir [Gestion du scintillement par at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

### bodyHidingEnabled

* **Type**: Boolean
* **Valeur** par défaut : true
* **Description**: Permet de contrôler le scintillement lorsqu’ `target-global-mbox` il est utilisé pour diffuser des offres créées dans le compositeur d’expérience visuelle, également appelées offres visuelles.

### clientCode

* **Type** : String
* **Valeur** par défaut : Valeur définie via l’interface utilisateur.
* **Description**: Représente le code client.

### cookieDomain

* **Type** : String
* **Valeur** par défaut : Si possible, définissez le domaine de niveau supérieur.
* **Description**: Représente le domaine utilisé lors de l’enregistrement des cookies.

### crossDomain

* **Type** : String
* **Valeur** par défaut : Valeur définie via l’interface utilisateur.
* **Description**: Indique si le suivi interdomaines est activé ou non. Les valeurs autorisées sont les suivantes : désactivé, activé ou x-uniquement.

### cspScriptNonce

* **Type**: Voir Stratégie [de sécurité de](#content-security) contenu ci-dessous.
* **Valeur** par défaut : Voir Stratégie [de sécurité de](#content-security) contenu ci-dessous.
* **Description**: Voir Stratégie [de sécurité de](#content-security) contenu ci-dessous.

### cspStyleNonce

* **Type**: Voir Stratégie [de sécurité de](#content-security) contenu ci-dessous.
* **Valeur** par défaut : Voir Stratégie [de sécurité de](#content-security) contenu ci-dessous.
* **Description**: Voir Stratégie [de sécurité de](#content-security) contenu ci-dessous.

### dataProviders

* **Type**: Voir Fournisseurs [de](#data-providers) données ci-dessous.
* **Valeur** par défaut : Voir Fournisseurs [de](#data-providers) données ci-dessous.
* **Description**: Voir Fournisseurs [de](#data-providers) données ci-dessous.

### defaultContentHiddenStyle

* **Type** : String
* **Valeur** par défaut : visibility: masqué
* **Description**: Utilisé uniquement pour envelopper les mbox qui utilisent DIV avec le nom de classe &quot;mboxDefault&quot; et sont exécutées via `mboxCreate()`, `mboxUpdate()`ou `mboxDefine()` pour masquer le contenu par défaut.

### defaultContentVisibleStyle

* **Type** : String
* **Valeur** par défaut : visibility: visible
* **Description**: Utilisé uniquement pour les mbox d’encapsulation qui utilisent DIV avec le nom de classe &quot;mboxDefault&quot; et sont exécutées via `mboxCreate()`, `mboxUpdate()`ou `mboxDefine()` pour révéler l’offre appliquée, le cas échéant ou le contenu par défaut.

### deviceIdLifetime

* **Type**: Nombre
* **Valeur** par défaut : 63244800000 ms = 2 ans
* **Description**: Durée de conservation `deviceId` des cookies.

>[!NOTE]
>
>Le paramètre deviceIdLifetime peut être remplacé dans at.js version 2.3.1 ou ultérieure.

### enabled

* **Type**: Boolean
* **Valeur** par défaut : true
* **Description**: Lorsqu’elle est activée, une [!DNL Target] demande de récupération d’expériences et de manipulation DOM pour générer les expériences est exécutée automatiquement. En outre, [!DNL Target] les appels peuvent être exécutés manuellement via `getOffer(s)` / `applyOffer(s)`.

   Lorsque cette option est désactivée, [!DNL Target] les requêtes ne sont pas exécutées automatiquement ou manuellement.

### globalMboxAutoCreate

* **Type**: Nombre
* **Valeur** par défaut : Valeur définie via l’interface utilisateur.
* **Description**: Indique si la requête de mbox globale doit être déclenchée ou non.

### imsOrgId

* **Type**: Sting
* **Valeur** par défaut : true
* **Description**: Représente l’ID d’organisation IMS.

### optoutEnabled

* **Type**: Boolean
* **Valeur** par défaut : false
* **Description**: Indique si la Cible doit appeler la `isOptedOut()` fonction API Visiteur. Fait partie de l’activation de Device Graph.

### overrideMboxEdgeServer

* **Type**: Boolean
* **Valeur** par défaut : true (true en commençant par at.js version 1.6.2)
* **Description**: Indique si nous devons utiliser `<clientCode>.tt.omtrdc.net` le domaine ou le `mboxedge<clusterNumber>.tt.omtrdc.net` domaine.

   If this value is true, `mboxedge<clusterNumber>.tt.omtrdc.net` domain will be saved to a cookie. Actuellement, il ne fonctionne pas avec [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md)

### overrideMboxEdgeServerTimeout

* **Type**: Nombre
* **Valeur** par défaut : 1860000 => 31 minutes
* **Description**: Indique la durée de vie du cookie qui contient la `mboxedge<clusterNumber>.tt.omtrdc.net` valeur.

### pageLoadEnabled

* **Type**: Boolean
* **Valeur** par défaut : true
* **Description**: Lorsque cette option est activée, récupérez automatiquement les expériences qui doivent être renvoyées au chargement de la page.

### secureOnly

* **Type**: Boolean
* **Valeur** par défaut : false
* **Description**: Indique si at.js doit utiliser HTTPS uniquement ou s’il peut permuter entre HTTP et HTTPS en fonction du protocole de la page.

### selectorsPollingTimeout

* **Type**: Nombre
* **Valeur** par défaut : 5 000 ms = 5 s
* **Description**: Dans at.js 0.9.6, [!DNL Target] a introduit ce nouveau paramètre qui peut être remplacé par `targetGlobalSettings`.

   The `selectorsPollingTimeout` setting represents how long the client is willing to wait for all the elements identified by selectors to appear on the page.

   Les activités créées via le compositeur d’expérience visuelle (VEC) comportent des offres qui contiennent des sélecteurs.

### serverDomain

* **Type** : String
* **Valeur** par défaut : Valeur définie via l’interface utilisateur.
* **Description**: Représente le serveur Cible Edge.

### serverState

* **Type**: Voir Personnalisation [](#server-state) hybride ci-dessous.
* **Valeur** par défaut : Voir Personnalisation [](#server-state) hybride ci-dessous.
* **Description**: Voir Personnalisation [](#server-state) hybride ci-dessous.

### timeout

* **Type**: Nombre
* **Valeur** par défaut : Valeur définie via l’interface utilisateur.
* **Description**: Représente le délai d’expiration de la requête [!DNL Target] Edge.

### viewsEnabled

* **Type**: Boolean
* **Valeur** par défaut : true
* **Description**: Lorsque cette option est activée, récupère automatiquement les vues qui doivent être renvoyées au chargement de la page. Les vues sont prises en charge dans at.js 2.*x* uniquement.

### visitorApiTimeout

* **Type**: Nombre
* **Valeur** par défaut : 2 000 ms = 2 s
* **Description**: Représente le délai d’expiration de la requête de l’API  Visiteur.

## Utilisation {#section_9AD6FA3690364F7480C872CB55567FB0}

This function can be defined before at.js is loaded or in **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

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
| [Utilisation des fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-feature-video-use.html) | L’option Fournisseurs de données est une fonctionnalité qui vous permet de transmettre facilement des données provenant de tiers à Target. Un tiers peut être un service météorologique, une plateforme de gestion des données, ou même votre propre service web. Vous pouvez ensuite utiliser ces données pour créer des audiences, cibler du contenu et enrichir le profil du visiteur. |
| [Implémenter les fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Détails de mise en œuvre et exemples d’utilisation de la fonctionnalité Fournisseurs de données d’Adobe Target pour récupérer les données de fournisseurs de données tiers et les transmettre dans la requête Target. |

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

at.js 2.3.0+ prend en charge la définition des nonies de la stratégie de sécurité de contenu sur les balises SCRIPT et STYLE ajoutées au DOM de la page lors de l’application d’offres de Cible distribuées.

Les nonces SCRIPT et STYLE doivent être définies dans `targetGlobalSettings.cspScriptNonce` et `targetGlobalSettings.cspStyleNonce` proportionnellement, avant le chargement du fichier at.js 2.3.0+. Consultez un exemple ci-dessous :

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

Une fois `cspScriptNonce` et `cspStyleNonce` les paramètres spécifiés, at.js 2.3.0+ les définit comme des attributs nonce sur toutes les balises SCRIPT et STYLE qu’il ajoute au modèle DOM lors de l’application d’offres de Cible.

## Personnalisation hybride {#server-state}

`serverState` est un paramètre disponible dans at.js v2.2+ qui peut être utilisé pour optimiser les performances des pages lorsqu’une intégration hybride de Cible est implémentée. L’intégration hybride signifie que vous utilisez at.js v2.2+ côté client et l’API de diffusion ou un SDK de Cible côté serveur pour diffuser des expériences. `serverState` donne à at.js v2.2+ la possibilité d’appliquer des expériences directement à partir du contenu récupéré côté serveur et renvoyé au client dans le cadre de la page diffusée.

### Conditions préalables

Vous devez avoir une intégration hybride de [!DNL Target].

* **Côté** serveur :  Vous devez utiliser la nouvelle API [de](https://developers.adobetarget.com/api/delivery-api/) diffusion ou les SDK de [Cible](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **Côté** client : Vous devez utiliser [at.js version 2.2 ou ultérieure](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

### Exemples de code

Pour mieux comprendre comment cela fonctionne, reportez-vous aux exemples de code ci-dessous que vous trouverez sur votre serveur. Le code suppose que vous utilisez le SDK [Node.js de](https://github.com/adobe/target-nodejs-sdk)Cible.

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

Un exemple d’objet `serverState` JSON pour la prérécupération de vue se présente comme suit :

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

Une fois la page chargée dans le navigateur, at.js applique toutes les [!DNL Target] offres depuis `serverState` immédiatement, sans déclencher d’appel réseau sur le [!DNL Target] bord. En outre, at.js prémasque uniquement les éléments DOM pour lesquels [!DNL Target] des offres sont disponibles dans le contenu récupéré côté serveur, ce qui a une incidence positive sur les performances de chargement de page et sur l’expérience de l’utilisateur final.

### Remarques importantes

Consider the following when using `serverState`:

* Actuellement, at.js v2.2 ne prend en charge que la diffusion d’expériences via serverState pour :

   * Activités créées par le compositeur d’expérience visuelle qui sont exécutées au chargement de la page.
   * Vues prérécupérées.

      Dans le cas d’applications monopages utilisant [!DNL Target] des Vues et `triggerView()` dans l’API at.js, at.js v2.2 met en cache le contenu de toutes les Vues prérécupérées côté serveur et les applique dès que chaque Vue est déclenchée par `triggerView()`le biais de, une fois de plus sans déclencher d’appels de récupération de contenu supplémentaires à la Cible.

   * **Remarque**:  Actuellement, les mbox récupérées côté serveur ne sont pas prises en charge dans `serverState`.

* Lors de l’application d’ `serverState `offres, at.js prend en compte `pageLoadEnabled` et `viewsEnabled` les paramètres ; par exemple, les offres de chargement de page ne seront pas appliquées si le `pageLoadEnabled` paramètre est false.

   Pour activer ces paramètres, activez la bascule dans **[!UICONTROL Administration]>[!UICONTROL Implémentation]>[!UICONTROL Modifier]> Chargement de[!UICONTROL page activé.]**

   ![Paramètres de chargement de page activés](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* Si vous utilisez `serverState` et utilisez des balises `<script>` dans le contenu renvoyé, veillez à ce que votre contenu HTML utilise `<\/script>` au lieu de `</script>`le faire. Si vous utilisez `</script>`, le navigateur interprète `</script>` comme la fin d’un SCRIPT intégré et il peut rompre la page HTML.

### Ressources supplémentaires

Pour en savoir plus sur le `serverState` fonctionnement, consultez les ressources suivantes :

* [Exemple de code](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Exemple d’application monopage avec `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
