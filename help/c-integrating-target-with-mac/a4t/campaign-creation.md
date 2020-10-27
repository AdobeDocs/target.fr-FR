---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Vous pouvez configurer une activité dans Target Standard/Premium afin d’utiliser Adobe Analytics en tant que source des rapports (A4T).
title: Création d’une activité qui utilise A4T comme source de rapports
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: b6d4cc35e32f118ff46fcd3b235c8b5deae35d05
workflow-type: tm+mt
source-wordcount: '1397'
ht-degree: 20%

---


# Création d’une activité qui utilise Analytics en tant que source du rapports

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. Sélectionnez une mesure de succès finale de l’activité. Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## Créez l’activité

Creating a [!DNL Target] activity that uses [!DNL Analytics] as the reporting source is similar to setting up a regular [!DNL Target] activity, with a few important differences. For example, you cannot select a segment for reporting while creating the activity because all segments available in [!DNL Analytics] can be applied when viewing a report.

1. Cliquez sur **[!UICONTROL Créer l’activité]**.

   >[!NOTE]
   >
   >An activity name cannot include the &quot;%&quot; character if [!DNL Analytics] is used as the reporting source.

1. Sélectionnez le type d’activité et commencez à configurer l’activité.
1. Lorsque vous êtes dans la section **[!UICONTROL Paramètres]** du flux de création de l’activité, choisissez **[!UICONTROL Adobe Analytics]** et entrez le nom de votre entreprise.
1. Sélectionnez une suite de rapports.

   Vous pouvez choisir toute suite de rapports disponible dans [!DNL Analytics]. La suite de rapports définit l’emplacement où les données collectées seront disponibles. Les suites de rapports virtuelles ne sont pas incluses dans la liste des suites de rapports..

   Lors de la sélection de la suite de rapports, vous êtes susceptible de rencontrer deux erreurs possibles :

   * Vous obtenez une erreur indiquant qu’aucune suite de rapports n’est disponible mais que votre compte est correctement configuré.

      You might need to check your [!DNL Analytics] company. If your [!DNL Adobe Experience Cloud] account is tied to more than one [!DNL Analytics] company, log out of [!DNL Target], and log in to [!DNL Analytics] under the right company. Then return to [!DNL Target], and the report suites will load.

   * Vous ne voyez pas les suites de rapports attendues.

      Only report suites that are provisioned to connect to [!DNL Target] will be available for selection. If you don&#39;t see the report suite(s) you expect, first try logging out and logging back in to the [!DNL Adobe Experience Cloud] to try again.
   Si la suite de rapports n’apparaît toujours pas dans la liste, veuillez contacter [l’assistance clientèle](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Spécifiez votre serveur de suivi.

   Consultez [Utilisation d’un serveur de suivi Analytics](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Définissez l’expérience.
1. Indiquez l’objectif de l’activité.

   Vous devez sélectionner une mesure de réussite à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. You can choose any [!DNL Analytics] metric available in the [!DNL Analytics] metric selector.

   >[!NOTE]
   >
   >You can send a custom Target-based metric to [!DNL Analytics] rather than relying only on [!DNL Analytics] data. Par exemple, vous pouvez surveiller les clics sur une page, surveillance qui n’est habituellement pas effectuée par [!DNL Analytics]. This custom metric is sent to [!DNL Analytics] automatically from the [!DNL Target] server, and appears as the &quot;[!DNL Target] Conversion&quot; metric in the metrics selector in [!DNL Analytics]. The [!DNL Target] Conversion metric is empty if you choose to use [!DNL Analytics] metrics.

   La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que l’activité permet d’améliorer.

   Le visiteur reste dans l’activité après avoir atteint l’objectif. Le visiteur continue à voir le contenu de l’activité mais n’est pas comptabilisé comme une nouvelle entrée d’activité.

   >[!NOTE]
   >
   >When setting up an activity after setting up [!DNL Analytics] as your reporting source, there is no option to set up audiences for reporting. [!DNL Analytics] sont disponibles dans le rapport [!DNL Target] Activités.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Prise en charge d’Analytics pour la Cible (A4T) pour les activités d’affectation automatique et de Cible automatique {#a4t-aa}

Nous avons mis à niveau l’intégration Adobe Target-to-Adobe Analytics, connue sous le nom d’ [Analytics pour la Cible](/help/c-integrating-target-with-mac/a4t/a4t.md). Les activités d’affectation automatique et d’Cible automatique prennent désormais en charge Analytics pour la Cible.

Cette intégration vous permet d’effectuer les opérations suivantes :

* Utilisez la fonctionnalité de bandit à plusieurs bras de l’affectation [](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)automatique pour diriger le trafic vers les expériences gagnantes.
* Utilisez l’algorithme d’apprentissage automatique de la Cible [](/help/c-activities/auto-target-to-optimize.md)automatique pour choisir la meilleure expérience pour chaque visiteur en fonction de son profil, de son comportement et de son contexte tout en utilisant une mesure [!DNL Adobe Analytics] d’objectif et les capacités d’rapports et d’analyse riches [!DNL Adobe Analytics]de celui-ci.

Assurez-vous d’avoir [implémenté A4T pour l’utiliser avec les activités](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)Test A/B et Ciblage d’expérience. Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la `sessionId` valeur à [!DNL Analytics]. Pour plus d’informations, voir [Adobe Analytics for Cible (A4T)](https://developers.adobetarget.com/api/delivery-api/#section/Integration-with-Experience-Cloud/Adobe-Analytics-for-Target-(A4T)) dans le Guide de l’API de Diffusion *Adobe Target.*

Pour démarrer :

1. Lors de la création d’une activité de test A/B, sur la page **[!UICONTROL Ciblage]** , sélectionnez l’une des options suivantes comme méthode **[!UICONTROL d’affectation du]** trafic :

   * Affectation automatique à la meilleure expérience
   * Cible automatique pour les expériences personnalisées

1. Sélectionnez **[!UICONTROL Adobe Analytics]** pour votre source **[!UICONTROL de]** Rapports sur la page **[!UICONTROL Objectifs et paramètres]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

1. Choisissez une mesure Objectif Principal.

   * Choisissez **[!UICONTROL Conversion]** à utiliser [!DNL Adobe Target] pour spécifier l’objectif d’optimisation.
   * Choisissez **[!UICONTROL Utiliser une mesure]** Analytics, puis sélectionnez une mesure [!DNL Analytics] à utiliser comme objectif d’optimisation. Vous pouvez utiliser une mesure de [!DNL Analytics] conversion prête à l’emploi ou un événement [!DNL Analytics] personnalisé.

1. Enregistrez et activez votre activité.

   [!UICONTROL L’affectation] automatique utilise la mesure sélectionnée pour optimiser l’activité, ce qui conduit les visiteurs à l’expérience qui optimise la mesure d’objectif.

   OU

   [!UICONTROL La Cible] automatique utilise la mesure sélectionnée pour optimiser l’activité, ce qui permet aux visiteurs de bénéficier d’une meilleure expérience personnalisée.

1. Utilisez l&#39;onglet **[!UICONTROL Rapports]** pour vue le rapports de votre activité en fonction de votre choix de [!DNL Adobe Analytics] mesures. Cliquez sur **[!UICONTROL Vue dans Analytics]** pour approfondir et segmenter davantage vos données de rapports.

### Mesures d’objectif prises en charge

[!UICONTROL A4T] pour l’affectation  automatique et la Cible  automatique vous permettent de choisir l’un des types de mesure suivants comme mesure d’objectif Principal pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] événements personnalisés

[!UICONTROL A4T] pour l’affectation  automatique et la Cible  automatique nécessitent que vous choisissiez une mesure basée sur un événement binomial, c’est-à-dire un événement qui se produit ou non, par exemple un clic, une conversion, une commande, etc. (Ces types de événements sont aussi parfois appelés événements Bernoulli, binaires ou discrets.)

[!UICONTROL A4T] pour l’affectation  automatique et la Cible  automatique ne prend pas en charge l’optimisation des mesures continues telles que les recettes, le nombre de produits commandés, la durée de la session, le nombre de vues de page dans la session, etc. (Ces types de mesures non pris en charge sont également parfois appelés mesures non binomiales ou non Bernoulli.)

Les types de mesures suivants ne sont pas pris en charge en tant que mesures d’objectif Principal :

* [!DNL Adobe Target] mesures d’engagement et de recettes
* [!DNL Adobe Analytics] mesures d’engagement et de recettes

   Il peut être possible de sélectionner une mesure d’engagement ou de recettes comme mesure d’objectif Principal car [!DNL Analytics] il est impossible d’identifier et d’exclure toutes les mesures d’engagement et de recettes de [!DNL Target] [!DNL Analytics]cette mesure. Soyez prudent lorsque vous sélectionnez uniquement des mesures de conversion binomales ou des événements personnalisés à partir de [!DNL Analytics].

* [!DNL Adobe Analytics] mesures calculées

### Limites et notes

Certaines limitations et remarques s’appliquent à la fois à l’affectation automatique et à la Cible automatique. D&#39;autres limitations et notes s&#39;appliquent à un type d&#39;activité ou à l&#39;autre.

#### Affectation automatique et Cible automatique

* Une fois une activité activée, la source du rapports ne peut pas être modifiée [!DNL Analytics] sur [!DNL Target] ou inversement.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat escompté en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure telle que &quot;remplissage de formulaires par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaires&quot; comme mesure d’objectif Principal. [!DNL Target] normalise automatiquement les mesures de conversion par visite pour tenir compte de la répartition inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.
* [!DNL Target] utilise le modèle d’attribution &quot;Même touche&quot; dans l’implémentation d’affectation  automatique d’A4T.

#### Affectation automatique

* [!UICONTROL Les modèles d’affectation] automatique continuent de s’entraîner toutes les deux heures, comme d’habitude.

#### Ciblage automatique

* [!UICONTROL Les modèles de Cible] automatique continuent à s&#39;entraîner toutes les 24 heures, comme d&#39;habitude. Toutefois, les données de événement de conversion provenant de [!DNL Analytics] sont retardées de six à 24 heures supplémentaires. Ce délai signifie que la distribution du trafic par [!DNL Target] va suivre les derniers événements enregistrés dans [!DNL Analytics]. Cela aura le plus grand effet au cours des 48 premières heures après la première activation d&#39;une activité ; les performances de l’activité refléteront plus étroitement le comportement de [!DNL Analytics] conversion après cinq jours d’expiration. Vous devriez envisager d’utiliser l’affectation  automatique plutôt que la Cible  automatique pour les activités de courte durée où la plupart du trafic survient au cours des cinq premiers jours de la vie de l’activité.
* Lors de [!DNL Analytics] l’utilisation en tant que source de données pour une Cible  automatique, les sessions sont considérées comme terminées après six heures. Les conversions survenant après six heures ne seront pas comptabilisées.

Pour plus d’informations, voir Modèles [d’attribution et fenêtres](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/models.html) de recherche en amont dans le Guide *des outils* Analytics.
