---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Kit de bienvenue Adobe Target - Chapitre 2 - Cible en un coup d'oeil
title: Kit de bienvenue Adobe Target - Chapitre 2 - Cible en un coup d'oeil
feature: Overview
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '2504'
ht-degree: 17%

---


# Chapitre 2 : Adobe Target en un coup d&#39;oeil

Avant de commencer à utiliser [!DNL Adobe Target], il peut s’avérer utile d’obtenir un aperçu général de la solution. Dans ce chapitre, découvrez les principales fonctionnalités de la solution, les points de contact de la marque sur lesquels vous pouvez l&#39;utiliser, les options d&#39;implémentation, les fonctions et workflows importants de l&#39;interface utilisateur, les fonctionnalités de gouvernance et son rôle dans l&#39;ensemble [!DNL Adobe Experience Cloud]. Sauf mention contraire, les éléments décrits dans ce chapitre sont disponibles avec [!DNL Adobe Target Premium] et [!DNL Adobe Target Standard]. [!DNL Adobe Target Premium] Pour plus d&#39;informations, voir [Introduction à la Cible](/help/c-intro/intro.md).

## Capacités et activités

Les tests et la personnalisation sont les deux grands types de fonctionnalités que [!DNL Target] offres et que vous pouvez utiliser lors de la création d&#39;une &quot;activité&quot; dans [!DNL Target]. Il se peut que le terme &quot;test&quot; soit utilisé de manière interchangeable avec &quot;optimisation&quot; et &quot;personnalisation&quot;, de manière interchangeable avec &quot;ciblage&quot;.

Dans une activité de test, vous comparez une variation d’une expérience numérique à une ou plusieurs autres variations afin de découvrir que l’une d’elles entraîne le plus de visiteurs à effectuer l’action souhaitée. [!DNL Target] offre les fonctionnalités de test suivantes : Test A/B, test multivarié (MVT) et affectation automatique.

Avec une activité de personnalisation, vous offrez une expérience numérique adaptée à un groupe spécifique de visiteurs ou à chaque visiteur individuel. [!DNL Target] offre les fonctionnalités de personnalisation suivantes : Ciblage d’expérience, Cible automatique, Automated Personalization et Recommendations.

Pour une compréhension plus approfondie du moment et de la manière d&#39;utiliser chaque fonctionnalité, voir [Cible activités types](/help/c-activities/target-activities-guide.md).

