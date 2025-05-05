---
keywords: a4t;A4T;Analytics comme source de création de rapports pour Target;Analytics for Target
description: Découvrez comment créer des [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] des activités dans  [!DNL Target]  qui utilisent  [!DNL Analytics]  comme source de création de rapports (A4T).
title: A4T prend-il en charge les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] ?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 80e4741f5f501a48b15b718c6c0bf55a86c4d676
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 1%

---

# Prise en charge d’A4T pour les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]

L’intégration [!DNL Adobe Target] à [!DNL Adobe Analytics], connue sous le nom d’[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), prend en charge les activités de [!UICONTROL Auto-Allocate] et de [!UICONTROL Auto-Target].

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisez la fonctionnalité de bandit à plusieurs bras [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour orienter le trafic vers des expériences gagnantes.
* Utilisez l’algorithme de machine learning d’ensemble [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) pour choisir la meilleure expérience pour chaque visiteur. [!UICONTROL Auto-Target] choisit la meilleure expérience en fonction du profil, du comportement et du contexte de chaque utilisateur, tout en utilisant une mesure d’objectif [!DNL Adobe Analytics] et les riches fonctionnalités de création de rapports et d’analyse de [!DNL Adobe Analytics].

Vérifiez que vous avez [implémenté A4T pour une utilisation avec les activités de test A/B et de ciblage d’expérience](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la valeur `sessionId` à [!DNL Analytics]. Pour plus d’informations, consultez [Rapports Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=fr){target=_blank} dans le *Guide de développement d’Adobe Target*.

Pour démarrer :

1. Lors de la [création d’une activité [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), sur la page **[!UICONTROL Targeting]**, sélectionnez l’une des options suivantes comme **[!UICONTROL Traffic Allocation Method]** :

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Options des méthodes d’affectation du trafic : manuel, affectation automatique et ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Pour plus d’informations et des instructions détaillées, voir [Création d’une activité d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et [Création d’une activité de ciblage automatique](/help/main/c-activities/auto-target/create-auto-target.md).

1. Sélectionnez **[!UICONTROL Adobe Analytics]** pour votre **[!UICONTROL Reporting Source]** sur la page **[!UICONTROL Goals & Settings]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

   ![Section Reporting Source sur la page Objectifs et paramètres](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Choisissez une mesure de [!UICONTROL Primary Goal].

   * Pour utiliser [!DNL Adobe Target] pour spécifier l’objectif d’optimisation, choisissez **[!UICONTROL Conversion]** .
   * Choisissez **[!UICONTROL Use an Analytics metric]** puis sélectionnez une mesure dans [!DNL Analytics] à utiliser comme objectif d’optimisation. Vous pouvez utiliser une mesure de conversion de [!DNL Analytics] prête à l’emploi ou un événement personnalisé [!DNL Analytics].

   Pour plus d’informations[&#128279;](#supported) voir  Mesures d’objectif prises en charge ci-dessous.

1. Enregistrez et activez votre activité.

   [!UICONTROL Auto-Allocate] utilise la mesure sélectionnée pour optimiser l’activité, orientant les visiteurs vers une expérience qui optimise votre mesure d’objectif.

   Ou

   [!UICONTROL Auto-Target] utilise la mesure sélectionnée pour optimiser l’activité, offrant ainsi aux visiteurs une expérience personnalisée optimale.

1. Utilisez l’onglet **[!UICONTROL Reports]** pour afficher les rapports de votre activité en fonction des mesures de [!DNL Adobe Analytics] de votre choix. Cliquez sur **[!UICONTROL View in Analytics]** pour approfondir et segmenter davantage vos données de rapports.

## Mesures d’objectif prises en charge {#supported}

[!UICONTROL A4T] pour [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] vous permet de choisir l’un des types de mesures suivants en tant que mesure d’objectif principale pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] d’événements personnalisés

>[!NOTE]
>
>Après avoir sélectionné [!UICONTROL Use an Analytics Metric], sélectionnez [!UICONTROL Maximize Unique Visitor Conversion Rate] pour afficher les mesures de conversion de [!DNL Adobe Analytics] disponibles et [!UICONTROL Maximize Metric Value per Visitor] pour explorer [!DNL Adobe Analytics] événements personnalisés.

[!DNL Target] vous permet de choisir des mesures en fonction d’événements binomiaux ou d’événements continus lors de l’utilisation de [!UICONTROL A4T] pour des activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].

* **Mesures basées sur des événements binomiaux** : un événement binomial se produit ou ne se produit pas. Les événements binomiaux incluent un clic, une conversion, une commande, etc. Ces types d’événements sont également parfois appelés événements de Bernoulli, binaires ou discrets.

* **Mesures basées sur des événements continus**. Les mesures continues incluent le chiffre d’affaires, le nombre de produits commandés, la durée de la session, le nombre de pages vues dans la session, etc. Ces types d’événements sont également parfois appelés mesures non binomiales ou non de Bernoulli.

>[!IMPORTANT]
>
>Depuis la version 22.15.1 de [!DNL Adobe Target Standard/Premium] (8 et 9 mars 2023), [!DNL Target] continue à prendre en charge les activités existantes avec les mesures qui ne sont désormais plus prises en charge (répertoriées dans les tableaux suivants). Cependant, après le 9 septembre 2023, ces mesures ne seront plus prises en charge dans les activités existantes et toutes les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers le nouveau comportement.

### Impact sur les activités [!UICONTROL Auto-Allocate]

| Nom de mesure | n’est plus pris en charge dans : |
| --- | --- |
| [!UICONTROL averagepagedepth] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL averagetimespentonsite] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL bouncerate] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL bounces] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL entries] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL exits] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de la mesure |
| [!UICONTROL reloads] | Maximiser la valeur de la mesure |
| [!UICONTROL visitors] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL visits] | Maximiser la valeur de la mesure |

