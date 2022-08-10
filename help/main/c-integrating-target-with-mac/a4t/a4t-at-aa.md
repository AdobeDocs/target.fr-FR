---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Découvrez comment créer des activités d’affectation automatique et de ciblage automatique dans Adobe [!DNL Target] qui utilisent Analytics comme source des rapports (A4T).
title: A4T prend-il en charge les activités d’affectation automatique et de ciblage automatique ?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: e8fc28ef2497c1dfea523a769c9c817cbd74fea2
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 3%

---

# Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique

Le [!DNL Adobe Target]-to-[!DNL Adobe Analytics] intégration, connue sous le nom de [Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) prend en charge [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités.

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisation [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)est une fonctionnalité de bandit à plusieurs bras qui permet de diriger le trafic vers des expériences gagnantes.
* Utilisation [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)de l’algorithme d’apprentissage automatique d’ensemble de afin de choisir la meilleure expérience pour chaque visiteur. Le ciblage automatique sélectionne la meilleure expérience en fonction des profils, des comportements et du contexte des utilisateurs tout en utilisant une [!DNL Adobe Analytics] mesure d’objectif et [!DNL Adobe Analytics]des capacités riches en rapports et analyses.

Assurez-vous que vous avez [Mise en oeuvre d’A4T pour une utilisation avec les activités de test A/B et de ciblage d’expérience](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la variable `sessionId` valeur à [!DNL Analytics]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} dans la variable *SDK Adobe Target* guide.

Pour démarrer :

1. Lors de la création d’une activité de test A/B, sur la page **[!UICONTROL Ciblage]** , sélectionnez l’une des options suivantes comme **[!UICONTROL Méthode d’affectation du trafic]**:

   * [!UICONTROL Affectation automatique à la meilleure expérience]
   * [!UICONTROL Ciblage automatique pour les expériences personnalisées]

   ![Options Méthodes d’affectation du trafic : Affectation automatique, manuelle et ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Pour plus d’informations et des instructions détaillées, voir [Création d’une activité d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et [Création d’une activité de ciblage automatique](/help/main/c-activities/auto-target/create-auto-target.md).

1. Sélectionner **[!UICONTROL Adobe Analytics]** pour votre **[!UICONTROL Source de création de rapports]** sur le **[!UICONTROL Objectifs et paramètres]** et sélectionnez la suite de rapports correspondant à l’objectif d’optimisation souhaité.

   ![Section Source de création de rapports sur la page Objectifs et paramètres](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Sélectionnez une mesure d’objectif Principal. La première liste déroulante vous permet d’indiquer un objectif dans la variable [!DNL Adobe Target] (qui sera ensuite suivi par [!DNL Adobe Analytics] comme mesure &quot;Conversions des activités&quot;), ou, pour utiliser une [!DNL Analytics] mesure comme objectif.

   * Pour utiliser [!DNL Adobe Target] pour spécifier l’objectif d’optimisation, choisissez **[!UICONTROL Conversion]**, puis spécifiez l’action qui doit être effectuée par votre audience pour indiquer que l’objectif de conversion a été atteint.
   * Si vous sélectionnez **[!UICONTROL Utilisation d’une mesure Analytics]**, vous aurez alors le choix du type de critère d’optimisation à utiliser.  Voir [Mesures d’objectif et critères d’optimisation pris en charge](#supported) ci-dessous pour plus d’informations. Après avoir spécifié le critère d’optimisation, vous pouvez sélectionner une mesure compatible à partir de [!DNL Analytics] à utiliser comme objectif d’optimisation. Vous pouvez utiliser une [!DNL Analytics] mesure de conversion ou [!DNL Analytics] événement personnalisé.


1. Enregistrez et activez votre activité.

   [!UICONTROL Affectation automatique] utilise la mesure que vous avez sélectionnée pour optimiser l’activité, en orientant les visiteurs vers l’expérience qui optimise la mesure de votre objectif.

   Ou

   [!UICONTROL Ciblage automatique] utilise la mesure que vous avez sélectionnée pour optimiser l’activité, ce qui redirige les visiteurs vers une meilleure expérience personnalisée.

1. Utilisez la variable **[!UICONTROL Rapports]** pour afficher les rapports de votre activité, puis cliquez sur **[!UICONTROL Afficher dans Analytics]** pour approfondir et segmenter davantage vos données de rapport dans un espace de travail Adobe Analytics. Vous pouvez suivre les tutoriels ci-dessous pour découvrir comment configurer vos rapports dans Workspace :
* Affectation automatique : see [Configuration des rapports A4T dans Analysis Workspace pour les activités d’affectation automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Tutorials Adobe Target*
* Ciblage automatique : see [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Tutorials Adobe Target*.

## Mesures d’objectif et critères d’optimisation pris en charge {#supported}

[!UICONTROL A4T] pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] vous permet de choisir l’un des types de mesures suivants comme mesure d’objectif Principal pour l’optimisation :

* [!DNL Adobe Target] des mesures de conversion
* [!DNL Adobe Analytics] des mesures de conversion
* [!DNL Adobe Analytics] événements personnalisés

Cependant, [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] les modèles s’optimiseront pour **normalisé** versions de ces mesures, avec la normalisation exacte selon le type d’activité. Les options des critères d&#39;optimisation pour chaque type d&#39;activité sont expliquées dans le tableau ci-dessous :

| Type d’activité | Source de mesure | Critère d’optimisation | Description |
|---------------|---------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Affectation automatique | Analytics | Maximiser le taux de conversion des visiteurs uniques | Les modèles tentent de trouver l’expérience avec le taux de conversion de visiteurs uniques le plus élevé, qui est défini comme le nombre de visiteurs pour lesquels la mesure d’analyse est non nulle, divisé par le nombre total de visiteurs (qui ont reçu cette expérience). Cela signifie que la mesure est traitée comme binaire : 0 ou 1 pour chaque visiteur unique de l’activité.   Utilisez cette option si vous ne vous souciez que de la fraction des utilisateurs effectuant une action spécifique ou lorsque plusieurs événements de conversion pour un seul utilisateur ne sont pas significatifs. |
| Affectation automatique | Analytics | Maximiser la valeur de mesure par visiteur | Les modèles tentent de trouver l’expérience avec la valeur de mesure la plus élevée par visiteur, qui est définie comme la valeur totale de la mesure pour tous les utilisateurs exposés à cette expérience, divisée par le nombre total de visiteurs qui ont reçu cette expérience. Cela signifie que la mesure peut prendre n’importe quelle valeur pour chaque visiteur unique de l’activité. Par exemple, si un visiteur effectue plusieurs conversions, chaque conversion est comptabilisée.  Utilisez cette option si vous souhaitez optimiser une mesure continue comme le total des recettes ou si plusieurs événements de conversion pour un seul utilisateur ont plus de sens qu’un seul (par exemple, plusieurs commandes valent plus qu’une). |
| Affectation automatique | Target | (non configurable) | La mesure est traitée comme binaire et le taux de conversion du visiteur unique est maximisé. |
| Ciblage automatique | Analytics | Maximiser le taux de conversion des visites uniques | Contrairement aux tests A/B manuels ou d’affectation automatique, la nature personnalisée du ciblage automatique signifie que l’expérience vue par un visiteur peut changer pour chaque nouvelle visite. Le taux approprié est alors un taux de conversion normalisé sur les visites, qui est défini comme la fraction des visites au cours desquelles une mesure non nulle est enregistrée. Il s’agit du taux de conversion optimisé par le ciblage automatique.   Tout comme l’affectation automatique, cette option doit être sélectionnée lorsque vous vous souciez du pourcentage de visites au cours desquelles une conversion a lieu, c’est-à-dire lorsque plusieurs événements de conversion se produisant pour une seule visite n’est pas important. |
| Ciblage automatique | Analytics | Maximiser la valeur de mesure par visite | Lorsque la mesure pour laquelle l’optimisation est effectuée est continue (recettes, par exemple) ou lorsque la présence de plusieurs événements de conversion au cours d’une même visite est significative (plusieurs commandes, par exemple), vous pouvez choisir d’optimiser la valeur de la mesure par visite. Le &quot;taux&quot; optimisé est la valeur totale de la mesure, divisée par le nombre de visites. |
| Ciblage automatique | Cible | (non configurable) | La mesure est traitée comme binaire et le taux de conversion des visites uniques est maximisé. |



Notez que selon le critère d’optimisation, certains [!DNL Adobe Analytics] ne sera pas prise en charge.

* [!DNL Adobe Analytics] les mesures calculées ne sont pas prises en charge.
* [!DNL Adobe Analytics] les mesures doivent toujours être segmentables. Si la valeur par visiteur/visite est optimisée, la mesure doit avoir une polarité positive (c’est-à-dire que les valeurs positives sont meilleures que les valeurs négatives).
* [!DNL Adobe Analytics] mesure utilisée dans [!DNL Auto-Target] Les activités doivent être disponibles dans les exports de DataWarehouses.

## Limites et notes

Certaines limites et notes s’appliquent à la fois à [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités. D’autres limitations et notes s’appliquent à un type d’activité ou à un autre.

### Affectation automatique et ciblage automatique {#both}

* Lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique], vous devez toujours afficher les rapports dans [!DNL Analytics].
* La source de création de rapports ne peut pas être modifiée à partir de [!DNL Analytics] to [!DNL Target] ou inversement, après l’activation d’une activité.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat prévu en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure comme &quot;remplissage de formulaire par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaire&quot; comme mesure d’objectif Principale. Comme expliqué dans [Mesures d’objectif et critères d’optimisation pris en charge](#supported), en fonction du type d’activité et de votre critère d’optimisation, [!DNL Target] normalise automatiquement les mesures de conversion. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.


### Affectation automatique {#aa}

* **Fréquence de formation**: [!UICONTROL Affectation automatique] les modèles continuent à s&#39;entraîner toutes les heures, comme d&#39;habitude.
* **Modèles d’attribution**: [!DNL Target] utilise la variable [!DNL Adobe Analytics] modèle d’attribution par défaut pour[!UICONTROL  Affectation automatique] activités qui utilisent A4T.
* **Confiance**: La formule de confiance utilisée par [!UICONTROL Affectation automatique] Les activités sont différentes de la formule affichée par défaut dans la variable [!DNL Adobe Analytics] [!UICONTROL A4T] du panneau. [Comme décrit ici](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Affectation automatique] utilise des intervalles de confiance plus conservateurs que standard [!UICONTROL Test A/B] activités. Ces niveaux de confiance conservateurs compensent les évaluations répétées (points ciblés) des données. Par conséquent, le rapport par défaut dans [!DNL Adobe Analytics] affiche des intervalles de confiance plus étroits que ceux utilisés par la variable [!UICONTROL Affectation automatique] algorithme. Néanmoins, vous pouvez déterminer l’expérience qui est préférée par les algorithmes en fonction de l’expérience à laquelle le nombre de visiteurs uniques est envoyé.
* **État du gagnant**: Actuellement, la variable [Badges &quot;Pas encore de gagnant&quot; et &quot;Gagnant&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) ne sont pas disponibles dans la variable [!UICONTROL A4T] dans [!DNL Analysis Workspace]. Ces badges ne sont pas non plus disponibles si le même rapport est affiché dans [!DNL Target]. Badge &quot;étoile&quot; gagnante affiché dans une [!DNL Target] rapport pour un [!UICONTROL Affectation automatique] L’activité utilisant A4T doit être ignorée. Ce badge reflète des calculs de confiance standard, et non ceux utilisés par [!UICONTROL Affectation automatique].

### Ciblage automatique {#at}

* **Fréquence de formation**: [!UICONTROL Ciblage automatique] les modèles continuent à s&#39;entraîner toutes les 24 heures, comme d&#39;habitude. Cependant, les données d’événement de conversion provenant de [!DNL Analytics] est retardée de six à 24 heures supplémentaires. Ce délai signifie la répartition du trafic par [!DNL Target] effectue le suivi des derniers événements enregistrés dans [!DNL Analytics]. Ce délai a le plus d’effet dans les 48 premières heures suivant l’activation initiale d’une activité. Les performances de l’activité seront plus fidèlement reflétées. [!DNL Analytics] comportement de conversion après cinq jours. Envisager d’utiliser [!UICONTROL Affectation automatique] au lieu de [!UICONTROL Ciblage automatique] pour les activités de courte durée dans lesquelles la plupart du trafic se produit au cours des cinq premiers jours de la vie de l’activité.
* Lors de l’utilisation de [!DNL Analytics] comme source de données pour un [!UICONTROL Ciblage automatique] activité, les sessions se terminent après six heures. Les conversions survenant après six heures ne sont pas comptabilisées.

Pour plus d’informations, voir [Modèles d’attribution et intervalles de recherche en amont](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) dans le *Guide sur les outils Analytics*.

## Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique et d’affectation automatique {#tutorial}

Bien que des fonctionnalités d’analyse complètes soient disponibles dans [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], quelques modifications apportées à la valeur par défaut [!UICONTROL Analytics pour Target] sont requis pour interpréter correctement les activités d’affectation automatique et de ciblage automatique.

Ces modifications sont requises en raison des définitions nuancées des taux de conversion décrites dans la section [Mesures d’objectif et critères d’optimisation pris en charge](#supported), ainsi que les différences entre les activités d’expérimentation (A/B manuel et [!UICONTROL Affectation automatique]) et des activités de personnalisation ([!UICONTROL Ciblage automatique]).

Ces tutoriels vous guident tout au long des modifications recommandées pour l’analyse [!UICONTROL A4T] [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités dans [!UICONTROL Workspace].

Pour plus d’informations, voir 
* [Configuration des rapports A4T dans Analysis Workspace pour les activités d’affectation automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Tutorials Adobe Target*.
* [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Tutorials Adobe Target*.
