---
keywords: jetons de réponse;jetons;modules externes;plug-ins;at.js;réponse;sdk web platform;google analytics
description: Découvrez comment utiliser des jetons de réponse dans  [!DNL Adobe Target]  informations spécifiques à la sortie pour le débogage et l’intégration à des outils tiers.
title: Que sont les jetons de réponse et comment les utiliser ?
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: 484971ab0fcd07205935c0fef3ea1484f40c3e96
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 22%

---

# Jetons de réponse

Les jetons de réponse vous permettent de générer automatiquement des informations spécifiques aux [!DNL Adobe Target] sur la page web de votre marque. Ces informations peuvent inclure des détails sur l’activité, l’offre, l’expérience, le profil utilisateur, des informations géographiques, etc. Ces détails fournissent des données de réponse supplémentaires à partager avec des outils internes ou tiers ou à utiliser pour le débogage.

Les jetons de réponse vous permettent de choisir les variables (dans les paires clé-valeur) à utiliser, puis de les autoriser à être envoyées dans le cadre d’une réponse [!DNL Target]. Vous activez une variable à l’aide du commutateur et la variable est envoyée avec des réponses [!DNL Target], qui peuvent être validées dans les appels réseau. Les jetons de réponse fonctionnent également en mode [!UICONTROL Preview].

Une différence essentielle entre les plug-ins et les jetons de réponse réside dans le fait que les plug-ins diffusent JavaScript vers la page qui s’exécute lors de la diffusion. Toutefois, les jetons de réponse fournissent un objet qui peut ensuite être lu et sur lequel il est possible d’agir à l’aide d’écouteurs d’événement. L’approche des jetons de réponse est plus sûre et permet un développement et une maintenance plus faciles des intégrations tierces.

>[!NOTE]
>
>Les jetons de réponse sont disponibles avec at.js version 1.1 ou ultérieure.

