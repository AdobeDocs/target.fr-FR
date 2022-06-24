---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;paramètres globaux;at.js;fonctions;fonction;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Personnalisation hybride;deviceIdLifetime
description: Utilisez la fonction targetGlobalSettings() pour l’Adobe [!DNL Target] bibliothèque JavaScript at.js pour remplacer les paramètres au lieu d’utiliser la variable [!DNL Target] API d’interface utilisateur ou REST.
title: Comment utiliser la fonction targetGlobalSettings() ?
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '2419'
ht-degree: 92%

---

# targetGlobalSettings()

Vous pouvez remplacer les paramètres de la bibliothèque at.js à l’aide de `targetGlobalSettings()`, au lieu de configurer les paramètres dans l’interface utilisateur de [!DNL Target] Standard/Premium, ou utiliser des API REST.

## Paramètres {#section_42C759AE9B524A43B8659018677224B8}

Vous pouvez remplacer les paramètres suivants :

### bodyHiddenStyle

* **Type** : String
* **Valeur par défaut** : body { opacity: 0 }
* **Description** : utilisé uniquement lorsque `globalMboxAutocreate === true` pour réduire les risques de scintillement.

   Pour plus d’informations, voir [Gestion du scintillement par at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/){target=_blank}.

### bodyHidingEnabled

* **Type** : booléen
* **Valeur par défaut** : true
* **Description** : utilisé pour contrôler le scintillement lorsque `target-global-mbox` est utilisé pour diffuser des offres créées dans le Compositeur d’expérience visuelle, également appelées offres visuelles.

### clientCode

* **Type** : String
* **Valeur par défaut** : valeur définie via l’interface utilisateur.
* **Description** : représente le code client.

### cookieDomain

* **Type** : String
* **Valeur par défaut** : si possible, définie sur le domaine de niveau supérieur.
* **Description** : représente le domaine utilisé lors de l’enregistrement de cookies.

### crossDomain

* **Type** : String
* **Valeur par défaut** : valeur définie via l’interface utilisateur.
* **Description** : indique si le suivi inter-domaines est activé ou non. Les valeurs autorisées sont les suivantes : désactivé, activé ou x-uniquement.

### cspScriptNonce