### Impact sur les activités [!UICONTROL Auto-Target]

| Nom de mesure | n’est plus pris en charge dans : |
| --- | --- |
| [!UICONTROL cartremovals] | Maximiser la valeur de la mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de la mesure |
| [!UICONTROL visitors] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL visits] | Maximiser la valeur de la mesure |

## Restrictions et notes

Certaines restrictions et notes s’appliquent aux activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]. D’autres restrictions et notes s’appliquent à un type d’activité ou à l’autre.

### Affectation automatique et ciblage automatique {#both}

* Lorsque vous utilisez [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target], vous devez toujours afficher les rapports dans [!DNL Analytics].
* La source de création de rapports ne peut pas être modifiée de [!DNL Analytics] en [!DNL Target] ou vice versa une fois qu’une activité a été activée.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif principales, il est souvent possible d’obtenir le résultat escompté en sélectionnant plutôt un événement personnalisé en tant que mesure d’objectif principale. Par exemple, si vous souhaitez optimiser une mesure telle que « fin de formulaire par visiteur », sélectionnez un événement personnalisé correspondant à « fin de formulaire » en tant que mesure d’objectif principale. [!DNL Target] normalise automatiquement les mesures de conversion sur une base par visite pour tenir compte de la distribution inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.

### Affectation automatique {#aa}

* **Fréquence d’entraînement** : les modèles [!UICONTROL Auto-Allocate] continuent de s’entraîner toutes les heures, comme d’habitude.
* **Modèles d’attribution** : [!DNL Target] utilise le modèle d’attribution par défaut [!DNL Adobe Analytics] pour [!UICONTROL &#x200B; Auto-Allocate] activités qui utilisent A4T.
* **Confiance** : la formule de confiance utilisée par [!UICONTROL Auto-Allocate] activités est différente de la formule affichée par défaut dans le panneau [!UICONTROL A4T] de [!DNL Adobe Analytics]. [Comme décrit ici](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Auto-Allocate] utilise des intervalles de confiance plus conservateurs que les activités de [!UICONTROL A/B Test] normales. Ces niveaux de confiance conservateurs compensent les évaluations répétées (aperçus) des données. Par conséquent, le rapport par défaut dans [!DNL Adobe Analytics] affiche des intervalles de confiance plus étroits par rapport à ceux utilisés par l’algorithme de [!UICONTROL Auto-Allocate]. Néanmoins, vous pouvez déterminer quelle expérience est favorisée par les algorithmes en fonction de quelle expérience reçoit le plus de visiteurs uniques.
* **Statut du gagnant** : actuellement, les badges [ « Pas encore de gagnant » et « Gagnant »](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) ne sont pas disponibles dans le panneau [!UICONTROL A4T] dans [!DNL Analysis Workspace]. Ces badges ne sont pas disponibles non plus si le même rapport est affiché dans [!DNL Target]. Le badge « étoile » gagnant affiché dans un rapport [!DNL Target] pour une activité [!UICONTROL Auto-Allocate] à l’aide d’A4T doit être ignoré. Ce badge reflète les calculs de confiance standard, et non les calculs utilisés par [!UICONTROL Auto-Allocate].

### Ciblage automatique {#at}

* [!UICONTROL Auto-Target] modèles continuent de s&#39;entraîner toutes les 24 heures, comme d&#39;habitude. Toutefois, les données d’événement de conversion provenant de [!DNL Analytics] sont retardées de six à 24 heures supplémentaires. Ce délai correspond à la répartition du trafic en [!DNL Target] les derniers événements enregistrés en [!DNL Analytics]. Ce délai a le plus grand effet dans les 48 premières heures suivant l’activation initiale d’une activité. Les performances de l’activité reflètent mieux [!DNL Analytics] comportement de conversion après cinq jours.

  Envisagez d’utiliser [!UICONTROL Auto-Allocate] au lieu de [!UICONTROL Auto-Target] pour les activités de courte durée, dans lesquelles la plupart du trafic se produit au cours des cinq premiers jours de la vie de l’activité.

* Lorsque vous utilisez [!DNL Analytics] comme source de données pour une activité [!UICONTROL Auto-Target], les sessions se terminent après six heures. Les conversions survenant après six heures ne sont pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et intervalles de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=fr) dans le *Guide des outils Analytics*.

## Tutoriels

Bien que des fonctionnalités d’analyse riches soient disponibles dans [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], quelques modifications sont nécessaires dans le panneau de [!UICONTROL Analytics for Target] par défaut pour interpréter correctement les activités de [!UICONTROL Auto-Allocate] et de [!UICONTROL Auto-Target]. Ces modifications sont requises en raison des différences entre les activités d’expérimentation (A/B et [!UICONTROL Auto-Allocate] manuels) et les activités de personnalisation ([!UICONTROL Auto-Target]).

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités [!UICONTROL Auto-Allocate]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse des activités [!UICONTROL Auto-Allocate] dans [!DNL Analysis Workspace].

Pour plus d’informations, consultez [Comment configurer des rapports A4T dans Analysis Workspace pour les activités d’affectation automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank} dans *Tutoriels Adobe Target*.

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités [!UICONTROL Auto-Target]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse des activités [!UICONTROL Auto-Target] dans [!DNL Analysis Workspace].

Pour plus d’informations, consultez [Comment configurer des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr){target=_blank} dans *Tutoriels Adobe Target*.


