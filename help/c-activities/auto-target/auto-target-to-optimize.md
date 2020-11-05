---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
description: La Cible automatique dans Adobe Target utilise l’apprentissage automatique avancé pour sélectionner parmi plusieurs expériences hautement performantes définies par les spécialistes du marketing afin de personnaliser le contenu et de générer des conversions. Le ciblage automatique offre à chaque visiteur l’expérience la plus personnalisée en fonction de son profil individuel et du comportement des visiteurs précédents avec des profils similaires.
title: Présentation de la Cible automatique
feature: auto-target
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
translation-type: tm+mt
source-git-commit: 7284a37dde0d89e1c81ef3813f98d936a4eced3b
workflow-type: tm+mt
source-wordcount: '2014'
ht-degree: 86%

---


# ![Présentation de la Cible automatique PREMIUM](/help/assets/premium.png)

[!UICONTROL Le ciblage automatique] utilise l’apprentissage automatique avancé pour sélectionner parmi plusieurs expériences hautement performantes définies par le marketeur pour personnaliser le contenu et générer des conversions. Le ciblage automatique offre à chaque visiteur l’expérience la plus personnalisée en fonction de son profil individuel et du comportement des visiteurs précédents avec des profils similaires.

>[!NOTE]
>
>Le [!UICONTROL ciblage automatique] fait partie de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/c-intro/intro.md).
>
>[!UICONTROL Analytics pour la Cible] (A4T) prend en charge les activités de Cible  automatique. Pour plus d’informations, voir [Création d’une activité qui utilise Analytics en tant que source](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)de rapports.

## Histoire de réussite dans le monde réel à l’aide de la Cible automatique {#success}

Un grand détaillant de vêtements a récemment utilisé une activité de Cible  automatique avec dix expériences basées sur la catégorie de produits (plus contrôle aléatoire) pour fournir le contenu approprié à chaque visiteur. &quot;[!UICONTROL Ajouter au panier]&quot; a été choisi comme mesure d’optimisation Principale. Les expériences ciblées ont connu un effet élévateur moyen de 29,09 %. Après avoir créé les modèles de Cible  automatique, l’activité a été définie sur 90 % d’expériences personnalisées.

En seulement dix jours, plus de 1 700 000 $ de croissance ont été obtenus.

Continuez à lire pour savoir comment utiliser la Cible  automatique pour augmenter l&#39;effet élévateur et les recettes de votre entreprise.

## Aperçu {#section_972257739A2648AFA7E7556B693079C9}

Lors de la [création d’une activité A/B à l’aide du workflow assisté en trois étapes](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), vous pouvez choisir d’affecter le trafic à l’aide de l’option [!UICONTROL Ciblage automatique pour les expériences personnalisées] :

![Option de Ciblage automatique pour les expériences personnalisées](/help/c-activities/assets/auto-target-ui-new.png)

L’option de [!UICONTROL ciblage automatique] au sein du flux d’activités A/B vous permet d’exploiter l’apprentissage automatique pour effectuer une personnalisation sur la base d’un ensemble d’expériences défini par le marketeur en un seul clic. [!UICONTROL Le ciblage automatique] est conçu pour offrir une optimisation maximale par rapport aux tests A/B traditionnels ou à l’affectation automatique, en déterminant quelle expérience afficher pour chaque visiteur. Contrairement à une activité A/B dont le but est de déterminer un gagnant unique, le [!UICONTROL ciblage automatique] détermine automatiquement la meilleure expérience pour un visiteur donné (en fonction de son profil et d’autres informations contextuelles) pour offrir une expérience hautement personnalisée.

À l’instar de la personnalisation automatisée, le [!UICONTROL ciblage automatique] utilise un algorithme Forêt aléatoire, c’est-à-dire une méthode d’ensemble issue de la science des données, pour déterminer la meilleure expérience à présenter à un visiteur. Comme le [!UICONTROL ciblage automatique] peut s’adapter aux changements de comportement du visiteur, il peut être exécuté perpétuellement pour générer un effet élévateur. Cette fonctionnalité est parfois appelée mode « toujours actif ».

Contrairement à une activité A/B où l’affectation d’expérience pour un visiteur donné est persistante, le [!UICONTROL ciblage automatique] optimise l’objectif commercial spécifié à chaque visite. À l’instar de la [!UICONTROL personnalisation automatisée], le [!UICONTROL ciblage automatique] réserve par défaut une partie du trafic de l’activité comme groupe de contrôle pour mesurer l’effet élévateur. Les visiteurs du groupe de contrôle reçoivent une expérience aléatoire dans l’activité.

## Considérations

There are a few important considerations to keep in mind when using [!UICONTROL Auto-Target]:

