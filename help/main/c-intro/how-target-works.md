---
keywords: SDK web Adobe Experience Platform;SDK web AEP;SDK AEP;optimisation du moteur de recherche;search engine optimization;seo;clusters edge;clusters centraux;at.js;mbox.js
description: Découvrez le fonctionnement  [!DNL Adobe Target]  et obtenez des informations sur les bibliothèques JavaScript (AEP Web SDK at.js), les stratégies d’utilisation des appels au serveur, l’utilisation de , les centres de données Adobe, les tests d’optimisation du moteur de recherche (SEO) et les robots.
title: Comment fonctionne  [!DNL Target]  ?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 85edad5c3adb3a7b01ee6d1eaf2c30c7596d5f92
workflow-type: tm+mt
source-wordcount: '2214'
ht-degree: 24%

---

# Fonctionnement de [!DNL Adobe Target]

Découvrez comment fonctionne [!DNL Adobe Target] et obtenez des détails sur les bibliothèques JavaScript ([!DNL Adobe Experience Platform Web SDK] et at.js). Cet article couvre également les différents types d’activités que vous pouvez créer, [!DNL Target] les stratégies de comptage de l’utilisation, la [!DNL Target] Edge Network, l’optimisation du moteur de recherche et la détection des robots.

Les points clés sont les suivants :

* **Bibliothèques JavaScript** : découvrez les bibliothèques JavaScript [!DNL Target] : [!DNL Adobe Experience Platform Web SDK] et at.js.
* **Stratégies d’utilisation des appels au serveur** : découvrez comment [!DNL Target] compte divers appels au serveur, y compris les points d’entrée, la mbox unique, la mbox par lots, les appels d’exécution, de prérécupération et de notification.
* **Edge Network** : découvrez comment [!DNL Target] interagit avec le [!DNL Adobe Experience Platform Edge Network].
* **Expérience utilisateur protégée** : découvrez comment [!DNL Adobe] garantit la disponibilité et les performances de son infrastructure de ciblage.
* **Directives SEO** : suivez les bonnes pratiques pour aligner les activités [!DNL Target] sur les directives SEO.
* **Trafic de robots** : découvrez comment Target gère le trafic de robots pour éviter de biaiser les tests et les algorithmes de personnalisation.

## [!DNL Adobe Target] bibliothèques JavaScript {#libraries}

Target s’intègre aux sites web à l’aide de [!DNL Experience Platform Web SDK] ou d’at.js :

