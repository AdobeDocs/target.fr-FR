---
description: Mise à niveau d’at.js 1.x vers at.js 2.x
keywords: mises à jour at.js; versions at.js; appli à une seule page, spa
seo-description: Informations détaillées sur la mise à niveau d’Adobe Target at.js 1.x vers at.js version 2.0.0
seo-title: 'Mise à niveau d’Adobe Target at.js version 1.x vers at.js version 2.0.0 '
solution: Target
subtopic: Prise en main
title: Mise à niveau d’at.js 1.x vers at.js 2.x
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Mise à niveau d’at.js 1.x vers at.js 2.x {#upgrading-from-atjs-1x-to-atjs-200}

La dernière version d’at.js [!DNL Adobe Target] propose des ensembles de fonctionnalités riches qui permettent à votre entreprise d’exécuter la personnalisation sur les technologies de nouvelle génération côté client. Cette nouvelle version vise à mettre à niveau at.js afin d’établir des interactions harmonieuses avec les applications monopages (SPA).

Voici quelques avantages de l’utilisation d’at.js 2.x qui ne sont pas disponibles dans les versions précédentes :

* La capacité à mettre en cache toutes les offres au chargement de la page afin de réduire plusieurs appels serveur à un seul appel serveur.
* Améliorez considérablement les expériences des utilisateurs finaux sur votre site. Les offres s’affichent immédiatement via le cache sans temps de latence que les appels serveur traditionnels imposent.
* Simple ligne de code unique et configuration de développeur ponctuel pour permettre aux marketeurs de créer et d’exécuter des activités A/B et XT via le VEC sur vos applications monopages.

## Diagrammes du système at.js 2.x

Les diagrammes suivants vous aident à comprendre le flux de tâches d’at.js 2.x avec les vues et la manière dont cela améliore l’intégration des applications web monopages. Pour une meilleure présentation des concepts utilisés dans at.js 2.x, voir [Implémentation d’applications monopage](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Flux Target avec at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| L’appel | Détails |
| --- | --- |
| 1 | L’appel renvoie le [!DNL Experience Cloud ID] si l’utilisateur est authentifié. Un autre appel synchronise l’ID de client. |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>at.js peut également être chargé de manière asynchrone avec une option pré-masquant l’extrait de code implémenté sur la page. |
| 3 | Une demande de chargement de page est faite, incluant tous les paramètres configurés (MCID, SDID et ID client). |
| 4 | Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils. Le magasin demande des audiences qualifiées auprès de la bibliothèque d’audiences (par exemple, audiences partagées depuis Adobe Analytics, Gestion de l’audience, etc.).<br>Les attributs du client sont envoyés par lot dans le magasin de profils. |
| 5 | Selon les paramètres de requête d’URL et les données de profil, [!DNL Target] décidez quelles activités et expériences renvoyer au visiteur pour la page active et les futures vues. |
| 6 | Le contenu ciblé est renvoyé à la page, comprenant, éventuellement, les valeurs de profil pour une personnalisation plus poussée.<br>Le contenu ciblé sur la page actuelle est affiché aussi rapidement que possible, sans scintillement du contenu par défaut.<br>Contenu ciblé pour les vues présentées à la suite d’actions de l’utilisateur dans une application d’une seule page cache dans le navigateur, afin qu’elles puissent être appliquées instantanément sans appel au serveur supplémentaire lorsque les vues sont `triggerView()` déclenchées. |
| 7 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 8 | Les données ciblées sont associées aux données d’Analytics par l’intermédiaire du SDID et sont traitées dans le stockage de rapports d’Analytics.<br>Il est alors possible de consulter les données Analytics dans Analytics et dans Target par l’intermédiaire des rapports Analytics for Target (A4T). |

Désormais, où que soit implémenté `triggerView()` sur votre application d’une seule page, les vues et actions sont récupérées depuis le cache et présentées à l’utilisateur sans appel au serveur. `triggerView()` envoie également une demande de notification au serveur principal [!DNL Target] afin d’incrémenter et d’enregistrer le nombre d’impressions.

![Déclencheur d’affichage at.js 2 de flux Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| L’appel | Détails |
| --- | --- |
| 1 | `triggerView()` est appelée dans l’application d’une seule page pour afficher les vues et appliquer les actions pour modifier les éléments visuels. |
| 2 | Le contenu ciblé pour la vue est lu à partir du cache. |
| 3 | Le contenu ciblé s’affiche aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 4 | La demande de notification est envoyée au magasin de profils [!DNL Target] pour compter le visiteur dans l’activité et incrémenter les mesures. |
| 5 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 6 | Les données Target sont associées aux données Analytics par l’intermédiaire du SDID et sont traitées dans le magasin de rapports Analytics. Il est alors possible de consulter les données Analytics à la fois dans Analytics et Target, par l’intermédiaire des rapports d’A4T. |

## Déployer at.js 2.x {#deploy-atjs-200}

1. Deploy at.js 2.x via the [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) extension.

   >[!NOTE]
   >
   > Le déploiement d&#39;at. js à l&#39;aide d&#39;Adobe Launch est la méthode privilégiée.

   OU

   Manually download at.js 2.x using the Target UI and deploy it using the [method of your choice](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

## Fonctions d’at.js obsolètes

Il existe plusieurs fonctions obsolètes dans at.js 2.x.

>[!IMPORTANT]
>
>Si ces fonctions obsolètes sont toujours utilisées sur votre site lorsque at.js 2.x est déployé, les avertissements de la console s’affichent. L’approche recommandée lors de la mise à niveau consiste à tester le déploiement d’at.js 2.x dans un environnement d’évaluation et à vérifier que chaque avertissement a été identifié sur la console et traduit les fonctions obsolètes en nouvelles fonctions introduites dans at.js 2.x.

Les fonctions obsolètes et leurs contreparties sont présentées ci-après. Pour obtenir la liste complète des fonctions, voir [Fonctions at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>at.js 2.x ne prémasque plus automatiquement les `mboxDefault` éléments marqués. Les clients doivent donc s’adapter manuellement à la logique pré-masquée, soit sur le site, soit via un gestionnaire de balises.

### mboxCreate(mbox,params)

**Description** :

Exécute une requête et applique l’offre au DIV le plus proche avec le nom de classe `mboxDefault`.

**Exemple** :

```
<div class="mboxDefault">
  default content to replace by offer
</div>
<script>
  mboxCreate('mboxName','param1=value1','param2=value2');
</script>
```

**at.js 2.x équivalent**

Une alternative à `mboxCreate(mbox, params)` est `getOffer()` et `applyOffer()`.

**Exemple** :

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  var el = document.currentScript.previousElementSibling;
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2"
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: el,
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      el.style.visibility = "visible";
    }
  });
</script> 
```

### mboxDefine() et mboxUpdate()

**Description** :

Crée un mappage interne entre un élément et le nom d’une mbox, mais n’exécute pas la demande. Utilisé conjointement avec `mboxUpdate()`, qui exécute la requête et applique l’offre à l’élément identifié par le nodeld dans `mboxDefine()`. Cette fonction peut être également utilisée pour mettre à jour une mbox initiée par `mboxCreate`.

**Exemple** :

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**at.js 2.x équivalent** :

Une alternative à `mboxDefine()` et `mboxUpdate`, est `getOffer()` et `applyOffer()`, avec l’option de sélecteur utilisée dans `applyOffer()`. Cette approche permet de mapper l’offre à un élément à l’aide d’un sélecteur CSS, et pas seulement avec un identifiant.

**Exemple** :

```
<div id="someId" class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2",
      param3: "value3",
      param4: "value4" 
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: "#someId",
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      var el = document.getElementById("someId");
      el.style.visibility = "visible";
    }
  });
