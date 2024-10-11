---
keywords: ciblage automatique;ciblage;affectation du trafic;questions fréquentes;faq;dépannage;dépannage
description: Découvrez comment une activité [!UICONTROL Auto-Target] diffuse l’expérience la plus personnalisée à chaque visiteur selon les profils client et le comportement de visiteurs similaires.
title: Qu’est-ce qu’une activité [!UICONTROL Auto-Target] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez ce qui est inclus dans Target Premium."
feature: Auto-Target
hide: true
hidefromtoc: true
source-git-commit: 5fc18c6d3b493ea0a58048cc20ce3a6c2ffb7d14
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 18%

---

# [!UICONTROL Auto-Target] - Aperçu

Les activités [!UICONTROL Auto-Target] de [!DNL Adobe Target] utilisent l’apprentissage automatique avancé pour effectuer une sélection parmi plusieurs expériences hautement performantes définies par des responsables du marketing afin de personnaliser le contenu et de générer des conversions. [!UICONTROL Auto-Target] diffuse l’expérience la plus personnalisée à chaque visiteur en fonction du profil client individuel et du comportement des visiteurs précédents dotés de profils similaires.

>[!NOTE]
>
>* [!UICONTROL Auto-Target] est disponible dans le cadre de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md).
>
>* [!UICONTROL Analytics for Target] (A4T) prend en charge les activités [!UICONTROL Auto-Target]. Pour plus d’informations, voir [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## Témoignage de succès dans le monde réel à l’aide du ciblage automatique {#success}

Un grand détaillant de vêtements a récemment utilisé une activité [!UICONTROL Auto-Target] avec dix expériences basées sur des catégories de produits (plus contrôle aléatoire) pour fournir le contenu approprié à chaque visiteur. &quot;[!UICONTROL Add to Cart]&quot; a été choisi comme mesure d’optimisation principale. Les expériences ciblées ont un effet élévateur moyen de 29,09 %. Après la création des modèles [!UICONTROL Auto-Target], l’activité a été définie sur 90 % d’expériences personnalisées.

En seulement dix jours, plus de 1 700 000 $ en effet élévateur a été atteint.

Continuez à lire pour savoir comment utiliser [!UICONTROL Auto-Target] pour augmenter l’effet élévateur et les recettes de votre entreprise.

## Aperçu {#section_972257739A2648AFA7E7556B693079C9}

Lors de la [création d’une activité A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) à l’aide du processus assisté en trois étapes, sélectionnez l’option **[!UICONTROL Auto-Target for personalized experiences]** sur la page **[!UICONTROL Targeting]** (étape 2).

![ Paramètres de méthode d’affectation du trafic ](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

L’option [!UICONTROL Auto-Target] du flux d’activité A/B vous permet d’exploiter l’apprentissage automatique pour effectuer une personnalisation sur la base d’un ensemble d’expériences définies par le marketeur en un seul clic. [!UICONTROL Auto-Target] est conçu pour offrir une optimisation maximale, par rapport aux tests A/B traditionnels ou [!UICONTROL Auto Allocate], en déterminant l’expérience à afficher pour chaque visiteur. Contrairement à une activité A/B dont l’objectif est de trouver un gagnant unique, [!UICONTROL Auto-Target] détermine automatiquement la meilleure expérience pour un visiteur donné. La meilleure expérience est basée sur le profil du visiteur et d’autres informations contextuelles pour offrir une expérience hautement personnalisée.

De même que [!UICONTROL Automated Personalization], [!UICONTROL Auto-Target] utilise un [ algorithme Forêt aléatoire ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), une méthode d’ensemble issue de la science des données, pour déterminer la meilleure expérience à présenter à un visiteur. [!UICONTROL Auto-Target] pouvant s’adapter aux changements de comportement du visiteur, il peut s’exécuter perpétuellement pour générer un effet élévateur. Cette méthode est parfois appelée mode &quot;toujours actif&quot;.

Contrairement à une activité A/B où l’affectation d’expérience pour un visiteur donné est persistante, [!UICONTROL Auto-Target] optimise l’objectif commercial spécifié à chaque visite. Comme dans [!UICONTROL Auto Personalization], [!UICONTROL Auto-Target], par défaut, réserve une partie du trafic de l’activité en tant que groupe témoin pour mesurer l’effet élévateur. Les visiteurs du groupe de contrôle reçoivent une expérience aléatoire dans l’activité.

## Considérations

Quelques points importants doivent être pris en compte lors de l’utilisation de [!UICONTROL Auto-Target] :

* Vous ne pouvez pas passer une activité spécifique de [!UICONTROL Auto-Target] à [!UICONTROL Automated Personalization], et de la manière inverse.
* Vous ne pouvez pas passer de l’affectation de trafic [!UICONTROL Manual] (traditionnelle [!UICONTROL A/B Test]) à [!UICONTROL Auto-Target], et de la manière inverse après l’enregistrement d’une activité en tant que brouillon.
* Un modèle est conçu pour identifier les performances de la stratégie personnalisée par rapport au trafic diffusé de manière aléatoire plutôt que d’envoyer tout le trafic à l’expérience gagnante globale. Ce modèle ne prend en compte que les accès et les conversions dans l’environnement par défaut.

  Le trafic provenant d’un deuxième ensemble de modèles est créé pour chaque groupe de modélisation (AP) ou expérience (AT). Pour chacun de ces modèles, les accès et les conversions sont pris en compte dans tous les environnements.

  Les requêtes sont diffusées avec le même modèle, quel que soit l’environnement. Cependant, la pluralité du trafic doit provenir de l’environnement par défaut pour s’assurer que l’expérience gagnante globale identifiée est cohérente avec le comportement du monde réel.

* Utilisez au moins deux expériences.

## Terminologie  {#section_A309B7E0B258467789A5CACDC1D923F3}

Les termes suivants sont utiles pour discuter de [!UICONTROL Auto-Target] :

| Terme | Définition |
|---|---|
| [Bandit à plusieurs bras](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | Une approche du type bandit à plusieurs bras de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage. |
| [Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. En langage de science des données, il s’agit d’une classification d’ensemble, ou méthode de régression, qui fonctionne en construisant de nombreux arbres de décision en fonction des attributs du visiteur et de la visite. Dans [!DNL Target], l’algorithme Forêt aléatoire est utilisé pour déterminer l’expérience qui devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. |
| [Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | L’objectif de l’échantillonnage de Thompson est de déterminer la meilleure expérience globale (non personnalisée), tout en minimisant le &quot;coût&quot; de la recherche de cette expérience. L’échantillonnage de Thompson sélectionne toujours un gagnant, même s’il n’existe aucune différence statistique entre deux expériences. |

## Fonctionnement de [!UICONTROL Auto-Target] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Pour en savoir plus sur les données et les algorithmes sous-jacents [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization], voir les liens ci-dessous :

| Terme | Détails |
|--- |--- |
| [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | L’algorithme de personnalisation principal de [!DNL Target] utilisé à la fois dans [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] est l’algorithme Forêt aléatoire. Les méthodes d’ensemble, telles que l’algorithme Forêt aléatoire, utilisent plusieurs algorithmes d’apprentissage pour obtenir de meilleures performances prédictives que celles qui peuvent être obtenues à partir de n’importe quel algorithme d’apprentissage constitutif. L’algorithme Forêt aléatoire dans les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target] est une classification, ou méthode de régression, qui fonctionne en construisant une multitude d’arbres de décision au moment de la formation. |
| [Chargement de données pour les  [!DNL Target] algorithmes Personalization ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Il existe plusieurs façons de saisir des données pour les modèles [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization]. |
| [ Collecte de données pour les  [!DNL Target] algorithmes Personalization ](/help/main/c-activities/t-automated-personalization/ap-data.md) | Les algorithmes de personnalisation de [!DNL Target] collectent automatiquement diverses données. |

## Détermination de l’affectation du trafic {#section_AB3656F71D2D4C67A55A24B38092958F}

Selon l’objectif de votre activité, vous pouvez sélectionner une affectation de trafic différente entre les expériences de contrôle et de ciblage. Une règle de bonne pratique consiste à déterminer cet objectif avant de lancer votre activité en direct.

La liste déroulante [!UICONTROL Custom Allocation] vous permet de choisir parmi les options suivantes :

* [!UICONTROL Evaluate Personalization Algorithm (50/50)]
* [!UICONTROL Maximize Personalization Traffic (90/10)]
* [!UICONTROL Custom Allocation]

![Liste déroulante Objectif d’affectation](/help/main/c-activities/assets/split-new-ui.png)

Le tableau suivant présente les trois options suivantes :

| Objectif de l’activité | Suggestion d’affectation du trafic | Compromis |
|--- |--- |--- |
| **[!UICONTROL Evaluate Personalization Algorithm (50/50)]** : si votre objectif est de tester l’algorithme, utilisez une répartition de 50/50 % de visiteurs entre le contrôle et l’algorithme ciblé. Cette répartition produira l’estimation de l’effet élévateur la plus précise. Suggestion d’utilisation avec &quot;expériences aléatoires&quot; comme contrôle. | Répartition entre contrôle à 50 % et expérience personnalisée à 50 % | <ul><li>Maximise la précision de l’effet élévateur entre le contrôle et la personnalisation</li><li>Relativement moins de visiteurs ont une expérience personnalisée</li></ul> |
| **[!UICONTROL Maximize Personalization Traffic (90/10)]** : si votre objectif est de créer une activité &quot;toujours active&quot;, placez 10 % des visiteurs dans le contrôle afin de vous assurer qu’il y a suffisamment de données pour que les algorithmes continuent à apprendre au fil du temps. Le compromis ici est qu&#39;en exchange pour personnaliser une plus grande partie de votre trafic, vous avez moins de précision dans l&#39;effet élévateur exact. Quel que soit votre objectif, il s’agit du trafic recommandé lors de l’utilisation d’une expérience spécifique comme contrôle. | Une règle de bonne pratique consiste à répartir le trafic entre le contrôle de 10 à 30 % et l’expérience personnalisée de 70 à 90 %. | <ul><li>Maximise le nombre de visiteurs ayant une expérience personnalisée</li><li>Maximise l’effet élévateur</li><li>Moins de précision quant à la nature de l’effet élévateur vis-à-vis de l’activité</li></ul> |
| **Affectation personnalisée** | Répartir manuellement le pourcentage suivant les besoins. | <ul><li>Il se peut que vous n’obteniez pas les résultats souhaités. En cas d’incertitude, suivez les suggestions indiquées pour l’une des options précédentes.</li></ul> |

Pour ajuster le pourcentage [!UICONTROL Control], cliquez sur [!UICONTROL Experiences] dans le volet [!UICONTROL Traffic Allocation], puis ajustez les pourcentages suivant vos besoins. Vous ne pouvez pas diminuer le groupe de contrôle à moins de 10 %.

Vous pouvez [sélectionner une expérience spécifique à utiliser comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou utiliser l’option Expérience aléatoire.

## Quand devriez-vous choisir [!UICONTROL Auto-Target] plutôt que [!UICONTROL Automated Personalization] ? {#section_BBC4871C87944DD7A8B925811A30C633}

Il existe plusieurs scénarios dans lesquels vous préférerez peut-être utiliser [!UICONTROL Auto-Target] plutôt que [!UICONTROL Automated Personalization] :

* Si vous souhaitez définir l’expérience entière plutôt que des offres individuelles automatiquement combinées pour former une expérience.
* Si vous souhaitez utiliser l’ensemble complet des fonctionnalités [!UICONTROL Visual Experience Composer] (VEC) non prises en charge par [!UICONTROL Auto Personalization] : l’éditeur de code personnalisé, les audiences d’expériences multiples, etc.
* Lorsque vous souhaitez apporter des modifications structurelles à votre page dans différentes expériences. Par exemple, si vous souhaitez réorganiser les éléments sur votre page d’accueil, [!UICONTROL Auto-Target] est plus approprié que [!UICONTROL Automated Personalization].

## Qu&#39;est-ce que [!UICONTROL Auto-Target] a en commun avec [!UICONTROL Automated Personalization] ? {#section_2A601F482F9A44E38D4B694668711319}

### L’algorithme optimise les résultats favorables pour chaque visite.

* L’algorithme prédit la propension d’un visiteur à la conversion (ou les recettes estimées de la conversion) afin de fournir la meilleure expérience.
* Un visiteur est éligible pour une nouvelle expérience à la fin d’une session existante (sauf s’il fait partie de la population témoin, auquel cas l’expérience qui lui est attribuée lors de sa première visite reste la même pour les visites suivantes).
* Dans une session, la prédiction ne change pas, pour maintenir la cohérence visuelle.

### L’algorithme s’adapte aux changements de comportement du visiteur.

* Le bandit à plusieurs bras garantit que le modèle &quot;dépense&quot; toujours une petite fraction de trafic pour continuer à apprendre tout au long de la vie de l’activité d’apprentissage et pour empêcher la surexploitation des tendances apprises précédemment.
* Les modèles sous-jacents sont reconstruits toutes les 24 heures à l’aide des dernières données de comportement des visiteurs afin de garantir que [!DNL Target] exploite toujours l’évolution des préférences des visiteurs.
* Si l’algorithme ne peut pas déterminer les expériences gagnantes pour les individus, il affiche automatiquement l’expérience globale la plus performante tout en continuant à rechercher des gagnants personnalisés. L’expérience la plus performante est trouvée en utilisant l’[échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

### L’algorithme assure une optimisation continue pour une mesure d’objectif unique.

* Cette mesure peut être basée sur la conversion ou sur les recettes (plus spécifiquement [!UICONTROL Revenue per Visit]).

### [!DNL Target] collecte automatiquement des informations sur les visiteurs pour créer les modèles de personnalisation.

* Pour plus d’informations sur les paramètres utilisés dans [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization], voir [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

### [!DNL Target] utilise automatiquement toutes les [!DNL Adobe Experience Cloud] audiences partagées pour créer les modèles de personnalisation.

* Vous n’avez rien besoin de faire de particulier pour ajouter des audiences au modèle. Pour plus d’informations sur l’utilisation de [!DNL Experience Cloud Audiences] avec [!DNL Target], voir [Audiences d’Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

### Les marketeurs peuvent charger des données hors ligne, des scores de propension ou d’autres données personnalisées pour créer des modèles de personnalisation.

* En savoir plus sur le [chargement de données pour [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## En quoi [!UICONTROL Auto-Target] diffère-t-il de [!UICONTROL Automated Personalization] ? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target] nécessite souvent moins de trafic que [!UICONTROL Automated Personalization] pour générer un modèle personnalisé.

Bien que la quantité de trafic *par expérience* requise pour la création des modèles [!UICONTROL Auto-Target] ou [!UICONTROL Auto Personalization] soit la même, il existe généralement plus d’expériences dans une activité [!UICONTROL Automated Personalization] qu’une activité [!UICONTROL Auto-Target].

Par exemple, si vous avez une activité [!UICONTROL Auto Personalization] dans laquelle vous avez créé deux offres par emplacement avec deux emplacements, il y a au total quatre (2 = 4) expériences incluses dans l’activité (sans exclusions). En utilisant [!UICONTROL Auto-Target], vous pouvez définir l’expérience 1 pour inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2, et l’expérience 2 pour inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2. Étant donné que [!UICONTROL Auto-Target] vous permet de choisir plusieurs modifications au sein d’une seule expérience, vous pouvez réduire le nombre total d’expériences dans votre activité.

Pour [!UICONTROL Auto-Target], des règles de base simples peuvent être utilisées pour comprendre les exigences de trafic :

* **Lorsque [!UICONTROL Conversion] est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour et par expérience. De plus, l’activité doit comporter au moins 7 000 visites et 350 conversions.
* **Lorsque [!UICONTROL Revenue per Visit] est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour et par expérience, et en outre l’activité doit comporter au moins 1 000 conversions par expérience. Le revenu par visite nécessite généralement plus de données pour élaborer des modèles en raison de la variance de données plus prononcée généralement constatée dans le revenu par visite comparativement au taux de conversion.

### [!UICONTROL Auto-Target] dispose d’une fonctionnalité de configuration complète.

* [!UICONTROL Auto-Target] étant incorporé dans le workflow d’activité A/B, [!UICONTROL Auto-Target] bénéficie des [!UICONTROL Visual Experience Composer] (VEC), plus matures et complets. Vous pouvez également utiliser des [liens QA](/help/main/c-activities/c-activity-qa/activity-qa.md) avec [!UICONTROL Auto-Target].

### [!UICONTROL Auto-Target] fournit un cadre de test en ligne complet.

* Le bandit à plusieurs bras fait partie d’un cadre de test en ligne plus vaste qui permet à [!DNL Adobe] spécialistes des données et chercheurs de comprendre les avantages de leurs améliorations constantes dans les conditions réelles.
* À l’avenir, ce banc de test nous permettra d’ouvrir la plateforme d’apprentissage automatique [!DNL Adobe] aux clients à l’aise avec les données afin qu’ils puissent introduire leurs propres modèles pour augmenter les modèles [!DNL Target].

## Reporting et [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Pour plus d’informations, voir [Création de rapports et ciblage automatique](/help/main/c-activities/auto-target/reporting-and-auto-target.md).