---
keywords: diagramme système;scintillement;at.js;implémentation;bibliothèque javascript;js;atjs
description: Découvrez le fonctionnement de la bibliothèque JavaScript at.js de  [!DNL Target] , y compris celui des diagrammes système pour vous aider à comprendre le workflow lors du chargement des pages.
title: Comment fonctionne la bibliothèque JavaScript at.js ?
feature: at.js
role: Developer
exl-id: 2193c02a-2a85-4ae1-bfbd-40fa7b87f0a0
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 97%

---

# Fonctionnement d’at.js

Pour implémenter [!DNL Adobe Target] côté client, vous devez utiliser la bibliothèque JavaScript at.js.

Dans une implémentation côté client de [!DNL Adobe Target], [!DNL Target] fournit les expériences associées directement à une activité dans le navigateur client. Le navigateur décide de l’expérience à afficher et l’affiche. Avec une implémentation côté client, vous pouvez utiliser un éditeur WYSIWYG, le [compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou une interface non visuelle, le [compositeur d’expérience basé sur les formulaires](/help/main/c-experiences/form-experience-composer.md), pour créer vos expériences de test et de personnalisation.

## Qu’est-ce qu’at.js ?

La Bibliothèque at.js est la nouvelle bibliothèque d’implémentation de Target. La bibliothèque at.js réduit les délais de chargement des pages pour les implémentations web et offre des options d’implémentation optimisées pour les applications d’une seule page. at.js est la bibliothèque d’implémentation recommandée. Elle est régulièrement mise à jour avec de nouvelles fonctionnalités. Nous recommandons à tous les clients de mettre en œuvre la dernière version d’  [at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) ou d’effectuer la migration vers cette dernière.

Pour plus d’informations, voir [Bibliothèques JavaScript Target](/help/main/c-intro/how-target-works.md#libraries).

Dans l’implémentation de [!DNL Target] illustrée ci-dessous, les solutions d’[!DNL Adobe Experience Cloud] suivantes sont mises en œuvre : Analytics, Target et Audience Manager. De plus, les principaux services d’Experience Cloud suivants sont implémentés : [!DNL Adobe Experience Platform], [!DNL Audiences] et [!DNL Visitor ID Service].

## Quelle différence y a-t-il entre les diagrammes de wordkflow at.js 1.*x* et at.js 2.x ?

Voir [Mise à niveau d’at.js 1.x vers at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) pour plus d’informations sur les différences introduites dans la version 2.0 depuis 1.*x*.

D’un point de vu général, il y a quelques différences entre les deux versions :

* at.js 2.x n’a pas de concept de requête de mbox globale, mais plutôt une requête de chargement de page. Une requête de chargement de page peut être vue comme une requête pour récupérer le contenu qui doit être appliqué au chargement initial de la page de votre site Web.
* at.js 2.x gère les concepts de Vues qui sont utilisés pour les applications web monopage (SPA). at.js 1.*x* n’a pas conscience de ce concept.

## Diagrammes at.js 2.x

Les diagrammes suivants vous aident à comprendre le flux de tâches d’at.js 2.x avec les vues et la manière dont cela améliore l’intégration des applications web monopages. Pour une meilleure présentation des concepts utilisés dans at.js 2.x, voir [Implémentation d’applications monopage](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/).

![Flux Target avec at.js 2.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Étape | Détails |
| --- | --- |
| 1 | L’appel renvoie le [!DNL Experience Cloud ID] si l’utilisateur est authentifié. Un autre appel synchronise l’ID de client. |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>at.js peut également être chargé de manière asynchrone avec en option un extrait de code pré-masquant, implémenté sur la page. |
| 3 | Une demande de chargement de page est faite, incluant tous les paramètres configurés (MCID, SDID et ID client). |
| 4 | Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils. Le magasin demande des audiences qualifiées auprès de la bibliothèque d’audiences (par exemple, audiences partagées depuis Adobe Analytics, Gestion de l’audience, etc.).<br>Les attributs du client sont envoyés par lot dans le magasin de profils. |
| 5 | Selon les paramètres de requête d’URL et les données de profil, [!DNL Target] décidez quelles activités et expériences renvoyer au visiteur pour la page active et les futures vues. |
| 6 | Le contenu ciblé est renvoyé à la page, comprenant, éventuellement, les valeurs de profil pour une personnalisation plus poussée.<br>Le contenu ciblé sur la page actuelle est affiché aussi rapidement que possible, sans scintillement du contenu par défaut.<br>Contenu ciblé pour les vues présentées à la suite d’actions de l’utilisateur dans une application d’une seule page cache dans le navigateur, afin qu’elles puissent être appliquées instantanément sans appel au serveur supplémentaire lorsque les vues sont déclenchées `triggerView()`. |
| 7 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 8 | Les données ciblées sont associées aux données d’Analytics par l’intermédiaire du SDID et sont traitées dans le stockage de rapports d’Analytics.<br>Il est alors possible de consulter les données Analytics dans Analytics et dans Target par l’intermédiaire des rapports Analytics for Target (A4T). |

Désormais, là où `triggerView()` est mis en œuvre sur votre application monopage, les actions et les affichages sont récupérés depuis le cache et présentés à l’utilisateur sans appel au serveur. `triggerView()` envoie également une demande de notification au serveur dorsal de [!DNL Target] afin d’incrémenter et d’enregistrer le nombre d’impressions. Pour plus d’informations sur at.js pour les applications monopages avec vues, voir [Implémentation d’application monopage](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/).

![Déclencheur d’affichage at.js 2.x du flux Target](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Étape | Détails |
| --- | --- |
| 1 | `triggerView()` est appelée dans l’application d’une seule page pour afficher les vues et appliquer les actions pour modifier les éléments visuels. |
| 2 | Le contenu ciblé pour la vue est lu à partir du cache. |
| 3 | Le contenu ciblé s’affiche aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 4 | La demande de notification est envoyée au magasin de profils [!DNL Target] pour compter le visiteur dans l’activité et incrémenter les mesures. |
| 5 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 6 | Les données Target sont associées aux données Analytics par l’intermédiaire du SDID et sont traitées dans le magasin de rapports Analytics. Il est alors possible de consulter les données Analytics à la fois dans Analytics et Target, par l’intermédiaire des rapports d’A4T. |

### Vidéo : diagramme architectural d’at.js 2.x

at.js 2.x améliore la prise en charge d’applications monopages par Adobe Target et s’intègre aux autres solutions d’Experience Cloud. Cette vidéo explique comment tout se connecte.

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Pour plus d’informations, consultez la page [Fonctionnement d’at.js 2.x](https://experienceleague.adobe.com/docs/target-learn/tutorials/implementation/understanding-how-atjs-20-works.html?lang=fr).

## Diagramme at.js 1.x

![Flux Target - at.js 1.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/target-flow.png)

| Étape | Description | L’appel | Description |
|--- |--- |--- |--- |
| 1 | L’appel renvoie le [!DNL Experience Cloud ID] (MCID) si l’utilisateur est authentifié ; un autre appel synchronise l’ID de client. | 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document. |
| 3 | Une demande de mbox globale, incluant tous les paramètres configurés (MCID, SDID et ID de client (facultatif)), est envoyée. | 4 | Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils. Le magasin demande des audiences qualifiées auprès de la [!UICONTROL bibliothèque d’audiences] (par exemple, audiences partagées depuis [!DNL Adobe Analytics], [!DNL Audience Manager], etc.).<br>Les attributs du client sont envoyés par lot dans le [!DNL Profile Store] |
| 5 | En fonction de l’URL, des paramètres de mbox et des données de profil, [!DNL Target] décide quelles activités et expériences renvoyer au visiteur. | 6 | Le contenu ciblé est renvoyé à la page, y compris, éventuellement, les valeurs de profil pour une personnalisation plus poussée.<br>L’expérience est affichée aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 7 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. | 8 | Les données [!DNL Target] sont associées aux données [!DNL Analytics] par l’intermédiaire du SDID et sont traitées dans le magasin de rapports [!DNL Analytics].<br>[!DNL Analytics] les données peuvent être vues dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports (A4T) de [!DNL Analytics for Target]. |

### Vidéo : Heures de bureau, conseils et présentation d’at.js (26 juin 2019)

Cette vidéo est un enregistrement de « Office Hours », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Avantages de l’utilisation d’at.js
* Paramètres d’at.js
* Gestion du scintillement
* Débogage d’at.js
* Problèmes connus
* FAQ

>[!VIDEO](https://video.tv.adobe.com/v/27959)

## Comment at.js effectue le rendu des offres avec du contenu HTML {#render}

Lors du rendu des offres avec du contenu HTML, at.js applique l’algorithme suivant :

1. Les images sont préchargées (s’il existe des balises `<img>` dans le contenu HTML).

1. Le contenu HTML est attaché au nœud DOM.

1. Les scripts intégrés sont exécutés (code inclus dans les balises `<script>`).

1. Les scripts distants sont chargés de manière asynchrone et exécutés (`<script>` balises avec les attributs `src`).

Remarques importantes :

* at.js ne fournit aucune garantie quant à l’ordre d’exécution des scripts distants, car ceux-ci sont chargés de manière asynchrone.
* Les scripts intégrés ne doivent pas avoir de dépendances sur les scripts distants, car ils sont chargés et exécutés plus tard.