* Vous ne pouvez pas passer une activité spécifique du mode [!UICONTROL ciblage automatique] au mode personnalisation automatisée, et vice versa.
* Une fois qu’une activité est activée, vous ne pouvez pas passer du mode affectation du trafic manuel (test A/B classique) au mode [!UICONTROL ciblage automatique] et vice versa.
* Un modèle est créé pour identifier les performances du trafic de stratégie personnalisée par rapport au trafic diffusé de manière aléatoire par rapport à l’envoi de tout le trafic vers l’expérience gagnante globale. Ce modèle ne prend en compte que les accès et les conversions dans l’environnement par défaut.

   Le trafic à partir d’un second ensemble de modèles est généré pour chaque groupe de modélisation (AP) ou expérience (AT). Pour chacun de ces modèles, les accès et les conversions sont pris en compte dans tous les environnements.

   Les demandes seront donc servies avec le même modèle, quel que soit l&#39;environnement, mais la pluralité du trafic doit provenir de l&#39;environnement par défaut pour s&#39;assurer que l&#39;expérience gagnante globale identifiée est cohérente avec le comportement du monde réel.

* Vous devez utiliser deux expériences au minimum.

## Terminologie {#section_A309B7E0B258467789A5CACDC1D923F3}

Les termes suivants sont utiles pour aborder le [!UICONTROL ciblage automatique] :

