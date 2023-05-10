---
keywords: a4t;A4T;Analytics comme source des rapports pour Target;analytics pour target
description: Découvrez comment créer [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités dans [!DNL Target] qui utilisent [!DNL Analytics] comme source des rapports (A4T).
title: Prise en charge d’A4T [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] Activités ?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 99bd509988a7d1545a6a1fe59aa59f35ef0a7d11
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 7%

---

# Prise en charge d’A4T pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique]

Le [!DNL Adobe Target]-to-[!DNL Adobe Analytics] intégration, connue sous le nom de [Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), prend en charge [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités.

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisez la variable [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) bandit à plusieurs bras pour diriger le trafic vers des expériences gagnantes.
* Utilisez la variable [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) algorithme d’apprentissage automatique d’ensemble pour choisir la meilleure expérience pour chaque visiteur. [!UICONTROL Ciblage automatique] sélectionne la meilleure expérience en fonction du profil, du comportement et du contexte de chaque utilisateur, tout en utilisant une [!DNL Adobe Analytics] la mesure des objectifs et les riches fonctionnalités de création de rapports et d’analyse de [!DNL Adobe Analytics].

Assurez-vous que vous avez [Mise en oeuvre d’A4T pour une utilisation avec les activités de test A/B et de ciblage d’expérience](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la variable `sessionId` valeur à [!DNL Analytics]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} dans le *Guide du développeur d’Adobe Target*.

Pour démarrer :

1. while [création d’un [!UICONTROL Test A/B] activité](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), sur le **[!UICONTROL Ciblage]** , sélectionnez l’une des options suivantes comme **[!UICONTROL Méthode d’affectation du trafic]**:

   * [!UICONTROL Affectation automatique à la meilleure expérience]
   * [!UICONTROL Ciblage automatique pour les expériences personnalisées]

   ![Options Méthodes d’affectation du trafic : Affectation automatique, manuelle et ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Pour plus d’informations et des instructions détaillées, voir [Création d’une activité d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et [Création d’une activité de ciblage automatique](/help/main/c-activities/auto-target/create-auto-target.md).

1. Sélectionner **[!UICONTROL Adobe Analytics]** pour votre **[!UICONTROL Source de création de rapports]** sur le **[!UICONTROL Objectifs et paramètres]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

   ![Section Source de création de rapports sur la page Objectifs et paramètres](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Choisissez une [!UICONTROL Principal objectif] mesure.

   * Pour utiliser [!DNL Adobe Target] pour spécifier l’objectif d’optimisation, choisissez **[!UICONTROL Conversion]** .
   * Choisir **[!UICONTROL Utilisation d’une mesure Analytics]** puis sélectionnez une mesure dans [!DNL Analytics] à utiliser comme objectif d’optimisation. Vous pouvez utiliser une [!DNL Analytics] mesure de conversion ou [!DNL Analytics] événement personnalisé.

   Voir [Mesures d’objectif prises en charge](#supported) ci-dessous pour plus d’informations.

1. Enregistrez et activez votre activité.

   [!UICONTROL Affectation automatique] utilise la mesure que vous avez sélectionnée pour optimiser l’activité, en orientant les visiteurs vers l’expérience qui optimise la mesure de votre objectif.

   Ou

   [!UICONTROL Ciblage automatique] utilise la mesure que vous avez sélectionnée pour optimiser l’activité, ce qui redirige les visiteurs vers une meilleure expérience personnalisée.

1. Utilisez la variable **[!UICONTROL Rapports]** pour afficher les rapports de votre activité selon votre choix : [!DNL Adobe Analytics] mesures. Cliquez sur **[!UICONTROL Afficher dans Analytics]** pour approfondir et segmenter davantage vos données de rapport.

## Mesures d’objectif prises en charge {#supported}

[!UICONTROL A4T] pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] vous permet de choisir l’un des types de mesures suivants comme mesure d’objectif Principal pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] événements personnalisés

[!DNL Target] vous permet de choisir des mesures en fonction d’événements binomiaux ou d’événements continus lors de l’utilisation de [!UICONTROL A4T] pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique].

* **Mesures basées sur des événements binaires**: Un événement binaire se produit ou ne se produit pas. Les événements binaires incluent un clic, une conversion, une commande, etc. On parle aussi parfois de Bernoulli, de binaire ou d’événement discret.

* **Mesures basées sur des événements continus**. Les mesures continues comprennent les recettes, le nombre de produits commandés, la durée de session, le nombre de pages vues dans la session, etc. Ces types d’événements sont également parfois appelés mesures non binaires ou non Bernoulli.

>[!IMPORTANT]
>
>À partir du [!DNL Adobe Target Standard/Premium] version 22.15.1 (8 et 9 mars 2023), [!DNL Target] continue à prendre en charge les activités existantes avec les mesures qui ne sont désormais plus prises en charge (répertoriées dans les tableaux suivants). Toutefois, après le 9 septembre 2023, ces mesures ne seront plus prises en charge dans les activités existantes et toutes les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers le nouveau comportement.

### Impact sur [!UICONTROL Affectation automatique] activités

| Nom de mesure | Plus pris en charge dans : |
| --- | --- |
| [!UICONTROL averagepagedepth] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL averagetimespentonsite] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL bouncerate] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL bounces] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL entrées] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL sorties] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de mesure |
| [!UICONTROL rechargements] | Maximiser la valeur de mesure |
| [!UICONTROL visiteurs] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL visites] | Maximiser la valeur de mesure |

