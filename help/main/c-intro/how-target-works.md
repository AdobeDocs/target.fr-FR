---
keywords: SDK web Adobe Experience Platform;SDK web AEP;SDK AEP;optimisation du moteur de recherche;search engine optimization;seo;clusters edge;clusters centraux;at.js;mbox.js
description: Découvrez le fonctionnement de  [!DNL Adobe Target]  et obtenez des informations sur les bibliothèques JavaScript (AEP Web SDK at.js), les centres de données Adobe, les tests d’optimisation pour les moteurs de recherche et les robots.
title: Comment fonctionne  [!DNL Target]  ?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 612089bcde266804efa6a54be89eff55329d4bfc
workflow-type: tm+mt
source-wordcount: '2562'
ht-degree: 98%

---

# Fonctionnement de [!DNL Adobe Target]

Découvrez le fonctionnement de [!DNL Adobe Target] et obtenez des informations sur les bibliothèques JavaScript ([!DNL Adobe Experience Platform Web SDK] et at.js). Cet article présente également les différents types d’activités que vous pouvez créer à l’aide de [!DNL Target]. Vous en apprendrez également davantage sur le réseau Edge [!DNL Target], l’optimisation du moteur de recherche (SEO) et la manière dont [!DNL Target] détecte les robots.

## [!DNL Adobe Target] bibliothèques JavaScript {#libraries}

[!DNL Target] s’intègre aux sites web à l’aide de [!DNL Experience Platform Web SDK] ou at.js :

