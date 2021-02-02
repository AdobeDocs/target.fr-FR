---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Puis-je utiliser A4T avec des activités de Cible automatique et d’affectation automatique ?
title: Prise en charge d’A4T pour les activités d’affectation automatique et de Cible automatique
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 8be597121eb30b56d3b106352678246fc71d667b
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 2%

---


# Prise en charge d’A4T pour les activités d’affectation automatique et de Cible automatique

L’intégration [!DNL Adobe Target]-à-[!DNL Adobe Analytics], connue sous le nom [Analytics pour la Cible](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), prend en charge les activités [!UICONTROL Affectation automatique] et [!UICONTROL Cible automatique].

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisez la fonctionnalité de bandit à plusieurs bras de [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour diriger le trafic vers les expériences gagnantes.
* Utilisez l’algorithme d’apprentissage automatique [de la Cible automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) pour choisir la meilleure expérience pour chaque visiteur en fonction de son profil, de son comportement et de son contexte tout en utilisant une mesure d’objectif [!DNL Adobe Analytics] et les capacités d’analyse et de rapports [!DNL Adobe Analytics] riches.

Vérifiez que [A4T a été implémenté pour être utilisé avec les activités de test A/B et de ciblage d’expérience](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la valeur `sessionId` à [!DNL Analytics]. Pour plus d’informations, voir le [rapports Analytics for Cible (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) dans le guide *Adobe Target SDKs*.

Pour démarrer :

1. Lors de la création d’une activité de test A/B, sur la page **[!UICONTROL Ciblage]**, sélectionnez l’une des options suivantes comme **[!UICONTROL Méthode d’affectation du trafic]** :

   * [!UICONTROL Affectation automatique à la meilleure expérience]
   * [!UICONTROL Cible automatique pour les expériences personnalisées]

   ![Options Méthodes d’affectation du trafic : Affectation manuelle, automatique et Cible automatique](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Pour plus d’informations et des instructions détaillées, voir [Création d’une activité d’affectation automatique](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et [Création d’une activité d’Cible automatique](/help/c-activities/auto-target/create-auto-target.md).

1. Sélectionnez **[!UICONTROL Adobe Analytics]** pour votre **[!UICONTROL source de Rapports]** sur la page **[!UICONTROL Objectifs et paramètres]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

   ![Section Source du rapports sur la page Objectifs et paramètres](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Choisissez une mesure Objectif Principal.

   * Sélectionnez **[!UICONTROL Conversion]** pour utiliser [!DNL Adobe Target] pour spécifier l&#39;objectif d&#39;optimisation.
   * Sélectionnez **[!UICONTROL Utiliser une mesure Analytics]**, puis sélectionnez une mesure dans [!DNL Analytics] pour l’utiliser comme objectif d’optimisation. Vous pouvez utiliser une mesure de conversion prête à l’emploi [!DNL Analytics] ou un événement personnalisé [!DNL Analytics].

   Voir [Mesures d’objectif prises en charge](#supported) ci-dessous pour plus d’informations.

1. Enregistrez et activez votre activité.

   [!UICONTROL L’] affectation automatique utilise la mesure sélectionnée pour optimiser l’activité, ce qui conduit les visiteurs à l’expérience qui optimise la mesure d’objectif.

   OU

   [!UICONTROL Le ] ciblage automatique utilise la mesure sélectionnée pour optimiser l’activité, ce qui permet aux visiteurs de bénéficier d’une meilleure expérience personnalisée.

1. Utilisez l&#39;onglet **[!UICONTROL Rapports]** pour vue le rapports de votre activité en fonction de votre choix de mesures [!DNL Adobe Analytics]. Cliquez sur **[!UICONTROL Vue dans Analytics]** pour approfondir et segmenter davantage vos données de rapports.

## Mesures d’objectif prises en charge {#supported}

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocateet  [!UICONTROL Auto-] Targetlet vous permettent de choisir l’un des types de mesure suivants comme mesure d’objectif Principal pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] événements personnalisés

[!UICONTROL A4] Tpour l’affectation  [!UICONTROL automatique ] et le  [!UICONTROL ciblage ] automatique vous oblige à choisir une mesure basée sur un événement binomial, c’est-à-dire un événement qui se produit ou non, par exemple un clic, une conversion, une commande, etc. Ces types de événements sont parfois appelés Bernoulli, binaires ou événements discrets.

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocateet  [!UICONTROL Auto-] Targetne prend pas en charge l&#39;optimisation pour les mesures continues telles que les recettes, le nombre de produits commandés, la durée de la session, le nombre de vues de page dans la session, etc. Ces types de mesures non pris en charge sont également parfois appelés mesures non binomiales ou non Bernoulli.

Les types de mesures suivants ne sont pas pris en charge en tant que mesures d’objectif Principal :

* [!DNL Adobe Target] mesures d’engagement et de recettes
* [!DNL Adobe Analytics] mesures d’engagement et de recettes

   Il peut être possible de sélectionner une mesure d&#39;engagement ou de recettes [!DNL Analytics] comme mesure d&#39;objectif Principal, car [!DNL Target] ne peut pas identifier et exclure toutes les mesures d&#39;engagement et de recettes de [!DNL Analytics]. Soyez prudent lorsque vous sélectionnez uniquement des mesures de conversion binomales ou des événements personnalisés dans [!DNL Analytics].

* [!DNL Adobe Analytics] mesures calculées

## Limites et notes

Certaines limitations et notes s’appliquent aux activités [!UICONTROL Affectation automatique] et [!UICONTROL Cible automatique]. D&#39;autres limitations et notes s&#39;appliquent à un type d&#39;activité ou à l&#39;autre.

### Affectation automatique et Cible automatique

* La source du rapports ne peut pas être changée de [!DNL Analytics] en [!DNL Target] ou inversement après l&#39;activation d&#39;une activité.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat escompté en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure telle que &quot;remplissage de formulaires par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaires&quot; comme mesure d’objectif Principal. [!DNL Target] normalise automatiquement les mesures de conversion par visite pour tenir compte de la répartition inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.
* [!DNL Target] utilise le modèle d’attribution &quot;Même touche&quot; dans la fonction d’  affectation automatique : Analyses pour la Cible (A4T).

### Affectation automatique

* [!UICONTROL Les modèles d&#39;] affectation automatique continuent de s&#39;entraîner toutes les deux heures, comme d&#39;habitude.

### Ciblage automatique

* [!UICONTROL Les modèles de ] ciblage automatique continuent de s’entraîner toutes les 24 heures, comme d’habitude. Toutefois, les données de événement de conversion provenant de [!DNL Analytics] sont retardées de six à 24 heures supplémentaires. Ce délai signifie que la distribution du trafic par [!DNL Target] suit les derniers événements enregistrés dans [!DNL Analytics]. Ce résultat est le plus important dans les 48 premières heures qui suivent l’activation initiale d’une activité. Les performances de l’activité refléteront plus étroitement le comportement de conversion [!DNL Analytics] après cinq jours. Vous devez utiliser [!UICONTROL Affectation automatique] au lieu de [!UICONTROL Cible automatique] pour les activités de courte durée dans lesquelles la plupart du trafic survient au cours des cinq premiers jours de la vie de l’activité.
* Lorsque vous utilisez [!DNL Analytics] comme source de données pour une activité [!UICONTROL Cible automatique], les sessions sont considérées comme terminées après six heures. Les conversions survenant après six heures ne seront pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et fenêtres de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) dans le *Guide des outils Analytics*.
