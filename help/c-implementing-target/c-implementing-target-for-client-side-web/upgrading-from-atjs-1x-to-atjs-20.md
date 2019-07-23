---
description: Mise à niveau à partir d'at. js 1. * x * à at. js 2. * x *
keywords: versions d'at. js ; versions d'at. js ; une seule application ; spa ; cross domain ; interdomaines
seo-description: Informations détaillées sur la mise à niveau d'Adobe Target at. js 1. * x * à at. js version 2.0.0
seo-title: Effectuez une mise à niveau à partir d'Adobe Target at. js version 1.* x * à at. js version 2.*x*
solution: Target
subtopic: Prise en main
title: Mise à niveau à partir d'at. js 1. * x * à at. js 2. * x *
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Upgrading from at.js 1.*x* to at.js 2.*x* {#upgrading-from-atjs-1x-to-atjs-200}

La dernière version d’at.js [!DNL Adobe Target] propose des ensembles de fonctionnalités riches qui permettent à votre entreprise d’exécuter la personnalisation sur les technologies de nouvelle génération côté client. Cette nouvelle version vise à mettre à niveau at.js afin d’établir des interactions harmonieuses avec les applications monopages (SPA).

Here are some benefits of using at.js 2.*x* that are not available in previous versions:

* La capacité à mettre en cache toutes les offres au chargement de la page afin de réduire plusieurs appels serveur à un seul appel serveur.
* Améliorez considérablement les expériences des utilisateurs finaux sur votre site. Les offres s’affichent immédiatement via le cache sans temps de latence que les appels serveur traditionnels imposent.
* Simple ligne de code unique et configuration de développeur ponctuel pour permettre aux marketeurs de créer et d’exécuter des activités A/B et XT via le VEC sur vos applications monopages.

## at.js 2.*x* system diagrams

The following diagrams help you understand the workflow of at.js 2.*x* with Views and how this enhances the SPA integration. To get a better introduction of the concepts used in at.js 2.*x*, see [Single Page Application implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Flux Target avec at. js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

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

![Target flow at. js 2.*x* triggerview](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| L’appel | Détails |
| --- | --- |
| 1 | `triggerView()` est appelée dans l’application d’une seule page pour afficher les vues et appliquer les actions pour modifier les éléments visuels. |
| 2 | Le contenu ciblé pour la vue est lu à partir du cache. |
| 3 | Le contenu ciblé s’affiche aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 4 | La demande de notification est envoyée au magasin de profils [!DNL Target] pour compter le visiteur dans l’activité et incrémenter les mesures. |
| 5 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 6 | Les données Target sont associées aux données Analytics par l’intermédiaire du SDID et sont traitées dans le magasin de rapports Analytics. Il est alors possible de consulter les données Analytics à la fois dans Analytics et Target, par l’intermédiaire des rapports d’A4T. |

## Déployer at.js 2.*x* {#deploy-atjs-200}

1. Déployer at.js 2.*x* via l'extension [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) .

   >[!NOTE]
   >
   > Le déploiement d'at. js à l'aide d'Adobe Launch est la méthode privilégiée.

   OU

   Téléchargez manuellement at. js 2.*x* à l'aide de l'interface utilisateur de Target et déployez-le à l'aide de [la méthode de votre choix](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

## Fonctions d’at.js obsolètes

There are several functions that have been deprecated in at.js 2.*x*.

>[!IMPORTANT]
>
>If these deprecated functions are still used on your site when at.js 2.*x* is deployed, you will see console warnings. The recommended approach when upgrading is to test the deployment of at.js 2.*x* in a staging environment and make sure to go through each and every warning that has been logged in the console and translate the deprecated functions to new functions introduced in at.js 2.*x*.

Les fonctions obsolètes et leurs contreparties sont présentées ci-après. Pour obtenir la liste complète des fonctions, voir [Fonctions at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>at.js 2.** x ne prémasque plus automatiquement les `mboxDefault` éléments marqués. Les clients doivent donc s’adapter manuellement à la logique pré-masquée, soit sur le site, soit via un gestionnaire de balises.

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

**at. js 2.*x*équivalent**

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

**at. js 2.*x*équivalent**:

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

### Suivi des conversions

Les clients qui utilisent `mboxCreate()` le suivi de conversion doivent utiliser `trackEvent()` ou `getOffer()`.

### Présentation des offres

Clients qui ne remplacent `mboxCreate()` pas les `getOffer()` offres ou `applyOffer()` ne les risquent pas.

### Can at. js 2.*x* être utilisé sur certaines pages pendant at. js 1.*x* ou mbox.js se trouve sur d’autres pages ?

Oui, le profil du visiteur est conservé sur plusieurs pages à l’aide de différentes versions et bibliothèques. Le format de cookie est identique.

### New API use in at.js 2.*x*

at.js 2.*x utilise une nouvelle API que nous appelons l’API de diffusion.* Pour déboguer si at.js appelle correctement le serveur [!DNL Target] Edge, vous pouvez filtrer l’onglet Réseau des outils de développement de votre navigateur en « livraison », « `tt.omtrdc.net`, » ou votre code client. Vous remarquerez également que [!DNL Target] envoie une charge utile JSON plutôt que des paires clé-valeur.

### La mbox globale de Target n’est plus utilisée

Dans at.js 2.*x*, vous ne voyez plus « `target-global-mbox` » visible dans les appels réseau. À la place, nous avons remplacé la syntaxe « `target-global-mbox` » par « `execute > pageLoad` » dans la charge utile JSON envoyée aux [!DNL Target] serveurs, comme illustré ci-dessous :

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

### Le nom de la mbox globale dans at.js est-il plus volumineux ?

Les clients peuvent spécifier un nom de mbox globale via [!UICONTROL Target &gt; Configuration &gt; Implémentation &gt; Modifier les paramètres at.js]. Ce paramètre est utilisé par les [!DNL Target] serveurs Edge pour convertir exécuter &gt; pageload en nom de mbox globale, qui apparaît dans [!DNL Target] l’interface utilisateur. Ainsi, les clients peuvent continuer à utiliser les API côté serveur, le compositeur basé sur les formulaires, les scripts de profil et créer des audiences à l’aide du nom de mbox globale. Nous vous recommandons vivement de vous assurer que le même nom de mbox globale est configuré également sur la [!UICONTROL page Configuration &gt; Préférences], au cas où vous auriez toujours des pages utilisant at.js 1.*x* ou mbox.js, comme illustré dans les illustrations suivantes.

![Modification de la boîte de dialogue at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

et

![Mbox globale personnalisée](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

### Does the auto-create global mbox setting need to be turned on for at.js 2.*x*?

Dans la plupart des cas, oui. This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers upon page load. La mbox globale étant traduite pour exécuter &gt; pageload, ce paramètre doit être activé si vous souhaitez déclencher une requête au chargement de la page.

### Will existing VEC activities continue to work, even though the target global mbox name is not specified from at.js 2.*x*?

Oui, car exécuter &gt; pageload est traité sur le [!DNL Target] serveur principal comme `target-global-mbox`.

### Si mes activités basées sur des formulaires sont ciblées sur `target-global-mbox`, ces activités continueront-elles à fonctionner ?

Oui, car exécuter &gt; pageload est traité sur les [!DNL Target] serveurs Edge comme `target-global-mbox`.

### Supported and non-supported at.js 2.*x* Settings

| Paramètre | Pris en charge ? |
| --- | --- |
| X-Domaine | Non |
| Créer automatiquement la mbox globale | Oui |
| Nom de mbox globale | Oui |

### Cross-domain tracking support in at.js 2.x {#cross-domain}

Le suivi inter-domaines permet de regrouper les visiteurs dans différents domaines. Un nouveau cookie devant être créé pour chaque domaine, il est difficile de suivre les visiteurs lorsqu'ils passent du domaine au domaine. To accomplish cross-domain tracking, [!DNL Target] uses a third-party cookie to track visitors across domains. This allows you to create a Target activity that spans `siteA.com` and `siteB.com` and visitors remain in the same experience when they navigate across unique domains. Cette fonctionnalité est liée au comportement des cookies tiers et des cookies de Target.

>[!NOTE]
>
>Le suivi inter-domaines n'est pas pris en charge dans at. js 2.*x*. Le suivi inter-domaines est pris en charge dans at. js 2.*x* via la bibliothèque d'Experience Cloud ID (ECID) version 4.3.0 +.

In Target, the third-party cookie is stored in `<CLIENTCODE>.tt.omtrdc.net`. The first-party cookie is stored in `clientdomain.com`. Première requête de renvoi des en-têtes de réponse HTTP qui tentent de définir des cookies tiers nommés `mboxSession` et `mboxPC` tandis qu’une requête de redirection est renvoyée avec un paramètre supplémentaire (`mboxXDomainCheck=true`). Si le navigateur accepte les cookies tiers, la requête de redirection inclut ces cookies et l'expérience est renvoyée. Ce processus est possible car nous utilisons la méthode HTTP GET.

However, in at.js 2.*x*, HTTP GET is no longer used and instead we use HTTP POST. HTTP POST est désormais utilisé via at. js 2.*x* pour envoyer les charges JSON aux serveurs Target Edge. Cela signifie que la requête de redirection pour vérifier si un navigateur prend en charge les cookies tiers est désormais interrompue. Cela est dû au fait que les requêtes HTTP GET sont des transactions idempotent, tandis que HTTP POST n'est pas un type idempotent et ne doit pas être répété arbitrairement. Par conséquent, le suivi inter-domaines dans at. js 2.*x* n'est plus prise en charge dans la zone. Uniquement at. js 1.*x* dispose de prise en charge prête à l'emploi pour le suivi inter-domaines.

If you want to use cross-domain tracking, you must install the [ECID library v4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) in conjunction with at.js 2.*x*. La bibliothèque ECID existe pour gérer les ID persistants utilisés pour identifier un visiteur même entre domaines. Après avoir installé la bibliothèque ECID v 4.3.0 + et at. js 2.*x*, vous pouvez créer des activités qui s'étendent sur des domaines uniques et effectuer le suivi des utilisateurs.

### La création automatique de la mbox globale est prise en charge

This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers on page-load. Etant donné que la mbox globale est convertie pour exécuter &gt; pageLoad, et que cela est interprété par les serveurs Edge [!DNL Target], les clients doivent activer cette fonction s’ils souhaitent déclencher une requête au moment du chargement de la page.

### Le nom de la mbox globale est pris en charge

Les clients peuvent spécifier un nom de mbox globale via [!UICONTROL Target &gt; Configuration &gt; Implémentation &gt; Modifier les paramètres at.js]. Ce paramètre est utilisé par les serveurs Edge [!DNL Target] pour convertir exécuter &gt; pageLoad en nom de la mbox globale saisi. Cela permet aux clients de continuer à utiliser les API côté serveur, le compositeur basé sur les formulaires, les scripts de profil et de créer les audiences qui ciblent la mbox globale.

### Les événements personnalisés at.js ci-dessous sont-ils applicables à `triggerView()` ou n’est-ce que pour `applyOffer()` ou `applyOffers()` ?

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

Oui, les événements personnalisés at.js s’appliquent à `triggerView()` également.

### Il indique quand j’appelle `triggerView()` avec `{“page” : “true”}`, qu’il enverra une notification au [!DNL Target] principal et augmentera l’impression. Cela entraîne-t-il également l’exécution des scripts de profil ?

Lorsqu’un appel de pré-récupération est effectué au [!DNL Target] principal, les scripts de profil sont exécutés. Ensuite, les données de profil impactées seront chiffrées et retransmises côté client. Après l’appel de `triggerView()` avec `{"page": "true"}`, une notification est envoyée avec les données de profil chiffrées. C’est alors que l’arrière-plan [!DNL Target] déchiffrera les données de profil et les stockera dans les bases de données.

### Devons-nous ajouter un prémasquage du code avant d’appeler `triggerView()` pour gérer le scintillement ?

Non, il n’est pas nécessaire d’ajouter un prémasquage du code avant d’appeler `triggerView()`. at.js 2.*x gère la logique de prémasquage et de scintillement avant l’affichage et l’application de la vue.*

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
>Auto-Target activities are supported through at.js 2.*x* and the VEC when all modifications are applied to the `Page Load Event`. Lorsque des modifications sont ajoutées à des vues particulières, les activités Test A/B, Affectation automatique et Ciblage d’expérience sont uniquement prises en charge.

### Intégrations {#integrations}

| Type | Pris en charge ? |
| --- | --- |
| Analytics for Target (A4T) | Oui |
| Audiences | Oui |
| Attributs du client | Oui |
| Fragments d’expérience AEM | Oui |
| Extension Adobe Launch | [Oui](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| Débogueur | Oui |
| Auditeur | Rules have not yet been updated for at.js 2.*x* |
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

## at.js 1.*paramètres x* à at. js 2.*mappage* de charge utile x {#payload-mapping}

Cette section décrit les mappages entre at.js 1.*x* et at. js 2.*x*.

Avant de passer à la correspondance des paramètres, les points de fin que ces versions de bibliothèque utilisent ont changé :

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2.*x* - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

Une autre différence majeure réside dans le fait que :

* at.js 1.*x* - Le code client fait partie du chemin d’accès
* at.js 2.*x* - Le code client est envoyé comme paramètre de chaîne de requête, par exemple :
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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### `vst.aaaa.id` et `vst.aaaa.authState`

(at.js 1.*x* paramètres)

Les identifiants de client doivent `id > customerIds`être transmis.

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

at.js 2.*x* JSON utile :

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

## Training video: at.js 2.*x* architectural diagram

at.js 2.*x améliore la prise en charge d’applications monopages par Adobe Target et s’intègre aux autres solutions d’Experience Cloud.* Cette vidéo explique comment tout se connecte.

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=fre_fr)

See [Understanding how at.js 2.*x* fonctionne](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) pour plus d'informations.