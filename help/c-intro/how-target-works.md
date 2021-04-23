---
keywords: Adobe Experience Platform Web SDK ; aep web sdk ; aep sdk ; optimisation des moteurs de recherche ; optimisation des moteurs de recherche ; seo ; grappes de périphérie, grappes centrales ; at.js ; mbox.js ;
description: Découvrez comment les bibliothèques Adobe [!DNL Target] works, including information about the [!DNL Target] JavaScript (at.js et AEP Web SDK), les centres de données d’Adobe et les tests d’optimisation du référencement.
title: Comment fonctionne  [!DNL Target] ?
feature: Aperçu
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2565'
ht-degree: 32%

---

# Fonctionnement de l’Adobe [!DNL Target]

Découvrez comment [!DNL Adobe Target] fonctionne, y compris les informations sur les bibliothèques [!DNL Adobe Experience Platform Web SDK] et JavaScript (at.js et mbox.js). Cet article présente également les différents types d&#39;activité que vous pouvez créer à l&#39;aide de [!DNL Target]. Vous pouvez également en savoir plus sur le réseau de périphérie [!DNL Target], l&#39;optimisation pour les moteurs de recherche (SEO), et sur la manière dont [!DNL Target] détecte les robots.

## SDK Web et bibliothèques JavaScript de la plateforme de cible {#libraries}

[!DNL Target] s’intègre aux sites Web à l’aide des bibliothèques JavaScript  [!DNL AEP Web SDK] ou JavaScript :

* **Adobe Experience Platform Web SDK :** le  [SDK Web ](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) AEP est une nouvelle bibliothèque JavaScript côté client. Le SDK Web AEP permet aux clients de [!DNL Adobe Experience Cloud] d&#39;interagir avec les différents services de [!DNL Experience Cloud] (y compris [!DNL Target]) via le réseau Edge [!DNL AEP]. Adobe recommande que tous les nouveaux clients [!DNL Target] implémentent [!DNL AEP Web SDK].
* **at.js :** La  [bibliothèque ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) at.js est une bibliothèque d’implémentation pour  [!DNL Target]. La bibliothèque at.js réduit les délais de chargement des pages pour les implémentations web et offre des options d’implémentation optimisées pour les applications d’une seule page. at.js est fréquemment mis à jour avec de nouvelles fonctionnalités. Adobe recommande à tous les clients utilisant at.js de mettre à jour leurs implémentations vers la [dernière version de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).
* **mbox.js :**[](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) La bibliothèque mbox.js est la bibliothèque d’implémentation héritée pour [!DNL Target]. La bibliothèque mbox.js est prise en charge jusqu’au 31 mars 2021 ; toutefois, il n’y aura aucune mise à jour des fonctionnalités.