</script>
```

### adobe.target.registerExtension()

**Description** :

Propose une méthode standard pour enregistrer une extension spécifique.

Ce paramètre n’est plus pris en charge et ne doit pas être utilisé.

## Résumé des fonctions at.js obsolètes, nouvelles et prises en charge dans 2.0

| Méthode | Pris en charge ? | Nouveau ? | Obsolète ?<br>(Le contenu par défaut s’affiche) |
| --- | --- | --- | --- |
| `getOffer()` | Oui |  |  |
| `getOffers()` |  | Oui |  |
| `applyOffer()` | Oui |  |  |
| `applyOffers()` |  | Oui |  |
| `triggerView()` |  | Oui |  |
| `trackEvent()` | Oui |  |  |
| `mboxCreate()` |  |  | Oui |
| `mboxDefine()`<br>`mboxUpdate()` |  |  | Oui |
| `targetGlobalSettings()` | Oui |  |  |
| `Data Providers` | Oui |  |  |
| `targetPageParams()` | Oui |  |  |
| `targetPageParamsAll()` | Oui |  |  |
| `registerExtension()` |  |  | Oui |
| `At.js Custom Events` | Oui |  |  |

## Limites et légendes

Gardez à l’esprit les limites et légendes suivantes :

**Suivi des conversions**

Les clients qui utilisent `mboxCreate()` le suivi de conversion doivent utiliser `trackEvent()` ou `getOffer()`.

**Présentation des offres**

Clients qui ne remplacent `mboxCreate()` pas les `getOffer()` offres ou `applyOffer()` ne les risquent pas.

**Peut-on utiliser at.js 2.x sur certaines pages pendant que at.js 1.*x*ou mbox.js se trouve sur d’autres pages ?**

Oui, le profil du visiteur est conservé sur plusieurs pages à l’aide de différentes versions et bibliothèques. Le format de cookie est identique.

**Nouvelle utilisation de l’API dans at.js 2.x**

at.js 2.x utilise une nouvelle API que nous appelons l’API de diffusion. Pour déboguer si at.js appelle correctement le serveur [!DNL Target] Edge, vous pouvez filtrer l’onglet Réseau des outils de développement de votre navigateur en « livraison », « `tt.omtrdc.net`, » ou votre code client. Vous remarquerez également que [!DNL Target] envoie une charge utile JSON plutôt que des paires clé-valeur.

**La mbox globale de Target n’est plus utilisée**

Dans at.js 2.x, vous ne voyez plus « `target-global-mbox` » visible dans les appels réseau. À la place, nous avons remplacé la syntaxe « `target-global-mbox` » par « `execute > pageLoad` » dans la charge utile JSON envoyée aux [!DNL Target] serveurs, comme illustré ci-dessous :

```
{
  "id": {
    // ...
  },
  "context": {
    "channel": "web",
    // ...
  },
  "execute": {
    "pageLoad": {}
  }
}
```

Essentiellement, le concept de mbox globale a été introduit pour faire savoir à [!DNL Target] si les offres et le contenu doivent être récupérés au chargement de la page. Cela a donc été plus explicite dans notre nouvelle version.

**Le nom de la mbox globale dans at.js est-il plus volumineux ?**

Les clients peuvent spécifier un nom de mbox globale via [!UICONTROL Target &gt; Configuration &gt; Implémentation &gt; Modifier les paramètres at.js]. Ce paramètre est utilisé par les [!DNL Target] serveurs Edge pour convertir exécuter &gt; pageload en nom de mbox globale, qui apparaît dans [!DNL Target] l’interface utilisateur. Ainsi, les clients peuvent continuer à utiliser les API côté serveur, le compositeur basé sur les formulaires, les scripts de profil et créer des audiences à l’aide du nom de mbox globale. Nous vous recommandons vivement de vous assurer que le même nom de mbox globale est configuré également sur la [!UICONTROL page Configuration &gt; Préférences], au cas où vous auriez toujours des pages utilisant at.js 1.*x* ou mbox.js, comme illustré dans les illustrations suivantes.

![Modification de la boîte de dialogue at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

et

![Mbox globale personnalisée](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

**Le paramètre de la mbox globale créée automatiquement doit-il être activé pour at.js 2.x ?**

Dans la plupart des cas, oui. Ce paramètre indique à at.js 2.x de déclencher une requête aux serveurs [!DNL Target] Edge au chargement de la page. La mbox globale étant traduite pour exécuter &gt; pageload, ce paramètre doit être activé si vous souhaitez déclencher une requête au chargement de la page.

**Les activités du compositeur d’expérience visuelle existantes continueront-elles à fonctionner si le nom de mbox globale cible n’est pas spécifié à partir d’at.js 2.x ?**

Oui, car exécuter &gt; pageload est traité sur le [!DNL Target] serveur principal comme `target-global-mbox`.

**Si mes activités basées sur des formulaires sont ciblées sur`target-global-mbox`, ces activités continueront-elles à fonctionner ?**

Oui, car exécuter &gt; pageload est traité sur les [!DNL Target] serveurs Edge comme `target-global-mbox`.

**Pris en charge et non pris en charge par at.js 2.x**

| Paramètre | Pris en charge ? |
| --- | --- |
| X-Domaine | Non |
| Créer automatiquement la mbox globale | Oui |
| Nom de mbox globale | Oui |

**Le suivi inter-domaines n’est*pas*pris en charge**

Le suivi inter-domaines permet de voir les sessions sur deux sites associés, mais avec des domaines différents, comme une session unique. Vous pouvez créer une [!DNL Target] activité qui s’étend `siteA.com` sur `siteB.com` et où le visiteur reste dans la même expérience lorsqu’il franchit les domaines. Cette fonctionnalité est liée au comportement des cookies tiers et des cookies de Target.

Dans [!DNL Target], les cookies tiers sont stockés dans `[CLIENTCODE].tt.omtrdc.net` et le cookie propriétaire dans `clientdomain.com`. Première requête de renvoi des en-têtes de réponse HTTP qui tentent de définir des cookies tiers nommés `mboxSession` et `mboxPC` tandis qu’une requête de redirection est renvoyée avec un paramètre supplémentaire (`mboxXDomainCheck=true`). Si le navigateur accepte les cookies tiers, la requête de redirection inclut ces cookies et l’offre est renvoyée. Ce processus est possible car nous utilisons la méthode HTTP GET.

Cependant, dans at.js 2.x, HTTP GET n’est plus utilisé et nous utilisons plutôt la méthode HTTP POST. HTTP POST est désormais utilisé via at.js pour envoyer des charges JSON aux serveurs Edge [!DNL Target]. Cela signifie que la requête de redirection pour vérifier si un navigateur prend en charge les cookies tiers est désormais interrompue. Cela est dû au fait que les requêtes HTTP GET sont des transactions idempotentes, tandis que HTTP POST est non idempotent et ne doit pas être répété arbitrairement. Le suivi inter-domaines dans at.js 2.x n’est donc plus pris en charge.

**La création automatique de la mbox globale est prise en charge**

Ce paramètre indique à at.js 2.x de déclencher une requête aux serveurs Edge [!DNL Target] au moment du chargement de la page. Etant donné que la mbox globale est convertie pour exécuter &gt; pageLoad, et que cela est interprété par les serveurs Edge [!DNL Target], les clients doivent activer cette fonction s’ils souhaitent déclencher une requête au moment du chargement de la page.

**Le nom de la mbox globale est pris en charge**

Les clients peuvent spécifier un nom de mbox globale via [!UICONTROL Target &gt; Configuration &gt; Implémentation &gt; Modifier les paramètres at.js]. Ce paramètre est utilisé par les serveurs Edge [!DNL Target] pour convertir exécuter &gt; pageLoad en nom de la mbox globale saisi. Cela permet aux clients de continuer à utiliser les API côté serveur, le compositeur basé sur les formulaires, les scripts de profil et de créer les audiences qui ciblent la mbox globale.

**Les événements personnalisés at.js ci-dessous sont-ils applicables à`triggerView()`ou n’est-ce que pour`applyOffer()`ou`applyOffers()` ?**

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

Oui, les événements personnalisés at.js s’appliquent à `triggerView()` également.

**Il indique quand j’appelle`triggerView()`avec`{“page” : “true”}`, qu’il enverra une notification au[!DNL Target]principal et augmentera l’impression. Cela entraîne-t-il également l’exécution des scripts de profil ?**

Lorsqu’un appel de pré-récupération est effectué au [!DNL Target] principal, les scripts de profil sont exécutés. Ensuite, les données de profil impactées seront chiffrées et retransmises côté client. Après l’appel de `triggerView()` avec `{"page": "true"}`, une notification est envoyée avec les données de profil chiffrées. C’est alors que l’arrière-plan [!DNL Target] déchiffrera les données de profil et les stockera dans les bases de données.

**Devons-nous ajouter un prémasquage du code avant d’appeler`triggerView()`pour gérer le scintillement ?**

Non, il n’est pas nécessaire d’ajouter un prémasquage du code avant d’appeler `triggerView()`. at.js 2.x gère la logique de prémasquage et de scintillement avant l’affichage et l’application de la vue.

## Compatibilité at.js

Les tableaux suivants décrivent at.js. Compatibilité 2.0.0 avec différents types d’activité, intégrations, fonctionnalités et fonctions at.js.

### Types d’activités {#types}

| Type | Pris en charge ? |
| --- | --- |
| Test A/B | Oui |
| Affectation automatique | Oui |
| Ciblage automatique | Oui |
| Ciblage d’expérience | Oui |
| Test multivarié | Oui |
| Automated Personalization | Oui |
| Recommandations | Oui |

>[!NOTE]
>
>Les activités de ciblage automatique sont prises en charge par at.js 2.x et le compositeur d’expérience visuelle lorsque toutes les modifications sont appliquées à `Page Load Event`la fonction. Lorsque des modifications sont ajoutées à des vues particulières, les activités Test A/B, Affectation automatique et Ciblage d’expérience sont uniquement prises en charge.

### Intégrations {#integrations}

| Type | Pris en charge ? |
| --- | --- |
| Analytics for Target (A4T) | Oui |
| Audiences | Oui |
| Attributs du client | Oui |
| Fragments d’expérience AEM | Oui |
| Extension Adobe Launch | [Oui](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| Débogueur | Oui |
| Auditeur | Les règles n’ont pas encore été mises à jour pour at.js 2.x |
| Gestionnaire dynamique de balises | Oui |
| Abonnement | Non. Opt-in support for [GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) is supported in [at.js version 2.1.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| Personnalisation améliorée d’AEM optimisée par Adobe Target | Non |

### Fonctionnalités

| Fonctionnalité | Pris en charge ? |
| --- | --- |
| X-Domaine | Non |
| Propriétés / Espaces de travail | Oui |
| Liens d’assurance qualité | Oui |
| Compositeur d’expérience d’après les formulaires | Oui |
| Compositeur d’expérience visuelle (VEC) | Oui |
| Code personnalisé | Oui |
| Jetons de réponse | [Oui](#response-tokens) |
| Suivi des clics | Oui |
| Diffusion multi-activité | Oui |
| targetGlobalSettings | Oui (mais pas x-domaine) |
| Méthodes at.js | Tout est pris en charge, sauf <br>`mboxCreate()`<br>`mboxUpdate()`<br>`mboxDefine()`<br>qui affichera le contenu par défaut. |

### Paramètres de chaîne de requête

| Paramètre | Pris en charge ? |
| --- | --- |
| `?mboxDisable` | Oui |
| `?mboxDisable` | Oui |
| `?mboxTrace` | Oui |
| `?mboxSession` | Non |
| `?mboxOverride.browserIp` | Non |

## Jetons de réponse {#response-tokens}

at.js 2.*x*, tout comme at.js 1.*x*, utilise l’événement personnalisé `at-request-succeeded` pour les jetons de réponse de surface. Pour des exemples de code utilisant l’événement `at-request-succeeded` personnalisé, voir [Jetons réponse](/help/administrating-target/response-tokens.md).

## Mappage des paramètres at.js 1.x vers at.js 2.x {#payload-mapping}

Cette section décrit les mappages entre at.js 1.*x* et at.js 2.x.

Avant de passer à la correspondance des paramètres, les points de fin que ces versions de bibliothèque utilisent ont changé :

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2.x - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

Une autre différence majeure réside dans le fait que :

* at.js 1.*x* - Le code client fait partie du chemin d’accès
* at.js 2.x - Le code client est envoyé en tant que paramètre de chaîne de requête, tel que :
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

Les sections suivantes répertorient chaque at.js 1.*le* paramètre x, sa description et la charge JSON 2.0.0 correspondante (le cas échéant) :

### at_property

(at.js 1.*x* paramètre)

Utilisé pour [les permissions utilisateur d’entreprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### browserHeight

(at.js 1.*x* paramètre)

Hauteur de la fenêtre du navigateur du visiteur.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "window": {
       "height": 200
    }
  }
}
```