### Impact sur [!UICONTROL Ciblage automatique] activités

| Nom de mesure | Plus pris en charge dans : |
| --- | --- |
| [!UICONTROL cartremovals] | Maximiser la valeur de mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de mesure |
| [!UICONTROL visiteurs] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL visites] | Maximiser la valeur de mesure |

## Limites et notes

Certaines limites et notes s’appliquent à la fois à [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités. D’autres limitations et notes s’appliquent à un type d’activité ou à un autre.

### Affectation automatique et ciblage automatique {#both}

* Lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique], vous devez toujours afficher les rapports dans [!DNL Analytics].
* La source de création de rapports ne peut pas être modifiée à partir de [!DNL Analytics] to [!DNL Target] ou vice versa une fois qu’une activité a été activée.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat prévu en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure comme &quot;remplissage de formulaire par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaire&quot; comme mesure d’objectif Principale. [!DNL Target] normalise automatiquement les mesures de conversion par visite pour tenir compte de la répartition inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.

### Affectation automatique {#aa}

* **Fréquence de formation**: [!UICONTROL Affectation automatique] les modèles continuent à s&#39;entraîner toutes les heures, comme d&#39;habitude.
* **Modèles d’attribution**: [!DNL Target] utilise la variable [!DNL Adobe Analytics] modèle d’attribution par défaut pour[!UICONTROL  Affectation automatique] activités qui utilisent A4T.
* **Confiance**: La formule de confiance utilisée par [!UICONTROL Affectation automatique] Les activités sont différentes de la formule affichée par défaut dans la variable [!DNL Adobe Analytics] [!UICONTROL A4T] du panneau. [Comme décrit ici](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Affectation automatique] utilise des intervalles de confiance plus conservateurs que standard [!UICONTROL Test A/B] activités. Ces niveaux de confiance conservateurs compensent les évaluations répétées (points ciblés) des données. Par conséquent, le rapport par défaut dans [!DNL Adobe Analytics] affiche des intervalles de confiance plus étroits que ceux utilisés par la variable [!UICONTROL Affectation automatique] algorithme. Néanmoins, vous pouvez déterminer l’expérience qui est préférée par les algorithmes en fonction de l’expérience à laquelle le nombre de visiteurs uniques est envoyé.
* **État du gagnant**: Actuellement, la variable [Badges &quot;Pas encore de gagnant&quot; et &quot;Gagnant&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) ne sont pas disponibles dans la variable [!UICONTROL A4T] dans [!DNL Analysis Workspace]. Ces badges ne sont pas non plus disponibles si le même rapport est affiché dans [!DNL Target]. Badge &quot;étoile&quot; gagnante affiché dans une [!DNL Target] rapport pour un [!UICONTROL Affectation automatique] L’activité utilisant A4T doit être ignorée. Ce badge reflète des calculs de confiance standard, et non ceux utilisés par [!UICONTROL Affectation automatique].

### Ciblage automatique {#at}

* [!UICONTROL Ciblage automatique] les modèles continuent à s&#39;entraîner toutes les 24 heures, comme d&#39;habitude. Cependant, les données d’événement de conversion provenant de [!DNL Analytics] est retardée de six à 24 heures supplémentaires. Ce délai signifie la répartition du trafic par [!DNL Target] effectue le suivi des derniers événements enregistrés dans [!DNL Analytics]. Ce délai a le plus d’effet dans les 48 premières heures suivant l’activation initiale d’une activité. Les performances de l’activité sont plus fidèles [!DNL Analytics] comportement de conversion après cinq jours.

   Envisager d’utiliser [!UICONTROL Affectation automatique] au lieu de [!UICONTROL Ciblage automatique] pour les activités de courte durée dans lesquelles la plupart du trafic se produit au cours des cinq premiers jours de la vie de l’activité.

* Lors de l’utilisation de [!DNL Analytics] comme source de données pour un [!UICONTROL Ciblage automatique] activité, les sessions se terminent après six heures. Les conversions survenant après six heures ne sont pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et intervalles de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) dans le *Guide sur les outils Analytics*.

## Tutoriels

Bien que des fonctionnalités d’analyse complètes soient disponibles dans [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], quelques modifications apportées à la valeur par défaut [!UICONTROL Analytics pour Target] doivent être correctement interprétés. [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités. Ces modifications sont requises en raison des différences entre les activités d’expérimentation (A/B manuel et [!UICONTROL Affectation automatique]) et des activités de personnalisation ([!UICONTROL Ciblage automatique]).

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités d’[!UICONTROL affectation automatique]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse [!UICONTROL Affectation automatique] activités dans [!DNL Analysis Workspace].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités d’affectation automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank} in *Tutorials Adobe Target*.

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités de [!UICONTROL ciblage automatique]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse [!UICONTROL Ciblage automatique] activités dans [!DNL Analysis Workspace].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr){target=_blank} in *Tutorials Adobe Target*.


