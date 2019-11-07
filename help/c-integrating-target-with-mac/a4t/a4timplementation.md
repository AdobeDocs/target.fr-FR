---
keywords: A4T;Adobe Analytics;activité basée sur Analytics;suite de rapports Analytics;suite de rapports;intégration d’Analytics Target;configurer une suite de rapports
description: Plusieurs étapes sont requises lors de l’implémentation d’Adobe Analytics en tant que source des rapports pour Target (A4T).
title: Implémentation d’Analytics for Target
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Implémentation d’Analytics for Target{#analytics-for-target-implementation}

Plusieurs étapes sont requises lors de l’implémentation d’Adobe Analytics en tant que source des rapports pour Target (A4T).

## Procédure de mise en œuvre {#section_73961BAD5BB4430A95E073DE5C026277}

Le tableau suivant décrit les étapes requises pour déployer cette intégration sur votre site.

## Étape 1 : demande d’approvisionnement pour Analytics et Target

Après avoir implémenté Analytics en tant que source de création de rapports pour Target, les privilèges d’accès doivent vous avoir été attribués pour Analytics et Target. [Pour ce faire, utilisez ce formulaire](http://www.adobe.com/go/audiences).

## Étape 2 : configuration des autorisations d’utilisateur

Les conditions du compte utilisateur doivent être respectées pour pouvoir créer une activité basée sur Adobe Analytics dans Adobe Target. Voir [Exigences d’autorisation des utilisateurs](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Étape 3 : implémentation du service Identification des visiteurs d’Experience Cloud

Le service Identifiant visiteur permet d’identifier les utilisateurs sur l’ensemble des solutions Experience Cloud. Vous devez mettre en œuvre la version requise de l’identifiant visiteur Experience Cloud ou effectuer la migration vers cette dernière. Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Voir [Mise en œuvre du service d’Experience Cloud ID pour Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) dans la documentation du service d’identification des visiteurs d’Experience Cloud.

## Étape 4 : mise à jour d’AppMeasurement pour JavaScript ou s_code

Vous devez mettre en œuvre la version requise d’appMeasurement.js ou effectuer la migration vers cette dernière. Pour plus d’informations, voir « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Pour les nouvelles implémentations, voir Présentation [de l’implémentation](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) JavaScript dans le Guide *de mise en oeuvre d’* Analytics.

Pour une migration, voir [Migration vers AppMeasurement pour JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) dans le Guide *de mise en oeuvre d’* Analytics.

## Étape 5 : téléchargement et mise à jour at.js ou mbox.js

À l’aide de votre compte de production, vous devez mettre en œuvre la version requise d’at.js ou de mbox.js ou effectuer la migration vers cette dernière. Aucune modification du code n’est requise.

Pour plus d’informations, consultez « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Étape 6 : hôte at.js ou mbox.js

Si vous avez déjà déployé at.js ou mbox.js, vous pouvez remplacer votre fichier existant par la version mise à jour. Pour plus d’informations, voir « Exigences d’implémentation » dans [Avant de procéder à l’implémentation](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Sinon, ce fichier peut être hébergé avec le service Identifiant visiteur et les fichiers AppMeasurement pour JavaScript. Ces fichiers doivent être hébergés sur un serveur web accessible par toutes les pages de votre site. Vous aurez besoin du chemin d’accès à ces fichiers à l’étape suivante.

## Étape 7 : référencement at.js ou mbox.js sur toutes les pages du site {#step7}

Insérez at.js ou mbox.js sous VisitorAPI.js en ajoutant la ligne de code suivante dans la balise de chaque page :

Pour at.js :

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Pour mbox.js :

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

Il est essentiel que VisitorAPI.js soit chargé avant at.js ou mbox.js. Si vous mettez à jour un fichier at.js ou mbox.js existant, veillez à vérifier l’ordre de chargement.

Du point de vue de l’implémentation, les paramètres prêts à l’emploi sont configurés pour l’intégration de Target et d’Analytics en utilisant le SDID transmis depuis la page pour assembler la demande Target et Analytics sur le serveur principal automatiquement pour vous.

Toutefois, si vous souhaitez mieux contrôler la manière et le moment où les données d’analyse liées à Target à Analytics sont envoyées à des fins de création de rapports, et que vous ne souhaitez pas associer automatiquement les données d’analyse à Target et Analytics par le biais du SDID, vous pouvez définir **analyticsLogging = client_side** via **window.targetGlobalSettings**. Remarque : Toutes les versions antérieures à 2.1 ne prennent pas en charge cette approche.

Par exemple :

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Cette configuration a un effet global. Cela signifie que chaque appel effectué par at.js aura **analyticsLogging: "client_side"** envoyé dans les requêtes Target et une charge utile Analytics est renvoyée pour chaque requête. Lors de la configuration, le format de la charge utile renvoyé ressemble à ce qui suit :

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La charge utile peut ensuite être transférée à Analytics via l’API [d’insertion de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)données.

Si un paramètre global n’est pas souhaité et qu’une approche plus à la demande est préférable, vous pouvez utiliser la fonction at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) pour obtenir ce résultat en transmettant **analyticsLogging: "client_side"**. La charge d’analyse est renvoyée pour cet appel uniquement et le serveur principal Target ne transmettra pas la charge utile à Analytics. En poursuivant cette approche, chaque requête Target at.js ne renvoie pas la charge utile par défaut, mais uniquement si elle est souhaitée et spécifiée.

Par exemple :

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

Cet appel appelle une réponse à partir de laquelle vous pouvez extraire la charge utile Analytics.

La réponse ressemble à ce qui suit :

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

La charge utile peut ensuite être transférée à Analytics via l’API [d’insertion de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)données.

## Étape 8 : validation de l’implémentation {#step8}

Chargez vos pages après avoir mis à jour les bibliothèques JavaScript afin de confirmer que les valeurs du paramètre mboxMCSDID dans les appels à Target correspondent à la valeur du paramètre sdid dans l’appel page-view d’Analytics.

Ceci s’avère particulièrement important dans les applications à une seule page, où l’ordre des appels n’est pas toujours prévisible.

**Remarque :** Ces valeurs doivent correspondre pour qu’A4T fonctionne correctement.

## Étape 9 (facultative) : suppression du code d’intégration précédent

Il est recommandé de supprimer l’intégration précédente afin de simplifier la mise en œuvre et d’éliminer la nécessité d’avoir à résoudre les incohérences entre les systèmes. Vous pouvez supprimer tout code que vous pouvez avoir déployé lors d’une intégration SC à T&amp;T précédente, notamment `mboxLoadSCPlugin`.

## Étape 10 : activation des options pour utiliser Analytics en tant que source de création de rapports pour Target

Dans Target, cliquez sur [!UICONTROL Configuration &gt; Préférences] et sélectionnez [!UICONTROL Sélection par activité] ou [!UICONTROL Adobe Analytics] pour activer les options.

* L’option Sélection par activité vous permet de choisir entre Target et Analytics lors de la création de chaque activité.
* L’option Adobe Analytics définit Analytics en tant que source des rapports pour toutes les activités que vous créez.

