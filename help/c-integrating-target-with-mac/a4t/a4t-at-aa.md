---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Découvrez comment créer des activités d’affectation automatique et de ciblage automatique dans Adobe [!DNL Target] qui utilisent Analytics comme source des rapports (A4T).
title: A4T prend-il en charge les activités d’affectation automatique et de ciblage automatique ?
feature: 'Analytics for Target (A4T) '
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 103ee22a4bf37569f8a02a91af194ebcdc79f3b4
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 3%

---

# Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique

L’intégration [!DNL Adobe Target]-to-[!DNL Adobe Analytics], connue sous le nom de [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) prend en charge [!UICONTROL l’affectation automatique] et les activités de [!UICONTROL ciblage automatique].

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisez la fonction de bandit à plusieurs bras de [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour diriger le trafic vers des expériences gagnantes.
* Utilisez l’algorithme d’apprentissage automatique d’ensemble de [ciblage automatique ](/help/c-activities/auto-target/auto-target-to-optimize.md) pour choisir la meilleure expérience pour chaque visiteur. Le ciblage automatique sélectionne la meilleure expérience en fonction des profils, des comportements et du contexte des utilisateurs tout en utilisant une [!DNL Adobe Analytics] mesure d’objectif et des [!DNL Adobe Analytics] fonctions riches de création de rapports et d’analyse.

Vérifiez que [A4T a été implémenté pour une utilisation avec les activités de test A/B et de ciblage d’expérience](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la valeur `sessionId` à [!DNL Analytics]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) dans le guide *SDK Adobe Target*.

Pour démarrer :

1. Lors de la création d’une activité de test A/B, sur la page **[!UICONTROL Ciblage]** , sélectionnez l’une des options suivantes comme **[!UICONTROL Méthode d’affectation du trafic]** :

   * [!UICONTROL Affectation automatique à la meilleure expérience]
   * [!UICONTROL Ciblage automatique pour les expériences personnalisées]

   ![Options Méthodes d’affectation du trafic : Affectation automatique, manuelle et ciblage automatique](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Pour plus d’informations et des instructions détaillées, voir [Création d’une activité d’affectation automatique](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et [Création d’une activité de ciblage automatique](/help/c-activities/auto-target/create-auto-target.md).

1. Sélectionnez **[!UICONTROL Adobe Analytics]** pour votre **[!UICONTROL source de création de rapports]** sur la page **[!UICONTROL Objectifs et paramètres]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

   ![Section Source de création de rapports sur la page Objectifs et paramètres](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Sélectionnez une mesure d’objectif Principal.

   * Pour utiliser [!DNL Adobe Target] afin de spécifier l’objectif d’optimisation, sélectionnez **[!UICONTROL Conversion]** .
   * Sélectionnez **[!UICONTROL Utiliser une mesure Analytics]** , puis une mesure de [!DNL Analytics] à utiliser comme objectif d’optimisation. Vous pouvez utiliser une mesure de conversion [!DNL Analytics] prête à l’emploi ou un événement personnalisé [!DNL Analytics].

   Pour plus d’informations, voir [Mesures d’objectif prises en charge](#supported) ci-dessous.

1. Enregistrez et activez votre activité.

   [!UICONTROL L’] affectation automatique utilise la mesure sélectionnée pour optimiser l’activité, ce qui dirige les visiteurs vers l’expérience qui optimise la mesure de votre objectif.

   Ou

   [!UICONTROL Le ] ciblage automatique utilise la mesure sélectionnée pour optimiser l’activité, redirigeant les visiteurs vers une meilleure expérience personnalisée.

1. Utilisez l’onglet **[!UICONTROL Rapports]** pour afficher les rapports de votre activité selon le choix de mesures [!DNL Adobe Analytics]. Cliquez sur **[!UICONTROL Afficher dans Analytics]** pour approfondir et segmenter davantage vos données de rapport.

## Mesures d’objectif prises en charge {#supported}

[!UICONTROL A4] pour l’ [!UICONTROL affectation ] automatique et le  [!UICONTROL ciblage ] automatique, vous pouvez choisir l’un des types de mesures suivants comme mesure d’objectif Principal pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] événements personnalisés

[!UICONTROL A4] Pour le  [!UICONTROL ciblage ] automatique et le  [!UICONTROL ciblage ] automatique, vous devez choisir une mesure basée sur un événement binaire. Un événement binaire se produit ou ne se produit pas. Les événements binaires incluent un clic, une conversion, une commande, etc. On parle aussi parfois de Bernoulli, de binaire ou d’événement discret.

[!UICONTROL A4] Pour le  [!UICONTROL ciblage ] automatique et le  [!UICONTROL ciblage ] automatique ne prennent pas en charge l’optimisation pour les mesures continues. Les mesures continues comprennent les recettes, le nombre de produits commandés, la durée de session, le nombre de pages vues dans la session, etc. Ces types de mesures non pris en charge sont également parfois appelés mesures non binaires ou non Bernoulli.

Les types de mesures suivants ne sont pas pris en charge en tant que mesures d’objectif Principal :

* [!DNL Adobe Target] mesures d’engagement et de recettes
* [!DNL Adobe Analytics] mesures d’engagement et de recettes

   Il est possible de sélectionner une mesure d’engagement ou de recettes [!DNL Analytics] comme mesure d’objectif Principale, car [!DNL Target] ne peut pas identifier et exclure toutes les mesures d’engagement et de recettes de [!DNL Analytics]. Sélectionnez uniquement des mesures de conversion binaires ou des événements personnalisés à partir de [!DNL Analytics].

* [!DNL Adobe Analytics] mesures calculées

## Limites et notes

Certaines limites et notes s’appliquent aux activités [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]. D’autres limitations et notes s’appliquent à un type d’activité ou à un autre.

### Affectation automatique et ciblage automatique

* Lorsque vous utilisez [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique], vous devez toujours afficher les rapports dans [!DNL Analytics].
* La source des rapports ne peut pas être changée de [!DNL Analytics] en [!DNL Target] ou inversement après l’activation d’une activité.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat prévu en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure comme &quot;remplissage de formulaire par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaire&quot; comme mesure d’objectif Principale. [!DNL Target] normalise automatiquement les mesures de conversion par visite pour tenir compte de la répartition inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.
* [!DNL Target] utilise le modèle d’attribution &quot;Même touche&quot; dans la fonction d’  affectation automatique : Analytics pour Target (A4T).

### Affectation automatique

* [!UICONTROL Les ] modèles d’affectation automatique continuent à s’entraîner toutes les deux heures, comme d’habitude.

### Ciblage automatique

* [!UICONTROL Les modèles de ] ciblage automatique continuent à s’entraîner toutes les 24 heures, comme d’habitude. Toutefois, les données d’événement de conversion provenant de [!DNL Analytics] sont retardées de six à 24 heures supplémentaires. Ce délai signifie que la distribution du trafic par [!DNL Target] effectue le suivi des derniers événements enregistrés dans [!DNL Analytics]. Ce délai a le plus d’effet dans les 48 premières heures suivant l’activation initiale d’une activité. Les performances de l’activité reflèteront plus étroitement le comportement de conversion [!DNL Analytics] après cinq jours. Pensez à utiliser [!UICONTROL Affectation automatique] au lieu de [!UICONTROL Ciblage automatique] pour les activités de courte durée dans lesquelles la plupart du trafic se produit au cours des cinq premiers jours de la vie de l’activité.
* Lors de l’utilisation de [!DNL Analytics] comme source de données pour une activité de [!UICONTROL ciblage automatique], les sessions se terminent après six heures. Les conversions survenant après six heures ne sont pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et intervalles de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) dans le *Guide des outils Analytics*.

## Tutoriel : Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique {#tutorial}

Bien que de riches fonctionnalités d’analyse soient disponibles dans [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], quelques modifications du panneau par défaut [!UICONTROL Analytics for Target] sont nécessaires pour interpréter correctement les activités de ciblage automatique. Ces modifications sont requises en raison des différences entre les activités d’expérimentation (A/B manuel et [!UICONTROL Affectation automatique]) et les activités de personnalisation ([!UICONTROL Ciblage automatique]).

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse des activités de [!UICONTROL ciblage automatique] dans [!UICONTROL Workspace].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) dans *Tutorials Adobe Target*.
