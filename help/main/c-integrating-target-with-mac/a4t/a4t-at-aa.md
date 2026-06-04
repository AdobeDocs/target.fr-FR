---
keywords: a4t;A4T;Analytics comme source de création de rapports pour Target;Analytics for Target
description: Découvrez comment créer des activités [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] dans  [!DNL Target]  qui utilisent  [!DNL Analytics]  comme source de création de rapports (A4T).
title: A4T prend-il en charge les activités [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] ?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
TQID: https://experienceleague.adobe.com/VVbjMp7jYDyslZ8ubn8ntPufLK8nKGI9k3ZGh1DLWWs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ceid: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2: id: df62f171-ac37-440f-8f0f-f41a72ebdd34
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1509
ht-degree: 6%

---

# Prise en charge d’A4T pour les activités [!UICONTROL  Affectation automatique ] et [!UICONTROL  Ciblage automatique ]

L’intégration [!DNL Adobe Target] à [!DNL Adobe Analytics], connue sous le nom d’[ Analytics for Target ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), prend en charge les activités [!UICONTROL  Affectation automatique ] et [!UICONTROL  Ciblage automatique ].

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisez la fonctionnalité de bandit à plusieurs bras [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour orienter le trafic vers des expériences gagnantes.
* Utilisez l’algorithme de machine learning d’ensemble [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) pour choisir la meilleure expérience pour chaque visiteur. Le [!UICONTROL ciblage automatique] sélectionne la meilleure expérience en fonction du profil, du comportement et du contexte de chaque utilisateur, tout en utilisant une mesure d’objectif [!DNL Adobe Analytics] et les riches fonctionnalités de création de rapports et d’analyse d’[!DNL Adobe Analytics].

Vérifiez que vous avez [implémenté A4T pour une utilisation avec les activités de test A/B et de ciblage d’expérience](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la valeur `sessionId` à [!DNL Analytics]. Pour plus d’informations, consultez [Rapports Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} dans le *Guide de développement d’Adobe Target*.

Pour démarrer :

1. Lors de la [création d’une activité [!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), sur la page **[!UICONTROL Ciblage]**, cliquez sur la commande **[!UICONTROL Affectation du trafic]** puis choisissez la méthode d’affectation du trafic souhaitée dans le volet de droite.

   ![Paramètres de la méthode d’affectation du trafic](/help/main/c-activities/assets/auto-target.png)

   Les méthodes d’affectation du trafic disponibles sont les suivantes :

   * **[!UICONTROL Manuel (par défaut)]** : indiquez le pourcentage de participants qui doivent voir chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %.

   * **[!UICONTROL Affectation automatique à la meilleure expérience]** : la plupart des personnes participant à l’activité sont automatiquement redirigées vers des expériences plus performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Pour plus d’informations, consultez la présentation de l’[[!UICONTROL affectation automatique] ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Ciblage automatique pour les expériences personnalisées]** : [!DNL Target] utilise le machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing, puis en proposant l’expérience la plus personnalisée aux visiteurs selon leur profil client individuel et le comportement antérieur de visiteurs similaires. Pour plus d’informations, voir [Présentation du ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Pour plus d’informations et des instructions détaillées, voir [Création d’une activité d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et [Création d’une activité de ciblage automatique](/help/main/c-activities/auto-target/create-auto-target.md).

1. Sélectionnez **** pour votre **[!UICONTROL Reporting Source]** sur la page **[!UICONTROL Objectifs et paramètres]**, sélectionnez la société et la suite de rapports correspondant à l’objectif d’optimisation souhaité.

   ![Section Reporting Source sur la page Objectifs et paramètres](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Spécifiez le serveur de suivi et le sandbox.

1. Choisissez une mesure [!UICONTROL Objectif de Principal ].

   * Pour utiliser [!DNL Adobe Target] pour spécifier l’objectif d’optimisation, choisissez **[!UICONTROL Conversion]** .
   * Choisissez **[!UICONTROL Utiliser une mesure Analytics]** puis sélectionnez une mesure dans la [!DNL Analytics] à utiliser comme objectif d’optimisation. Vous pouvez utiliser une mesure de conversion de [!DNL Analytics] prête à l’emploi ou un événement personnalisé [!DNL Analytics].

   Pour plus d’informations](#supported) voir [ Mesures d’objectif prises en charge ci-dessous.

1. Enregistrez et activez votre activité.

   L’[!UICONTROL Affectation automatique] utilise la mesure sélectionnée pour optimiser l’activité, orientant les visiteurs vers l’expérience qui optimise votre mesure d’objectif.

   Ou

   Le [!UICONTROL ciblage automatique] utilise les mesures sélectionnées pour optimiser l’activité, offrant ainsi aux visiteurs une expérience optimale et personnalisée.

1. Utilisez l’onglet **[!UICONTROL Rapports]** pour afficher les rapports de votre activité en fonction des mesures de [!DNL Adobe Analytics] de votre choix. Cliquez sur **[!UICONTROL Afficher dans Analytics]** pour approfondir et segmenter davantage vos données de rapports.

## Mesures d’objectif prises en charge {#supported}

[!UICONTROL A4T] pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] vous permet de choisir l’un des types de mesures suivants en tant que mesure d’objectif principale pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] d’événements personnalisés

>[!NOTE]
>
>Après avoir sélectionné [!UICONTROL Utiliser une mesure Analytics], sélectionnez [!UICONTROL Maximiser le taux de conversion des visiteurs uniques] pour afficher les mesures de conversion de [!DNL Adobe Analytics] disponibles, et [!UICONTROL Maximiser la valeur de la mesure par visiteur] pour explorer [!DNL Adobe Analytics] événements personnalisés.

[!DNL Target] vous permet de choisir des mesures en fonction d’événements binomiaux ou d’événements continus lors de l’utilisation d’[!UICONTROL A4T] pour les activités [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique].

* **Mesures basées sur des événements binomiaux** : un événement binomial se produit ou ne se produit pas. Les événements binomiaux incluent un clic, une conversion, une commande, etc. Ces types d’événements sont également parfois appelés événements de Bernoulli, binaires ou discrets.

* **Mesures basées sur des événements continus**. Les mesures continues incluent le chiffre d’affaires, le nombre de produits commandés, la durée de la session, le nombre de pages vues dans la session, etc. Ces types d’événements sont également parfois appelés mesures non binomiales ou non de Bernoulli.

>[!IMPORTANT]
>
>Depuis la version 22.15.1 de [!DNL Adobe Target Standard/Premium] (8 et 9 mars 2023), [!DNL Target] continue à prendre en charge les activités existantes avec les mesures qui ne sont désormais plus prises en charge (répertoriées dans les tableaux suivants). Cependant, après le 9 septembre 2023, ces mesures ne seront plus prises en charge dans les activités existantes et toutes les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers le nouveau comportement.

### Impact sur les activités [!UICONTROL  Affectation automatique ]

| Nom de mesure | n’est plus pris en charge dans : |
| --- | --- |
| [!UICONTROL averagepagedepth] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL averagetimespentonsite] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL bounce] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL  bounces ] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL entrées] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL quitte] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de la mesure |
| [!UICONTROL rechargements] | Maximiser la valeur de la mesure |
| [!UICONTROL visiteurs] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL visites] | Maximiser la valeur de la mesure |