| Terme | Définition |
|---|---|
| Bandit à plusieurs bras | Une approche du type bandit à plusieurs bras de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage. |
| Forêt aléatoire | La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. Dans le jargon de la science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en générant un grand nombre d’arbres de décision en fonction des attributs du visiteur et de la visite. Dans Target, le concept de la forêt aléatoire est utilisé pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. Pour plus d’informations sur l’application de la forêt aléatoire dans Target, voir [Algorithme Forêt aléatoire](/help/c-activities/t-automated-personalization/algo-random-forest.md). |
| Échantillonnage de Thompson | L’échantillonnage de Thompson a pour but de déterminer la meilleure expérience globale (non personnalisée), tout en minimisant le « coût » de son identification. L’échantillonnage de Thompson désigne toujours un gagnant, même s’il n’existe aucune différence statistique entre deux expériences. Pour plus d’informations, voir [Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Fonctionnement du [!UICONTROL ciblage automatique ]{#section_77240E2DEB7D4CD89F52BE0A85E20136}

Pour plus d’informations sur les données et les algorithmes sous-jacents du [!UICONTROL ciblage automatique] et de la personnalisation automatisée, voir les liens ci-dessous :

| Terme | Détails |
|--- |--- |
| [Algorithme Forêt aléatoire](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Le principal algorithme de personnalisation de Target utilisé à la fois pour le [!UICONTROL ciblage automatique] et la personnalisation automatisée est l’algorithme Forêt aléatoire. Les méthodes d’ensemble telles que la forêt aléatoire utilisent plusieurs algorithmes d’apprentissage pour obtenir de meilleures performances prédictives que celles qui peuvent être obtenues à partir des algorithmes d’apprentissage qui les constituent. L’algorithme Forêt aléatoire du système d’Automated Personalization est une classification ou une méthode de régression qui fonctionne en générant une multitude d’arbres de décision au moment de la formation. |
| [Chargement de données pour les algorithmes de personnalisation de Target](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Il existe plusieurs façons de saisir des données dans les modèles de [!UICONTROL ciblage automatique] et de personnalisation automatisée. |
| [Collecte de données pour les algorithmes de personnalisation de Target](/help/c-activities/t-automated-personalization/ap-data.md) | Les algorithmes de personnalisation de Target recueillent automatiquement une grande diversité de données. |

## Détermination de l’affectation du trafic {#section_AB3656F71D2D4C67A55A24B38092958F}

Selon l’objectif de votre activité, vous pouvez sélectionner une affectation de trafic différente entre les expériences de contrôle et de ciblage. Une règle de bonne pratique consiste à déterminer cet objectif avant de lancer votre activité en direct.

La liste déroulante [!UICONTROL Affectation personnalisée] vous permet de choisir parmi les options suivantes :

* Évaluer l’algorithme de personnalisation
* Maximiser le trafic de personnalisation
* Affectation personnalisée

![Liste déroulante Objectif d’affectation](/help/c-activities/assets/split-new.png)

| Objectif de l’activité | Suggestion d’affectation du trafic | Compromis |
|--- |--- |--- |
| **Évaluer l’algorithme de personnalisation (50/50)** : Si votre objectif est de tester l’algorithme, utilisez une répartition à 50/50 des visiteurs entre le contrôle et l’algorithme ciblé. Cette répartition produira l’estimation de l’effet élévateur la plus précise. Utilisation suggérée avec des « expériences aléatoires » comme contrôle. | Répartition entre contrôle à 50 % et expérience personnalisée à 50 % | <ul><li>Maximise la précision de l’effet élévateur entre le contrôle et la personnalisation</li><li>Relativement moins de visiteurs auront une expérience personnalisée</li></ul> |
| **Maximiser le trafic de personnalisation (90/10)** : Si votre but est de créer une activité « toujours active », affectez 10 % des visiteurs dans le contrôle afin de vous assurer que la quantité de données est suffisante pour que les algorithmes continuent d’apprendre au fil du temps. Il est à noter que le compromis ici est qu’en échangeant la personnalisation d’une plus grande portion de votre trafic, vous obtiendrez une moins bonne précision de l’effet élévateur exact. Quel que soit votre objectif, il s’agit du trafic recommandé lors de l’utilisation d’une expérience spécifique comme contrôle. | Une règle de bonne pratique consiste à répartir le trafic entre le contrôle de 10 à 30 % et l’expérience personnalisée de 70 à 90 %. | <ul><li>Maximise le nombre de visiteurs qui auront une expérience personnalisée</li><li>Maximise l’effet élévateur</li><li>Moins de précision quant à la nature de l’effet élévateur vis-à-vis de l’activité</li></ul> |
| **Affectation personnalisée** | Répartir manuellement le pourcentage suivant les besoins. | <ul><li>Il se peut que vous n’obteniez pas les résultats souhaités. En cas d’incertitude, suivez les suggestions indiquées pour l’une des options précédentes.</li></ul> |

Pour ajuster le pourcentage de contrôle, cliquez sur les icônes dans la colonne Attribution. Vous ne pouvez pas diminuer le groupe de contrôle à moins de 10 %.

![Modification de l’affectation du trafic de ciblage automatique](/help/c-activities/assets/auto-target-control.png)

Vous pouvez [sélectionner une expérience spécifique à utiliser comme contrôle](/help/c-activities/t-automated-personalization/experience-as-control.md) ou utiliser l’option Expérience aléatoire.

## Quand devez-vous choisir le [!UICONTROL ciblage automatique] plutôt que la personnalisation automatisée ?{#section_BBC4871C87944DD7A8B925811A30C633}

Il existe plusieurs scénarios où vous pourrez privilégier le [!UICONTROL ciblage automatique] par rapport à la personnalisation automatisée :

* Lorsque vous souhaitez définir l’expérience entière plutôt que des offres individuelles qui seront automatiquement combinées pour former une expérience.
* Lorsque vous souhaitez exploiter l’ensemble des fonctionnalités du compositeur d’expérience visuelle (VEC) non prises en charge par la [!UICONTROL personnalisation automatisée] : l’éditeur de code personnalisé, les audiences d’expériences multiples, etc.
* Lorsque vous souhaitez apporter des modifications structurelles à votre page dans différentes expériences. Si vous souhaitez par exemple modifier l’ordre des éléments sur votre page d’accueil, le [!UICONTROL ciblage automatique] est plus approprié que la personnalisation automatisée.

## Quels sont les points communs entre le [!UICONTROL ciblage automatique] et la personnalisation automatisée ?{#section_2A601F482F9A44E38D4B694668711319}

**L’algorithme optimise le ciblage pour favoriser une issue positive à chaque visite.**

* L’algorithme prévoit la propension d’un visiteur à la conversion (ou les recettes estimées de la conversion) afin de servir la meilleure expérience.
* Un visiteur est éligible pour une nouvelle expérience au terme d’une session existante (à moins qu’il appartienne au groupe témoin, auquel cas l’expérience qui lui est affectée lors de sa première visite reste la même pour les visites ultérieures).
* Au sein d’une session, la prévision ne change pas afin de maintenir la cohérence visuelle.

**L’algorithme s’adapte aux changements de comportement du visiteur.**

* Le bandit à plusieurs bras garantit que le modèle utilise toujours une petite partie du trafic pour continuer d’apprendre tout au long de la vie de l’activité et prévenir la surexploitation des tendances apprises précédemment.
* Les modèles sous-jacents sont reconstruits toutes les 24 heures à l’aide des dernières données de comportement des visiteurs afin de garantir que Target exploite toujours l’évolution des préférences des visiteurs.
* Si l’algorithme ne peut pas déterminer les expériences gagnantes pour les individus, il affiche automatiquement l’expérience globale la plus performante tout en continuant à rechercher des gagnants personnalisés. L’expérience la plus performante est trouvée en utilisant l’[échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**L’algorithme assure une optimisation continue pour une mesure d’objectif unique.**

* Cette mesure peut être basée sur les conversions ou sur les recettes (plus spécifiquement les recettes par visite).

**Target collecte automatiquement des informations sur les visiteurs pour créer les modèles de personnalisation.**

* Pour plus d’informations sur les paramètres utilisés pour le [!UICONTROL ciblage automatique] et la personnalisation automatisée, voir [Collecte de données de personnalisation automatisée](/help/c-activities/t-automated-personalization/ap-data.md).

**Target utilise automatiquement toutes les audiences partagées d’Experience Cloud pour créer les modèles de personnalisation.**

* Vous n’avez rien besoin de faire de particulier pour ajouter des audiences au modèle. Pour plus d’informations sur l’utilisation des audiences Experience Cloud avec Target, voir [Audiences Experience Cloud](/help/c-integrating-target-with-mac/mmp.md)

**Les marketeurs peuvent télécharger des données hors ligne, les scores de propension ou d’autres données personnalisées pour créer des modèles de personnalisation.**

* En savoir plus sur le [téléchargement de données pour le ciblage automatique et la personnalisation automatisée](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## En quoi le [!UICONTROL ciblage automatique] diffère-t-il de la personnalisation automatisée ?{#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL Le ciblage automatique] nécessite souvent moins de trafic qu’Automated Personalization pour générer un modèle personnalisé.**

Bien que la quantité de trafic *par expérience* requise pour la création des modèles de [!UICONTROL ciblage automatique] ou [!UICONTROL d’Automated Personalization] soit la même, il y a habituellement plus d’expériences dans une activité Automated Personalization que dans une activité de [!UICONTROL ciblage automatique]. Si vous avez, par exemple, une activité [!UICONTROL Personnalisation automatisée] dans laquelle vous avez créé deux offres par lieu et comportant deux lieux, il y a au total quatre (2 = 4) expériences incluses dans l’activité (hors exclusions). En utilisant le [!UICONTROL ciblage automatique], vous pouvez définir l’expérience 1 de manière à inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2, et l’expérience 2 pour inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2. Étant donné que le [!UICONTROL ciblage automatique] permet de sélectionner plusieurs modifications au sein d’une seule expérience, vous pouvez réduire le nombre total d’expériences dans votre activité.

Pour le [!UICONTROL ciblage automatique], des règles de base simples permettent de comprendre les exigences en termes de trafic :

* **Lorsque la conversion est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour, par expérience, de plus l’activité doit comporter au moins 7 000 visites et 350 conversions.
* **Lorsque le revenu par visite est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour, par expérience, de plus l’activité doit comporter au moins 1 000 conversions par expérience. Le revenu par visite nécessite généralement plus de données pour élaborer des modèles en raison de la variance de données plus prononcée généralement constatée dans le revenu par visite comparativement au taux de conversion.

**[!UICONTROL Le ciblage automatique] offre des fonctionnalités de configuration complètes.**

* Comme le [!UICONTROL ciblage automatique] est incorporé dans le workflow d’activité A/B, il bénéficie des avantages offerts par le compositeur d’expérience visuelle (VEC), plus mûr et complet. Vous pouvez également utiliser [des liens QA](/help/c-activities/c-activity-qa/activity-qa.md) avec le [!UICONTROL ciblage automatique].

**[!UICONTROL Le ciblage automatique] offre un cadre de test en ligne complet.**

* Le bandit à plusieurs bras fait partie d’un cadre de test en ligne plus étendu permettant à nos chercheurs et analystes en données de cerner les avantages de leurs améliorations constantes en conditions réelles.
* À l’avenir, ce banc d’essai nous permettra d’ouvrir notre plateforme d’apprentissage automatique à nos clients disposant d’un savoir-faire en analyse de données afin qu’ils puissent introduire leurs propres modèles et ainsi étoffer la base de modèles de Target.

## Rapports et [!UICONTROL ciblage automatique] {#section_42EE7F5E65E84F89A872FE9921917F76}

Pour plus d’informations, voir [Rapport de synthèse de ciblage automatique](/help/c-reports/auto-target-summary-report.md) dans la section [Rapports](/help/c-reports/reports.md).

## Vidéo de formation : Présentation du badge ![Aperçu des Activités d&#39;Cible automatique](/help/assets/overview.png)

Cette vidéo explique comment configurer une activité A/B de [!UICONTROL ciblage automatique].

Après avoir terminé cette formation, vous devez être en mesure de :

* Définir des tests de [!UICONTROL ciblage automatique]
* Comparer le [!UICONTROL ciblage automatique] à la personnalisation automatisée
* Créer des activités de [!UICONTROL ciblage automatique]

>[!VIDEO](https://video.tv.adobe.com/v/18558)