| SDK Target | Actions suggérées |
|--- |--- |
| [SDK web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank} | Assurez-vous d’utiliser la version 2.6.0 ou ultérieure de Platform Web SDK. Pour plus d’informations sur le téléchargement de la dernière version de Platform Web SDK, consultez [Installation de SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html){target=_blank} dans le guide *Présentation de Platform Web SDK*. Pour plus d’informations sur les nouvelles fonctionnalités de chaque version de Platform Web SDK, consultez [Notes de mise à jour](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) dans le guide *Présentation de Platform Web SDK*. |
| [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} | Assurez-vous que vous utilisez at.js version 1.1 ou ultérieure. Pour plus d’informations sur le téléchargement de la dernière version d’at.js, voir [Télécharger at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=en){target=_blank}. Pour plus d’informations sur les nouvelles fonctionnalités de chaque version d’at.js, voir [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.<br>Les clients utilisant at.js sont encouragés à utiliser les jetons de réponse et à ne plus utiliser les modules externes. Certains plug-ins qui reposent sur des méthodes internes qui existaient dans mbox.js (désormais obsolète), mais pas dans at.js, sont diffusés, mais échouent. |

## Utilisation de jetons de réponse {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Assurez-vous d’utiliser la version 2.6.0 de Platform Web SDK (ou ultérieure) ou la version 1.1 d’at.js (ou ultérieure).

   Pour plus d’informations :

   * **Platform Web SDK** : consultez la section [Installation de SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) dans le guide *Présentation de Platform Web SDK*.
   * **at.js** : consultez la section [Téléchargement d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html){target=_blank}.

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**.

1. Activez les jetons de réponse souhaités, tels que `activity.id` et `offer.id`.

   Les paramètres suivants sont disponibles par défaut :

   | Type | Paramètre | Remarques |
   |--- |--- |--- |
   | Profils intégrés | `profile.activeActivities` | Renvoie une multitude de `activityIds` pour lesquels le visiteur est qualifié. Elle s’incrémente lorsque les utilisateurs sont qualifiés. Par exemple, sur une page comportant deux requêtes [!DNL Target] fournissant deux activités différentes, la seconde requête inclut les deux activités. |
   |  | `profile.isFirstSession` | Renvoie « true » ou « false ». |
   |  | `profile.isNewSession` | Renvoie « true » ou « false ». |
   |  | `profile.daysSinceLastVisit` | Renvoie le nombre de jours depuis la dernière visite du visiteur. |
   |  | `profile.tntId` | Renvoie le tntID du visiteur. |
   |  | `profile.marketingCloudVisitorId` | Renvoie l’identifiant visiteur Experience Cloud du visiteur. |
   |  | `profile.thirdPartyId` | Renvoie l’identifiant tiers du visiteur. |
   |  | `profile.categoryAffinity` | Renvoie la catégorie préférée du visiteur. |
   |  | `profile.categoryAffinities` | Renvoie un tableau des 5 catégories favorites du visiteur sous la forme de chaînes. |
   | Activité | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | Détails de l’activité courante.<br> Notez que les valeurs des paramètres d’offre sont évaluées au niveau de l’expérience. |
   | Géo | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Pour plus d’informations sur l’utilisation du géociblage dans les activités, voir [Géociblage](/help/main/c-target/c-audiences/c-target-rules/geo.md). |
   | Méthode d’affectation du trafic <br>(s’applique uniquement aux activités [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization].) | `experience.trafficAllocationId` | Renvoie 0 si un visiteur a bénéficié d’une expérience en se trouvant dans le trafic « de contrôle » et 1 si un visiteur a bénéficié d’une expérience dans la distribution du trafic « ciblé ». |
   |  | `experience.trafficAllocationType` | Renvoie « contrôle » ou « ciblé ». |

   Les attributs de profil utilisateur et les attributs du client s’affichent également dans la liste.

   >[!NOTE]
   >
   >Les paramètres dotés de caractères spéciaux ne s’affichent pas dans la liste. Seuls les caractères alphanumériques et les traits de soulignement sont pris en charge.

1. (Conditionnel) Pour utiliser un paramètre de profil comme jeton de réponse, mais comme le paramètre n’a pas été transmis par une requête [!DNL Target] et n’a donc pas été chargé dans l’interface utilisateur de [!DNL Target], vous pouvez utiliser le bouton [!UICONTROL Add Response Token] pour ajouter le profil à l’interface utilisateur.

   Cliquez sur **[!UICONTROL Add Response Token]**, indiquez le nom du jeton, puis cliquez sur **[!UICONTROL Activate]**.

1. Créez une activité.

## Écoute des réponses et lecture des jetons de réponse

Le processus que vous utilisez pour écouter les réponses [!DNL Target] et lire les jetons de réponse diffère selon que vous disposez d’une implémentation [!DNL Platform Web SDK] ou at.js.

### ![Badge Adobe Experience Platform Web SDK](/help/main/assets/platform.png) [!DNL Platform Web SDK] à l’aide de la classe d’objet Handle {#platform-web-sdk}

Utilisez la classe d’objet Handle , qui comporte un objet de métadonnées et un objet de données pour écouter les réponses [!DNL Target] et lire les jetons de réponse.

L’exemple de réponse suivant ajoute un gestionnaire d’événements personnalisé [!DNL Platform Web SDK] directement à la page HTML (le tableau explique les objets utilisés dans le code) :

| Objet | Informations |
| --- | --- |
| Type - Personalization.decision | Si la décision a été prise par le [!DNL Target] ou le fournisseur d’Offer decisioning. |
| DecisionProvider - TGT | TGT-[!DNL Target]. [!DNL Target] fournit les métadonnées et les valeurs du jeton de réponse à la page. |
| Méta | Métadonnées transmises à la page. |
| Données | Valeurs des métadonnées transmises à la page. |

```html
<html>

<head>
 ...
 <script src="alloy.js"></script>
 <script>
  {
   "requestId": "4d0a7cfd-952c-408c-b3b8-438edc38250a",
   "handle": [{
    "type": "personalization:decisions",
    "payload": [{
     "id": "....",
     "scope": "__view__",
     "scopeDetails": {
      "decisionProvider": "TGT",
      "activity": {
       "id": "..."
      },
      "experience": {
       "id": "...."
      }
     },
     "items": [{
      "id": "123",
      "schema": "https://ns.adobe.com/personalization/dom-action",
      "meta": {
       "activity.id": "...",
       "activity.name": "...",
       "profile.foo": "...",
       "profile.bar": "..."
      },
      "data": {
       "id": "123",
       "type": "setHtml",
       "selector": "#foo",
       "prehidingSelector": "#foo",
       "content": "<div>Hello world</div>"
      }
     }]
    }]
   }]
  }
  });
 </script>
</head>

<body>
 ...
</body>

</html>
```

### ![badge at.js](/help/main/assets/atjs.png) at.js avec des événements personnalisés

Utilisez des événements personnalisés [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/atjs-custom-events.html?lang=en){target=_blank} pour écouter la réponse [!DNL Target] et lire les jetons de réponse.

L’échantillon de code suivant ajoute un gestionnaire d’événements personnalisés [!DNL at.js] directement dans la page HTML :

```html
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

## Questions fréquentes sur les jetons de réponse {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**Quel rôle est requis pour activer ou désactiver les jetons de réponse ?**

Les jetons de réponse ne peuvent être activés ou désactivés que par les utilisateurs dotés du rôle [!DNL Target] [!UICONTROL Administrator] .

**Que se passe-t-il si j’exécute [!DNL Platform Web SDK] 2.6.0 (ou une version antérieure) ?**

Vous n’avez pas accès aux jetons de réponse.

**Que se passe-t-il si j’exécute at.js 1.0 (ou version antérieure) ?**

Les jetons de réponse s’affichent, mais at.js ne peut pas les utiliser.

**Puis-je avoir à la fois [!DNL Target Classic] modules externes et des jetons de réponse actifs en même temps ?**

Les plug-ins et les jetons de réponse sont disponibles en parallèle. Cependant, les plug-ins seront abandonnés à l’avenir.

**Les jetons de réponse sont-ils délivrés par le biais de toutes les réponses [!DNL Target] ou uniquement par le biais de réponses [!DNL Target] délivrant une activité ?**

Les jetons de réponse ne sont délivrés que par le biais de réponses [!DNL Target] qui diffusent une activité.

**Mon plug-in [!DNL Target Classic] incluait JavaScript. Comment puis-je reproduire ses fonctionnalités à l’aide des jetons de réponse ?**

Lors de la migration vers des jetons de réponse, ce type de JavaScript doit être conservé dans votre base de code ou votre solution de gestion des balises. Vous pouvez déclencher ce code à l’aide d’événements personnalisés [!DNL Platform Web SDK] ou [!DNL at.js] et transmettre les valeurs du jeton de réponse à vos fonctions JavaScript.

**Pourquoi mon paramètre d’attribut de profil/client ne s’affiche-t-il pas dans la liste des jetons de réponse ?**

[!DNL Target] actualise normalement les paramètres toutes les 15 minutes. Cette actualisation dépend de l’action de l’utilisateur et les données sont actualisées uniquement lorsque vous affichez la page des jetons de réponse. Si vos paramètres ne s’affichent pas dans la liste des jetons de réponse, [!DNL Target] n’a pas encore actualisé les données.

En outre, si votre paramètre ne contient pas de caractères non alphanumériques ou de symboles autres que des traits de soulignement, il n’apparaît pas dans la liste. Actuellement, seuls les caractères alphanumériques et les traits de soulignement sont pris en charge.

**Le jeton de réponse diffuse-t-il toujours du contenu s’il utilise un script de profil supprimé ou un paramètre de profil ?**

Les jetons de réponse extraient des informations des profils utilisateur, puis diffusent ces informations. Si vous supprimez un script ou un paramètre de profil, cela ne signifie pas que les informations ont été supprimées des profils utilisateur. Les profils utilisateur contiennent toujours des données correspondant au script de profil. Le jeton de réponse continue à diffuser le contenu. Pour les utilisateurs et utilisatrices qui n’ont pas ces informations enregistrées dans leurs profils, ou pour les nouveaux visiteurs et visiteuses, ce jeton n’est pas diffusé, car les données ne sont pas présentes dans leurs profils.

[!DNL Target] ne désactive pas automatiquement le jeton. Si vous supprimez un script de profil et que vous ne voulez plus que le jeton soit diffusé, vous devez le désactiver vous-même.

**J’ai renommé mon script de profil, mais pourquoi le jeton utilisant ce script est-il toujours actif avec l’ancien nom ?**

Comme mentionné ci-dessus, les jetons de réponse fonctionnent selon les informations de profil enregistrées pour les utilisateurs. Même si vous avez renommé votre script de profil, la valeur de l’ancien script de profil est enregistrée dans les profils des utilisateurs qui ont visité votre site Web. Le jeton continue à récupérer l’ancienne valeur déjà enregistrée dans les profils utilisateur. Si vous voulez maintenant diffuser du contenu sur le nouveau nom, vous devez désactiver le jeton précédent et activer le nouveau jeton.

**Si mes attributs ont changé, quand seront-ils supprimés de la liste ?**

[!DNL Target] actualise les attributs à intervalles réguliers. Tout attribut qui n’est pas activé est supprimé lors de la prochaine actualisation. Cependant, si vous avez un attribut qui a été activé et supprimé, ce script n’est pas supprimé de la liste des attributs tant que vous ne le désactivez pas. Par exemple, vous avez supprimé un script de profil utilisé comme jeton. [!DNL Target] supprime uniquement les attributs activés de la liste lorsqu’ils sont supprimés ou renommés.

## Envoi de données aux Google Analytics

Les sections suivantes décrivent comment envoyer des données [!DNL Target] aux Google Analytics 4. Les données envoyées par les jetons de réponse peuvent également être envoyées à d’autres intégrations tierces.

### ![Badge AEP](/help/main/assets/platform.png) Envoi de données aux Google Analytics via Platform Web SDK

Il est possible d’envoyer des données aux Google Analytics via la version 2.6.0 (ou ultérieure) de Platform Web SDK en ajoutant le code suivant dans la page d’HTML.

>[!NOTE]
>
>Assurez-vous que la paire clé-valeur du jeton de réponse se trouve sous l’objet `alloy("sendEvent"` .

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
<script type="text/javascript">
    alloy("sendEvent", {
 
 
    })
    .then(({ renderedPropositions, nonRenderedPropositions }) => {
        // concatenate all the propositions
        const propositions = [...renderedPropositions, ...nonRenderedPropositions];
        // extractResponseTokens() extract the meta from item -> meta
        const tokens = extractResponseTokens(propositions);
        const activityNames = [];
        const experienceNames = [];
        const uniqueTokens = distinct(tokens);
    
    
        uniqueTokens.forEach(token => {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });
 
        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });
</script>
```

### ![badge at.js](/help/main/assets/atjs.png) Envoi de données aux Google Analytics via at.js {#section_04AA830826D94D4EBEC741B7C4F86156}

Vous pouvez envoyer des données à Google Analytics par l’intermédiaire d’at.js en ajoutant le code suivant à la page HTML :

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>

<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
        var tokens = e.detail.responseTokens;

        if (isEmpty(tokens)) {
            return;
        }

        var activityNames = [];
        var experienceNames = [];
        var uniqueTokens = distinct(tokens);

        uniqueTokens.forEach(function(token) {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });

        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });

    function isEmpty(val) {
        return (val === undefined || val == null || val.length <= 0) ? true : false;
    }

    function key(obj) {
        return Object.keys(obj)
        .map(function(k) { return k + "" + obj[k]; })
        .join("");
    }

    function distinct(arr) {
        var result = arr.reduce(function(acc, e) {
            acc[key(e)] = e;
            return acc;
        }, {});

        return Object.keys(result)
        .map(function(k) { return result[k]; });
    }