| Type d&#39;activité | Détails |
| --- | --- |
| Tests A/B | Comparez plusieurs variantes de vos expériences ou offres sur votre site Web ou d’autres points de contact clients numériques pour identifier celle qui améliore le plus les mesures commerciales clés au cours d’une période de test prédéfinie. Les tests A/B sont adaptés aux modifications importantes, telles que les nouvelles mises en page de page Web, les différentes approches de navigation sur le site ou les traitements radicalement différents des éléments individuels d’une expérience numérique, tels que les copies, les images et les boutons d’appel à l’action. [En savoir plus](/help/c-activities/t-test-ab/test-ab.md). |
| Affectation automatique | Identifiez l’expérience la plus performante parmi deux expériences ou plus et réaffectez automatiquement plus de trafic à l’expérience gagnante afin d’augmenter les conversions pendant que le test continue à s’exécuter et à apprendre. Utilise l&#39;intelligence artificielle optimisée par [!DNL Adobe Sensei]. [En savoir plus](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Cible automatique <br>(Premium) | Tirez parti de Adobe Sensei AI dans [!DNL Target] pour déterminer et fournir à chaque visiteur la meilleure expérience de plusieurs d&#39;entre eux en fonction de son profil client individuel et du comportement des visiteurs précédents ayant des profils similaires. La Cible automatique permet la personnalisation à l’échelle. [En savoir plus](/help/c-activities/auto-target/auto-target-to-optimize.md). |
| Automated Personalization<br>(Premium) | Utilisez des algorithmes d&#39;apprentissage automatique et une automatisation avancés optimisés par [!DNL Adobe Sensei] pour examiner différentes combinaisons d&#39;images, de copies et d&#39;autres éléments dans une offre et fournir la meilleure combinaison à chaque visiteur en fonction des objectifs commerciaux les plus performants, tels que l&#39;augmentation des conversions ou des recettes par visiteur. [En savoir plus](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Ciblage d’expérience (XT) | Diffusez du contenu à une audience spécifique en fonction d’un ensemble de règles et de critères définis par l’utilisateur. **[!UICONTROL Le]** ciblage d’expérience s’avère utile pour cibler une expérience ou un contenu spécifique sur une audience particulière lorsque vous comprenez qu’une audience est précieuse et que vous connaissez l’expérience qui y trouve son écho. [En savoir plus](/help/c-activities/t-experience-target/experience-target.md). |
| Test multivarié (MVT) | Comparez toutes les combinaisons possibles de variations d’éléments sur votre page ou votre expérience numérique (par exemple, trois images d’arrière-plan différentes, deux variantes de copie et deux couleurs de bouton différentes). Le test multivarié détermine la combinaison la plus performante pour une audience spécifique et les éléments qui ont le plus d’impact sur les résultats. [En savoir plus](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Recommendations<br>(Premium) | Utilisez Adobe Sensei AI pour suggérer automatiquement des produits ou du contenu susceptibles d’intéresser vos clients en fonction de leur activité précédente et de celle d’autres clients. [En savoir plus](/help/c-recommendations/recommendations.md). |

## Canaux

Vous pouvez utiliser [!DNL Target] pour tester et personnaliser des expériences numériques n&#39;importe où : des points de contact numériques traditionnels tels que votre site Web, votre site mobile et votre application mobile, mais aussi sur des points de contact tels que des kiosques, des courriels, des périphériques IoT, des consoles de jeux et même des assistants vocaux tels que Alexa et Cortana. De nombreuses sociétés début à utiliser [!DNL Target] sur leur site Web. Cependant, des recherches récentes indiquent que plus de personnes visitent des marques à partir de leurs appareils mobiles. L&#39;optimisation de vos canaux mobiles est désormais essentielle. Idéalement, vous connecterez les expériences du visiteur à tous vos points de contact pour offrir une expérience homogène et cohérente.

| Canal | Détails |
| --- | --- |
| Site Web | [!DNL Target] peut être utilisé pour exécuter des activités A/B Testing, Multivariate Testing, Experience Targeting, Auto-Allocation, Auto-Cible, Automated Personalization, et Recommendations sur les pages de vos sites Web de plusieurs pages, d’applications d’une seule page (SPA) et de sites Web mobiles afin d’améliorer l’engagement des visiteurs et des clients, d’augmenter les conversions et d’augmenter les recettes. |
| Web mobile | [!DNL Target] peut être utilisé pour exécuter tous les mêmes types d’activité que ceux que vous exécutez sur votre site Web sur les pages de votre site Web mobile afin d’améliorer de manière similaire l’engagement des visiteurs et des clients, d’augmenter les conversions et d’augmenter les recettes. |
| Applications mobiles | [!DNL Target] peut être utilisé pour tester et personnaliser des expériences d’applications mobiles en fonction du comportement des utilisateurs et du contexte mobile. [!DNL Target] vous permet de proposer des interactions qui impliquent et convertissent par le biais de tests itératifs, ainsi que du ciblage d’expérience et de la personnalisation basée sur l’IA. Pour utiliser [!DNL Target] sur votre application mobile, vous devez utiliser l’Adobe Mobile Services SDK. |
| IoT/Partout | [!DNL Target] offre une mise en oeuvre côté serveur afin que vous puissiez utiliser les mêmes fonctionnalités de test et de personnalisation dans les activités que celles que vous utilisez sur votre site Web, site mobile et applications mobiles traditionnels dans les courriels et sur les points de contact qui ne disposent pas de navigateur ou qui n’utilisent pas de code JavaScript. Par exemple, vous pouvez tester et personnaliser des kiosques, des décodeurs, des consoles de jeux, des assistants vocaux et d’autres points de contact non traditionnels. |

## Mises en œuvre

La plupart d’entre vous peuvent utiliser [!DNL Target] pour tester et personnaliser vos nombreux points de contact numériques, y compris les points de contact Web et mobiles traditionnels, mais aussi les points de contact qui ne disposent pas de navigateur ou n’utilisent pas de code JavaScript. Dans certains cas, la politique interne ou externe nécessite des niveaux de contrôle et de sécurité supplémentaires. Vous pouvez également avoir des processus qui doivent s’exécuter sur un serveur principal pour des raisons de performances. Pour répondre à cette grande variété d&#39;utilisations, nous vous donnons la possibilité de mettre en oeuvre [!DNL Target] de différentes manières : côté client, côté serveur ou une combinaison des deux.

| Type d’implémentation | Détails |
| --- | --- |
| Côté client | Avec cette implémentation de [!DNL Target], [!DNL Target] fournit les expériences associées à une activité directement au navigateur client. Le navigateur décide de l’expérience à afficher et l’affiche. Côté client, vous pouvez utiliser un éditeur WYSIWYG, le **[!UICONTROL compositeur d’expérience visuelle]** (VEC), ou une interface non visuelle, le **[!UICONTROL compositeur d’expérience d’après les formulaires]**, pour créer vos expériences de test et de personnalisation. [En savoir plus](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Côté serveur | Dans ce type d’implémentation [!DNL Target], un périphérique client émet une demande d’expérience par l’intermédiaire de votre serveur, votre serveur envoie cette demande à [!DNL Target], [!DNL Target] renvoie la réponse à votre serveur et votre serveur décide de l’expérience à fournir au périphérique client pour qu’il effectue le rendu. L’expérience n’a pas besoin de s’afficher dans un navigateur. Elle peut être affichée dans un e-mail ou kiosque, par l’intermédiaire d’un assistant vocal ou via une autre expérience non visuelle ou un périphérique non basé sur un navigateur. Étant donné que votre serveur se trouve entre le client et [!DNL Target], ce type d’implémentation est également idéal si vous avez besoin de plus de contrôle et de sécurité ou si vous avez des processus complexes de serveur principal, que vous souhaitez exécuter sur votre serveur. [En savoir plus](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Implémentation hybride | Dans cette implémentation, vous choisissez l’approche d’implémentation qui fonctionne le mieux pour un cas d’utilisation donné. Par exemple, vous pouvez utiliser une mise en oeuvre côté client pour tester une offre A/B dans une bannière à forte identification sur la page d&#39;accueil, mais également une mise en oeuvre côté serveur pour déterminer les résultats de la recherche interne à afficher sur un navigateur client, l’expérience à afficher sur un tableau de bord de voiture intelligent ou la réponse vocale à fournir à partir d’un assistant vocal. |

## Éléments d’Activité

Dans [!DNL Target], vous pouvez créer une activité de personnalisation, une activité d&#39;optimisation ou une activité qui optimise votre approche de personnalisation. Chaque activité comporte des éléments clés : les expériences ou offres que vous testez ou personnalisez, les audiences ou les personnes auxquelles vous proposez une expérience, les mesures par lesquelles vous mesurez l’impact de l’activité et les rapports qui affichent visuellement cet impact.

| Type d&#39;élément | Détails |
| --- | --- |
| Expériences | Une offre, une image, un texte, un bouton, une vidéo, une combinaison de ces différents éléments sur une page, une page Web entière ou un ensemble de pages qui peut éventuellement former un tunnel de vente ou une autre séquence logique de pages. Il peut également s’agir de la réponse d’un assistant vocal, d’un script de service à la clientèle ou même d’une saveur personnalisée provenant d’un distributeur de boissons. Vous pouvez tester ou personnaliser des expériences dans les activités [!DNL Target]. [En savoir plus](/help/c-experiences/experiences.md). |
| Offres | Bloc de contenu pouvant contenir des images, du texte, du code HTML, des liens, de la vidéo, un bouton d’appel à l’action, une réponse d’assistant vocal ou tout autre type de contenu. Une offre peut être pour une remise, une livraison gratuite, etc. Une offre peut être affichée sur une page Web, mais peut également être ressentie sur n’importe quel point de contact client, tel qu’un assistant vocal ou une console de jeux. Lorsque vous testez une offre, vous mesurez sa réussite par rapport à d&#39;autres offres ou sans offre. [En savoir plus](/help/c-experiences/c-manage-content/manage-content.md). |
| Audiences | Groupe de personnes ayant les mêmes caractéristiques, telles qu’un nouveau visiteur, un visiteur récurrent ou des visiteurs récurrents du Midwest. Pour optimiser votre marketing web, la fonctionnalité Audience vous permet de cibler différents contenus et expériences selon les audiences, afin de présenter les messages adéquats aux personnes appropriées au moment opportun. Si un visiteur est identifié comme faisant partie d&#39;une audience de cible, [!DNL Target] détermine l&#39;expérience à afficher, en fonction des critères définis lors de la création de l&#39;activité. [En savoir plus](/help/c-target/target.md). |
| Mesures de succès | Mesures clés de l&#39;activité qui vous permettent de déterminer la réussite d&#39;une expérience ou d&#39;une offre donnée dans une activité [!DNL Target]. Par exemple, vous pouvez déterminer si une nouvelle offre ou l’ajout d’un article à un panier augmente les recettes par visiteur. Les mesures de succès peuvent s’avérer utiles pour identifier des problèmes liés à l’inscription, à la commande ou aux tunnels de vente, mais aussi avec l’engagement des visiteurs ou des clients. [En savoir plus](/help/c-activities/r-success-metrics/success-metrics.md). |
| Rapports | Informations sur l’avancement et les résultats de vos activités qui vous aident à prendre des décisions basées sur vos données. Les données des rapports peuvent vous aider à décider à quel moment terminer un test, vous montrer quelle expérience d’offre est gagnante et fournir des informations ou des leçons dont vous avez besoin pour déterminer les actions suivantes. [En savoir plus](/help/c-reports/reports.md). |

## Outils de création d&#39;Activités

[!DNL Target] Vous propose trois méthodes principales pour configurer vos activités de test et de personnalisation, le compositeur [!UICONTROL  d’expérience ] visuelle (VEC), le compositeur [!UICONTROL  d’expérience d’après les ]formulaires et le compositeur [!UICONTROL  d’expérience visuelle de l’application ]d’une seule page (SPA). Les deux étapes vous guident tout au long du processus de configuration des activités en trois étapes : la définition des expériences, la sélection ou la définition des audiences et la sélection des mesures de réussite Principales et secondaires par lesquelles vous mesurerez les résultats de votre activité.

| Outil | Détails |
| --- | --- |
| Compositeur d’expérience visuelle | Interface utilisateur WYSIWYG qui vous permet de créer et de tester facilement des expériences et des offres personnalisées dans le contexte du site. Vous pouvez créer des expériences et des offres pour les activités [!DNL Target] en les faisant glisser et en les déposant, en les permutant et en modifiant la disposition et le contenu d’une page Web (ou offre) ou d’une page Web mobile. [En savoir plus](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Compositeur d’expérience d’après les formulaires] | Interface de création d’expériences et d’offres non visuelles qui est utile pour créer des expériences à utiliser dans les tests A/B, le ciblage d’expérience, Automated Personalization et Recommendations lorsque le compositeur d’expérience visuelle n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le compositeur basé sur les formulaires pour créer des expériences et des offres pour une diffusion dans des courriels, des bornes et des assistants vocaux. [En savoir plus](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Compositeur visuel d’expérience de l’application d’une seule page (SPA)] | Le compositeur d’expérience visuelle (VEC) pour applications d’une seule page (SPA) permet aux marketeurs de créer des tests et de personnaliser le contenu des SPA eux-mêmes sans dépendances de développement continu. Le compositeur d’expérience visuelle peut être utilisé pour créer des activités de test AB et de ciblage d’expérience (XT) sur les infrastructures les plus populaires, telles que React et Angular. [En savoir plus](/help/c-experiences/spa-visual-experience-composer.md). |

## Gouvernance et contrôle

Pour fournir aux personnes appropriées les rôles appropriés et les niveaux d&#39;accès et d&#39;autorisations associés à [!DNL Target], nous avons une console d&#39;administration. Pour les utilisateurs de [!UICONTROL Cible Premium], nous offres une gouvernance et un contrôle plus détaillés
avec [!UICONTROL Autorisations d’entreprise].

| Outil | Détails |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Ajoutez les utilisateurs à Adobe Target et affectez des autorisations à partir du Adobe Admin Console. [En savoir plus](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| Autorisations<br> Enterprise (Premium) | Un moyen officiel d&#39;administrer à l&#39;échelle de l&#39;entreprise l&#39;accès des utilisateurs à [!DNL Target]. Ajoutez les utilisateurs à [!DNL Target], attribuez des autorisations en fonction de leurs rôles et créez des espaces de travail pour les équipes en fonction de différents départements, emplacements globaux, canaux et autres regroupements logiques. Vous pouvez attribuer aux utilisateurs les rôles d’observateur, d’éditeur, d’éditeur ou d’approbateur. [En savoir plus](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

## Intégrations

[!DNL Target] peut s’intégrer à de nombreux systèmes propriétaires, secondaires et tiers. Ces
les intégrations peuvent s’avérer utiles pour vous permettre d’accéder aux données des visiteurs et des clients disponibles à partir de ces systèmes pour les utiliser dans la création d’audiences à des fins de test et de personnalisation. Dans le cadre de [!DNL Adobe Experience Cloud], [!DNL Target] s&#39;intègre étroitement aux solutions [!DNL Experience Cloud] et à ses services principaux.

| Intégration | Détails |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] comporte des fonctionnalités intégrées avec d’autres  [!DNL Adobe Experience Cloud] solutions pour personnaliser les expériences à grande échelle. Exploitez la puissance de [!DNL Target] avec [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), [Audiences Experience Cloud](/help/c-integrating-target-with-mac/mmp.md), [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) et [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM). |
| API de cible (Premium) |  Target propose plus de 40 API que vous pouvez utiliser pour intégrer Adobe Target à des systèmes propriétaires, secondaires et tiers. [En savoir plus](/help/api/api-overview.md). |

## Gardez à l’esprit

Examinons les idées suivantes avant de passer au chapitre suivant : &quot;Développez vos idées de test et de personnalisation.&quot;

### Meilleures pratiques en matière d’optimisation

* **Bonne stratégie** : Quel est notre objectif et notre hypothèse ? Sont-ils alignés ? Par exemple, nous voulons augmenter les soumissions de demandes de prêt, nous supposons donc que la réduction du nombre de champs dans le formulaire de demande fera cela.
* **Une** méthodologie disciplinéeCommençons-nous à tester aux bons endroits ? Par exemple, vous avez besoin d’emplacements qui ont un trafic suffisant et qui ont un impact sur les mesures importantes.    à l&#39;entreprise.
* **Une bonne** configurationNotre activité est-elle configurée pour atteindre notre objectif ? Par exemple, si nous tentons d&#39;augmenter les demandes de prêt, nous devrions cible les personnes intéressées par les prêts et mesurer les clics sur le bouton &quot;Envoyer&quot;.
* **Analyse** approfondie : L&#39;activité de test s&#39;est-elle exécutée jusqu&#39;à la fin ? Que disent les résultats ? Exécutez votre activité jusqu’à ce qu’elle atteigne un degré de confiance statistique compris entre 95 et 99 %. Document pourquoi vous pensez que l&#39;expérience gagnante a gagné et appliquer l&#39;apprentissage ailleurs.
* **Tests** itératifs : Tirons-nous parti des enseignements tirés des activités précédentes ? Si vous trouvez une tactique gagnante, essayez de l’améliorer ou d’apporter des modifications qui l’accompagnent pour améliorer davantage votre mesure de réussite.

### Les opinions peuvent avoir une incidence négative sur vos résultats.

* Opinions qui peuvent avoir un impact négatif sur votre efficacité. Opinion de la personne la plus payée (HIPPO), attitudes, préjugés. Par exemple, le PDG souhaite réduire la taille de la zone de recherche pour faire plus de place sur chaque page. Nous devons effectuer des tests pour nous assurer qu’ils ne réduisent pas le nombre de recherches.
* Agis-tu sur les opinions ? Je n&#39;aime pas l&#39;aspect de ce test. Le client n’appréciera pas du tout cette expérience. Bien que l’intuition soit utile, les tests A/B ont prouvé à maintes reprises qu’elle n’est pas toujours visible.
* Ou avez-vous un état d&#39;esprit d&#39;optimisation ? Je suis ravi de voir quelle expérience gagne. Avons-nous suffisamment d&#39;options à tester ?

### Les hypothèses peuvent également avoir une incidence négative sur les résultats

* Hypothèses qui peuvent avoir un impact négatif sur votre efficacité. La mentalité des troupeaux (c&#39;est comme ça que nos concurrents le font). Par exemple, tous nos concurrents utilisent des bannières à héros avec des images rotatives, donc nous devrions aussi.
* En supposant que nous sachions pourquoi quelque chose fonctionne ou non. En supposant que nous n&#39;ayons pas besoin de tester quelque chose. Par exemple, nous avons toujours liste les chambres d&#39;hôtel dans l&#39;ordre du plus élevé au plus bas prix comme valeur par défaut.
* Agis-tu selon des hypothèses ? Nous n&#39;avons pas besoin de tester cela, nous avons vérifié les analyses. (Oui, mais il y a peut-être plus que ce que révèle l&#39;analyse.)
* Ou avez-vous un état d&#39;esprit d&#39;optimisation ? Nous testons tout.