* **[!DNL Adobe Experience Platform Web SDK]:** Le [SDK Web Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} est une nouvelle bibliothèque JavaScript côté client. Le [!DNL Experience Platform Web SDK] permet aux clients de [!DNL Adobe Experience Cloud] d’interagir avec les différents services dans le [!DNL Experience Cloud] (y compris [!DNL Target]) via le réseau Edge [!DNL Experience Platform]. [!DNL Adobe] recommande à tous les nouveaux clients [!DNL Target] d’implémenter [!DNL Experience Platform Web SDK].
* **at.js :** la bibliothèque at.js est la nouvelle bibliothèque d’implémentation de [!DNL Target]. La bibliothèque at.js réduit les délais de chargement des pages pour les implémentations web et offre des options d’implémentation optimisées pour les applications d’une seule page. at.js est fréquemment mis à jour avec de nouvelles fonctionnalités. [!DNL Adobe] recommande à tous les clients qui utilisent at.js de mettre à jour leurs implémentations vers la [dernière version d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

>[!NOTE]
>
>La bibliothèque mbox.js est l’ancienne bibliothèque d’implémentation de [!DNL Target]. La bibliothèque mbox.js nʼest plus prise en charge depuis le 31 mars 2021. Effectuez la mise à niveau vers le SDK Web Experience Platform (recommandé) ou vers la dernière version d’at.js.

Référencez [!DNL Experience Platform Web SDK] ou at.js sur chaque page de votre site. Par exemple, vous pouvez ajouter l’une de ces bibliothèques à votre en-tête global. Vous pouvez également utiliser les [balises dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr) pour implémenter [!DNL Target].

Les ressources suivantes contiennent des informations détaillées sur l’implémentation de [!DNL Experience Platform Web SDK] ou d’at.js :

* [[!DNL Adobe Experience Platform Web SDK] Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=fr)
* [Implémentation de  [!DNL Target]  à l’aide d’ [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/)

Chaque fois qu’un visiteur demande une page qui a été optimisée pour [!DNL Target], une requête est envoyée au système de ciblage. La requête permet de déterminer le contenu à proposer à ce visiteur. Ce processus se produit en temps réel. Chaque fois qu’une page est chargée, une demande de contenu est créée et traitée par le système. Le contenu est régi par les règles des activités et des expériences contrôlées par le spécialiste du marketing et est ciblé sur le visiteur individuel du site. Le contenu est proposé à chaque visiteur du site en fonction des éléments auxquels il est le plus susceptible de réagir, de ceux avec lesquels il est le plus susceptible d’interagir ou de ceux qu’il est le susceptible d’acheter. Le contenu personnalisé permet d’optimiser les taux de réponse, les taux d’acquisition et le chiffre d’affaires.

Dans [!DNL Target], chaque élément de la page fait partie d’une seule expérience pour l’ensemble de la page. Chaque expérience peut inclure plusieurs éléments de la page.

Le contenu présenté aux visiteurs dépend du type d’activité que vous avez créé :

### [!UICONTROL Test A/B]

Le contenu qui s’affiche dans un test A/B de base est choisi de manière aléatoire à partir des expériences que vous affectez à l’activité. Vous pouvez attribuer les pourcentages d’affectation du trafic pour chaque expérience. Suite à ce fractionnement aléatoire du trafic, il se peut qu’il faille une quantité importante de trafic initial avant que les pourcentages ne s’équilibrent. Si, par exemple, vous créez deux expériences, l’expérience initiale est choisie de façon aléatoire. Si le trafic est léger, il est possible que le pourcentage des visiteurs puisse être réorienté vers une seule expérience. Avec l’augmentation du trafic, les pourcentages s’égalisent.

Vous pouvez préciser des cibles de pourcentage pour chaque expérience. Dans ce cas, un nombre aléatoire est généré et utilisé pour choisir l’expérience à afficher. Les pourcentages résultants peuvent ne pas correspondre exactement aux cibles spécifiées, mais un trafic plus élevé signifie que les expériences doivent être fractionnées en tenant davantage compte des objectifs de cible.

1. Un client demande une page de votre serveur et l’affiche dans le navigateur.
1. Un cookie propriétaire est défini dans le navigateur du client pour stocker son comportement.
1. La page appelle le système de ciblage.
1. Le contenu s’affiche en fonction des règles de votre activité.

Pour plus d’informations, consultez [Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### [!UICONTROL Affectation automatique]

L’[!UICONTROL affectation automatique] identifie un gagnant parmi plusieurs expériences. L’[!UICONTROL affectation automatique] réaffecte automatiquement davantage de trafic à l’expérience gagnante, ce qui permet d’augmenter les conversions pendant que le test continue à s’exécuter et à apprendre.

Pour plus d’informations, voir [[!UICONTROL Affectation automatique]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

### [!UICONTROL Ciblage automatique] (AT)

[!UICONTROL Le ciblage automatique] s’appuie sur un machine learning avancé pour sélectionner plusieurs expériences hautement performantes définies par des spécialistes du marketing. [!UICONTROL Le ciblage automatique] offre donc à chaque visiteur l’expérience la plus adaptée. La diffusion d’expérience est basée sur les profils individuels des clients et le comportement des visiteurs précédents ayant des profils similaires. Utilisez le [!UICONTROL ciblage automatique] pour personnaliser le contenu et générer des conversions.

Pour plus d’informations, consultez [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP) combine des offres ou des messages et s’appuie sur un machine learning avancé pour faire correspondre différentes variations d’offre pour chaque visiteur. La diffusion d’expérience s’appuie sur les profils individuels des clients pour personnaliser le contenu et stimuler l’effet élévateur.

Pour plus d’informations, consultez [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### [!UICONTROL Ciblage d’expérience] (XT)

Le [!UICONTROL ciblage d’expérience] (XT) diffuse un contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables marketing.

[!UICONTROL Le ciblage d’expérience], qui inclut le géociblage, présente un atout majeur pour la définition de règles ciblant une expérience ou un contenu spécifique pour une audience particulière. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes. Lorsque des visiteurs consultent votre site, le [!UICONTROL ciblage d’expérience] (XT) les évalue pour déterminer s’ils répondent aux critères définis. S’ils correspondent aux critères, ils entrent dans l’activité et l’expérience pour l’audience éligible. Vous pouvez créer des expériences pour plusieurs audiences au sein d’une activité unique.

Pour plus d’informations, consultez [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4).

### [!UICONTROL Test multivarié] (MVT)

Le [!UICONTROL test multivarié] (MVT) comparent les combinaisons d’offres dans les éléments d’une page afin de déterminer la combinaison la plus performante pour une audience spécifique. Le test multivarié permet d’identifier l’élément qui a le plus d’effet sur la réussite de l’activité.

Pour plus d’informations, consultez [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499).

### [!UICONTROL Recommendations]

Les activités [!UICONTROL Recommendations] affichent automatiquement les produits ou le contenu susceptibles d’intéresser vos clients selon l’activité précédente de l’utilisateur ou d’autres algorithmes. Recommendations permet d’orienter les clients vers des éléments pertinents qu’ils ne connaîtraient pas autrement.

Pour plus d’informations, consultez [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

## Le réseau Edge {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Un « Edge » est une architecture de diffusion géographiquement distribuée qui garantit un temps de réponse optimal aux visiteurs qui demandent du contenu, où qu’ils se trouvent dans le monde.

Pour améliorer les temps de réponse, les Edges de [!DNL Target] hébergent uniquement la logique d’activité, les profils mis en cache et les informations d’offre.

Bases de données des activités et du contenu, les données [!DNL Analytics], les API et les interfaces utilisateur des marketeurs sont hébergées dans les grappes centrales d’Adobe. Des mises à jour sont alors envoyées aux Edges de [!DNL Target]. Les clusters centraux et les clusters Edge sont automatiquement synchronisés en vue de continuellement mettre à jour les données d’activité mises en cache. Toute la modélisation 1:1 est également stockée sur chaque nœud, afin que les demandes les plus complexes puissent aussi être traitées sur le réseau Edge.

Chaque cluster Edge comporte toutes les informations nécessaires pour répondre à la demande de contenu du visiteur et pour effectuer un suivi sur les données d’analyse de cette demande. Les demandes des visiteurs sont acheminées vers le cluster Edge le plus proche.

Pour plus d’informations, consultez l’article technique [Présentation de la sécurité d’Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

La solution [!DNL Target] est hébergée dans des centres de données détenus et loués par Adobe aux quatre coins du monde.

Les emplacements des clusters centraux comprennent un centre de collecte de données et un centre de traitement des données. Les emplacements des clusters Edge comprennent uniquement un centre de collecte de données. Chaque suite de rapports est affectée à un centre de traitement des données spécifique.

Les données d’activité sur le site du client sont collectées par le plus proche des sept clusters Edge. Ces données sont dirigées vers la destination prédéfinie du cluster central d’un client (l’un des trois emplacements : Oregon, Dublin, Singapour) pour le traitement. Les données du profil du visiteur sont stockées sur le cluster Edge le plus proche du visiteur. Les clusters Edge comprennent les clusters centraux et ceux situés en Virginie, à Bombay, à Sydney et à Tokyo.

Au lieu de répondre à toutes les requêtes de ciblage à partir d’un seul emplacement, les requêtes sont traitées par le cluster Edge le plus proche du visiteur. Ce processus permet d’atténuer l’effet du temps de déplacement réseau/Internet.

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
>[!DNL Adobe Target] ne dispose actuellement pas d’un cluster Edge en Chine et les performances des visiteurs restent limitées pour les client de [!DNL Target] en Chine. En raison du pare-feu et de l’absence de clusters Edge dans le pays, les expériences des sites où [!DNL Target] a été déployé peuvent être affectées. Le rendu des expériences peut être lent et le chargement des pages peut être affecté. En outre, les spécialistes du marketing peuvent rencontrer une latence lors de l’utilisation de l’interface utilisateur de création de [!DNL Target].

Si vous le souhaitez, vous pouvez ajouter des clusters Edge de [!DNL Target] sur liste autorisée. Pour plus d’informations, consultez [Ajout des nœuds Edge de Target sur liste autorisée](https://developer.adobe.com/target/before-implement/privacy/allowlist-edges/){target=_blank}.

## Expérience utilisateur protégée {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] garantit que la disponibilité et la performance de l’infrastructure de ciblage sont aussi fiables que possible. Cependant, une ventilation des communications entre le navigateur d’un visiteur et les serveurs [!DNL Adobe] peuvent provoquer une interruption de la diffusion de contenu.

Pour éviter les interruptions de service et les problèmes de connectivité, tous les emplacements sont configurés pour inclure le contenu par défaut (défini par le client). Ce contenu par défaut s’affiche si le navigateur de l’utilisateur ne parvient pas à se connecter à [!DNL Target].

Aucune modification n’est apportée à la page si le navigateur de l’utilisateur ne parvient pas à se connecter dans un délai d’expiration défini (par défaut : 15 secondes). Si ce seuil de délai est atteint, le contenu de l’emplacement par défaut est affiché.

[!DNL Adobe] protège l’expérience de l’utilisateur en optimisant et en protégeant les performances.

* [!DNL Adobe] procède aux benchmarks de performances en fonction des normes de l’industrie, qui sont garanties par le contrat de niveau de service d’Adobe.
* Le réseau Edge garantit la diffusion opportune des données.
* [!UICONTROL Adobe] sécurise ses applications en appliquant une approche à plusieurs niveaux afin de fournir aux utilisateurs le plus haut niveau possible de disponibilité et de fiabilité.
* [!DNL Target] Consulting aide à l’implémentation et propose une assistance produit continue.

## Tests adaptés à l’optimisation du moteur de recherche (SEO) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] s’aligne sur les directives des moteurs de recherche pour les tests.

Google encourage les tests d’utilisateurs. Google indique dans sa documentation que A/B et le [!UICONTROL test multivarié] n’endommage pas les classements des moteurs de recherche organiques si vous suivez certaines instructions.

Pour plus d’informations, voir les ressources Google suivantes :

* [Test de site web et recherche Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Expériences et cloaking](https://support.google.com/analytics/answer/2576845?hl=fr&amp;ref_topic=1745207)

Les directives sont présentées dans une publication de [Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Bien que la publication date de 2012, elle rappelle les instructions les plus récentes de Google sur le sujet et les directives continuent de s’appliquer.

* **Pas de cloaking** : le cloaking affiche un ensemble de contenus à vos utilisateurs et un ensemble différent aux robots des moteurs de recherche. Le cloaking est réalisé en identifiant spécifiquement les robots et en leur donnant volontairement un contenu différent.

   [!DNL Target], en tant que plateforme, a été configurée pour traiter ces robots de moteurs de recherche de la même façon que n’importe quel autre utilisateur. Par conséquent, des robots peuvent être inclus dans les activités s’ils sont sélectionnés de manière aléatoire et « voient » les variations de test.

* **Utiliser rel=&quot;canonical&quot;** : il arrive parfois qu’un test A/B doive être configuré à l’aide d’URL différentes pour les variations. Dans ces instances, toutes les variations doivent comporter la balise `rel="canonical"` qui fait référence à l’URL d’origine (contrôle). Par exemple, supposons que [!DNL Adobe] teste sa page d’accueil à l’aide de différentes URL pour chaque variation. La balise canonique suivante pour la page d’accueil serait placée dans la balise `<head>` pour chacune des variations suivantes :

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Utiliser les redirections 302 (temporaires)** : dans les instances où les URL distinctes sont utilisées pour les pages de variation dans un test, Google recommande d’utiliser la redirection 302 pour diriger le trafic dans les variations de test. La redirection 302 indique aux moteurs de recherche que la redirection est temporaire et n’est active que tant que le test est en cours d’exécution.

   Une redirection 302 est une redirection côté serveur, tandis que [!DNL Target] et la plupart des responsables d’optimisation utilisent les fonctionnalités côté client. Ainsi, la redirection est une zone où [!DNL Target] n’est pas tout à fait conforme aux recommandations de Google. Cette pratique n’affecte toutefois qu’un petit nombre de tests. L’approche standard pour l’exécution de tests [!DNL Target] a recours aux appels pour la modification du contenu dans une seule URL ; aucune redirection n’est donc nécessaire. Des instances ont lieu lorsque des clients doivent utiliser plusieurs URL pour représenter leurs variations de test. Dans ces instances, [!DNL Target] utilise la commande JavaScript `window.location`. Cette commande dirige les utilisateurs vers les variations de test, ce qui n’indique pas explicitement si c’est une redirection 301 ou 302.

   [!DNL Adobe] continue de rechercher des solutions viables pour s’aligner complètement sur les directives des moteurs de recherche. Pour les clients qui doivent utiliser des URL distinctes à des fins de test, [!DNL Adobe] est certain que la mise en oeuvre correcte des balises canoniques réduit le risque associé à cette approche.

* **Exécuter des expériences uniquement aussi longtemps que nécessaire** : [!DNL Adobe] estime qu’« aussi longtemps que nécessaire » doit durer aussi longtemps que nécessaire pour atteindre une signification statistique. [!DNL Target] fournit les bonnes pratiques et la variable [!DNL Adobe Target] [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) pour déterminer quand votre test a atteint ce point. [!DNL Adobe] recommande d’incorporer l’implémentation en codage en dur des tests concluants dans votre flux de travaux de test et d’allouer les ressources appropriées.

   L’utilisation de la plateforme [!DNL Target] pour « publier » les tests gagnants n’est pas recommandée en tant que solution à long terme. Si le test gagnant est publié pour 100 % des utilisateurs 100 % du temps, alors cette approche peut être utilisée pendant que le processus de codage en dur du test gagnant se termine.

   Il est essentiel de prendre également en compte les éléments que votre test a modifiés. Le simple fait de mettre à jour la couleur des boutons ou d’autres éléments mineurs non textuels de la page n’influence pas vos classements organiques. Les modifications apportées au texte doivent toutefois être en codage dur.

   Il est également important de prendre en compte l’accessibilité de la page que vous testez. Si la page n’est pas accessible aux moteurs de recherche et n’a jamais été conçue pour être classée dans le référencement organique en premier lieu, alors aucune des considérations ci-dessus ne s’applique. Un bon exemple est une page de destination pour une campagne par e-mail.

Google indique que suivre ces directives « devrait avoir pour vos tests peu voire aucun impact sur votre site dans les résultats de recherche ».

En plus de ces directives, Google présente une directive supplémentaire dans la documentation de leur outil Content Experiments :

* « Vos pages de variation doivent conserver l’esprit du contenu de vos pages originales. Ces variations ne devraient pas changer le sens de la perception générale que vos utilisateurs ont de ce contenu original. »

Google précise à titre d’exemple que « si une page originale d’un site est chargée avec des mots-clés qui ne sont pas associés aux combinaisons présentées aux utilisateurs, nous pouvons supprimer ce site de notre index ».

[!UICONTROL Adobe] estime qu’il serait difficile de modifier involontairement la signification du contenu original dans les variations de test. Cependant, [!UICONTROL Adobe] recommande de connaître les thèmes des mots-clés sur une page et de conserver ces thèmes. Les modifications apportées au contenu d’une page, en particulier l’ajout ou la suppression de mots-clés pertinents, peuvent donner lieu à des changements de classement pour l’URL dans les recherches organiques. [!DNL Adobe] recommande de consulter votre partenaire SEO dans le cadre de votre protocole de test.

## Robots {#bots}

Adobe [!DNL Target] utilise la mesure [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) « isRobot » pour détecter les robots connus en fonction de la chaîne de l’agent utilisateur transmise dans l’en-tête de requête.

>[!NOTE]
>
> Pour les requêtes [!DNL Server-Side], la valeur transmise dans le [nœud « Context » de la requête](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) est prioritaire sur la chaîne de l’agent utilisateur pour la détection des robots.

Le trafic identifié comme étant généré par un robot est toujours diffusé. Les robots sont traités comme un utilisateur régulier afin de s’assurer que [!DNL Target] est conforme aux directives SEO. L’utilisation du trafic de robots peut fausser les tests A/B ou les algorithmes de personnalisation s’il est traité comme pour des utilisateurs standard. Par conséquent, si un robot connu est détecté dans votre activité [!DNL Target], le trafic est traité légèrement différemment. La suppression du trafic de robots permet de mesurer plus précisément l’activité des utilisateurs.

En particulier, pour le trafic de robots connu, [!DNL Target] :

* Ne crée pas ni ne récupère de profil de visiteur
* Ne consigne aucun attribut de profil ou n’exécute pas de scripts de profil
* Recherche des segments [!DNL Adobe Audience Manager] (AAM) (le cas échéant)
* Utiliser de trafic de robots dans la modélisation et la diffusion de contenu personnalisé pour les activités de [!UICONTROL Recommendations], de [!UICONTROL ciblage automatique], de [!UICONTROL ciblage automatique] ou d’[!UICONTROL affectation automatique]
* Ne consigne pas de visite d’activité pour la création de rapports
* Ne consigne pas de données à envoyer à la plateforme [!DNL Adobe Experience Cloud]

Pour le trafic de robots connu lors de l’utilisation d’[!UICONTROL Analytics for Target] (A4T), [!DNL Target] ne renvoie pas :

* d’événements à [!DNL Analytics]

Pour le trafic de robots connu lors de l’utilisation de la journalisation côté client, [!DNL Target] ne renvoie pas :

* payload tnta