</script>
```

## Débogage

Les sections suivantes fournissent des informations sur le débogage des jetons de réponse :

### ![badge at.js](/help/main/assets/atjs.png) Google Analytics et débogage

Le code suivant permet de déboguer à l’aide de Google Analytics :

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
  
<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
      var tokens = e.detail.responseTokens;
  
      if (isEmpty(tokens)) {
        return;
      }
  
      var activityNames = [];
      var experienceNames = [];
      var uniqueTokens = distinct(tokens);
  
      uniqueTokens.forEach(function(token) {
        activityNames.push(token["activity.name"]);
        experienceNames.push(token["experience.name"]);
      });
  
      gtag('config', 'TAG_ID');
      gtag('event', 'action_name', {'eventCategory': 'target',
          'eventAction': experienceNames, 'eventLabel': activityNames
      });
    });
  
    function isEmpty(val) {
      return (val === undefined || val == null || val.length <= 0) ? true : false;
    }
  
    function key(obj) {
       return Object.keys(obj)
      .map(function(k) { return k + "" + obj[k]; })
      .join("");
    }
  
    function distinct(arr) {
      var result = arr.reduce(function(acc, e) {
        acc[key(e)] = e;
        return acc;
      }, {});
  
      return Object.keys(result)
      .map(function(k) { return result[k]; });
    }
</script>
```

### Débogage à l’aide de l’équivalent du plug-in ttMeta

Vous pouvez créer l’équivalent du module externe ttMeta à des fins de débogage en ajoutant le code suivant à la page HTML :

```javascript
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["offer.id"], 
        'OfferName': token["offer.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## Vidéo de formation ![at.js](/help/main/assets/atjs.png) : jetons de réponse et événements personnalisés at.js {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

La vidéo suivante explique comment utiliser les jetons de réponse et les événements personnalisés at.js pour partager des informations de profil de [!DNL Target] vers des systèmes tiers.

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Setup]) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur. Les informations de la vidéo suivante sont correctes. Toutefois, les options se trouvent à des emplacements légèrement différents.
>
>La vidéo mentionne `option.name` et `option.id`, qui ont été remplacées par `offer.name` et `offer.id`, respectivement.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
