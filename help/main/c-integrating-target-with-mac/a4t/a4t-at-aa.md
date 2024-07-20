---
keywords: a4t;A4T;Analytics comme source des rapports pour Target;analytics pour target
description: Découvrez comment créer des activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] dans  [!DNL Target] qui utilisent [!DNL Analytics] comme source des rapports (A4T).
title: A4T prend-il en charge les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] ?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 99bd509988a7d1545a6a1fe59aa59f35ef0a7d11
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 1%

---

# Prise en charge d’A4T pour les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]

L’intégration [!DNL Adobe Target] à [!DNL Adobe Analytics], connue sous le nom de [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), prend en charge les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisez la fonctionnalité de bandit à plusieurs bras [Auto-affectation](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour diriger le trafic vers des expériences gagnantes.
* Utilisez l’algorithme d’apprentissage automatique d’ensemble [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) pour choisir la meilleure expérience pour chaque visiteur. [!UICONTROL Auto-Target] sélectionne la meilleure expérience en fonction du profil, du comportement et du contexte de chaque utilisateur, tout en utilisant une mesure d’objectif [!DNL Adobe Analytics] et les riches fonctionnalités de création de rapports et d’analyse de [!DNL Adobe Analytics].

Assurez-vous que vous avez [implémenté A4T pour une utilisation avec les activités de test A/B et de ciblage d’expérience](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la valeur `sessionId` à [!DNL Analytics]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} dans le *Guide du développeur Adobe Target*.

Pour démarrer :

1. Lors de la [ création d’une [!UICONTROL A/B Test] activité](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), sur la page **[!UICONTROL Targeting]**, sélectionnez l’une des options suivantes comme **[!UICONTROL Traffic Allocation Method]** :

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![ Options des méthodes d’affectation du trafic : Manuel, Affectation automatique et Ciblage automatique ](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Pour plus d’informations et des instructions détaillées, voir [Création d’une activité d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et [Création d’une activité de ciblage automatique](/help/main/c-activities/auto-target/create-auto-target.md).

1. Sélectionnez **[!UICONTROL Adobe Analytics]** pour votre **[!UICONTROL Reporting Source]** sur la page **[!UICONTROL Goals & Settings]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

   ![Section Source de création de rapports sur la page Objectifs et paramètres](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Sélectionnez une mesure [!UICONTROL Primary Goal].

   * Pour utiliser [!DNL Adobe Target] pour spécifier l’objectif d’optimisation, choisissez **[!UICONTROL Conversion]** .
   * Sélectionnez **[!UICONTROL Use an Analytics metric]**, puis une mesure [!DNL Analytics] à utiliser comme objectif d’optimisation. Vous pouvez utiliser une mesure de conversion [!DNL Analytics] prête à l’emploi ou un événement personnalisé [!DNL Analytics].

   Pour plus d’informations, voir [Mesures d’objectif prises en charge](#supported) ci-dessous.

1. Enregistrez et activez votre activité.

   [!UICONTROL Auto-Allocate] utilise la mesure sélectionnée pour optimiser l’activité, orientant les visiteurs vers l’expérience qui maximise la mesure de votre objectif.

   Ou

   [!UICONTROL Auto-Target] utilise la mesure sélectionnée pour optimiser l’activité, conduisant les visiteurs vers une meilleure expérience personnalisée.

1. Utilisez l’onglet **[!UICONTROL Reports]** pour afficher les rapports de votre activité selon le choix de mesures [!DNL Adobe Analytics]. Cliquez sur **[!UICONTROL View in Analytics]** pour approfondir et segmenter davantage vos données de rapport.

## Mesures d’objectif prises en charge {#supported}

[!UICONTROL A4T] pour [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] vous permet de choisir l’un des types de mesures suivants comme mesure d’objectif principal pour l’optimisation :

* [!DNL Adobe Target] mesures de conversion
* [!DNL Adobe Analytics] mesures de conversion
* [!DNL Adobe Analytics] événements personnalisés

[!DNL Target] vous permet de choisir des mesures basées sur des événements binaires ou des mesures basées sur des événements continus lors de l’utilisation de [!UICONTROL A4T] pour les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].

* **Mesures basées sur des événements binaires** : un événement binaire se produit ou ne se produit pas. Les événements binaires incluent un clic, une conversion, une commande, etc. On parle aussi parfois de Bernoulli, de binaire ou d’événement discret.

* **Mesures basées sur des événements continus**. Les mesures continues comprennent les recettes, le nombre de produits commandés, la durée de session, le nombre de pages vues dans la session, etc. Ces types d’événements sont également parfois appelés mesures non binaires ou non Bernoulli.

>[!IMPORTANT]
>
>À compter de la version [!DNL Adobe Target Standard/Premium] 22.15.1 (8 et 9 mars 2023), [!DNL Target] continuera à prendre en charge les activités existantes avec les mesures qui ne sont désormais plus prises en charge (répertoriées dans les tableaux ci-dessous). Toutefois, après le 9 septembre 2023, ces mesures ne seront plus prises en charge dans les activités existantes et toutes les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers le nouveau comportement.

### Impact sur les activités [!UICONTROL Auto-Allocate]

| Nom de mesure | Plus pris en charge dans : |
| --- | --- |
| [!UICONTROL averagepagedepth] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL averagetimespentonsite] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL bouncerate] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL bounces] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL entries] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL exits] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de la mesure |
| [!UICONTROL reloads] | Maximiser la valeur de la mesure |
| [!UICONTROL visitors] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL visits] | Maximiser la valeur de la mesure |