### browserWidth

(at.js 1.*x* paramètre)

Largeur de la fenêtre du navigateur du visiteur.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "window": {
       "width": 200
    }
  }
}
```

### browserTimeOffset

(at.js 1.*x* paramètre)

Décalage du fuseau horaire.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### screenHeight

(at.js 1.*x* paramètre)

Hauteur de l’écran du visiteur.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "screen": {
       "height": 200
    }
  }
}
```

### screenWidth

(at.js 1.*x* paramètre)

Largeur de l’écran du visiteur.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "screen": {
       "width": 200
    }
  }
}
```

### colorDepth

(at.js 1.*x* paramètre)

Intensité des couleurs de l’écran du visiteur.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "screen": {
       "colorDepth": 24
    }
  }
}
```

### mboxHost

(at.js 1.*x* paramètre)

Domaine de la page dans laquelle la bibliothèque Target s’exécute.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "browser": {
       "host": "test.com"
    }
  }
}
```

### webGLRenderer

(at.js 1.*x* paramètre)

Fonctionnalités du rendu WEB GL du navigateur. Ce mécanisme est utilisé par notre mécanisme de détection de périphérique pour déterminer si le périphérique du visiteur est un ordinateur, un iPhone, un périphérique Android, etc.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### mboxURL

(at.js 1.*x* paramètre)

URL de la page.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### mboxReferrer

(at.js 1.*x* paramètre)

Référent de la page.

Charge utile JSON at.js 2.x :

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox (nom) est égal à mbox globale

(at.js 1.*x* paramètre)

L’API de diffusion n’a plus de concept de mbox globale. Dans la charge utile JSON, vous devez utiliser `execute > pageLoad`.

Charge utile JSON at.js 2.x :

```
{
  "execute": {
    "pageLoad": {
       "parameters": ....
       "profileParameters": ...
       .....
    }
  }
}
```

### mbox (nom) n’est *pas* égale à la mbox globale

(at.js 1.*x* paramètre)

Pour utiliser un nom de mbox, transmettez-le `execute > mboxes`. Une mbox requiert un index et un nom.

Charge utile JSON at.js 2.x :

```
{
  "execute": {
    "mboxes": [{
       "index": 0,
       "name": "some-mbox",
       "parameters": ....
       "profileParameters": ...
       .....
    }]
  }
}
```

### mboxId

(at.js 1.*x* paramètre)

N’est plus utilisée.

### mboxCount

(at.js 1.*x* paramètre)

N’est plus utilisée.

### mboxRid

(at.js 1.*x* paramètre)

ID de requête utilisé par les systèmes en aval pour faciliter le débogage.

Charge utile JSON at.js 2.x :

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at.js 1.*x* paramètre)

N’est plus utilisée.

### mboxSession

(at.js 1.*x* paramètre)

L’ID de session est envoyé en tant que paramètre de chaîne de requête (`sessionId`) au point de fin de l’API de diffusion.

### mboxPC

(at.js 1.*x* paramètre)

L’identifiant TNT est transmis `id > tntId`.

Charge utile JSON at.js 2.x :

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.*x* paramètre)

L’identifiant visiteur Experience Cloud est transmis `id > marketingCloudVisitorId`.

Charge utile JSON at.js 2.x :

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### vst.aaaa.id and vst.aaaa.authState

(at.js 1.*x* paramètres)

Les identifiants de client doivent `id > customerIds`être transmis.

Charge utile JSON at.js 2.x :

```
{
  "id": {
    "customerIds": [{
       "id": "1232131",
       "integrationCode": "aaaa",
       "authenticatedState": "....."
     }]
  }
  ....
}
```

### mbox3rdPartyId

(at.js 1.*x* paramètre)

L’identifiant tiers client utilisé pour lier différents identifiants Target.

Charge utile JSON at.js 2.x :

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

(at.js 1.*x* paramètre)

SDID, également appelé identifiant de données supplémentaires. Doit être transmis `experienceCloud > analytics > supplementalDataId`.

Charge utile JSON at.js 2.x :

```
{
  "experienceCloud": {
    "analytics": {
      "supplementalDataId": "1212321132123131"
    }
  }
  ....
}
```

### vst.trk

(at.js 1.*x* paramètre)

Serveur de suivi Analytics. Doit être transmis `experienceCloud > analytics > trackingServer`.

Charge utile JSON at.js 2.x :

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServer": "analytics.test.com"
    }
  }
  ....
}
```