* **[Adobe Experience Platform Web SDK ](https://experienceleague.adobe.com/fr/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}** : cette bibliothèque JavaScript côté client permet aux clients [!DNL Adobe Experience Cloud] d’interagir avec divers services via [!DNL Experience Platform Edge Network]. [!DNL Adobe] recommande aux nouveaux clients [!DNL Target] d’implémenter le [!DNL Experience Platform Web SDK] .
* **[at.js](https://experienceleague.adobe.com/fr/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/how-to-deployatjs){target=_blank}** : cette bibliothèque d’implémentation pour [!DNL Target] réduit les temps de chargement des pages pour les implémentations web et offre de meilleures options pour les applications d’une seule page. Mise à jour fréquente avec de nouvelles fonctionnalités, [!DNL Adobe] recommande à tous les utilisateurs d’[at.js d’effectuer la mise à jour vers la dernière version](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

>[!NOTE]
>
>La bibliothèque mbox.js est une implémentation héritée de [!DNL Target] et n’est plus prise en charge après le 31 mars 2021. Effectuez la mise à niveau vers la version [!UICONTROL Experience Platform Web SDK] (préférée) ou la dernière version d’at.js.

Référencez le fichier [!UICONTROL Experience Platform Web SDK] ou at.js sur chaque page de votre site. Par exemple, ajoutez l’une de ces bibliothèques à votre en-tête global. Vous pouvez également utiliser des [balises dans Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/home){target=_blank} pour implémenter [!DNL Target].

Les ressources suivantes contiennent des informations détaillées sur l’implémentation de [!DNL Experience Platform Web SDK] ou d’at.js :

* [[!DNL Adobe Experience Platform Web SDK] Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=fr){target=_blank}
* [Implémentation de  [!DNL Target]  à l’aide d’ [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/fr/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

Chaque fois qu’un visiteur demande une page optimisée pour la [!DNL Target], une requête en temps réel est envoyée au système de ciblage pour déterminer le contenu à diffuser. Cette demande est effectuée et honorée chaque fois qu’une page se charge, selon des activités et des expériences contrôlées par les spécialistes marketing. Le contenu est ciblé sur les visiteurs et visiteuses du site, afin d’optimiser les taux de réponse, les taux d’acquisition et les recettes. Le contenu personnalisé permet de s’assurer que les visiteurs répondent, interagissent ou effectuent des achats.

En [!DNL Target], chaque élément de la page fait partie d’une seule expérience, qui peut inclure plusieurs éléments.

Le contenu affiché dépend du type d’activité que vous créez :

### [!UICONTROL A/B Test]

Dans un test A/B de base, le contenu est choisi de manière aléatoire à partir des expériences attribuées. Vous pouvez définir des pourcentages d’affectation du trafic pour chaque expérience. Au départ, le trafic peut être inégalement réparti en raison d’un fractionnement aléatoire, mais il s’égalise à mesure que le trafic augmente. Par exemple, avec deux expériences, l’expérience de départ est choisie de manière aléatoire. Un trafic faible peut biaiser les pourcentages des visiteurs vers une expérience, mais cette situation s’équilibre avec un trafic plus important.

Spécifiez des cibles en pourcentage pour chaque expérience. Un nombre aléatoire est généré pour sélectionner l’expérience à afficher. Bien que les pourcentages obtenus puissent ne pas correspondre exactement aux cibles, un trafic plus élevé entraîne une répartition plus proche des objectifs cibles.

1. Un client demande une page à votre serveur, qui s’affiche dans son navigateur.
1. Un cookie propriétaire est défini dans le navigateur du client pour stocker son comportement.
1. La page appelle le système de ciblage.
1. Le contenu s’affiche en fonction des règles d’activité.

Pour plus d’informations, consultez [Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] identifie l’expérience gagnante parmi plusieurs options. Il réaffecte ensuite automatiquement davantage de trafic au gagnant, ce qui augmente les conversions à mesure que le test continue à s’exécuter et à apprendre.

Voir [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) pour plus d’informations.

### [!UICONTROL Auto-Target] (AT)

[!UICONTROL Auto-Target] tire parti du machine learning avancé pour choisir parmi plusieurs expériences hautement performantes définies par des spécialistes marketing. [!UICONTROL Auto-Target] offre à chaque visiteur l’expérience la plus adaptée en fonction des profils individuels des clients et du comportement des visiteurs précédents présentant des profils similaires. Utilisez des [!UICONTROL Auto-Target] pour personnaliser le contenu et générer des conversions.

Pour plus d’informations, consultez [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP) combine des offres ou des messages et utilise le machine learning avancé pour faire correspondre différentes variations pour chaque visiteur. AP personnalise le contenu en fonction des profils individuels des clients pour stimuler l’effet élévateur.

Pour plus d’informations, consultez [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### [!UICONTROL Experience Targeting] (XT)

[!UICONTROL Experience Targeting] (XT) diffuse du contenu à des audiences spécifiques en fonction de règles et de critères définis par les spécialistes marketing. En incluant le géociblage, l’XT est utile pour définir des règles qui ciblent des expériences ou du contenu spécifiques pour des audiences particulières. Plusieurs règles peuvent être définies dans une activité afin de fournir différentes variations de contenu à différentes audiences. Lorsque des visiteurs consultent votre site, XT les évalue pour déterminer s’ils répondent aux critères. S’ils remplissent les critères, ils rejoignent l’activité et voient l’expérience qui leur est destinée. Vous pouvez créer des expériences pour plusieurs audiences au sein d’une activité unique.

Pour plus d’informations, consultez [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4).

### [!UICONTROL Multivariate Test] (VMT)

[!UICONTROL Multivariate Testing] (MVT) compare les combinaisons d’offres dans les éléments de page afin de déterminer la combinaison la plus performante pour une audience spécifique. Le test multivarié permet d’identifier l’élément qui a le plus d’effet sur la réussite de l’activité.

Pour plus d’informations, consultez [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499).

### [!UICONTROL Recommendations]

Les activités [!UICONTROL Recommendations] affichent automatiquement les produits ou le contenu susceptibles d’intéresser les clients selon leur activité précédente ou d’autres algorithmes. Les recommandations aident à diriger les clients vers des éléments pertinents qu’ils ne découvriraient pas autrement.

Pour plus d’informations, consultez [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

<!--
## How [!DNL Target] counts server-call usage {#usage}

[!DNL Target] counts only server calls that provide value to customers. The following table shows how [!DNL Target] counts endpoints, single mbox, batch mbox calls, execute, prefetch, and notification calls.

The following information helps you understand the counting strategy used for [!DNL Target] server calls, as shown in the table below:

* **Count Once**: Counts once per API call.
* **Count the Number of mboxes**: Counts the number of mboxes under the array in the payload of a single API call.
* **Ignore**: Is not counted at all.
* **Count the Number of Views (Once)**: Counts the number of views under the array in the payload. In a typical implementation, a view notification has only one view under the notifications array, making this equivalent to counting once in most implementations.

|Endpoint|Fetch type|Options|Counting strategy|
|--- |--- |--- |-- |
|`rest//v1/mbox`|Single|[!UICONTROL execute]|Count once|
|`rest/v2/batchmbox`|Batch|[!UICONTROL execute]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch]|Ignore|
||Batch|[!UICONTROL notifications]|Count the number of mboxes|
|`/ubox/[raw\|image\|page]`|Single|[!UICONTROL execute]|Count once|
|`rest/v1/delivery`<p>`/rest/v1/target-upstream`|Single|[!UICONTROL execute] > [!UICONTROL pageLoad]|Count once|
||Single|[!UICONTROL prefetch] > [!UICONTROL pageLoad]|Ignore|
||Single|[!UICONTROL prefetch] > [!UICONTROL views]|Ignore|
||Batch|[!UICONTROL execute] > [!UICONTROL mboxes]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch] > [!UICONTROL mboxes]|Ignore|
||Batch|[!UICONTROL notifications] > [!UICONTROL views]|Count the number of views (once)|
||Batch|[!UICONTROL notifications] > [!UICONTROL pageLoad]|Count once|
||Batch|[!UICONTROL notifications] > type ([!UICONTROL conversions])|Count once|
||Batch|[!UICONTROL notifications] > [!UICONTROL mboxes]|Count the number of mboxes|

-->

## Le réseau Edge {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Une « Edge » est une architecture de diffusion géographiquement distribuée qui assure des temps de réponse optimaux pour les visiteurs qui demandent du contenu, quel que soit leur emplacement.

Pour améliorer les temps de réponse, les Edges de [!DNL Target] hébergent uniquement la logique d’activité, les profils mis en cache et les informations d’offre.

Les bases de données des activités et du contenu, les données [!DNL Analytics], les API et les interfaces utilisateur des spécialistes du marketing sont hébergées dans [!DNL Adobe] clusters centraux. Des mises à jour sont envoyées aux Edges de [!DNL Target], qui sont automatiquement synchronisées avec les clusters centraux pour mettre à jour en continu les données d’activité mises en cache. Toute la modélisation 1:1 est également stockée sur chaque serveur Edge, ce qui permet aux requêtes complexes d’être traitées localement.

Chaque cluster Edge contient toutes les informations nécessaires pour répondre aux demandes de contenu des visiteurs et pour effectuer le suivi des données d’analyse. Les demandes des visiteurs sont acheminées vers le cluster Edge le plus proche.

Pour plus d’informations, consultez l’article technique [Présentation de la sécurité d’Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

[!DNL Target] est hébergé dans des centres de données détenus et loués par Adobe Adobe dans le monde entier.

Les clusters centraux hébergent des centres de collecte et de traitement des données. Les emplacements des clusters Edge contiennent uniquement des centres de collecte de données. Chaque suite de rapports est affectée à un centre de traitement des données spécifique.

Les données d’activité sur le site du client sont collectées par le plus proche des sept clusters Edge. Ces données sont ensuite dirigées vers une destination prédéfinie du cluster central (Oregon, Dublin ou Singapour) pour traitement. Les données du profil du visiteur sont stockées sur le cluster Edge le plus proche du visiteur. Les clusters Edge comprennent les clusters centraux, ainsi que ceux de Virginie, de Mumbai, de Sydney et de Tokyo.

Au lieu de traiter toutes les requêtes de ciblage à partir d’un seul emplacement, elles sont traitées par le cluster Edge le plus proche du visiteur. Cette approche atténue l’impact du temps de déplacement réseau et Internet.

![Carte présentant les différents types de serveurs Target](/help/main/c-intro/assets/target-servers.png)

Les clusters centraux [!DNL Target], hébergés sur Amazon Web Services (AWS), incluent les suivants :

* Oregon, États-Unis
* Dublin, Irlande
* République de Singapour

Les clusters Edge [!DNL Target], hébergés sur AWS, incluent les suivants :

* Mumbai, Inde
* Tokyo, Japon
* Virginie, États-Unis
* Oregon, États-Unis
* Sydney, Australie
* Dublin, Irlande
* République de Singapour

Le service [!DNL Target Recommendations] est hébergé dans un centre de données [!DNL Adobe] en Oregon.

>[!IMPORTANT]
>
>Il manque actuellement à [!DNL Target] un cluster Edge en Chine, ce qui limite les performances des visiteurs pour les clients [!DNL Target] de la région. Le pare-feu et l’absence de clusters Edge peuvent affecter les expériences du site et ralentir le rendu et les temps de chargement des pages. En outre, les spécialistes marketing peuvent rencontrer une latence lors de l’utilisation de l’interface utilisateur de création [!DNL Target].

Si vous le souhaitez, vous pouvez ajouter des clusters Edge de [!DNL Target] sur liste autorisée. Pour plus d’informations, consultez [Ajout des nœuds Edge de Target sur liste autorisée](https://experienceleague.adobe.com/fr/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}.

## Expérience utilisateur protégée {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] garantit que la disponibilité et la performance de son infrastructure de ciblage sont aussi fiables que possible. Cependant, les répartitions de communication entre le navigateur d’un visiteur et les serveurs [!DNL Adobe] peuvent interrompre la diffusion de contenu.

Pour éviter les interruptions de service et les problèmes de connectivité, tous les emplacements sont configurés pour inclure le contenu par défaut (défini par le client). Ce contenu par défaut s’affiche si le navigateur du visiteur ne parvient pas à se connecter à [!DNL Target].

Aucune modification n’est apportée à la page si le navigateur du visiteur ne parvient pas à se connecter dans un délai d’expiration défini (par défaut : 15 secondes). Si ce seuil de délai est atteint, le contenu de l’emplacement par défaut est affiché.

[!DNL Adobe] protège l’expérience de l’utilisateur en optimisant et en protégeant les performances.

* [!DNL Adobe] garantit des références de performance basées sur les normes du secteur, garanties par la [!UICONTROL Adobe Service Level Agreement].
* Le réseau Edge garantit la diffusion opportune des données.
* [!UICONTROL Adobe] utilise une approche à plusieurs niveaux pour sécuriser ses applications, offrant ainsi aux clients le plus haut niveau de disponibilité et de fiabilité.
* [!DNL Target] Consulting aide à l’implémentation et propose une assistance produit continue.

## Tests adaptés à l’optimisation du moteur de recherche (SEO) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] s’aligne sur les directives des moteurs de recherche pour les tests. [!DNL Google] encourage les tests utilisateur et indique que A/B et [!UICONTROL Multivariate Testing] n’endommage pas les classements des moteurs de recherche organiques si certaines directives sont suivies.

[!DNL Adobe Target] s’aligne sur les directives des moteurs de recherche pour les tests.

Pour plus d’informations, voir les ressources Google suivantes :

* [Test de site web et recherche Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Expériences et cloaking](https://support.google.com/analytics/answer/12979939?hl)


Les directives sont présentées dans une publication de [Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Bien que le billet date de 2012, il reste la déclaration la plus récente de [!DNL Google] sur la question, et les directives sont toujours pertinentes.

* **Pas de cloaking** : le cloaking consiste à afficher un ensemble de contenus aux utilisateurs et un ensemble différent aux robots des moteurs de recherche en identifiant spécifiquement les robots et en leur fournissant un contenu différent.

  [!DNL Target] est configuré de manière à traiter les robots des moteurs de recherche de la même manière que n’importe quel autre utilisateur. Par conséquent, les robots peuvent être inclus dans les activités s’ils sont sélectionnés de manière aléatoire et « voient » les variations de test.

* **Utiliser rel=« canonical »** : il arrive parfois qu’un test A/B nécessite des URL différentes pour les variations. Dans ce cas, toutes les variations doivent inclure une balise rel=« canonical » référençant l’URL d’origine (contrôle). Par exemple, si [!DNL Adobe] teste sa page d’accueil avec différentes URL pour chaque variation, la balise canonique suivante pour la page d’accueil doit être placée dans la balise `<head>` de chaque variation :

  `<link rel="canonical" href="https://www.adobe.com" />`

* **Utiliser les redirections 302 (temporaires)** : lorsque des URL distinctes sont utilisées pour les pages de variation dans un test, [!DNL Google] recommande d’utiliser la redirection 302 pour diriger le trafic vers les variations de test. La redirection 302 informe les moteurs de recherche que la redirection est temporaire et active uniquement pendant l’exécution du test.

  Une redirection 302 est une redirection côté serveur, tandis que la [!DNL Target] et la plupart des fournisseurs d’optimisation utilisent les fonctionnalités côté client. Par conséquent, [!DNL Target] n’est pas entièrement conforme aux recommandations de [!DNL Google] concernant les redirections. Cependant, cela n’affecte qu’une petite partie des tests. L’approche standard pour l’exécution de tests par le biais de [!DNL Target] implique de modifier le contenu dans une seule URL, ce qui élimine le besoin de redirections. Dans les cas où plusieurs URL sont requises pour les variations de test, [!DNL Target] utilise la commande JavaScript `window.location`, qui ne spécifie pas si la redirection est une 301 ou une 302.

  [!DNL Adobe] recherche activement des solutions pour se conformer pleinement aux directives des moteurs de recherche. Pour les clients qui ont besoin d’URL distinctes pour les tests, [!DNL Adobe] pense que l’implémentation correcte des balises canoniques réduit les risques associés.

* **Exécuter des expériences uniquement aussi longtemps que nécessaire** : [!DNL Adobe] définit « aussi longtemps que nécessaire » comme le temps nécessaire pour atteindre une signification statistique. [!DNL Target] propose les bonnes pratiques et le [!DNL Adobe Target] [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) pour déterminer à quel moment votre test a atteint ce point. [!DNL Adobe] recommande d’incorporer l’implémentation en codage en dur des tests concluants dans votre workflow de test et d’allouer les ressources appropriées.

  L’utilisation de [!DNL Target] pour « publier » les tests gagnants n’est pas recommandée en tant que solution à long terme. Si le test gagnant est publié en permanence pour 100 % des utilisateurs, cette approche peut être utilisée temporairement lors du codage en dur du test gagnant.

  Tenez compte de ce que votre test a changé. Les mises à jour mineures, telles que les couleurs des boutons, n’ont aucune incidence sur les classements organiques. Toutefois, les modifications de texte doivent être codées en dur.

  Tenez également compte de l’accessibilité de la page que vous testez. Si la page n’est pas accessible aux moteurs de recherche et n’a jamais été conçue pour être classée dans le référencement organique, ces considérations ne s’appliquent pas. Un bon exemple est une page de destination pour une campagne par e-mail.

Google indique que suivre ces directives « devrait avoir pour vos tests peu voire aucun impact sur votre site dans les résultats de recherche ».

En plus de ces directives, Google présente une directive supplémentaire dans la documentation de leur outil Content Experiments :

* « Vos pages de variation doivent conserver l’esprit du contenu de vos pages originales. Ces variations ne devraient pas changer le sens de la perception générale que vos utilisateurs ont de ce contenu original. »

Google précise à titre d’exemple que « si une page originale d’un site est chargée avec des mots-clés qui ne sont pas associés aux combinaisons présentées aux utilisateurs, nous pouvons supprimer ce site de notre index ».

[!UICONTROL Adobe] estime qu’il serait difficile de modifier involontairement la signification du contenu original dans les variations de test. Cependant, [!UICONTROL Adobe] recommande de connaître les thèmes de mots-clés sur une page et de conserver ces thèmes. Les modifications apportées au contenu d’une page, en particulier l’ajout ou la suppression de mots-clés pertinents, peuvent donner lieu à des changements de classement pour l’URL dans les recherches organiques. [!DNL Adobe] recommande de consulter votre partenaire SEO dans le cadre de votre protocole de test.

## Robots {#bots}

[!DNL Target] utilise la mesure [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) « isRobot » pour détecter les robots connus en fonction de la chaîne de l’agent utilisateur transmise dans l’en-tête de requête.

>[!NOTE]
>
> Pour les requêtes [!DNL Server-Side], la valeur transmise dans le [nœud « Context » de la requête](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) est prioritaire sur la chaîne de l’agent utilisateur pour la détection des robots.

Le trafic identifié comme généré par les robots est toujours diffusé. Les robots sont traités comme des utilisateurs standard afin de s’assurer que [!DNL Target] est conforme aux directives SEO. Cependant, le trafic de robots peut fausser les tests A/B ou les algorithmes de personnalisation s’il est traité comme des utilisateurs normaux. Par conséquent, le trafic de robots connu dans votre activité [!DNL Target] est traité différemment. La suppression du trafic de robots permet de mesurer plus précisément l’activité des utilisateurs et utilisatrices.

Pour le trafic de robots connu, [!DNL Target] ne :

* Ne crée pas ni ne récupère de profil de visiteur
* Consigner les attributs de profil ou exécuter les scripts de profil
* Recherche des segments [!DNL Adobe Audience Manager] (AAM) (le cas échéant)
* Utiliser de trafic de robots dans la modélisation ou la diffusion de contenu personnalisé pour des activités de [!UICONTROL Recommendations], de [!UICONTROL Auto-Target], de [!UICONTROL Automated Personalization] ou de [!UICONTROL Auto-Allocate]
* Ne consigne pas de visite d’activité pour la création de rapports
* Ne consigne pas de données à envoyer à la plateforme [!DNL Adobe Experience Cloud]

Pour le trafic de robots connu, lors de l’utilisation de [!UICONTROL Analytics for Target] (A4T), [!DNL Target] ne :

* d’événements à [!DNL Analytics]

Pour le trafic de robots connu lors de l’utilisation de la journalisation `client_side`, [!DNL Target] ne renvoie pas :

* `tnta payload`