* **Type** : consultez la section [Stratégie de sécurité du contenu](#content-security) ci-dessous.
* **Valeur par défaut** : consultez la section [Stratégie de sécurité du contenu](#content-security) ci-dessous.
* **Description** : consultez la section [Stratégie de sécurité du contenu](#content-security) ci-dessous.

### cspStyleNonce

* **Type** : consultez la section [Stratégie de sécurité du contenu](#content-security) ci-dessous.
* **Valeur par défaut** : consultez la section [Stratégie de sécurité du contenu](#content-security) ci-dessous.
* **Description** : consultez la section [Stratégie de sécurité du contenu](#content-security) ci-dessous.

### dataProviders

* **Type** : consultez la section [Fournisseurs de données](#data-providers) ci-dessous.
* **Valeur par défaut** : consultez la section [Fournisseurs de données](#data-providers) ci-dessous.
* **Description** : consultez la section [Fournisseurs de données](#data-providers) ci-dessous.

### decisioningMethod {#on-device-decisioning}

* **Type** : String
* **Valeur par défaut** : côté serveur
* **Autres valeurs** : sur l’appareil, hybride
* **Description** : consultez la section Méthodes de prise de décision ci-dessous.

   **Méthodes de prise de décision**

   Avec la prise de décision sur l’appareil, Target propose un nouveau paramètre appelé [!UICONTROL Méthode de prise de décision], lequel détermine la manière dont at.js diffuse vos expériences. `decisioningMethod` dispose de trois valeurs : côté serveur uniquement, sur l’appareil uniquement et hybride. Lorsque `decisioningMethod` est défini dans `targetGlobalSettings()`, il agit comme méthode de prise de décision par défaut pour toutes les décisions [!DNL Target].

   **[!UICONTROL Côté serveur uniquement]** :

   [!UICONTROL Côté serveur uniquement] est la méthode de prise de décision par défaut préconfigurée lors de l’implémentation et du déploiement d’at.js 2.5+ sur vos propriétés web.

   L’utilisation de [!UICONTROL Côté serveur uniquement] comme configuration par défaut signifie que toutes les décisions sont prises sur le réseau Edge de [!DNL Target], ce qui implique un appel au serveur bloquant. Cette approche peut entraîner une latence incrémentielle, mais elle offre également des avantages significatifs, comme la possibilité d’appliquer les fonctionnalités de machine learning de Target qui incluent les activités [Recommendations](/help/main/c-recommendations/recommendations.md), [Personnalisation automatisée](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) et [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   En outre, l’amélioration de vos expériences personnalisées à l’aide du profil utilisateur de Target, qui est persistant entre les sessions et les canaux, peut fournir des résultats performants pour votre entreprise.

   Enfin, la valeur [!UICONTROL côté serveur uniquement] vous permet d’utiliser Adobe Experience Cloud et d’affiner les audiences qui peuvent être ciblées par le biais des segments d’Audience Manager et d’Adobe Analytics.

   **[!UICONTROL Sur l’appareil uniquement]** :

   [!UICONTROL Sur l’appareil uniquement] est la méthode de prise de décision qui doit être définie dans at.js 2.5+ lorsque la prise de décision sur l’appareil doit uniquement être utilisée sur l’ensemble de vos pages web.

   La prise de décision sur l’appareil permet une diffusion incroyablement rapide de vos expériences et de vos activités de personnalisation. Les décisions sont en effet prises à partir d’un artefact de règles mis en cache qui contient toutes vos activités remplissant les critères de la prise de décision sur l’appareil.

   Pour en savoir plus sur les activités qui remplissent les critères de la prise de décision sur l’appareil, consultez la section relative aux fonctionnalités prises en charge.

   Cette méthode de prise de décision ne doit être utilisée que si les performances sont très critiques sur toutes les pages qui requièrent des décisions de [!DNL Target]. En outre, gardez en tête que lorsque cette méthode de prise de décision est sélectionnée, vos activités [!DNL Target] ne remplissant pas les critères de la prise de décision sur l’appareil ne seront ni diffusées ni exécutées. La bibliothèque at.js version 2.5+ est configurée pour rechercher uniquement l’artefact de règles mis en cache afin de prendre des décisions.

   **Hybride** :

   [!UICONTROL Hybride] représente la méthode de prise de décision qui doit être définie dans at.js 2.5+ lorsque la prise de décision sur l’appareil et les activités nécessitant un appel au réseau Edge d’Adobe Target doivent être exécutées.

   Lorsque vous gérez des activités de prise de décision sur l’appareil et des activités côté serveur, il peut s’avérer un peu compliqué et fastidieux de réfléchir à la manière de déployer et de configurer [!DNL Target] sur vos pages. Avec la méthode de prise de décision hybride, [!DNL Target] sait quand il doit effectuer un appel au serveur vers le réseau Edge d’Adobe Target pour les activités qui nécessitent une exécution côté serveur. Il sait également quand exécuter uniquement les décisions sur l’appareil.

   L’artefact de règles JSON comprend des métadonnées qui indiquent à at.js si une mbox comporte une activité côté serveur en cours d’exécution ou une activité de prise de décision sur l’appareil. Cette méthode de prise de décision garantit que les activités que vous prévoyez de diffuser rapidement sont conduites par le biais de la prise de décision sur l’appareil. Les activités qui nécessitent une personnalisation plus puissante pilotée par ML sont conduites via le réseau Edge d’Adobe Target.

### defaultContentHiddenStyle

* **Type** : String
* **Valeur par défaut** : visibility: hidden
* **Description** : utilisé uniquement pour les mbox d’encapsulation qui font appel à des DIV avec le nom de classe « mboxDefault » et sont exécutées via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` pour masquer le contenu par défaut.

### defaultContentVisibleStyle

* **Type** : String
* **Valeur par défaut** : visibility: visible
* **Description** : utilisé uniquement pour les mbox d’encapsulation qui font appel à des DIV avec le nom de classe « mboxDefault » et sont exécutées via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` pour révéler l’offre appliquée (le cas échéant) ou le contenu par défaut.

### deviceIdLifetime

* **Type** : nombre
* **Valeur par défaut** : 63244800000 ms = 2 ans
* **Description** : la durée de conservation de `deviceId` dans les cookies.

>[!NOTE]
>
>Le paramètre deviceIdLifetime peut être remplacé dans at.js version 2.3.1 ou une version ultérieure.

### enabled

* **Type** : booléen
* **Valeur par défaut** : true
* **Description** : son activation entraîne l’exécution automatique d’une requête [!DNL Target] pour la récupération d’expériences et une manipulation DOM pour le rendu des expériences. De plus, les appels [!DNL Target] peuvent être exécutés manuellement via `getOffer(s)` / `applyOffer(s)`.

   En cas de désactivation, les requêtes [!DNL Target] ne sont pas exécutées automatiquement ou manuellement.

### globalMboxAutoCreate

* **Type** : nombre
* **Valeur par défaut** : valeur définie via l’interface utilisateur.
* **Description** : indique si la demande de mbox globale doit être déclenchée ou non.

### imsOrgId

* **Type** : chaîne
* **Valeur par défaut** : true
* **Description** : représente l’ID d’organisation IMS.

### optinEnabled

* **Type** : booléen
* **Valeur par défaut** : false
* **Description** : [!DNL Target] fournit la prise en charge de la fonctionnalité d’accord préalable par le biais d’[!DNL Adobe Experience Platform]. Cela facilite la mise en application de votre stratégie de gestion du consentement. La fonctionnalité de souscription (opt-in) permet aux clients de décider comment et à quel moment la balise [!DNL Target] est déclenchée. Une autre option permet, toujours par le biais d’[!DNL Adobe Experience Platform], l’approbation préalable de la balise [!DNL Target]. Pour permettre l’utilisation de la fonctionnalité d’accord préalable dans la bibliothèque at.js de [!DNL Target], ajoutez le paramètre `optinEnabled=true`. Dans [!DNL Adobe Experience Platform], vous devez sélectionner « activer » dans la liste déroulante d’[!UICONTROL accord préalable RGPD] dans la vue d’installation de l’extension. Voir [Documentation Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} pour plus d’informations. Pour plus d’informations sur ce paramètre en ce qui concerne les réglementations relatives à la confidentialité et à la protection des données, y compris le Règlement général sur la protection des données (RGPD) de l’Union européenne{target=_blank} et le California Consumer Privacy Act (CCPA), voir [Réglementations relatives à la confidentialité et à la protection des données](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/){target=_blank}.

### optoutEnabled

* **Type** : booléen
* **Valeur par défaut** : false
* **Description** : indique si Target doit invoquer la fonction `isOptedOut()` de l’API visiteur. Fait partie de l’activation de Device Graph.

### overrideMboxEdgeServer

* **Type** : booléen
* **Valeur par défaut** : true (à partir de la version 1.6.2 d’at.js)
* **Description** : indique s’il convient d’utiliser le domaine `<clientCode>.tt.omtrdc.net` ou le domaine `mboxedge<clusterNumber>.tt.omtrdc.net`.

   Si cette valeur est définie sur true, le domaine `mboxedge<clusterNumber>.tt.omtrdc.net` est enregistré dans un cookie. Actuellement, ne fonctionne pas avec [CNAME](https://developer.adobe.com/target/before-implement/implement-cname-support-in-target/){target=_blank} lors de l’utilisation des versions d’at.js antérieures à at.js 1.8.2 et at.js 2.3.1. S’il s’agit d’un problème pour vous, pensez à [mise à jour d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} vers une version plus récente et prise en charge.

### overrideMboxEdgeServerTimeout

* **Type** : nombre
* **Valeur par défaut** : 1860000 => 31 minutes
* **Description** : indique la durée de vie du cookie qui contient la valeur `mboxedge<clusterNumber>.tt.omtrdc.net`.

### pageLoadEnabled

* **Type** : booléen
* **Valeur par défaut** : true
* **Description** : son activation entraîne la récupération automatique des expériences qui doivent être renvoyées au chargement de la page.

### secureOnly

* **Type** : booléen
* **Valeur par défaut** : false
* **Description** : indique si at.js doit uniquement utiliser le protocole HTTPS ou s’il peut permuter entre les protocoles HTTP et HTTPS en fonction du protocole de la page. Lorsque la valeur est définie sur true, secureOnly définit également les attributs Secure et SameSite sur le cookie de la mbox.

### selectorsPollingTimeout

* **Type** : nombre
* **Valeur par défaut** : 5 000 ms = 5 s
* **Description** : dans at.js 0.9.6, [!DNL Target] présente ce nouveau paramètre qui peut être remplacé via `targetGlobalSettings`.

   Le paramètre `selectorsPollingTimeout` représente la durée d’attente acceptable du client pour que tous les éléments identifiés par les sélecteurs s’affichent sur la page.

   Les activités créées via le compositeur d’expérience visuelle (VEC) comportent des offres qui contiennent des sélecteurs.

### serverDomain

* **Type** : String
* **Valeur par défaut** : valeur définie via l’interface utilisateur.
* **Description** : représente le serveur Edge de Target.

### serverState

* **Type** : consultez la section [Personnalisation hybride](#server-state) ci-dessous.
* **Valeur par défaut** : consultez la section [Personnalisation hybride](#server-state) ci-dessous.
* **Description** : consultez la section [Personnalisation hybride](#server-state) ci-dessous.

### telemetryEnabled {#telemetry}

* **Type** : booléen
* **Valeur par défaut** : true
* **Description**: Lorsqu’elle est activée, [!DNL Adobe] collecte les données d’utilisation et de télémétrie des performances des fonctionnalités du SDK. Les données personnelles ne sont pas collectées.

### timeout

* **Type** : nombre
* **Valeur par défaut** : valeur définie via l’interface utilisateur.
* **Description** : représente le délai d’expiration de la requête Edge de [!DNL Target].

### viewsEnabled

* **Type** : booléen
* **Valeur par défaut** : true
* **Description** : son activation entraîne la récupération automatique des vues qui doivent être renvoyées au chargement de la page. Les vues sont prises en charge dans at.js 2.*x* uniquement.

### visitorApiTimeout

* **Type** : nombre
* **Valeur par défaut** : 2 000 ms = 2 s
* **Description** : représente le délai d’expiration de la demande de l’[!UICONTROL API visiteur].

## Utilisation {#section_9AD6FA3690364F7480C872CB55567FB0}

Cette fonction peut être définie avant le chargement du fichier at.js ou dans **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!UICONTROL Modifier les paramètres at.js]** > **[!UICONTROL Paramètres de code]** > **[!UICONTROL En-tête de bibliothèque]**.

Le champ En-tête de bibliothèque vous permet de saisir du code JavaScript de forme libre. Le code de personnalisation doit être similaire au suivant :

```javascript
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## Fournisseurs de données  {#data-providers}

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

```javascript
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

```javascript
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

```javascript
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

## Stratégie de sécurité du contenu {#content-security}

at.js 2.3.0+ prend en charge la définition de nonces pour la stratégie de sécurité du contenu sur les balises SCRIPT et STYLE ajoutées au DOM de la page lors de l’application des offres Target diffusées.

Les nonces des balises SCRIPT et STYLE doivent être respectivement définis dans `targetGlobalSettings.cspScriptNonce` et `targetGlobalSettings.cspStyleNonce` avant le chargement d’at.js 2.3.0+. Découvrez un exemple ci-dessous :

```javascript
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

Une fois les paramètres `cspScriptNonce` et `cspStyleNonce` spécifiés, at.js 2.3.0+ les définit comme attributs de nonces sur toutes les balises SCRIPT et STYLE qu’il ajoute au DOM lors de l’application des offres Target.

## Personnalisation hybride {#server-state}

`serverState` est un paramètre disponible dans at.js v2.2+ qui peut être utilisé pour optimiser les performances des pages lors de l’implémentation d’une intégration hybride de Target. L’intégration hybride signifie que vous utilisez at.js v2.2+ côté client et l’API de diffusion ou un SDK Target côté serveur pour diffuser des expériences. `serverState` permet à at.js v2.2+ d’appliquer des expériences directement à partir du contenu récupéré côté serveur et renvoyé au client dans le cadre de la page diffusée.

### Conditions requises

Vous devez disposer d’une intégration hybride de [!DNL Target].

* **Côté serveur** : vous devez utiliser la nouvelle [API de diffusion](https://developers.adobetarget.com/api/delivery-api/) ou les [SDK Target](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **Côté client**: Vous devez utiliser [at.js version 2.2 ou ultérieure](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

### Exemples de code

Pour mieux comprendre comment cela fonctionne, reportez-vous aux exemples de code ci-dessous que vous trouverez sur votre serveur. Le code suppose que vous utilisez le [SDK Node.js de Target](https://github.com/adobe/target-nodejs-sdk).

```javascript
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

Un exemple d’objet JSON `serverState` pour la prérécupération des vues se présente comme suit :

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

Une fois la page chargée dans le navigateur, at.js applique immédiatement toutes les offres [!DNL Target] provenant de `serverState` sans déclencher d’appels au réseau Edge de [!DNL Target]. En outre, at.js prémasque uniquement les éléments DOM pour lesquels des offres [!DNL Target] sont disponibles dans le contenu récupéré côté serveur. Cela a un impact positif sur les performances de chargement des pages et sur l’expérience de l’utilisateur final.

### Remarques importantes

Veuillez tenir compte des points suivants lors de l’utilisation de `serverState` :

* Actuellement, at.js v2.2 prend uniquement en charge la diffusion d’expériences via serverState pour :

   * Les activités créées par le Compositeur d’expérience visuelle qui sont exécutées au chargement de la page.
   * Les vues prérécupérées.

      Dans le cas de SPA utilisant les vues [!DNL Target] et `triggerView()` dans l’API at.js, at.js v2.2 met en cache le contenu de toutes les vues prérécupérées côté serveur et les applique dès que chaque vue est déclenchée via `triggerView()`. Là encore, il ne déclenche pas d’autres appels de récupération de contenu à Target.

   * **Remarque** : les mbox récupérées côté serveur ne sont actuellement pas prises en charge dans `serverState`.

* Lors de l’application d’offres `serverState `, at.js prend en compte les paramètres `pageLoadEnabled` et `viewsEnabled`. Par exemple, les offres de chargement de page ne sont pas appliquées si le paramètre `pageLoadEnabled` est défini sur false.

   Pour activer ces paramètres, activez la bascule dans **[!UICONTROL Administration] > [!UICONTROL Implémentation] > [!UICONTROL Modifier] > [!UICONTROL Chargement de page activé]**.

   ![Paramètres du chargement de page activé](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* Si vous utilisez `serverState` ainsi que des balises `<script>` dans le contenu renvoyé, veillez à ce que votre contenu HTML utilise `<\/script>` au lieu de `</script>`. Si vous utilisez `</script>`, le navigateur interprète `</script>` comme la fin d’un SCRIPT inséré et il peut interrompre la page HTML.

### Ressources supplémentaires

Pour en savoir plus sur le fonctionnement de `serverState`, consultez les ressources suivantes :

* [Exemple de code](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Exemple d’application monopage (SPA) avec `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
