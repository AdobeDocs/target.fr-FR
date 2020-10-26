---
keywords: Overview and Reference;SEO;search engine optimization;edge clusters, central clusters
description: 'Il est possible d’intégrer Adobe Target à des sites web par le biais d’une de ces deux bibliothèques JavaScript : at.js ou mbox.js'
title: Fonctionnement d’Adobe Target
feature: intro
subtopic: Getting Started
topic: Standard
uuid: 01c0072d-f77d-4f14-935b-8633f220db7b
translation-type: tm+mt
source-git-commit: 02b0bd61d1ba7a591a5b61df36acc5d136e787f0
workflow-type: tm+mt
source-wordcount: '2403'
ht-degree: 82%

---


# Fonctionnement d’Adobe Target

Informations sur le fonctionnement d’Adobe Target, notamment sur les bibliothèques JavaScript Target (at.js et mbox.js) et les différents types d’activité incluses dans Target.

## Bibliothèques JavaScript pour Target {#libraries}

Il est possible d’intégrer Adobe Target à des sites web par le biais d’une de ces deux bibliothèques JavaScript : at.js ou mbox.js

* **at.js :** la [bibliothèque at.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) est la nouvelle bibliothèque d’implémentation de Target. La bibliothèque at.js réduit les délais de chargement des pages pour les implémentations web et offre des options d’implémentation optimisées pour les applications d’une seule page. at.js est la bibliothèque d’implémentation recommandée. Elle est régulièrement mise à jour avec de nouvelles fonctionnalités. Nous recommandons à tous les clients de mettre en œuvre la dernière version d’ [at.js](../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) ou d’effectuer la migration vers cette dernière.
* **mbox.js :** La bibliothèque mbox.js est la bibliothèque d’implémentation héritée pour Target. La bibliothèque mbox.js est toujours prise en charge, mais il n’y aura plus aucune mise à jour des fonctionnalités.

>[!IMPORTANT]
>
>Tous les clients doivent migrer vers at.js. Pour plus d’informations, voir [Migration vers at.js à partir de mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)

Vous devez référencer le fichier de bibliothèques JavaScript pour Target sur chaque page de votre site. Vous pouvez par exemple l’ajouter à votre en-tête global. Vous pouvez également utiliser le [gestionnaire de balises Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md).

Chaque fois qu’un visiteur demande une page qui a été optimisée pour Target, une demande est envoyée au système de ciblage afin de déterminer le contenu à présenter à un visiteur. Ce processus survient en temps réel : chaque fois qu’une page est chargée, une demande de contenu est créée et remplie par le système. Le contenu est régi par les règles des activités et des expériences contrôlées par le spécialiste du marketing et est ciblé sur le visiteur individuel du site. Le contenu est présenté en fonction de ce que à quoi chaque visiteur de site est le plus susceptible de répondre, d’interagir et d’acheter, en vue d’accroître les taux de réponse, les taux d’acquisition et les recettes.

Dans Target, chaque élément de la page fait partie d’une seule expérience pour l’ensemble de la page. Chaque expérience peut inclure plusieurs éléments de la page.

Le contenu affiché aux visiteurs dépend du type d’activité que vous avez créé.

### Test A/B

Pour plus d’informations, voir [Création d’un test AB](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72).

Le contenu qui s’affiche dans un test A/B de base est choisi de façon aléatoire parmi les ressources que vous affectez à l’activité, selon les pourcentages que vous choisissez pour chaque expérience. Suite à ce fractionnement aléatoire du trafic, il se peut qu’il faille beaucoup de trafic initial avant que les pourcentages ne s’équilibrent. Si, par exemple, vous créez deux expériences, l’expérience initiale est choisie de façon aléatoire. Si le trafic est léger, il est possible que le pourcentage des visiteurs puisse être réorienté vers une seule expérience. Quand le trafic augmente, les pourcentages doivent être plus égaux.

Vous pouvez préciser des cibles de pourcentage pour chaque expérience. Dans ce cas, un nombre aléatoire est généré et utilisé pour choisir l’expérience à afficher. Les pourcentages résultants peuvent ne pas correspondre exactement aux cibles spécifiées, mais un trafic plus élevé signifie que les expériences doivent être fractionnées en tenant davantage compte des objectifs de cible.

1. Un client demande une page de votre serveur et l’affiche dans le navigateur.
2. Un cookie propriétaire est défini dans le navigateur du client pour stocker son comportement.
3. La page appelle le système de ciblage.
4. Le contenu s’affiche en fonction des règles de votre activité.

### Affectation automatique