### Impact sur les activités de [!UICONTROL  ciblage automatique ]

| Nom de mesure | n’est plus pris en charge dans : |
| --- | --- |
| [!UICONTROL cartremovals] | Maximiser la valeur de la mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de la mesure |
| [!UICONTROL visiteurs] | Taux De Conversion, Maximiser La Valeur De La Mesure |
| [!UICONTROL visites] | Maximiser la valeur de la mesure |

## Restrictions et notes

Certaines restrictions et notes s’appliquent à la fois aux activités [!UICONTROL  Affectation automatique ] et [!UICONTROL  Ciblage automatique ]. D’autres restrictions et notes s’appliquent à un type d’activité ou à l’autre.

### Affectation automatique et ciblage automatique {#both}

* Lorsque vous utilisez [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique], vous devez toujours afficher les rapports dans [!DNL Analytics].
* La source de création de rapports ne peut pas être modifiée de [!DNL Analytics] en [!DNL Target] ou vice versa une fois qu’une activité a été activée.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif principales, il est souvent possible d’obtenir le résultat escompté en sélectionnant plutôt un événement personnalisé en tant que mesure d’objectif principale. Par exemple, si vous souhaitez optimiser une mesure telle que « fin de formulaire par visiteur », sélectionnez un événement personnalisé correspondant à « fin de formulaire » en tant que mesure d’objectif principale. [!DNL Target] normalise automatiquement les mesures de conversion sur une base par visite pour tenir compte de la distribution inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.

