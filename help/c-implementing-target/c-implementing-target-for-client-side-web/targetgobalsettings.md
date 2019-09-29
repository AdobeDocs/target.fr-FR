---
description: 'Informations sur la fonction targetGlobalSettings() pour at.js. '
keywords: targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;paramètres globaux;at.js;fonctions;fonction;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders
seo-description: Informations sur la fonction targetGlobalSettings() pour la bibliothèque JavaScript at.js d’Adobe Target.
seo-title: Informations sur la fonction targetGlobalSettings() pour la bibliothèque JavaScript at.js d’Adobe Target.
solution: Target
subtopic: Prise en main
title: targetGlobalSettings()
topic: Standard
translation-type: tm+mt
source-git-commit: bc5acc09c1bc8e412929ad9a0ede8a80b6405d5d

---


# targetGlobalSettings()

Vous pouvez remplacer les paramètres de la bibliothèque at.js à l’aide de `targetGlobalSettings()`, au lieu de configurer les paramètres dans l’interface utilisateur de [!DNL Target] Standard/Premium, ou utiliser des API REST.

Dans certains cas d’utilisation, en particulier lorsque at.js est distribué via la [!DNL Dynamic Tag Management] (DTM), il se peut que vous souhaitiez remplacer certains des paramètres.

## Paramètres {#section_42C759AE9B524A43B8659018677224B8}

Vous pouvez remplacer les paramètres suivants :

| Paramètres | Type | Valeur par défaut | Description |
|--- |--- |--- |--- |
| clientCode | Chaîne | Valeur définie via l’interface utilisateur | Représente le code client |
| serverDomain | Chaîne | Valeur définie via l’interface utilisateur | Représente le serveur Target Edge |
| cookieDomain | Chaîne | Si possible, définissez la valeur sur le domaine de niveau supérieur | Représente le domaine utilisé lors de l’enregistrement de cookies |
| crossDomain | Chaîne | Valeur définie via l’interface utilisateur | Indique si le suivi interdomaine est activé ou non.<br>Les valeurs autorisées sont les suivantes :<ul><li>disabled</li><li>enabled</li><li>x-uniquement</li></ul> |
| timeout | Nombre | Valeur définie via l’interface utilisateur | Représente le délai d’expiration de la demande Target Edge |
| globalMboxAutoCreate | Booléen | Valeur définie via l’interface utilisateur | Indique si la demande de mbox globale doit être déclenchée ou non |
| visitorApiTimeout | Nombre | 2 000 ms = 2 s | Représente le délai d’expiration de la demande de l’API visiteur |
| enabled | Booléen | true | Indique si at.js est activé en tant que bibliothèque, c’est-à-dire s’il doit exécuter quelque chose ou non. Ce paramètre est principalement utilisé pour les cookies d’exclusion ou d’autres décisions personnalisées qui désactivent la fonctionnalité d’at.js |
| defaultContentHiddenStyle | Chaîne | visibility: hidden | Utilisé uniquement pour les mbox d’encapsulation qui font appel à des DIV avec le nom de classe « mboxDefault » et sont exécutées via `mboxCreate()`, `mboxUpdate()`, ou `mboxDefine()` () pour masquer le contenu par défaut |
| defaultContentVisibleStyle | Chaîne | visibility: visible | Utilisé uniquement pour les mbox d’encapsulation qui font appel à des DIV avec le nom de classe « mboxDefault » et sont exécutées via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` pour révéler l’offre appliquée (le cas échéant) ou le contenu par défaut |
| bodyHiddenStyle | Chaîne | body { opacity: 0 } | Utilisé uniquement lorsque `globalMboxAutocreate === true` pour minimiser les risques de scintillement.<br>Pour plus d’informations, voir [Gestion du scintillement par at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md). |
| bodyHidingEnabled | Booléen | true | Utilisé pour contrôler le scintillement lorsque `target-global-mbox` est utilisé pour diffuser des offres créées dans le composition d’expérience visuelle (également appelées offres visuelles) |
| imsOrgId | Chaîne | ID d’entreprise IMS | Représente l’ID d’entreprise IMS |
| secureOnly | Booléen | false | Indique si at.js doit utiliser le protocole HTTPS seulement ou s’il peut permuter entre les protocoles HTTP et HTTPS en fonction du protocole de la page. |
| overrideMboxEdgeServer | Booléen | vrai (vrai commençant par at.js version 1.6.2) | Indique s’il convient d’utiliser le domaine `<clientCode>.tt.omtrdc.net` ou le domaine `mboxedge<clusterNumber>.tt.omtrdc.net`.<br>Si cette valeur est définie sur vrai, le domaine `mboxedge<clusterNumber>.tt.omtrdc.net` sera enregistré dans un cookie. |
| overrideMboxEdgeServerTimeout | Nombre | 1 860 000 =&gt; 31 minutes | Indique la durée de vie du cookie qui contient la valeur `mboxedge<clusterNumber>.tt.omtrdc.net`. |
| optoutEnabled | Booléen | false | Indique si Target doit invoquer la fonction `isOptedOut()` de l’API visiteur. Fait partie de l’activation de Device Graph. |
| selectorsPollingTimeout | Nombre | 5 000 ms = 5 s | Dans at.js 0.9.6, Target présente ce nouveau paramètre qui peut être remplacé via `targetGlobalSettings`.<br>`selectorsPollingTimeout` représente la durée d’attente acceptable du client pour tous les éléments identifiés par les sélecteurs qui s’affichent sur la page.<br>Les activités créées via le compositeur d’expérience visuelle (VEC) comportent des offres qui contiennent des sélecteurs. |
| dataProviders | Voir la section Fournisseurs de données ci-dessous. | Voir la section Fournisseurs de données ci-dessous. | Voir la section Fournisseurs de données ci-dessous. |

## Utilisation {#section_9AD6FA3690364F7480C872CB55567FB0}

Cette fonction peut être définie avant le chargement du fichier at.js ou dans **[!UICONTROL Configuration]** &gt; **[!UICONTROL Mise en œuvre]** &gt; **[!UICONTROL Modifier les paramètres at.js]** &gt; **[!UICONTROL Paramètres des codes]** &gt; **[!UICONTROL En-tête de bibliothèque]**.

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