Pour plus d’informations, voir [Affectation automatique](../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

L’affectation automatique identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement du trafic supplémentaire vers l’expérience gagnante afin d’augmenter les conversions pendant que le test se poursuit et apprend.

### Ciblage automatique (AT)

Pour plus d’informations, voir [Ciblage automatique](../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

Le ciblage automatique met à profit l’apprentissage automatique avancé pour effectuer une sélection à partir de plusieurs expériences hautement performantes définies par des responsables du marketing et diffuse l’expérience la plus personnalisée à chaque visiteur selon son profil client et le comportement des visiteurs précédents dotés de profils similaires afin de personnaliser le contenu et de générer des conversions.

### Automated Personalization (AP)

Pour plus d’informations, voir [personnalisation automatisée](../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

Automated Personalization (AP) associe des offres ou des messages et utilise l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur selon leur profil client spécifique afin de personnaliser le contenu et de générer des conversions.

### Ciblage d’expérience (XT)

[Ciblage d’expérience](../c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)

Le ciblage d’expérience (XT) diffuse le contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables du marketing.

Le ciblage d’expérience, qui inclut le géociblage, présente un atout majeur pour la définition de règles ciblant une expérience ou un contenu spécifique pour une audience particulière. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes. Lorsque des visiteurs consultent votre site, le ciblage d’expérience les évalue pour déterminer s’ils répondent aux critères définis. S’ils correspondent aux critères, ils entrent dans l’activité et l’expérience pour l’audience éligible. Vous pouvez créer des expériences pour plusieurs audiences au sein d’une activité unique.

### Test multivarié (MVT)

Voir [Test multivarié](../c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) pour en savoir plus.

Le test multivarié (MVT) compare des combinaisons d’offres d’éléments sur une page afin de déterminer la combinaison offrant les meilleures performances pour une audience spécifique. Il identifie l’élément qui impacte le plus le succès de l’activité.

### Recommandations

Pour plus d’informations, voir [Recommandations](../c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

Les activités de recommandations affichent automatiquement les produits ou le contenu susceptibles d’intéresser vos clients selon l’activité précédente de l’utilisateur ou d’autres algorithmes. Les recommandations aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.

## The edge network {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Un &quot;Edge&quot; est une architecture de diffusion géographiquement distribuée qui garantit des temps de réponse optimaux aux aux utilisateurs finaux qui demandent du contenu, quel que soit leur emplacement sur le globe.

Pour améliorer les temps de réponse, l’hôte Contours de la Cible n’héberge que la logique d’activité, les profils mis en cache et les informations d’offre.

Activity and content databases, [!DNL Analytics] data, APIs, and marketer user interfaces are housed in Adobe’s Central Clusters. Les mises à jour sont ensuite envoyées aux arêtes de Cible. Les grappes centrales et les grappes d&#39;arête sont automatiquement synchronisées afin de continuellement mettre à jour les données d&#39;activité mises en cache. La modélisation 1:1 est également stockée sur chaque bord, de sorte que les requêtes les plus complexes puissent également être traitées sur le bord.

Chaque cluster Edge contient toutes les informations nécessaires pour répondre à la demande de contenu de l’utilisateur et pour effectuer le suivi des données d’analyse sur cette demande. Les demandes des utilisateurs sont acheminées vers le cluster Edge le plus proche.

Pour plus d’informations, consultez le livre blanc [Adobe Target Security Overview](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

The [!DNL Adobe Target] solution is hosted on Adobe-owned and Adobe-leased data centers around the globe.

Les emplacements de cluster Central contiennent à la fois un centre de collecte de données et un centre de traitement des données. Les emplacements Edge Cluster ne contiennent qu’un centre de collecte de données. Chaque suite de rapports est affectée à un centre de traitement des données spécifique.

Les données d’activité sur le site du client sont collectées par le plus proche des sept clusters Edge et dirigées vers la destination de cluster central prédéfinie d’un client (l’un des trois emplacements suivants : Oregon, Dublin, Singapour) pour le traitement. Les données de profil visiteur sont stockées sur le cluster Edge le plus proche du visiteur du site (les emplacements comprennent les emplacements de cluster Central et Virginia, Amsterdam, Sydney, Tokyo et Hong Kong).

Plutôt que de répondre à toutes les requêtes de ciblage provenant d’un seul emplacement, les requêtes sont traitées par le cluster Edge le plus proche du visiteur, ce qui réduit l’impact du temps de déplacement réseau/Internet.

![Types de mappage des serveurs de Cible](/help/c-intro/assets/target-servers.png)

Les grappes de cible Central, hébergées sur Amazon Web Services (AWS), se trouvent dans :

* Oregon, États-Unis
* Dublin, Irlande
* République de Singapour

Les grappes Edge de cible, hébergées sur AWS, se trouvent dans :

* Mumbai, Inde
* Tokyo, Japon
* Virginie, États-Unis
* Oregon, États-Unis
* Sydney, Australie
* Dublin, Irlande
* République de Singapour

Le [!DNL Target Recommendations] service est hébergé dans un centre de [!DNL Adobe] données de l&#39;Oregon.

>[!IMPORTANT]
>
>[!DNL Adobe Target] actuellement, il n’y a pas de cluster Edge en Chine et les performances des utilisateurs finaux continueront d’être limitées pour [!DNL Target] les clients en Chine. Because of the firewall and the lack of Edge Clusters within the country, the experiences of sites with [!DNL Target] deployed will be slow to render and page loads will be affected. Also, marketers might experience latency when using the [!DNL Target] authoring UI.

Si vous le souhaitez, vous pouvez placer sur la liste autorisée des grappes de Cible Edge. Pour plus d’informations, voir Noeuds [de bord de la Cible de](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md)liste autorisée.

## Protected user experience {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe garantit que la disponibilité et la performance de l’infrastructure de ciblage sont aussi fiables que possible. Toutefois, la répartition des communications entre le navigateur d’un utilisateur et les serveurs d’Adobe peuvent interrompre la diffusion de contenu.

Afin d’éviter les interruptions de service et les problèmes de connectivité, tous les emplacements sont configurés afin d’inclure le contenu par défaut (défini par le client), qui est affiché si le navigateur de l’utilisateur ne parvient pas à se connecter à [!DNL Target].

Aucune modification n’est apportée à la page si le navigateur de l’utilisateur ne peut pas se connecter au cours du délai d’attente défini (par défaut, 15 secondes). Si ce seuil de délai est atteint, le contenu de l’emplacement par défaut est affiché.

Adobe protège l’expérience de l’utilisateur en optimisant et en protégeant les performances.

* Adobe procède aux benchmarks de performances en fonction des normes de l’industrie, qui sont garanties par le contrat de niveau de service d’Adobe.
* Le réseau Edge garantit la diffusion opportune des données.
* Adobe sécurise ses applications en appliquant une approche à plusieurs niveaux afin de fournir aux utilisateurs le plus haut niveau possible de disponibilité et de fiabilité.
* [!DNL Target] Consulting aide à l’implémentation et propose une assistance produit continue.

## Tests adaptés à l’optimisation du référencement {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] s’aligne sur les directives des moteurs de recherche pour les tests.

Google encourage les utilisateurs à tester et a indiqué dans sa documentation que les tests A/B et multivariés ne nuisent pas aux classements des moteurs de recherche organiques tant qu’un petit nombre de directives simples sont suivies.

Pour plus d’informations, voir les ressources Google suivantes :

* [Test de site web et recherche Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Expériences et cloaking](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

Les directives sont présentées dans une publication de [Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Bien que la publication date de 2012, elle rappelle les instructions les plus récentes de Google sur le sujet et les directives continuent de s’appliquer.

* **Aucun cloaking** : le cloaking consiste à montrer un ensemble de contenus à vos utilisateurs et un ensemble différent de contenus aux robots des moteurs en les identifiant spécifiquement et en les alimentant volontairement avec un contenu différent.

   Target, en tant que plateforme, a été configurée pour traiter ces robots de moteurs de recherche de la même façon que n’importe quel autre utilisateur. Cela signifie que les robots peuvent être inclus dans les tests que vous exécutez, si leur sélection est aléatoire, et « voir » les variations de test.

* **Utiliser rel=&quot;canonical&quot;** : il arrive parfois qu’un test A/B ait besoin d’être configuré à l’aide d’URL différentes pour les variations. Dans ces instances, toutes les variations doivent comporter la balise `rel="canonical"` qui fait référence à l’URL d’origine (contrôle). Par exemple, si Adobe testait sa page d’accueil à l’aide de différentes URL pour chaque variation, la balise canonique suivante pour la page d’accueil serait placée dans la balise `<head>` pour chacune des variations :

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Utiliser les redirections 302 (temporaires)** : dans les instances où les URL distinctes sont utilisées pour les pages de variation dans un test, Google recommande d’utiliser la redirection 302 pour diriger le trafic dans les variations de test. Cela indique aux moteurs de recherche que la redirection est temporaire et qu’elle sera uniquement active aussi longtemps que durera le test.

   Une redirection 302 est une redirection côté serveur, et Target, ainsi que la plupart des responsables d’optimisation, utilise les fonctionnalités côté client. Ainsi, il s’agit d’une zone où Target n’est pas tout à fait conforme aux recommandations de Google. Cela n’affecte toutefois qu’un petit nombre de tests. L’approche standard pour l’exécution de tests a recours aux appels Target pour la modification du contenu dans une seule URL ; aucune redirection n’est donc nécessaire. Des instances ont lieu lorsque des clients ont besoin d’utiliser plusieurs URL pour représenter leurs variations de test. Dans ces instances, Target utilise la commande JavaScript `window.location` pour diriger les utilisateurs vers des variations de test, ce qui n’indique pas explicitement s’il s’agit d’une redirection 301 ou 302.

   Bien que nous continuions à rechercher des solutions viables pour nous aligner totalement selon les directives des moteurs de recherche, pour les clients qui doivent utiliser des URL distinctes pour les tests, nous sommes convaincus que l’implémentation elle-même des balises canoniques mentionnée ci-dessus réduit le risque associé à cette approche.

* **Exécuter des expériences uniquement aussi longtemps que nécessaire** : nous considérons que « aussi longtemps que nécessaire » doit durer suffisamment longtemps pour obtenir une signification statistique. Target [fournit les bonnes pratiques](https://docs.adobe.com/content/target-microsite/testcalculator.html) pour déterminer le moment où votre test a atteint ce point. Nous vous recommandons d’incorporer l’implémentation en codage dur des tests concluants dans votre flux de travaux de test et d’allouer les ressources appropriées.

   L’utilisation de la plateforme Target pour « publier » des tests concluants n’est pas conseillée en tant que solution permanente, mais aussi longtemps que le test concluant est publié pour 100 % des utilisateurs à 100 % du temps, cette approche peut être utilisée pendant le processus de codage dur du test concluant.

   Il est essentiel de prendre également en compte les éléments que votre test a modifiés. La mise à jour simple de la couleur des boutons ou d’autres éléments mineurs non basés sur le texte sur la page n’auront aucune incidence sur vos classements organiques. Les modifications apportées au texte doivent toutefois être en codage dur.

   Il est également important de prendre en compte l’accessibilité de la page que vous testez. Si la page n’est pas accessible aux moteurs de recherche et ne s’est jamais vu attribuer la première place dans un classement organique, telle qu’une page d’entrée pour une campagne par messagerie électronique, aucune des considérations ci-dessus mentionnées ne s’applique alors.

Google indique que suivre ces directives « devrait avoir pour vos tests peu voire aucun impact sur votre site dans les résultats de recherche ».

En plus de ces directives, Google présente une directive supplémentaire dans la documentation de leur outil Content Experiments :

* « Vos pages de variation doivent conserver l’esprit du contenu de vos pages originales. Ces variations ne devraient pas changer le sens de la perception générale que vos utilisateurs ont de ce contenu original. »

Google précise à titre d’exemple que « si une page originale d’un site est chargée avec des mots-clés qui ne sont pas associés aux combinaisons présentées aux utilisateurs, nous pouvons supprimer ce site de notre index ».

Nous estimons qu’il serait difficile de changer involontairement le sens du contenu original dans des variations de test, nous vous recommandons toutefois de rester vigilants avec les thèmes des mots-clés sur une page et de conserver ces thèmes. Les modifications apportées au contenu d’une page, en particulier l’ajout ou la suppression de mots-clés pertinents, peuvent donner lieu à des changements de classement pour l’URL dans les recherches organiques. Nous vous recommandons de consulter votre partenaire d’optimisation du référencement dans le cadre de votre protocole de test.

## Robots {#bots}

Adobe Target uses [DeviceAtlas](https://deviceatlas.com/) to detect known bots. Le trafic identifié comme étant généré par un robot est toujours du contenu diffusé, comme pour un utilisateur standard, pour être en conformité avec les directives d’optimisation du référencement. L’utilisation du trafic de robots peut fausser les tests A/B ou les algorithmes de personnalisation s’il est traité comme pour des utilisateurs standard. Par conséquent, si un robot connu est détecté dans votre activité Target, le trafic est traité légèrement différemment. La suppression du trafic de robots permet de mesurer plus précisément l’activité des utilisateurs.

En particulier, pour le trafic de robots connu, Target :

* Ne crée pas ni ne récupère de profil de visiteur
* Ne consigne aucun attribut de profil ou n’exécute pas de scripts de profil
* N’effectue pas de recherche de segments Adobe Audience Manager (AAM) (le cas échéant)
* N’utilise pas de trafic de robots dans la modélisation et la diffusion de contenu personnalisé pour les activités de recommandations, de ciblage automatique, de personnalisation automatisée ou d’affectation automatique
* Ne consigne pas de visite d’activité pour la création de rapports
* Ne consigne pas de données à envoyer à la plate-forme Adobe Experience Cloud