### Affectation automatique {#aa}

* **Fréquence d’entraînement** : [!UICONTROL Affectation automatique] les modèles continuent de s’entraîner toutes les heures, comme d’habitude.
* **Modèles d’attribution** : [!DNL Target] utilise le modèle d’attribution par défaut [!DNL Adobe Analytics] pour les activités d[!UICONTROL affectation automatique] qui utilisent A4T.
* **Confiance** : la formule de confiance utilisée par les activités [!UICONTROL Affectation automatique] est différente de la formule affichée par défaut dans le panneau [!DNL Adobe Analytics] [!UICONTROL A4T]. [Comme décrit ici](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) l’[!UICONTROL affectation automatique] utilise des intervalles de confiance plus conservateurs que les activités [!UICONTROL Test A/B] standard. Ces niveaux de confiance conservateurs compensent les évaluations répétées (aperçus) des données. Par conséquent, le rapport par défaut dans [!DNL Adobe Analytics] affiche des intervalles de confiance plus étroits par rapport à ceux utilisés par l’algorithme [!UICONTROL  Affectation automatique ]. Néanmoins, vous pouvez déterminer quelle expérience est favorisée par les algorithmes en fonction de quelle expérience reçoit le plus de visiteurs uniques.
* **Statut du gagnant** : actuellement, les badges [ « Pas encore de gagnant » et « Gagnant »](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) ne sont pas disponibles dans le panneau [!UICONTROL A4T] dans [!DNL Analysis Workspace]. Ces badges ne sont pas disponibles non plus si le même rapport est affiché dans [!DNL Target]. Le badge « étoile » gagnant affiché dans un rapport [!DNL Target] pour une activité [!UICONTROL  Affectation automatique ] à l’aide d’A4T doit être ignoré. Ce badge reflète les calculs de confiance standard, et non les calculs utilisés par l’[!UICONTROL  Affectation automatique].

### Ciblage automatique {#at}

* Les modèles de [!UICONTROL ciblage automatique] continuent de s’entraîner toutes les 24 heures, comme d’habitude. Toutefois, les données d’événement de conversion provenant de [!DNL Analytics] sont retardées de six à 24 heures supplémentaires. Ce délai correspond à la répartition du trafic en [!DNL Target] les derniers événements enregistrés en [!DNL Analytics]. Ce délai a le plus grand effet dans les 48 premières heures suivant l’activation initiale d’une activité. Les performances de l’activité reflètent mieux [!DNL Analytics] comportement de conversion après cinq jours.

  Utilisez l’option [!UICONTROL  Affectation automatique ] au lieu de [!UICONTROL Ciblage automatique] pour les activités de courte durée dans lesquelles la plupart du trafic se produit au cours des cinq premiers jours de la vie de l’activité.

* Lorsque vous utilisez [!DNL Analytics] comme source de données pour une activité de [!UICONTROL ciblage automatique], les sessions se terminent au bout de six heures. Les conversions survenant après six heures ne sont pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et intervalles de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) dans le *Guide des outils Analytics*.

## Tutoriels

Bien que des fonctionnalités d’analyse riches soient disponibles dans [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], quelques modifications sont nécessaires dans le panneau par défaut [!UICONTROL Analytics for Target] pour interpréter correctement les activités [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]. Ces modifications sont requises en raison des différences entre les activités d’expérimentation (A/B manuel et [!UICONTROL Affectation automatique]) et les activités de personnalisation ([!UICONTROL Ciblage automatique]).

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités [!UICONTROL  Affectation automatique ]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse des activités [!UICONTROL  Affectation automatique ] dans [!DNL Analysis Workspace].

Pour plus d’informations, consultez [Comment configurer des rapports A4T dans Analysis Workspace pour les activités d’affectation automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank} dans *Tutoriels Adobe Target*.

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités de [!UICONTROL  ciblage automatique ]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse des activités de [!UICONTROL ciblage automatique] dans [!DNL Analysis Workspace].

Pour plus d’informations, consultez [Comment configurer des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr){target=_blank} dans *Tutoriels Adobe Target*.


