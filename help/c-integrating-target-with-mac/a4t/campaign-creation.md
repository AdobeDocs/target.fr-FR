---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Vous pouvez configurer une activité dans Target Standard/Premium afin d’utiliser Adobe Analytics en tant que source des rapports (A4T).
title: Création d’une activité qui utilise A4T comme source de rapports
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '1394'
ht-degree: 20%

---


# Création d’une activité qui utilise Analytics en tant que source du rapports

Vous pouvez configurer une activité dans [!DNL Target] pour utiliser [!DNL Adobe Analytics] comme source de rapports (A4T).

Avant de configurer une activité qui utilise [!DNL Analytics] comme source de rapports, définissez l’objectif de l’activité, par exemple améliorer les recettes par visiteur (RPV) ou augmenter les clics sur votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner d&#39;autres mesures à tout moment dans [!DNL Analytics], vous devez tout de même spécifier une mesure particulière que vous prévoyez que ce test affectera.

## Créez l’activité

La création d&#39;une activité [!DNL Target] qui utilise [!DNL Analytics] comme source de rapports est similaire à la configuration d&#39;une activité [!DNL Target] régulière, avec quelques différences importantes. Par exemple, vous ne pouvez pas sélectionner un segment pour le rapports lors de la création de l&#39;activité, car tous les segments disponibles dans [!DNL Analytics] peuvent être appliqués lors de l&#39;affichage d&#39;un rapport.

1. Cliquez sur **[!UICONTROL Créer l’activité]**.

   >[!NOTE]
   >
   >Un nom d&#39;activité ne peut pas inclure le caractère &quot;%&quot; si [!DNL Analytics] est utilisé comme source de rapports.