>[!IMPORTANT]
>
>Tous les clients doivent migrer vers [!DNL AEP Web SDK] ou vers la dernière version d’at.js. Pour plus d’informations, voir [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) ou [Migration vers at.js à partir de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

Référencez [!DNL AEP Web SDK] ou at.js sur chaque page de votre site. Par exemple, vous pouvez ajouter l’une de ces bibliothèques à votre en-tête global. Vous pouvez également utiliser [Adobe Platform launch](https://experienceleague.adobe.com/docs/launch/using/overview.html) pour implémenter [!DNL Target].

Les ressources suivantes contiennent des informations détaillées sur la mise en oeuvre du SDK Web AEP ou d’at.js :

* [Extension SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Mise en oeuvre de la Cible à l’aide d’Adobe Experience Platform Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

Chaque fois qu’un visiteur demande une page qui a été optimisée pour [!DNL Target], une requête est envoyée au système de ciblage. La requête permet de déterminer le contenu à fournir à ce visiteur. Ce processus se produit en temps réel. Chaque fois qu’une page est chargée, une demande de contenu est effectuée et satisfaite par le système. Le contenu est régi par les règles des activités et des expériences contrôlées par le spécialiste du marketing et est ciblé sur le visiteur individuel du site. Le contenu est diffusé auquel chaque visiteur du site est le plus susceptible de répondre, d&#39;interagir ou d&#39;acheter. Le contenu personnalisé permet d’optimiser les taux de réponse, les taux d’acquisition et les recettes.

Dans [!DNL Target], chaque élément de la page fait partie d’une expérience unique pour la page entière. Chaque expérience peut inclure plusieurs éléments sur la page.

Le contenu affiché aux visiteurs dépend du type d’activité que vous avez créé.

### Test A/B

Le contenu qui s’affiche dans un test A/B de base est choisi de manière aléatoire à partir des expériences que vous affectez à l’activité. Vous pouvez attribuer les pourcentages d’affectation du trafic pour chaque expérience. En raison de ce fractionnement aléatoire du trafic, un volume important de trafic initial peut s’écouler avant que les pourcentages ne s’équilibrent. Si, par exemple, vous créez deux expériences, l’expérience initiale est choisie de façon aléatoire. Si le trafic est léger, il est possible que le pourcentage des visiteurs puisse être réorienté vers une seule expérience. Avec l&#39;augmentation du trafic, les pourcentages s&#39;égalisent.

Vous pouvez préciser des cibles de pourcentage pour chaque expérience. Dans ce cas, un nombre aléatoire est généré et utilisé pour choisir l’expérience à afficher. Les pourcentages résultants peuvent ne pas correspondre exactement aux cibles spécifiées, mais un trafic plus élevé signifie que les expériences doivent être fractionnées en tenant davantage compte des objectifs de cible.

1. Un client demande une page de votre serveur et l’affiche dans le navigateur.
1. Un cookie propriétaire est défini dans le navigateur du client pour stocker son comportement.
1. La page appelle le système de ciblage.
1. Le contenu s’affiche en fonction des règles de votre activité.

Pour plus d’informations, voir [Création d’un test AB](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### Affectation automatique

L’affectation automatique identifie un gagnant parmi deux expériences ou plus. L’affectation automatique réaffecte automatiquement davantage de trafic à l’expérience gagnante, ce qui permet d’augmenter les conversions pendant que le test continue à s’exécuter et à s’instruire.

Pour plus d’informations, voir [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

### Ciblage automatique (AT)

La Cible automatique utilise l’apprentissage automatique avancé pour effectuer un choix parmi plusieurs expériences définies par les spécialistes du marketing hautement performants. La Cible automatique offre à chaque visiteur l’expérience la plus adaptée. La diffusion d’expérience repose sur des profils client individuels et sur le comportement de visiteurs précédents ayant des profils similaires. Utilisez la Cible automatique pour personnaliser le contenu et générer des conversions.

Pour plus d’informations, voir [Ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md).

### Automated Personalization (AP)

Automated Personalization (AP) combine des offres ou des messages et utilise l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur. Experience diffusion est basée sur des profils clients individuels pour personnaliser le contenu et stimuler l’effet élévateur.

Pour plus d’informations, voir [personnalisation automatisée](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### Ciblage d’expérience (XT)

Le ciblage d’expérience (XT) diffuse le contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables du marketing.

Le ciblage d’expérience, qui inclut le géociblage, présente un atout majeur pour la définition de règles ciblant une expérience ou un contenu spécifique pour une audience particulière. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes. Lorsque des visiteurs consultent votre site, le ciblage d’expérience les évalue pour déterminer s’ils répondent aux critères définis. S’ils correspondent aux critères, ils entrent dans l’activité et l’expérience pour l’audience éligible. Vous pouvez créer des expériences pour plusieurs audiences au sein d’une activité unique.

Voir [Ciblage d’expérience](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) pour plus d’informations.

### Test multivarié (MVT)

Multivariate Testing (MVT) compare les combinaisons d’offres dans les éléments d’une page afin de déterminer quelle combinaison produit le meilleur résultat pour une audience spécifique. Le test multivarié permet d&#39;identifier l&#39;élément qui a le plus d&#39;impact sur la réussite de l&#39;activité.

Voir [Test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) pour en savoir plus.

### Recommandations

Les activités de recommandations affichent automatiquement les produits ou le contenu susceptibles d’intéresser vos clients selon l’activité précédente de l’utilisateur ou d’autres algorithmes. Les recommandations aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.

Pour plus d’informations, voir [Recommandations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

## Réseau Edge {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Un &quot;Edge&quot; est une architecture de diffusion géographiquement distribuée qui garantit un temps de réponse optimal aux visiteurs qui demandent du contenu, où qu’ils se trouvent dans le monde.

Pour améliorer les temps de réponse, [!DNL Target] Contours hébergent uniquement la logique d’activité, les profils mis en cache et les informations d’offre.

Les bases de données d’Activité et de contenu, les données [!DNL Analytics], les API et les interfaces utilisateur des spécialistes du marketing sont hébergées dans les grappes centrales d’Adobe. Les mises à jour sont ensuite envoyées aux arêtes [!DNL Target]. Les grappes centrales et les grappes d&#39;arête sont automatiquement synchronisées afin de continuellement mettre à jour les données d&#39;activité mises en cache. La modélisation 1:1 est également stockée sur chaque bord, de sorte que les requêtes les plus complexes puissent également être traitées sur le bord.

Chaque cluster Edge contient toutes les informations nécessaires pour répondre à la demande de contenu du visiteur et pour effectuer le suivi des données d’analyse sur cette demande. Les demandes du visiteur sont acheminées vers le cluster Edge le plus proche.

Pour plus d’informations, consultez le livre blanc [Adobe Target Security Overview](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

La solution [!DNL Target] est hébergée dans des centres de données appartenant à des Adobes et loués à des Adobes dans le monde entier.

Les emplacements de cluster Central contiennent à la fois un centre de collecte de données et un centre de traitement des données. Les emplacements Edge Cluster ne contiennent qu’un centre de collecte de données. Chaque suite de rapports est affectée à un centre de traitement des données spécifique.

Les données d&#39;activité sur le site du client sont collectées par le plus proche des sept clusters Edge. Ces données sont dirigées vers la destination de cluster central prédéfinie d’un client (l’un des trois emplacements suivants : Oregon, Dublin, Singapour) pour le traitement. Les données du profil du visiteur sont stockées sur la grappe Edge la plus proche du visiteur du site. Les emplacements de clusters Edge comprennent les emplacements de clusters Central et Virginia, Amsterdam, Sydney, Tokyo et Hong Kong.

Au lieu de répondre à toutes les requêtes de ciblage provenant d’un seul emplacement, les requêtes sont traitées par la grappe Edge la plus proche du visiteur. Ce processus permet d&#39;atténuer l&#39;impact du temps de déplacement réseau/Internet.

![Carte présentant les différents types de serveurs de Cible](/help/c-intro/assets/target-servers.png)

[!DNL Target] Les grappes centrales, hébergées sur Amazon Web Services (AWS), incluent :

* Oregon, États-Unis
* Dublin, Irlande
* République de Singapour

[!DNL Target] Les grappes Edge, hébergées sur AWS, incluent :

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
>[!DNL Adobe Target] actuellement, il n’y a pas de cluster Edge en Chine et les performances des visiteurs restent limitées pour  [!DNL Target] les clients en Chine. En raison du pare-feu et de l&#39;absence de grappes Edge dans le pays, les expériences des sites où [!DNL Target] a été déployé peuvent être affectées. Le rendu des expériences peut être lent et le chargement des pages peut être affecté. En outre, les spécialistes du marketing peuvent connaître une latence lors de l’utilisation de l’interface utilisateur de création [!DNL Target].

Si vous le souhaitez, vous pouvez placer sur la liste autorisée des grappes de serveurs [!DNL Target] Edge Clusters. Pour plus d’informations, voir [liste autorisée Cible edge nodes](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Expérience utilisateur protégée {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe garantit que la disponibilité et la performance de l’infrastructure de ciblage sont aussi fiables que possible. Cependant, une ventilation des communications entre le navigateur d’un visiteur et les serveurs de l’Adobe peut entraîner une interruption de la diffusion du contenu.

Pour éviter les interruptions de service et les problèmes de connectivité, tous les emplacements sont configurés pour inclure le contenu par défaut (défini par le client). Ce contenu par défaut s’affiche si le navigateur de l’utilisateur ne parvient pas à se connecter à [!DNL Target].

Aucune modification n’est apportée à la page si le navigateur de l’utilisateur ne peut pas se connecter au cours du délai d’attente défini (par défaut, 15 secondes). Si ce seuil de délai est atteint, le contenu de l’emplacement par défaut est affiché.

Adobe protège l’expérience de l’utilisateur en optimisant et en protégeant les performances.

* Adobe procède aux benchmarks de performances en fonction des normes de l’industrie, qui sont garanties par le contrat de niveau de service d’Adobe.
* Le réseau Edge garantit la diffusion opportune des données.
* Adobe sécurise ses applications en appliquant une approche à plusieurs niveaux afin de fournir aux utilisateurs le plus haut niveau possible de disponibilité et de fiabilité.
* [!DNL Target] Consulting aide à l’implémentation et propose une assistance produit continue.

## Tests adaptés à l’optimisation du référencement {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] s’aligne sur les directives des moteurs de recherche pour les tests.

Google encourage les tests d&#39;utilisateurs. Google indique dans sa documentation que A/B et Multivariate Testing ne portent pas atteinte aux classements des moteurs de recherche organiques si vous suivez certaines directives.

Pour plus d’informations, voir les ressources Google suivantes :

* [Test de site web et recherche Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Expériences et cloaking](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

Les directives sont présentées dans une publication de [Google Webmaster Central Blog](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Bien que la publication date de 2012, elle rappelle les instructions les plus récentes de Google sur le sujet et les directives continuent de s’appliquer.

* **Pas de cloaking** : Le cloaking affiche un ensemble de contenus pour vos utilisateurs et un autre ensemble de contenus pour les robots des moteurs de recherche. Le cloaking est réalisé en identifiant spécifiquement les robots et en leur donnant volontairement un contenu différent.

   [!DNL Target], en tant que plateforme, a été configurée pour traiter ces robots de moteurs de recherche de la même façon que n’importe quel autre utilisateur. Par conséquent, les robots peuvent être inclus dans les activités si les robots sont sélectionnés de manière aléatoire et &quot;voir&quot; les variations de test.

* **Utiliser rel=&quot;canonical&quot;** : Parfois, un test A/B doit être configuré à l’aide de différentes URL pour les variations. Dans ces instances, toutes les variations doivent comporter la balise `rel="canonical"` qui fait référence à l’URL d’origine (contrôle). Par exemple, supposons que l’Adobe teste sa page d&#39;accueil à l’aide de différentes URL pour chaque variation. La balise canonique suivante pour la page d&#39;accueil serait placée dans la balise `<head>` pour chacune des variations :

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Utiliser des redirections** 302 (temporaires) : Dans les cas où des URL distinctes sont utilisées pour les pages de variation dans un test, Google recommande d’utiliser une redirection 302 pour diriger le trafic vers les variations de test. La redirection 302 indique aux moteurs de recherche que la redirection est temporaire et n&#39;est principale que tant que le test est en cours d&#39;exécution.

   Une redirection 302 est une redirection côté serveur et [!DNL Target], ainsi que la plupart des fournisseurs d’optimisation, utilise des fonctionnalités côté client. Par conséquent, la redirection est une zone où [!DNL Target] n’est pas entièrement conforme aux recommandations de Google. Toutefois, cette pratique n&#39;affecte qu&#39;une petite partie des tests. L’approche standard pour exécuter des tests via des appels [!DNL Target] permettant de modifier le contenu dans une seule URL ; aucune redirection n’est donc nécessaire. Il existe des cas où les clients doivent utiliser plusieurs URL pour représenter leurs variations de test. Dans ces cas, [!DNL Target] utilise la commande JavaScript `window.location`. Cette commande oriente les utilisateurs vers les variations de test, ce qui n’indique pas explicitement si la redirection est 301 ou 302.

   L&#39;Adobe continue de rechercher des solutions viables pour s&#39;aligner complètement sur les directives des moteurs de recherche. Pour les clients qui doivent utiliser des URL distinctes à des fins de test, l’Adobe est convaincu que la bonne mise en oeuvre des balises canoniques atténue le risque associé à cette approche.

* **Exécuter des expériences uniquement aussi longtemps que nécessaire** : L&#39;Adobe estime que &quot;aussi longtemps que nécessaire&quot; doit être aussi long que nécessaire pour atteindre une signification statistique. [!DNL Target] [fournit les bonnes pratiques](https://docs.adobe.com/content/target-microsite/testcalculator.html) pour déterminer le moment où votre test a atteint ce point. L’Adobe vous recommande d’incorporer l’implémentation en codage dur des tests concluants dans votre processus de test et d’allouer les ressources appropriées.

   L&#39;utilisation de la plate-forme [!DNL Target] pour &quot;publier&quot; les tests gagnants n&#39;est pas recommandée en tant que solution permanente. Si le test gagnant est publié pour 100 % des utilisateurs 100 % du temps, cette approche peut être utilisée pendant que le processus de codage en dur du test gagnant est terminé.

   Il est essentiel de prendre également en compte les éléments que votre test a modifiés. La simple mise à jour de la couleur des boutons ou d’autres éléments mineurs non basés sur du texte sur la page n’a aucune incidence sur vos classements organiques. Les modifications apportées au texte doivent toutefois être en codage dur.

   Il est également important de prendre en compte l’accessibilité de la page que vous testez. Si la page n&#39;est pas accessible aux moteurs de recherche et n&#39;a jamais été conçue pour être classée dans la recherche organique en premier lieu, aucune des considérations ci-dessus ne s&#39;applique. Un exemple est un landing page dédié à une campagne par courriel.

Google indique que suivre ces directives « devrait avoir pour vos tests peu voire aucun impact sur votre site dans les résultats de recherche ».

En plus de ces directives, Google présente une directive supplémentaire dans la documentation de leur outil Content Experiments :

* « Vos pages de variation doivent conserver l’esprit du contenu de vos pages originales. Ces variations ne devraient pas changer le sens de la perception générale que vos utilisateurs ont de ce contenu original. »

Google précise à titre d’exemple que « si une page originale d’un site est chargée avec des mots-clés qui ne sont pas associés aux combinaisons présentées aux utilisateurs, nous pouvons supprimer ce site de notre index ».

L&#39;Adobe estime qu&#39;il serait difficile de modifier involontairement la signification du contenu original dans les variations de test. Toutefois, l’Adobe recommande de connaître les thèmes de mots-clés sur une page et de les gérer. Les modifications apportées au contenu d’une page, en particulier l’ajout ou la suppression de mots-clés pertinents, peuvent donner lieu à des changements de classement pour l’URL dans les recherches organiques. L’Adobe vous conseille d’interagir avec votre partenaire d’optimisation du référencement dans le cadre de votre protocole de test.

## Robots {#bots}

L&#39;Adobe [!DNL Target] utilise la mesure [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) &quot;isRobot&quot; pour détecter les robots connus en fonction de la chaîne User Agent transmise dans l&#39;en-tête de requête.

>[!NOTE]
>
> Pour les requêtes [!DNL Server-Side], la valeur transmise dans le noeud &quot;Context&quot;](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) de la requête [est prioritaire sur la chaîne User Agent pour la détection des robots.

Le trafic identifié comme étant généré par un bot est toujours diffusé. Les robots sont traités comme un utilisateur régulier afin de s’assurer que [!DNL Target] est conforme aux directives d’optimisation du référencement. L’utilisation du trafic de robots peut fausser les tests A/B ou les algorithmes de personnalisation s’il est traité comme pour des utilisateurs standard. Par conséquent, si un robot connu est détecté dans votre activité [!DNL Target], le trafic est traité légèrement différemment. La suppression du trafic de robots permet de mesurer plus précisément l’activité des utilisateurs.

En particulier, pour le trafic de robots [!DNL Target] connu, ce n’est pas le cas :

* Ne crée pas ni ne récupère de profil de visiteur
* Ne consigne aucun attribut de profil ou n’exécute pas de scripts de profil
* N’effectue pas de recherche de segments Adobe Audience Manager (AAM) (le cas échéant)
* Utiliser le trafic de robots dans la modélisation et la diffusion de contenu personnalisé pour les activités Recommendations, Cible automatique, Automated Personalization ou affectation automatique
* Ne consigne pas de visite d’activité pour la création de rapports
* Enregistrer les données à envoyer à la plate-forme [!DNL Adobe Experience Cloud]
