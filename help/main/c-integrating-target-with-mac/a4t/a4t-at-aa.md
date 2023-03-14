---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Découvrez comment créer [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités dans [!DNL Target] qui utilisent [!DNL Analytics] comme source des rapports (A4T).
title: Prise en charge d’A4T [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] Activités ?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '1292'
ht-degree: 2%

---

# Prise en charge d’A4T pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités

Le [!DNL Adobe Target]-to-[!DNL Adobe Analytics] intégration, connue sous le nom de [Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) prend en charge [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités.

L’intégration A4T vous permet d’effectuer les opérations suivantes :

* Utilisation [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)La fonctionnalité de bandit à plusieurs bras d’ pour orienter le trafic vers des expériences gagnantes.
* Utilisation [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)algorithme d’apprentissage automatique d’ensemble de afin de choisir la meilleure expérience pour chaque visiteur. [!UICONTROL Ciblage automatique] choisit la meilleure expérience en fonction des profils, des comportements et du contexte des utilisateurs tout en utilisant une [!DNL Adobe Analytics] mesure d’objectif et [!DNL Adobe Analytics]Riches capacités de création de rapports et d’analyse.

Assurez-vous que vous avez [Mise en oeuvre d’A4T pour une utilisation avec les activités de test A/B et de ciblage d’expérience](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si vous utilisez `analyticsLogging = client_side`, vous devez également transmettre la variable `sessionId` valeur à [!DNL Analytics]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} dans le *SDK Adobe Target* guide.

Pour démarrer :

1. Lors de la création d’une [!UICONTROL Test A/B] , sur la **[!UICONTROL Ciblage]** , sélectionnez l’une des options suivantes comme **[!UICONTROL Méthode d’affectation du trafic]**:

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

[!UICONTROL A4T] pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] nécessite que vous choisissiez une mesure basée sur un événement binaire. Un événement binaire se produit ou ne se produit pas. Les événements binaires incluent un clic, une conversion, une commande, etc. On parle aussi parfois de Bernoulli, de binaire ou d’événement discret.

[!UICONTROL A4T] pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] ne prend pas en charge l’optimisation des mesures continues. Les mesures continues comprennent les recettes, le nombre de produits commandés, la durée de session, le nombre de pages vues dans la session, etc. Ces types de mesures non pris en charge sont également parfois appelés mesures non binaires ou non Bernoulli.

Les types de mesures suivants ne sont pas pris en charge en tant que mesures d’objectif Principal :

* [!DNL Adobe Target] mesures d’engagement et de recettes
* [!DNL Adobe Analytics] mesures d’engagement et de recettes

   Il est possible de sélectionner une [!DNL Analytics] la mesure d’engagement ou de recettes comme mesure d’objectif Principale, car [!DNL Target] ne peuvent pas identifier et exclure toutes les mesures d’engagement et de recettes de [!DNL Analytics]. Sélectionnez uniquement des mesures de conversion binaires ou des événements personnalisés dans [!DNL Analytics].

* [!DNL Adobe Analytics] mesures calculées

## Limites et notes

Certaines limites et notes s’appliquent à la fois à [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités. D’autres limitations et notes s’appliquent à un type d’activité ou à un autre.

### Affectation automatique et ciblage automatique {#both}

* Lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique], vous devez toujours afficher les rapports dans [!DNL Analytics].
* La source de création de rapports ne peut pas être modifiée à partir de [!DNL Analytics] to [!DNL Target] ou vice versa une fois qu’une activité a été activée.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat prévu en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure comme &quot;remplissage de formulaire par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaire&quot; comme mesure d’objectif Principale. [!DNL Target] normalise automatiquement les mesures de conversion par visite pour tenir compte de la répartition inégale du trafic. Il n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.
* Lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique] activités, vous devez toujours afficher les rapports dans [!DNL Analytics].
* La source de création de rapports ne peut pas être modifiée à partir de [!DNL Analytics] to [!DNL Target] ou vice versa une fois qu’une activité a été activée.
* Bien que les mesures calculées ne soient pas prises en charge en tant que mesures d’objectif Principal, il est souvent possible d’obtenir le résultat prévu en sélectionnant plutôt un événement personnalisé comme mesure d’objectif Principal. Par exemple, si vous souhaitez optimiser une mesure comme &quot;remplissage de formulaire par visiteur&quot;, sélectionnez un événement personnalisé correspondant à &quot;remplissage de formulaire&quot; comme mesure d’objectif Principale. [!DNL Target] normalise automatiquement les mesures de conversion par visiteur pour [!UICONTROL Affectation automatique] n’est donc pas nécessaire d’utiliser une mesure calculée pour effectuer la normalisation.

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

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour [!UICONTROL Affectation automatique] activités

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse [!UICONTROL Affectation automatique] activités dans [!DNL Analysis Workspace].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités d’affectation automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} in *Tutorials Adobe Target*.

### Configuration de rapports A4T dans [!DNL Analysis Workspace] pour [!UICONTROL Ciblage automatique] activités

Ce tutoriel vous guide tout au long des modifications recommandées pour l’analyse [!UICONTROL Ciblage automatique] activités dans [!DNL Analysis Workspace].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank} in *Tutorials Adobe Target*.