### vst.trks

(at.js 1.*x* paramètre)

Serveur de suivi Analytics sécurisé. Doit être transmis `experienceCloud > analytics > trackingServerSecure`.

Charge utile JSON at.js 2.x :

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServerSecure": "secure-analytics.test.com"
    }
  }
  ....
}
```

### mboxMCGLH

(at.js 1.*x* paramètre)

Conseil d’emplacement d’Audience Manager. Doit être transmis `experienceCloud > audienceManager > locationHint`.

Charge utile JSON at.js 2.x :

```
{
  "experienceCloud": {
    "audienceManager": {
      "locationHint": 9
    }
  }
  ....
}
```

### mboxAAMB

(at.js 1.*x* paramètre)

Blob Audience Manager. Doit être transmis `experienceCloud > audienceManager > blob`.

Charge utile JSON at.js 2.x :

```
{
  "experienceCloud": {
    "audienceManager": {
      "blob": "2142342343242342"
    }
  }
  ....
}
```

### mboxVersion

(at.js 1.*x* paramètre)

La version est envoyée en tant que paramètre de chaîne de requête via le paramètre de version.

## Vidéo de formation : diagramme architectural d’at.js 2.x

at.js 2.x améliore la prise en charge d’applications monopages par Adobe Target et s’intègre aux autres solutions d’Experience Cloud. Cette vidéo explique comment tout se connecte.

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=fre_fr)

See [Understanding how at.js 2.x works](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) for more information.