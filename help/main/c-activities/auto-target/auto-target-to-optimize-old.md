---
keywords: ciblage automatique;ciblage;affectation de trafic;questions fréquentes;faq;dépannage;dépannage
description: Découvrez comment une activité [!UICONTROL Auto-Target] dans offre  [!DNL Target]  expérience la plus adaptée à chaque visiteur en fonction des profils client et du comportement de visiteurs similaires.
title: Qu’est-ce qu’une activité [!UICONTROL Auto-Target] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1864'
ht-degree: 21%

---

# Vue d’ensemble des [!UICONTROL Auto-Target]

[!UICONTROL Auto-Target] activités dans [!DNL Adobe Target] utilisent le machine learning avancé pour sélectionner plusieurs expériences hautement performantes définies par des spécialistes marketing afin de personnaliser le contenu et de générer des conversions. [!UICONTROL Auto-Target] offre à chaque visiteur l’expérience la plus adaptée en fonction du profil client individuel et du comportement des visiteurs précédents présentant des profils similaires.

>[!NOTE]
>
>* [!UICONTROL Auto-Target] est disponible dans le cadre de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md).
>
>* [!UICONTROL Analytics for Target] (A4T) prend en charge les activités [!UICONTROL Auto-Target]. Pour plus d’informations, consultez Prise en charge d’[&#x200B; A4T pour les activités d’affectation automatique et de ciblage automatique &#x200B;](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## Témoignages de clients qui utilisent le ciblage automatique {#success}

Un retailer vestimentaire majeur a récemment utilisé une activité [!UICONTROL Auto-Target] avec dix expériences basées sur des catégories de produits (ainsi qu’un contrôle randomisé) pour fournir le contenu approprié à chaque visiteur. « [!UICONTROL Add to Cart] » a été choisi comme mesure d’optimisation principale. Les expériences ciblées ont connu une augmentation moyenne de 29,09 %. Après avoir créé les modèles [!UICONTROL Auto-Target], l’activité a été définie sur 90 % d’expériences personnalisées.

En dix jours seulement, plus de 1 700 000 $ ont été débloqués.

Continuez à lire pour savoir comment utiliser [!UICONTROL Auto-Target] afin d’augmenter l’effet élévateur et les recettes de votre entreprise.

## Aperçu {#section_972257739A2648AFA7E7556B693079C9}

Lors de la [création d’une activité A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) à l’aide du workflow guidé en trois étapes, choisissez l’option **[!UICONTROL Auto-Target for personalized experiences]** sur la page **[!UICONTROL Targeting]** (étape 2).

![Option de Ciblage automatique pour les expériences personnalisées](/help/main/c-activities/assets/auto-target-ui-new.png)

L’option [!UICONTROL Auto-Target] dans le flux d’activités A/B vous permet d’exploiter le machine learning pour effectuer une personnalisation en fonction d’un ensemble d’expériences définies par les spécialistes marketing en un seul clic. [!UICONTROL Auto-Target] est conçu pour offrir une optimisation maximale, par rapport aux tests A/B ou aux [!UICONTROL Auto Allocate] traditionnels, en déterminant l’expérience à afficher pour chaque visiteur. Contrairement à une activité A/B dans laquelle l’objectif est de trouver un gagnant unique, [!UICONTROL Auto-Target] détermine automatiquement la meilleure expérience pour un visiteur donné. La meilleure expérience est basée sur le profil du visiteur et d’autres informations contextuelles afin de fournir une expérience hautement personnalisée.

De même qu’[!UICONTROL Automated Personalization], [!UICONTROL Auto-Target] utilise un [algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), une méthode d’ensemble de science des données de pointe, pour déterminer la meilleure expérience à montrer à un visiteur. Étant donné que [!UICONTROL Auto-Target] pouvez s’adapter aux changements de comportement des visiteurs, il peut s’exécuter perpétuellement pour fournir un effet élévateur. Cette méthode est parfois appelée mode « toujours actif ».

Contrairement à une activité A/B dans laquelle l’affectation d’expérience pour un visiteur donné est persistante, [!UICONTROL Auto-Target] optimise l’objectif commercial spécifié pour chaque visite. Comme dans [!UICONTROL Auto Personalization], [!UICONTROL Auto-Target], par défaut, réserve une partie du trafic de l’activité en tant que population témoin pour mesurer l’effet élévateur. Les visiteurs du groupe de contrôle reçoivent une expérience aléatoire dans l’activité.

## Considérations

Voici quelques points importants à garder à l’esprit lors de l’utilisation de [!UICONTROL Auto-Target] :

* Vous ne pouvez pas changer une activité spécifique de [!UICONTROL Auto-Target] en [!UICONTROL Automated Personalization], et inversement.
* Vous ne pouvez pas passer de l’affectation de trafic [!UICONTROL Manual] ([!UICONTROL A/B Test] classique) à [!UICONTROL Auto-Target], et inversement après l’enregistrement d’une activité en tant que brouillon.
* Un modèle est conçu pour identifier les performances de la stratégie personnalisée par rapport au trafic diffusé de manière aléatoire par rapport à l’envoi de tout le trafic vers l’expérience gagnante globale. Ce modèle prend uniquement en compte les accès et les conversions dans l’environnement par défaut.

  Le trafic provenant d’un second ensemble de modèles est créé pour chaque groupe de modélisation (AP) ou expérience (AT). Pour chacun de ces modèles, les accès et les conversions dans tous les environnements sont pris en compte.

  Les requêtes sont diffusées avec le même modèle, quel que soit l’environnement, mais la pluralité de trafic doit provenir de l’environnement par défaut pour s’assurer que l’expérience gagnante globale identifiée est cohérente avec le comportement réel.

* Utilisez au moins deux expériences.

## Terminologie  {#section_A309B7E0B258467789A5CACDC1D923F3}

Les termes suivants sont utiles pour aborder le [!UICONTROL Auto-Target] :

| Terme | Définition |
|---|---|
| [Bandit manchot](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | Une approche du type bandit à plusieurs bras de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage. |
| [Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. En langage de science des données, il s’agit d’une classification d’ensemble, ou méthode de régression, qui fonctionne en construisant de nombreux arbres de décision en fonction des attributs du visiteur et de la visite. Dans [!DNL Target], Random Forest est utilisé pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou le revenu le plus élevé par visite) pour chaque visiteur spécifique. |
| [Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | L’objectif de l’échantillonnage de Thompson est de déterminer quelle expérience est la meilleure globalement (non personnalisée), tout en réduisant le « coût » de la recherche de cette expérience. L’échantillonnage de Thompson sélectionne toujours un gagnant, même s’il n’existe aucune différence statistique entre deux expériences. |

## Fonctionnement de [!UICONTROL Auto-Target] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Pour en savoir plus sur les données et les algorithmes sous-jacents aux [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization], consultez les liens ci-dessous :

| Terme | Détails |
|--- |--- |
| [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Le principal algorithme de personnalisation de [!DNL Target] utilisé dans [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] est Random Forest. Des méthodes d&#39;ensemble, telles que Random Forest, utilisent de multiples algorithmes d&#39;apprentissage pour obtenir de meilleures performances prédictives que celles qui pourraient être obtenues à partir de n&#39;importe lequel des algorithmes d&#39;apprentissage constitutifs. L’algorithme Forêt aléatoire dans les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target] est une méthode de classification, ou de régression, qui fonctionne en construisant une multitude d’arbres de décision au moment de l’entraînement. |
| [Chargement des données pour  [!DNL Target] algorithmes Personalization de &#x200B;](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Il existe plusieurs façons de saisir des données pour les modèles [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization]. |
| [Collecte de données pour les algorithmes Personalization de  [!DNL Target]](/help/main/c-activities/t-automated-personalization/ap-data.md) | Les algorithmes de personnalisation de [!DNL Target] collectent automatiquement diverses données. |

## Détermination de l’affectation du trafic {#section_AB3656F71D2D4C67A55A24B38092958F}

Selon l’objectif de votre activité, vous pouvez sélectionner une affectation de trafic différente entre les expériences de contrôle et de ciblage. Une règle de bonne pratique consiste à déterminer cet objectif avant de lancer votre activité en direct.

La liste déroulante [!UICONTROL Custom Allocation] permet d&#39;effectuer un choix parmi les options suivantes :

* [!UICONTROL Evaluate Personalization Algorithm]
* [!UICONTROL Maximize Personalization Traffic]
* [!UICONTROL Custom Allocation]

![Liste déroulante Objectif d’affectation](/help/main/c-activities/assets/split-new.png)

| Objectif de l’activité | Suggestion d’affectation du trafic | Compromis |
|--- |--- |--- |
| **Évaluer l’algorithme de personnalisation (50/50)** : Si votre objectif est de tester l’algorithme, utilisez une répartition à 50/50 des visiteurs entre le contrôle et l’algorithme ciblé. Cette répartition produira l’estimation de l’effet élévateur la plus précise. Suggérée pour une utilisation avec des « expériences aléatoires » comme contrôle. | Répartition entre contrôle à 50 % et expérience personnalisée à 50 % | <ul><li>Maximise la précision de l’effet élévateur entre le contrôle et la personnalisation</li><li>Moins de visiteurs ont une expérience personnalisée</li></ul> |
| **Maximiser le trafic Personalization (90/10)** : si votre objectif est de créer une activité « toujours active », placez 10 % des visiteurs dans le contrôle pour vous assurer qu’il y a suffisamment de données pour que les algorithmes continuent à apprendre au fil du temps. Le compromis ici est qu&#39;en échange de la personnalisation d&#39;une plus grande proportion de votre trafic, vous avez moins de précision dans ce qu&#39;est exactement l&#39;ascenseur. Quel que soit votre objectif, il s’agit du trafic recommandé lors de l’utilisation d’une expérience spécifique comme contrôle. | Une règle de bonne pratique consiste à répartir le trafic entre le contrôle de 10 à 30 % et l’expérience personnalisée de 70 à 90 %. | <ul><li>Maximise le nombre de visiteurs qui auront une expérience personnalisée</li><li>Maximise l’effet élévateur</li><li>Moins de précision quant à la nature de l’effet élévateur vis-à-vis de l’activité</li></ul> |
| **Affectation personnalisée** | Répartir manuellement le pourcentage suivant les besoins. | <ul><li>Il se peut que vous n’obteniez pas les résultats souhaités. En cas d’incertitude, suivez les suggestions indiquées pour l’une des options précédentes.</li></ul> |

Pour ajuster le pourcentage de [!UICONTROL Control], cliquez sur les icônes de la colonne [!UICONTROL Allocation]. Vous ne pouvez pas diminuer le groupe de contrôle à moins de 10 %.

![Modification de l’affectation du trafic de ciblage automatique](/help/main/c-activities/assets/auto-target-control.png)

Vous pouvez [sélectionner une expérience spécifique à utiliser comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou utiliser l’option Expérience aléatoire.

## Quand devriez-vous choisir [!UICONTROL Auto-Target] plutôt que [!UICONTROL Automated Personalization] ? {#section_BBC4871C87944DD7A8B925811A30C633}

Il existe plusieurs scénarios dans lesquels vous pouvez préférer utiliser [!UICONTROL Auto-Target] plutôt que [!UICONTROL Automated Personalization] :

* Si vous souhaitez définir l’expérience entière plutôt que des offres individuelles automatiquement combinées pour former une expérience.
* Si vous souhaitez utiliser l’ensemble des fonctionnalités [!UICONTROL Visual Experience Composer] (VEC) non prises en charge par [!UICONTROL Auto Personalization] : l’éditeur de code personnalisé, plusieurs audiences d’expérience, etc.
* Lorsque vous souhaitez apporter des modifications structurelles à votre page dans différentes expériences. Par exemple, si vous souhaitez réorganiser les éléments sur votre page d’accueil, [!UICONTROL Auto-Target] est plus approprié d’utiliser que [!UICONTROL Automated Personalization].

## Qu&#39;est-ce que [!UICONTROL Auto-Target] avez en commun avec [!UICONTROL Automated Personalization] ? {#section_2A601F482F9A44E38D4B694668711319}

### L’algorithme s’optimise pour obtenir un résultat favorable pour chaque visite.

* L’algorithme prédit la propension d’un visiteur à la conversion (ou le chiffre d’affaires estimé provenant de la conversion) pour offrir la meilleure expérience.
* Un visiteur est éligible à une nouvelle expérience à la fin d’une session existante (sauf s’il fait partie de la population témoin, auquel cas l’expérience qui lui est affectée lors de sa première visite reste la même pour les visites suivantes).
* Au cours d’une session, la prédiction ne change pas afin de maintenir la cohérence visuelle.

### L’algorithme s’adapte aux changements de comportement des visiteurs.

* Le bandit à plusieurs bras garantit que le modèle « dépense » toujours une petite fraction du trafic pour continuer à apprendre tout au long de la vie de l’apprentissage par activité et pour éviter la surexploitation des tendances apprises précédemment.
* Les modèles sous-jacents sont reconstruits toutes les 24 heures à l’aide des dernières données de comportement des visiteurs afin de s’assurer que [!DNL Target] exploite toujours les préférences changeantes des visiteurs.
* Si l’algorithme ne peut pas déterminer les expériences gagnantes pour les individus, il affiche automatiquement l’expérience globale la plus performante tout en continuant à rechercher des gagnants personnalisés. L’expérience la plus performante est trouvée en utilisant l’[échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

### L’algorithme s’optimise en continu pour une seule mesure d’objectif.

* Cette mesure peut être basée sur la conversion ou sur le chiffre d’affaires (plus précisément [!UICONTROL Revenue per Visit]).

### [!DNL Target] collecte automatiquement des informations sur les visiteurs afin de créer les modèles de personnalisation.

* Pour plus d’informations sur les paramètres utilisés dans [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization], voir [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

### [!DNL Target] utilise automatiquement toutes [!DNL Adobe Experience Cloud] audiences partagées pour créer des modèles de personnalisation.

* Vous n’avez rien besoin de faire de particulier pour ajouter des audiences au modèle. Pour plus d’informations sur l’utilisation de [!DNL Experience Cloud Audiences] avec [!DNL Target], voir [Audiences d’Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

### Les marketeurs peuvent charger des données hors ligne, des scores de propension ou d’autres données personnalisées pour créer des modèles de personnalisation.

* En savoir plus sur le [chargement de données pour [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## En quoi diffère-t-[!UICONTROL Auto-Target] de [!UICONTROL Automated Personalization] ? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target] nécessite souvent moins de trafic que [!UICONTROL Automated Personalization] pour la création d’un modèle personnalisé.

Bien que la quantité de trafic *par expérience* requise pour que les modèles [!UICONTROL Auto-Target] ou [!UICONTROL Auto Personalization] soient créés soit la même, il y a généralement plus d’expériences dans une activité [!UICONTROL Automated Personalization] qu’une activité [!UICONTROL Auto-Target].

Par exemple, si vous aviez une activité [!UICONTROL Auto Personalization] dans laquelle vous avez créé deux offres par emplacement avec deux emplacements, il y aurait quatre (2 = 4) expériences totales incluses dans l’activité (sans exclusion). En utilisant [!UICONTROL Auto-Target], vous pouvez définir l’expérience 1 pour inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2, et l’expérience 2 pour inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2. Étant donné que [!UICONTROL Auto-Target] vous permet de choisir plusieurs modifications au sein d’une expérience, vous pouvez réduire le nombre total d’expériences dans votre activité.

Par [!UICONTROL Auto-Target], des règles générales simples peuvent être utilisées pour comprendre les exigences du trafic :

* **Lorsque [!UICONTROL Conversion] est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour et par expérience, et en outre l’activité doit avoir au moins 7 000 visites et 350 conversions.
* **Lorsque [!UICONTROL Revenue per Visit] est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour et par expérience, et en outre l’activité doit avoir au moins 1 000 conversions par expérience. Le revenu par visite nécessite généralement plus de données pour élaborer des modèles en raison de la variance de données plus prononcée généralement constatée dans le revenu par visite comparativement au taux de conversion.

### [!UICONTROL Auto-Target] dispose d’une fonctionnalité de configuration complète.

* Étant donné que [!UICONTROL Auto-Target] est incorporé dans le workflow d’activité A/B, [!UICONTROL Auto-Target] bénéficie des [!UICONTROL Visual Experience Composer] plus matures et à part entière (VEC). Vous pouvez également utiliser des liens [QA](/help/main/c-activities/c-activity-qa/activity-qa.md) avec [!UICONTROL Auto-Target].

### [!UICONTROL Auto-Target] fournit un cadre de test en ligne complet.

* Le bandit à plusieurs bras fait partie d&#39;un cadre de test en ligne plus vaste qui permet aux chercheurs et aux spécialistes des données [!DNL Adobe] de comprendre les avantages de leurs améliorations continues dans des conditions réelles.
* À l’avenir, ce banc d’essai nous permettra d’ouvrir [!DNL Adobe] plateforme d’apprentissage automatique aux clients qui maîtrisent les données afin qu’ils puissent introduire leurs propres modèles pour compléter les modèles [!DNL Target].

## Rapports et [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Pour plus d’informations, voir [Reporting et ciblage automatique](/help/main/c-activities/auto-target/reporting-and-auto-target.md).

## Vidéo de formation : Présentation des activités de ciblage automatique

Cette vidéo explique comment configurer une activité A/B [!UICONTROL Auto-Target].

Après avoir terminé cette formation, vous devez être en mesure de :

* Définition des tests de [!UICONTROL Auto-Target]
* Comparer et mettre en contraste les [!UICONTROL Auto-Target] avec les [!UICONTROL Automated Personalization]
* Création d’activités [!UICONTROL Auto-Target]

>[!VIDEO](https://video.tv.adobe.com/v/18558)
