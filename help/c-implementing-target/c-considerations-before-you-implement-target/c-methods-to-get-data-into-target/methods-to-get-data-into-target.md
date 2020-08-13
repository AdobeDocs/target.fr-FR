---
keywords: implement;implementing;setting up;setup;page parameter;tomcat;url encoded;in-page profile attribute;mbox parameter;in-page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;dataprovider;data provider
description: Informations sur les diverses méthodes permettant d’intégrer des données dans Target, y compris les paramètres de page, les attributs de profil internes à la page, les attributs de profil de script, les fournisseurs de données, l’API de mise à jour des profils en masse, l’API de mise à jour de profil individuel et les attributs du client.
title: Méthodes de transfert de données dans Target
feature: implementation general
subtopic: Getting Started
topic: Standard
uuid: a6d64e39-6cdc-49fe-afe5-ecf7dcacf97d
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1940'
ht-degree: 96%

---


# Méthodes de transfert de données dans Target{#methods-to-get-data-into-target}

Informations sur les diverses méthodes permettant d’intégrer des données dans Target, y compris les paramètres de page, les attributs de profil internes à la page, les attributs de profil de script, les fournisseurs de données, l’API de mise à jour des profils en masse, l’API de mise à jour de profil individuel et les attributs du client.

## Paramètres de page (également appelés « paramètres de mbox »){#section_5A297816173C4FE48DC4FE03860CB42B}

Les paramètres de page sont des paires nom/valeur transmises directement par le biais du code de page qui ne sont pas enregistrées dans le profil du visiteur pour une utilisation ultérieure.

Les paramètres de page sont utiles pour envoyer à Target des données de page supplémentaires qui ne doivent pas être enregistrées avec le profil du visiteur pour une utilisation ultérieure dans le cadre du ciblage. Ces valeurs sont utilisées pour décrire la page ou l’action effectuée par l’utilisateur sur cette page spécifique.

### Format

Les paramètres de page sont transmis à Target via un appel au serveur sous la forme d’une paire nom/valeur de chaîne. Les noms et les valeurs de paramètre sont personnalisables (cependant, certains noms sont réservés à des utilisations spécifiques).

Exemples :

* `page=productPage`

* `categoryId=homeLoans`

### Exemples de cas d’utilisation

**Pages de produit** : envoyez les informations relatives au produit spécifique consulté (c’est ainsi que fonctionnent les recommandations).

**Détails de la commande** : envoyez l’identifiant de la commande, orderTotal, etc. pour la collecte de la commande.

**Affinité catégorielle** : envoyez les informations de consultation de catégorie à Target afin de développer la connaissance de l’affinité de l’utilisateur pour des catégories de site particulières.

**Données tierces** : envoyez des informations provenant de sources de données tierces, telles que les fournisseurs de ciblage météo, les fournisseurs de données de compte (par exemple, DemandBase), les fournisseurs de données démographiques (par exemple, Experian), etc.

### Avantages de la méthode

Les données sont envoyées à Target en temps réel et peuvent être utilisées sur le même appel au serveur que celui sur lequel elles ont été transmises.

### Avertissements

* Nécessite une mise à jour du code de page (directement ou par l’intermédiaire d’un système de gestion des balises).
* Si les données doivent être utilisées pour le ciblage sur une page/un appel au serveur ultérieur, elles doivent être converties en script de profil.
* Les caractères contenus dans les chaînes de requête doivent obligatoirement respecter les [standards de l’Internet Engineering Task Force (IETF)](https://www.ietf.org/rfc/rfc3986.txt).

   En plus des caractères mentionnés sur le site de l’IETF, Target autorise l’utilisation des caractères suivants dans les chaînes de requête :

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   Le reste doit être encodé en URL. The standard specifies the following format ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), as illustrated below:

   ![](assets/ietf1.png)

   Ou la liste complète, pour plus de simplicité :

   ![](assets/ietf2.png)

### Exemples de code

targetPageParamsAll (ajoute les paramètres à tous les appels de mbox sur la page) :

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (ajoute les paramètres à la mbox globale sur la page) :

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Paramètres dans le code mboxCreate :

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