### Impact sur les activités [!UICONTROL Auto-Target]

| Nom de mesure | Plus pris en charge dans : |
| --- | --- |
| [!UICONTROL cartremovals] | Maximiser la valeur de la mesure |
| [!UICONTROL pageviews] | Maximiser la valeur de la mesure |
| [!UICONTROL visitors] | Taux de conversion, Maximiser la valeur de mesure |
| [!UICONTROL visits] | Maximiser la valeur de la mesure |

## Limites et notes

Certaines limites et notes s’appliquent aux activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]. D’autres limitations et notes s’appliquent à un type d’activité ou à un autre.

### Affectation automatique et ciblage automatique {#both}

* Lorsque vous utilisez [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target], vous devez toujours afficher les rapports dans [!DNL Analytics].
* Une fois qu’une activité a été activée, la source des rapports ne peut pas être modifiée de [!DNL Analytics] à [!DNL Target] ou vice versa.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif principales, il est souvent possible d’obtenir le résultat prévu en sélectionnant plutôt un événement personnalisé comme mesure d’objectif principale. Par exemple, si vous souhaitez optimiser pour une mesure telle que &quot;remplissage de formulaire par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaire&quot; comme mesure d’objectif principale. [!DNL Target] normalise automatiquement les mesures de conversion par visite pour tenir compte de la distribution inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.

### Affectation automatique {#aa}

* **Fréquence d’entraînement** : [!UICONTROL Auto-Allocate] les modèles continuent à s’entraîner toutes les heures, comme d’habitude.
* **Modèles d’attribution** : [!DNL Target] utilise le modèle d’attribution par défaut [!DNL Adobe Analytics] pour les activités [!UICONTROL  Auto-Allocate] qui utilisent A4T.
* **Confiance** : la formule de confiance utilisée par les activités [!UICONTROL Auto-Allocate] est différente de la formule affichée par défaut dans le panneau [!DNL Adobe Analytics] [!UICONTROL A4T]. [Comme décrit ici](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Auto-Allocate] utilise des intervalles de confiance plus conservateurs que les activités [!UICONTROL A/B Test] standard. Ces niveaux de confiance conservateurs compensent les évaluations répétées (points ciblés) des données. Par conséquent, le rapport par défaut dans [!DNL Adobe Analytics] affiche des intervalles de confiance plus étroits par rapport à ces intervalles utilisés par l’algorithme [!UICONTROL Auto-Allocate]. Néanmoins, vous pouvez déterminer l’expérience qui est préférée par les algorithmes en fonction de l’expérience à laquelle le nombre de visiteurs uniques est envoyé.
* **Statut de la gagnante** : actuellement, les badges [ &quot;Pas encore de gagnante&quot; et &quot;Gagnant&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) ne sont pas disponibles dans le panneau [!UICONTROL A4T] de [!DNL Analysis Workspace]. Ces badges ne sont pas non plus disponibles si le même rapport est affiché dans [!DNL Target]. Un badge &quot;étoile&quot; gagnant affiché dans un rapport [!DNL Target] pour une activité [!UICONTROL Auto-Allocate] utilisant A4T doit être ignoré. Ce badge reflète des calculs de confiance standard, et non les calculs utilisés par [!UICONTROL Auto-Allocate].

### Ciblage automatique {#at}

* Les modèles [!UICONTROL Auto-Target] continuent à s’entraîner toutes les 24 heures, comme d’habitude. Toutefois, les données d’événement de conversion provenant de [!DNL Analytics] sont retardées de six à 24 heures supplémentaires. Ce délai signifie que la distribution du trafic par [!DNL Target] effectue le suivi des derniers événements enregistrés dans [!DNL Analytics]. Ce délai a le plus d’effet dans les 48 premières heures suivant l’activation initiale d’une activité. Les performances de l’activité reflètent plus étroitement le comportement de conversion [!DNL Analytics] après cinq jours.

  Pensez à utiliser [!UICONTROL Auto-Allocate] au lieu de [!UICONTROL Auto-Target] pour les activités de courte durée dans lesquelles la plupart du trafic se produit au cours des cinq premiers jours de la vie de l’activité.

* Lors de l’utilisation de [!DNL Analytics] comme source de données pour une activité [!UICONTROL Auto-Target], les sessions se terminent après six heures. Les conversions survenant après six heures ne sont pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et intervalles de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) dans le *Guide des outils Analytics*.

## Tutoriels

Bien que de riches fonctionnalités d&#39;analyse soient disponibles dans [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], quelques modifications du panneau par défaut [!UICONTROL Analytics for Target] sont nécessaires pour interpréter correctement les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]. Ces modifications sont requises en raison des différences entre les activités d’expérimentation (A/B manuel et [!UICONTROL Auto-Allocate]) et les activités de personnalisation ([!UICONTROL Auto-Target]).

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités [!UICONTROL Auto-Allocate]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse des activités [!UICONTROL Auto-Allocate] dans [!DNL Analysis Workspace].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités d’affectation automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank} dans *Adobe Target Tutorials*.

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour les activités [!UICONTROL Auto-Target]

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse des activités [!UICONTROL Auto-Target] dans [!DNL Analysis Workspace].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr){target=_blank} dans *Adobe Target Tutorials*.