1. Sélectionnez le type d’activité et commencez à configurer l’activité.
1. Lorsque vous êtes dans la section **[!UICONTROL Paramètres]** du flux de création de l’activité, choisissez **[!UICONTROL Adobe Analytics]** et entrez le nom de votre entreprise.
1. Sélectionnez une suite de rapports.

   Vous pouvez choisir toute suite de rapports disponible dans [!DNL Analytics]. La suite de rapports définit l’emplacement où les données collectées seront disponibles. Les suites de rapports virtuelles ne sont pas incluses dans la liste des suites de rapports..

   Lors de la sélection de la suite de rapports, vous êtes susceptible de rencontrer deux erreurs possibles :

   * Vous obtenez une erreur indiquant qu’aucune suite de rapports n’est disponible mais que votre compte est correctement configuré.

      Vous devrez peut-être vérifier votre société [!DNL Analytics]. Si votre compte [!DNL Adobe Experience Cloud] est lié à plusieurs sociétés [!DNL Analytics], déconnectez-vous de [!DNL Target] et connectez-vous à [!DNL Analytics] sous la société appropriée. Revenez ensuite à [!DNL Target] et les suites de rapports se chargeront.

   * Vous ne voyez pas les suites de rapports attendues.

      Seules les suites de rapports configurées pour se connecter à [!DNL Target] pourront être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d&#39;abord de vous déconnecter et de vous reconnecter à [!DNL Adobe Experience Cloud] pour réessayer.
   Si la suite de rapports n’apparaît toujours pas dans la liste, veuillez contacter [l’assistance clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Spécifiez votre serveur de suivi.

   Consultez [Utilisation d’un serveur de suivi Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Définissez l’expérience.
1. Indiquez l’objectif de l’activité.

   Vous devez sélectionner une mesure de réussite à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez choisir n’importe quelle mesure [!DNL Analytics] disponible dans le sélecteur de mesures [!DNL Analytics].

   >[!NOTE]
   >
   >Vous pouvez envoyer une mesure personnalisée basée sur une Cible à [!DNL Analytics] au lieu de vous reposer uniquement sur les données [!DNL Analytics]. Par exemple, vous pouvez surveiller les clics sur une page, surveillance qui n’est habituellement pas effectuée par [!DNL Analytics]. Cette mesure personnalisée est envoyée automatiquement à [!DNL Analytics] à partir du serveur [!DNL Target] et s’affiche sous la forme de la mesure &quot;[!DNL Target] Conversion&quot; dans le sélecteur de mesures de [!DNL Analytics]. La mesure de conversion [!DNL Target] est vide si vous choisissez d’utiliser des mesures [!DNL Analytics].

   La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que l’activité permet d’améliorer.

   Le visiteur reste dans l’activité après avoir atteint l’objectif. Le visiteur continue à voir le contenu de l’activité mais n’est pas comptabilisé comme une nouvelle entrée d’activité.

   >[!NOTE]
   >
   >Lors de la configuration d&#39;une activité après avoir configuré [!DNL Analytics] comme source de rapports, il n&#39;existe aucune option pour configurer des audiences pour le rapports. [!DNL Analytics] sont disponibles dans le rapport  [!DNL Target] Activités.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Prise en charge d’Analytics pour la Cible (A4T) pour les activités d’affectation automatique et de Cible automatique {#a4t-aa}

Nous avons mis à niveau l’intégration Adobe Target-to-Adobe Analytics, appelée [Analyses pour la Cible](/help/c-integrating-target-with-mac/a4t/a4t.md). Les activités d’affectation automatique et d’Cible automatique prennent désormais en charge Analytics pour la Cible.

Cette intégration vous permet d’effectuer les opérations suivantes :

* Utilisez la fonctionnalité de bandit à plusieurs bras de [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour diriger le trafic vers les expériences gagnantes.
* Utilisez l’algorithme d’apprentissage automatique [de la Cible automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) pour choisir la meilleure expérience pour chaque visiteur en fonction de son profil, de son comportement et de son contexte tout en utilisant une mesure d’objectif [!DNL Adobe Analytics] et les capacités d’analyse et de rapports [!DNL Adobe Analytics] riches.

Vérifiez que [A4T a été implémenté pour être utilisé avec les activités de test A/B et de ciblage d’expérience](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la valeur `sessionId` à [!DNL Analytics]. Pour plus d’informations, voir le [rapports Analytics for Cible (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) dans le guide *Adobe Target SDKs*.

Pour démarrer :

1. Lors de la création d’une activité de test A/B, sur la page **[!UICONTROL Ciblage]**, sélectionnez l’une des options suivantes comme **[!UICONTROL Méthode d’affectation du trafic]** :

   * Affectation automatique à la meilleure expérience
   * Cible automatique pour les expériences personnalisées

1. Sélectionnez **[!UICONTROL Adobe Analytics]** pour votre **[!UICONTROL source de Rapports]** sur la page **[!UICONTROL Objectifs et paramètres]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

1. Choisissez une mesure Objectif Principal.

   * Sélectionnez **[!UICONTROL Conversion]** pour utiliser [!DNL Adobe Target] pour spécifier l&#39;objectif d&#39;optimisation.
   * Sélectionnez **[!UICONTROL Utiliser une mesure Analytics]**, puis sélectionnez une mesure dans [!DNL Analytics] pour l’utiliser comme objectif d’optimisation. Vous pouvez utiliser une mesure de conversion prête à l’emploi [!DNL Analytics] ou un événement personnalisé [!DNL Analytics].

1. Enregistrez et activez votre activité.

   [!UICONTROL L’] affectation automatique utilise la mesure sélectionnée pour optimiser l’activité, ce qui conduit les visiteurs à l’expérience qui optimise la mesure d’objectif.

   OU

   [!UICONTROL Le ] ciblage automatique utilise la mesure sélectionnée pour optimiser l’activité, ce qui permet aux visiteurs de bénéficier d’une meilleure expérience personnalisée.

1. Utilisez l&#39;onglet **[!UICONTROL Rapports]** pour vue le rapports de votre activité en fonction de votre choix de mesures [!DNL Adobe Analytics]. Cliquez sur **[!UICONTROL Vue dans Analytics]** pour approfondir et segmenter davantage vos données de rapports.

### Mesures d’objectif prises en charge

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocateet  [!UICONTROL Auto-] Targetpermet de choisir l’un des types de mesure suivants comme mesure d’objectif Principal pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] événements personnalisés

[!UICONTROL A4] Tpour l’affectation  [!UICONTROL automatique ] et le  [!UICONTROL ciblage ] automatique vous oblige à choisir une mesure basée sur un événement binomial, c’est-à-dire un événement qui se produit ou non, par exemple un clic, une conversion, une commande, etc. (Ces types de événements sont aussi parfois appelés événements Bernoulli, binaires ou discrets.)

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocateet  [!UICONTROL Auto-] Targetne prend pas en charge l&#39;optimisation pour les mesures continues telles que les recettes, le nombre de produits commandés, la durée de la session, le nombre de vues de page dans la session, etc. (Ces types de mesures non pris en charge sont également parfois appelés mesures non binomiales ou non Bernoulli.)

Les types de mesures suivants ne sont pas pris en charge en tant que mesures d’objectif Principal :

* [!DNL Adobe Target] mesures d’engagement et de recettes
* [!DNL Adobe Analytics] mesures d’engagement et de recettes

   Il peut être possible de sélectionner une mesure d&#39;engagement ou de recettes [!DNL Analytics] comme mesure d&#39;objectif Principal, car [!DNL Target] ne peut pas identifier et exclure toutes les mesures d&#39;engagement et de recettes de [!DNL Analytics]. Soyez prudent lorsque vous sélectionnez uniquement des mesures de conversion binomales ou des événements personnalisés dans [!DNL Analytics].

* [!DNL Adobe Analytics] mesures calculées

### Limites et notes

Certaines limitations et remarques s’appliquent à la fois à l’affectation automatique et à la Cible automatique. D&#39;autres limitations et notes s&#39;appliquent à un type d&#39;activité ou à l&#39;autre.

#### Affectation automatique et Cible automatique

* La source du rapports ne peut pas être changée de [!DNL Analytics] en [!DNL Target] ou inversement après l&#39;activation d&#39;une activité.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat escompté en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure telle que &quot;remplissage de formulaires par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaires&quot; comme mesure d’objectif Principal. [!DNL Target] normalise automatiquement les mesures de conversion par visite pour tenir compte de la répartition inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.
* [!DNL Target] utilise le modèle d’attribution &quot;Même touche&quot; dans la fonction d’  affectation automatique : Analyses pour la Cible (A4T).

#### Affectation automatique

* [!UICONTROL Les modèles d&#39;] affectation automatique continuent de s&#39;entraîner toutes les deux heures, comme d&#39;habitude.

#### Ciblage automatique

* [!UICONTROL Les modèles de ] ciblage automatique continuent de s’entraîner toutes les 24 heures, comme d’habitude. Toutefois, les données de événement de conversion provenant de [!DNL Analytics] sont retardées de six à 24 heures supplémentaires. Ce délai signifie que la distribution du trafic par [!DNL Target] suit les derniers événements enregistrés dans [!DNL Analytics]. Cela aura le plus grand effet au cours des 48 premières heures après la première activation d&#39;une activité ; les performances de l’activité refléteront plus étroitement le comportement de conversion [!DNL Analytics] après cinq jours. Vous devez utiliser [!UICONTROL Affectation automatique] au lieu de [!UICONTROL Cible automatique] pour les activités de courte durée où la plupart du trafic survient au cours des cinq premiers jours de la vie de l’activité.
* Lorsque vous utilisez [!DNL Analytics] comme source de données pour une activité [!UICONTROL Cible automatique], les sessions sont considérées comme terminées après six heures. Les conversions survenant après six heures ne seront pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et fenêtres de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) dans le *Guide des outils Analytics*.