### Liens vers les informations connexes

Recommandations : [implémentation selon le type de page](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Confirmation de commande : [suivi des conversions](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Affinité catégorielle : [affinité catégorielle](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)

## Attributs de profil internes à la page (également appelés « attributs de profil internes à la mbox »){#section_57E1C161AA7B444689B40B6F459302B6}

Les attributs de profil internes à la page sont des paires nom/valeur transmises directement par le biais du code de page qui sont enregistrées dans le profil du visiteur pour une utilisation ultérieure.

Les attributs de profil internes à la page permettent d’enregistrer les données spécifiques à l’utilisateur dans le profil de Target pour un ciblage et une segmentation ultérieurs.

### Format

Les attributs de profil internes à la page sont transmis à Target via un appel au serveur sous la forme d’une paire nom/valeur de chaîne précédée du préfixe « profile » .

Les noms et les valeurs d’attribut sont personnalisables (cependant, certains noms sont réservés à des utilisations spécifiques).

Exemples :

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

### Exemples de cas d’utilisation

**Informations de connexion** : partagez les données non personnelles avec Target selon la connexion de l’utilisateur. Il peut par exemple s’agir du statut de membre, de l’historique des commandes ou autres données non personnelles.

**Informations de boutique** : déterminez quelle est la boutique de prédilection de cet utilisateur.

**Interactions précédentes** : effectuez le suivi des activités précédentes de l’utilisateur sur le site afin d’informer la personnalisation ultérieure.

### Avantages de la méthode

Les données sont envoyées à Target en temps réel et peuvent être utilisées sur le même appel au serveur que celui sur lequel elles ont été transmises.

### Avertissements

Nécessite des mises à jour du code de page (directement ou par l’intermédiaire d’un système de gestion des balises).

Les attributs et valeurs sont visibles dans les appels au serveur, ce qui signifie qu’un visiteur peut les voir. Cette approche n’est peut-être pas appropriée si vous partagez des informations telles que des fourchettes de score de crédit ou d’autres informations potentiellement confidentielles.

### Exemples de code

targetPageParamsAll (ajoute les attributs à tous les appels de mbox sur la page) :

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (ajoute les attributs à la mbox globale sur la page) :

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Attributs dans le code mboxCreate :

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

### Liens vers les informations connexes

[Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Profil du visiteur](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)

## Attributs de profil de script {#section_3E27B58C841448C38BDDCFE943984F8D}

Les attributs de profil de script sont des paires nom/valeur définies dans la solution Target. La valeur est déterminée grâce à l’exécution d’un fragment de code JavaScript sur le serveur de Target à chaque appel de serveur.

Les utilisateurs écrivent de petits fragments de code qui s’exécutent à chaque appel de mbox, avant l’évaluation de l’appartenance d’audience et de l’appartenance à une activité d’un visiteur.

### Format

Les attributs de profil de script sont créés dans la section Audiences de Target. Tout nom d’attribut est valide et la valeur est le résultat d’une fonction JavaScript écrite par l’utilisateur de Target. Les noms d’attributs sont automatiquement précédés du préfixe « user. » dans Target pour les distinguer des attributs de profil internes à la page.

Les fragments de code sont écrits dans le langage JavaScript Rhino et peuvent référencer des jetons et d’autres valeurs.

### Exemples de cas d’utilisation

**Abandon de panier** : lorsque le visiteur accède au panier, définissez le script de profil sur 1. Lorsque le visiteur convertit, redéfinissez-le sur 0. Si la valeur = 1, le visiteur a un article dans le panier.

**Nombre de visites** : à chaque nouvelle visite, incrémentez le compteur de 1 pour effectuer le suivi des visites récurrentes d’un visiteur sur le site.

### Avantages de la méthode

Ne nécessite aucune mise à jour du code de page.

S’exécute avant les décisions concernant l’appartenance d’audience et l’appartenance à une activité, ce qui signifie que les attributs de script de profil peuvent affecter l’appartenance sur un appel au serveur unique.

Peut être très robuste. Jusqu’à 2 000 instructions peuvent être exécutées par script.

### Avertissements

Exige la connaissance de JavaScript.

L’ordre d’exécution des scripts de profil ne peut être garanti, ils ne peuvent donc pas dépendre les uns des autres.

Peut être difficile à déboguer.

### Exemples de code

Les scripts de profil sont assez souples :

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### Liens vers les informations connexes

[Attributs de script de profil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)

## Fournisseurs de données {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

L’option Fournisseurs de données est une fonctionnalité qui vous permet de transmettre facilement des données provenant de tiers à Target.

Remarque : La section Fournisseurs de données doit disposer du fichier at.js 1.3 ou d’une version ultérieure.

### Format

Le paramètre `window.targetGlobalSettings.dataProviders` est un tableau de fournisseurs de données.

Pour plus d’informations sur la structure de chaque fournisseur de données, voir [Fournisseurs de données](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Exemples de cas d’utilisation

Collectez des données auprès d’un tiers (par exemple, un service météorologique, une plateforme de gestion des données, ou même votre propre service Web). Vous pouvez ensuite utiliser ces données pour créer des audiences, cibler du contenu et enrichir le profil du visiteur.

### Avantages de la méthode

Ce paramètre permet aux clients de collecter des données auprès de fournisseurs de données tiers tels que Demandbase, BlueKai ou des services personnalisés, et de les transmettre à Target sous forme de paramètres mbox dans la requête globale mbox.

Cette fonction prend en charge la collecte des données en provenance de fournisseurs multiples via des requêtes synchrones et asynchrones.

Cette approche permet de gérer aisément le scintillement du contenu de la page par défaut, tout en incluant des délais d’attente indépendants pour chaque fournisseur afin de limiter l’impact sur les performances de la page

### Avertissements

Si les fournisseurs de données ajoutés à `window.targetGlobalSettings.dataProviders` sont asynchrones, ils sont exécutés en parallèle. La requête d’API Visitor sera exécutée en parallèle avec des fonctions ajoutées à `window.targetGlobalSettings.dataProviders` afin de permettre un temps d’attente minimal.

at.js ne tentera pas de mettre les données en cache. Si le fournisseur de données extrait les données en une seule fois, il doit s’assurer que les données sont mises en cache et que, lorsque la fonction du fournisseur est appelée, les données du cache sont envoyées pour le second appel.

### Exemples de code

Vous trouverez plusieurs exemples dans la section [Fournisseurs de données](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Liens vers les informations connexes

Documentation : [Fournisseurs de données](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

### Vidéos de formation :

* [Utilisation des fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implémenter les fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-technical-video-implement.html)

## API de mise à jour des profils en masse {#section_92AB4820A5624C669D9A1F1B6220D4FA}

L’API permet d’envoyer à Target un fichier .csv contenant les mises à jour des profils d’un grand nombre de visiteurs. Chaque profil du visiteur peut être mis à jour avec plusieurs attributs de profil internes à la page en un seul appel.

Cette option est très similaire à l’option Attributs du client, avec quelques différences :

* Les attributs du client utilisent le transfert FTP, tandis que l’API de mise à jour des profils en masse de Target utilise une API HTTP POST.
* Les données d’attributs du client peuvent être partagées avec Analytics. La mise à jour des profils en masse peut uniquement être utilisée dans Target.
* Les attributs du client prennent en charge la création d’un profil pour un utilisateur que Target n’a pas encore vu. L’API de mise à jour des profils en masse met uniquement à jour les profils Target existants.
* Les attributs du client requièrent l’utilisation de l’Experience Cloud ID (ECID). L’API de mise à jour des profils en masse requiert soit l’ID TNT, soit l’ID `mbox3rdPartyId`.
* Vous ne pouvez pas envoyer les caractères suivants dans `mbox3rdPartyID` : signe plus (+) et barre oblique (/).

### Format

Le fichier .csv doit désigner chaque visiteur par son PCID ou son mboxThirdPartyId Target. L’Experience Cloud ID (ECID) n’est pas pris en charge. Tous les attributs/valeurs de profil sont créés et mis à jour via l’API. Les détails relatifs au format sont disponibles dans la documentation de l’API.

### Exemples de cas d’utilisation

Votre logiciel de gestion de la relation client ou autre système interne stocke des données importantes sur vos visiteurs que vous souhaitez constamment mettre à jour dans Target, sans exposer les données du profil dans l’implémentation de votre page.

### Avantages de la méthode

Nombre d’attributs de profil illimité.

Les attributs de profil envoyés via le site peuvent être mis à jour via l’API et vice versa.

### Avertissements

La taille du fichier de traitement par lot doit être inférieure à 50 Mo. En outre, le nombre total de lignes ne doit pas dépasser 500 000 lignes par téléchargement.

Le nombre de lignes pouvant être téléchargées en lots ultérieurs sur une période de 24 heures est illimité. Cependant, le processus d’assimilation peut être ralenti pendant les heures ouvrables pour s’assurer que les autres processus s’exécutent efficacement.

Les [appels de mise à jour de lots V2](https://developers.adobetarget.com/api/#updating-profiles) consécutifs non espacés par des appels mbox pour le même identifiant tiers remplacent les propriétés mises à jour au premier appel de mise à jour de lots.

### Exemples de code

Voir [Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles).

### Liens vers les informations connexes

[Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles)

## API de mise à jour de profil individuel {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Presque identique à l’API de mise à jour des profils en masse, mais un seul profil du visiteur est mis à jour à la fois, en ligne dans l’appel de l’API plutôt qu’au moyen d’un fichier .csv.

### Format

Le visiteur doit être identifié à l’aide de la valeur mboxPC ou mboxThirdPartyId de Target. L’Experience Cloud ID (ECID) n’est pas pris en charge.

### Exemples de cas d’utilisation

Vous souhaitez mettre à jour Target en temps réel lorsqu’un visiteur effectue une action hors ligne, telle que contacter un centre d’appel, financer un prêt, utiliser une carte de fidélité en boutique, accéder à un kiosque, etc.

### Avantages de la méthode

Nombre d’attributs de profil illimité.

Les attributs de profil envoyés via le site peuvent être mis à jour via l’API et vice versa.

### Avertissements

Limite de 1 000 000 d’appels de l’API (1 million) par période de 24 heures.

Met à jour le profil uniquement. Ne prend pas en charge la création d’un profil pour un utilisateur que Target n’a pas encore vu.

### Exemples de code

Prise en charge des commandes GET et POST. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Liens vers les informations connexes

[Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles)

## Attributs du client {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le chargement effectué, vous pouvez exploiter les données dans Adobe Analytics et Adobe Target.

Les clients Target Standard peuvent utiliser 5 attributs et les clients Target Premium peuvent utiliser 200 attributs.

### Format

Un fichier .csv contenant des Experience Cloud IDs (ECID) et des paires nom/valeur d’attributs est chargé par FTP ou manuellement dans l’interface utilisateur d’Experience Cloud.

### Exemples de cas d’utilisation

Votre logiciel de gestion de la relation client ou autre système interne stocke des informations importantes que vous voulez partager avec la solution Experience Cloud d’Adobe, notamment Target et Analytics.

### Avantages de la méthode

Le chargement des données d’un client crée une entrée de profil pour ce visiteur dans Target, même si Target ne l’a pas encore vu.

Les mêmes données sont automatiquement disponibles dans Target et Analytics.

Le chargement par FTP peut constituer une méthode d’implémentation plus simple que l’API.

### Avertissements

Les clients Target Standard peuvent utiliser 5 attributs et les clients Target Premium peuvent utiliser 200 attributs.

Les valeurs peuvent uniquement être mises à jour par le biais des attributs du client, pas sur la page.

Cette méthode requiert l’implémentation de l’Experience Cloud ID (ECID).

### Exemples de code

Details can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

### Liens vers les informations connexes

[Création d’une source d’attributs du client et transfert du fichier de données](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).