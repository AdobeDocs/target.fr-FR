---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
title: Ciblage automatique
feature: auto-target
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '3610'
ht-degree: 85%

---


# ![PREMIUM](/help/assets/premium.png) Ciblage automatique{#auto-target}

[!UICONTROL Le ciblage automatique] utilise l’apprentissage automatique avancé pour sélectionner parmi plusieurs expériences hautement performantes définies par le marketeur pour personnaliser le contenu et générer des conversions. Le ciblage automatique offre à chaque visiteur l’expérience la plus personnalisée en fonction de son profil individuel et du comportement des visiteurs précédents avec des profils similaires.

>[!NOTE]
>
>Le [!UICONTROL ciblage automatique] fait partie de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/c-intro/intro.md).

Lors de la [création d’une activité A/B à l’aide du workflow assisté en trois étapes](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72), vous pouvez choisir d’affecter le trafic à l’aide de l’option [!UICONTROL Ciblage automatique pour les expériences personnalisées] :

![Option de Ciblage automatique pour les expériences personnalisées](/help/c-activities/assets/auto-target-ui-new.png)

## Aperçu {#section_972257739A2648AFA7E7556B693079C9}

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
| Forêt aléatoire | La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. Dans le jargon de la science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en générant un grand nombre d’arbres de décision en fonction des attributs du visiteur et de la visite. Dans Target, le concept de la forêt aléatoire est utilisé pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. Pour plus d’informations sur l’application de la forêt aléatoire dans Target, voir [Algorithme Forêt aléatoire](../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
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

**L’algorithme ne prend pas en charge l’utilisation d’[!DNL Analytics]en tant que source de données ou point de contact de création de rapports.**

**Target collecte automatiquement des informations sur les visiteurs pour créer les modèles de personnalisation.**

* Pour plus d’informations sur les paramètres utilisés pour le [!UICONTROL ciblage automatique] et la personnalisation automatisée, voir [Collecte de données de personnalisation automatisée](../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**Target utilise automatiquement toutes les audiences partagées d’Experience Cloud pour créer les modèles de personnalisation.**

* Vous n’avez rien besoin de faire de particulier pour ajouter des audiences au modèle. Pour plus d’informations sur l’utilisation des audiences Experience Cloud avec Target, voir [Audiences Experience Cloud](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

**Les marketeurs peuvent télécharger des données hors ligne, les scores de propension ou d’autres données personnalisées pour créer des modèles de personnalisation.**

* En savoir plus sur le [téléchargement de données pour le ciblage automatique et la personnalisation automatisée](../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

## En quoi le [!UICONTROL ciblage automatique] diffère-t-il de la personnalisation automatisée ?{#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL Le ciblage automatique]nécessite souvent moins de trafic qu’Automated Personalization pour générer un modèle personnalisé.**

Bien que la quantité de trafic *par expérience* requise pour la création des modèles de [!UICONTROL ciblage automatique] ou [!UICONTROL d’Automated Personalization] soit la même, il y a habituellement plus d’expériences dans une activité Automated Personalization que dans une activité de [!UICONTROL ciblage automatique]. Si vous avez, par exemple, une activité [!UICONTROL Personnalisation automatisée] dans laquelle vous avez créé deux offres par lieu et comportant deux lieux, il y a au total quatre (2 = 4) expériences incluses dans l’activité (hors exclusions). En utilisant le [!UICONTROL ciblage automatique], vous pouvez définir l’expérience 1 de manière à inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2, et l’expérience 2 pour inclure l’offre 1 à l’emplacement 1 et l’offre 2 à l’emplacement 2. Étant donné que le [!UICONTROL ciblage automatique] permet de sélectionner plusieurs modifications au sein d’une seule expérience, vous pouvez réduire le nombre total d’expériences dans votre activité.

Pour le [!UICONTROL ciblage automatique], des règles de base simples permettent de comprendre les exigences en termes de trafic :

* **Lorsque la conversion est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour, par expérience, de plus l’activité doit comporter au moins 7 000 visites et 350 conversions.
* **Lorsque le revenu par visite est votre mesure de succès :** 1 000 visites et au moins 50 conversions par jour, par expérience, de plus l’activité doit comporter au moins 1 000 conversions par expérience. Le revenu par visite nécessite généralement plus de données pour élaborer des modèles en raison de la variance de données plus prononcée généralement constatée dans le revenu par visite comparativement au taux de conversion.

**[!UICONTROL Le ciblage automatique]offre des fonctionnalités de configuration complètes.**

* Comme le [!UICONTROL ciblage automatique] est incorporé dans le workflow d’activité A/B, il bénéficie des avantages offerts par le compositeur d’expérience visuelle (VEC), plus mûr et complet. Vous pouvez également utiliser [des liens QA](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) avec le [!UICONTROL ciblage automatique].

**[!UICONTROL Le ciblage automatique]offre un cadre de test en ligne complet.**

* Le bandit à plusieurs bras fait partie d’un cadre de test en ligne plus étendu permettant à nos chercheurs et analystes en données de cerner les avantages de leurs améliorations constantes en conditions réelles.
* À l’avenir, ce banc d’essai nous permettra d’ouvrir notre plateforme d’apprentissage automatique à nos clients disposant d’un savoir-faire en analyse de données afin qu’ils puissent introduire leurs propres modèles et ainsi étoffer la base de modèles de Target.

## Rapports et [!UICONTROL ciblage automatique] {#section_42EE7F5E65E84F89A872FE9921917F76}

Pour plus d’informations, voir [Rapport de synthèse de ciblage automatique](../c-reports/auto-target-summary-report.md#concept_E2171F7B57C1417DAAD7E7909A3FB073) dans la section [Rapports](../c-reports/reports.md#concept_B5077F5503AA4C98901AA99EDCE6CDE6).

## Questions fréquentes sur le ciblage automatique {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consultez les questions fréquentes et les réponses suivantes lorsque vous travaillez avec des activités de Cible  automatique :

### Quelles sont les bonnes pratiques pour configurer une activité de [!UICONTROL ciblage automatique] ?

* Décidez si la valeur commerciale d’une mesure de succès fondée sur le revenu par visite (RPV) bénéficie des exigences de trafic supplémentaires. Le RPV nécessite généralement au moins 1 000 conversions par expérience pour qu’une activité soit plus performante qu’une conversion.
* Décidez l’affectation ente l’expérience de contrôle et l’expérience personnalisée avant de débuter l’activité d’après vos objectifs.
* Déterminez si vous disposez d’un trafic suffisant sur la page où votre activité de [!UICONTROL ciblage automatique] doit être exécutée pour que les modèles de personnalisation soient créés dans un laps de temps raisonnable.
   * Si vous testez l’algorithme de personnalisation, vous ne devriez pas modifier les expériences ni ajouter ou supprimer des attributs de profil alors que l’activité est active.

* Envisagez d’exécuter une activité A/B entre les offres et les lieux que vous prévoyez d’utiliser dans votre activité de [!UICONTROL ciblage automatique], afin d’assurer que les lieu(x) et offres ont une incidence sur l’objectif d’optimisation. Si une activité A/B ne met pas en évidence de différence significative, il est probable que le [!UICONTROL ciblage automatique] ne parviendra pas non plus à générer un effet élévateur.

   * Si un test A/B ne montre aucune différence statistiquement significative entre des expériences, il est probable que les offres considérées ne sont pas suffisamment différentes les unes des autres, que les emplacements sélectionnés n’influencent pas la mesure de succès, ou que l’objectif d’optimisation soit trop distant dans l’entonnoir de conversion pour être affecté par les offres que vous avez choisies.

* Essayez de ne pas modifier sensiblement l’expérience durant le déroulement de l’activité.

### Les coches indiquant qu’un modèle est construit pour cette expérience se mettent-elles à jour en cas de modification de la plage de dates du rapport ?

Non, les coches relatives à la génération des modèles indiquent uniquement les modèles créés jusqu’à ce stade. Il n’y a aucun moyen de revenir en arrière et de voir à quel moment un modèle a été complété.

### Si un visiteur NE voit PAS l’activité de [!UICONTROL ciblage automatique] et effectue une conversion, celle-ci est-elle prise en compte dans mon activité ?

Non, seuls les visiteurs éligibles ayant visualisé l’activité de [!UICONTROL ciblage automatique] sont comptabilisés dans les rapports.

### Mon activité de [!UICONTROL ciblage automatique] ne semble générer aucun effet élévateur. Que se passe-t-il ?

Quatre facteurs sont requis pour qu’une activité de [!UICONTROL ciblage automatique] génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées de manière à créer une différence du point de vue de l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

Le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications.

Si le résultat du test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, les problèmes proviennent de ce que les offres ou les lieux n’ont ne pas un impact suffisant sur l’objectif d’optimisation pour être détectés de façon statistiquement pertinente.

### Quand dois-je arrêter mon activité de [!UICONTROL ciblage automatique] ?

[!UICONTROL Le ciblage automatique] peut être utilisé comme une personnalisation « toujours active » qui s’optimise en permanence. Dans le cas des contenus sans cesse renouvelés, notamment, il n’y a aucune nécessité d’arrêter votre activité de [!UICONTROL ciblage automatique].

Si vous souhaitez apporter des modifications substantielles au contenu de votre activité de [!UICONTROL ciblage automatique], la meilleure pratique consiste à démarrer une nouvelle activité, afin que les autres utilisateurs qui visualisent les rapports n’en confondent pas les résultats, ou ne les relient pas à d’anciens résultats portant sur des contenus différents.

### Combien de temps dois-je attendre la compilation des modèles ? {#how-long}

The length of time it takes for models to build in your [!UICONTROL Auto-Target] activity typically depends on the traffic to your selected activity location(s) and conversion rates associated with you activity success metric.

[!UICONTROL La Cible] automatique ne tente pas de créer un modèle personnalisé pour une expérience donnée tant qu’il n’y a pas moins de 50 conversions pour cette expérience. De plus, si le modèle créé est de qualité insuffisante (comme déterminé par l’évaluation hors ligne sur les données de &quot;test&quot; en attente, à l’aide [d’une mesure appelée AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), le modèle ne sera pas utilisé pour desservir le trafic d’une manière personnalisée.

D&#39;autres points méritent d&#39;être rappelés au sujet de la construction de modèles de Cible automatique :

* Une fois qu’une activité est active, la Cible  automatique prend en compte jusqu’aux 45 derniers jours de données réparties de manière aléatoire lors de la tentative de création de modèles (c.-à-d. contrôle du trafic, plus certaines données fournies de manière aléatoire supplémentaires détenues par notre algorithme).
* Lorsque [!UICONTROL Recettes par visite] est votre mesure de réussite, ces activités ont généralement besoin de davantage de données pour créer des modèles en raison de la variance de données plus élevée qui existe généralement en termes de recettes de visite par rapport au taux de conversion.
* Etant donné que les modèles sont créés sur la base d’une expérience par expérience, le remplacement d’une expérience par une autre signifie qu’un trafic suffisant (c’est-à-dire au moins 50 conversions) doit être collecté pour la nouvelle expérience avant que les modèles personnalisés ne puissent être recréés.

### Un modèle est compilé dans mon activité. Les visites de cette expérience sont-elles personnalisées ?

Non, il doit exister au moins deux modèles construits au sein de votre activité pour que la personnalisation puisse débuter.

### Quand puis-je commencer à consulter les résultats de mon activité de [!UICONTROL ciblage automatique] ?

Vous pouvez commencer à consulter les résultats de votre test de [!UICONTROL ciblage automatique] dès qu’au moins deux expériences ont été compilées à partir des modèles (indiquées par une coche verte) pour l’expérience sur laquelle les modèles sont construits.

### Puis-je spécifier une expérience spécifique à utiliser comme contrôle ?

Vous pouvez sélectionner une expérience à utiliser en tant que contrôle lors de la création d’une [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (Personnalisation automatisée) ou d’une activité de [ciblage automatique](/help/c-activities/auto-target-to-optimize.md).

Cette fonctionnalité vous permet d’acheminer tout le trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/c-activities/t-automated-personalization/experience-as-control.md).

### Puis-je modifier la mesure d’objectif à mi-chemin d’une activité d’Cible automatique ? {#change-metric}

Il est déconseillé de modifier la mesure d’objectif à mi-chemin d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’ [!DNL Target] interface utilisateur, vous devez toujours début une nouvelle activité. Nous ne garantissons pas ce qui se passe si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités d’affectation automatique, de Cible automatique et d’ [!UICONTROL Automated Personalization] qui utilisent soit [!DNL Target] soit  (A4T) comme source de rapports.[!DNL Analytics]

### Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité d’Cible automatique ?

Il n’est pas conseillé d’utiliser l’option [!UICONTROL Réinitialiser les données] du rapport pour les activités de Cible  automatique. Bien qu’elle supprime les données de rapports visibles, cette option ne supprime pas tous les enregistrements d’identification du modèle de Cible  automatique. Au lieu d’utiliser l’option [!UICONTROL Réinitialiser les données] du rapport pour les activités de Cible  automatique, créez une activité et désactivez l’activité d’origine. (Remarque : Cette directive s’applique également aux [!UICONTROL activités d’affectation] automatique et d’ [!UICONTROL Automated Personalization] .)

## Dépannage du [!UICONTROL ciblage automatique] {#section_23995AB813F24525AF294D20A20875C8}

Il arrive parfois que les activités ne se déroulent pas comme prévu. Voici quelques défis potentiels auxquels vous pourriez faire face lorsque vous utilisez le [!UICONTROL ciblage automatique], ainsi que quelques suggestions de solutions.

**Mon activité de[!UICONTROL ciblage automatique]prend trop de temps pour générer des modèles.**

Plusieurs modifications de configuration de l’activité peuvent diminuer le temps escompté pour la création des modèles, dont le nombre d’expériences incluses dans votre activité de [!UICONTROL ciblage automatique], le trafic entrant sur votre site et le critère de mesure de succès sélectionné.

**Solution :** passez en revue la configuration de votre activité et déterminez si des modifications sont souhaitables pour accélérer la compilation des modèles.

* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdrez pas les données d’activité si vous modifiez le critère de mesure de succès en passant du RPV à la conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible est de nature à augmenter les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Y a-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité peut raccourcir le délai nécessaire à la compilation des modèles.
* Existe-t-il une page à trafic élevé sur laquelle cette activité serait plus efficace ? Plus les lieux de votre activité génèrent de trafic et de conversions, plus les modèles se compileront rapidement.

**Mon activité de[!UICONTROL ciblage automatique]ne génère aucun effet élévateur.**

Quatre facteurs sont requis pour qu’une activité AP génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées de manière à créer une différence du point de vue de l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** tout d’abord, assurez-vous que votre activité personnalise le trafic. Si aucun modèle n’est compilé pour l’ensemble des expériences, votre activité de [!UICONTROL ciblage automatique] continue de générer au hasard une portion significative des visites pour tenter de créer tous les modèles aussi rapidement que possible. Si les modèles ne sont pas créés, le [!UICONTROL ciblage automatique] ne personnalise pas le trafic.

Ensuite, assurez-vous que les offres et les lieux de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si le résultat d’un test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, les problèmes proviennent de ce que les offres ou les lieux n’ont ne pas un impact suffisant sur l’objectif d’optimisation pour être détectés de façon statistiquement pertinente.

**Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties.**

Ce comportement est attendu.

Dans une activité de [!UICONTROL ciblage automatique], dès qu’une mesure de conversion (qu’il s’agisse d’un objectif d’optimisation ou d’un objectif postérieur) est convertie, l’utilisateur est libéré de l’expérience et l’activité redémarre.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 est dépendant de C1. Lorsqu’un visiteur entre dans l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas convertis, la mesure A1 n’est pas convertie en raison de la dépendance de la mesure de succès. Si le visiteur convertit C1, puis A1, A1 n’est toujours pas converti car dès que C1 est converti, le visiteur est libéré.

## Vidéo de formation : Présentation des activités de ciblage automatique ![badge Aperçu](/help/assets/overview.png)

Cette vidéo explique comment configurer une activité A/B de [!UICONTROL ciblage automatique].

Après avoir terminé cette formation, vous devez être en mesure de :

* Définir des tests de [!UICONTROL ciblage automatique]
* Comparer le [!UICONTROL ciblage automatique] à la personnalisation automatisée
* Créer des activités de [!UICONTROL ciblage automatique]

>[!VIDEO](https://video.tv.adobe.com/v/18558)