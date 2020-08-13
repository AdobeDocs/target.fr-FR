---
keywords: reports;auto-target;auto target;AT
description: Informations sur la manière d’interpréter le rapport de synthèse de ciblage automatique.
title: Rapport de synthèse de ciblage automatique
feature: reports
subtopic: Multivariate Test
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 65%

---


# Rapport de synthèse de ciblage automatique{#auto-target-summary-report}

Informations sur la façon d’interpréter les rapports de synthèse de la Cible automatique.

Pour afficher les rapports Synthèse des Cibles automatiques :

1. Dans la page [!UICONTROL Activités] , cliquez sur l’activité d’Cible automatique de votre choix.

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes Type, État, Propriété, Source du Rapports, Compositeur d’expérience, Type de mesure et Source de l’Activité.

1. Cliquez sur l’onglet [!UICONTROL Rapports].

## Vue Tableau

L’illustration suivante présente l’aspect d’un rapport de synthèse type dans la &quot;vue de tableau&quot; lors de l’utilisation de la Cible automatique :

![Rapport de vue de tableau à Cible automatique](/help/c-reports/assets/at-table-view.png)

Quelques conseils et considérations lorsque vous interprétez vos rapports de ciblage automatique :

* Les différentes lignes du tableau permettent de mieux comprendre les performances de l’activité.

   * Les deux premières lignes du tableau affiché sur la page du rapport présentent les résultats d’un test A/B entre les visiteurs qui ont été affectés au groupe témoin (c’est-à-dire des expériences livrées au hasard) et les visiteurs qui ont été affectés à l’algorithme de personnalisation. Ces informations permettent de mesurer les performances de l’algorithme de personnalisation par rapport au contrôle délivré au hasard.
   * Les lignes restantes affichent les résultats au niveau de l’expérience. Pour chaque expérience, il existe une comparaison entre la réponse moyenne des visiteurs qui ont assisté à cette expérience servie par un contrôle au hasard et la réponse moyenne des visiteurs qui ont assisté à l’expérience via l’algorithme de personnalisation.

* L’icône de vérification verte en regard du nom de chaque expérience dans le rapport indique qu’un modèle d’apprentissage automatique personnalisé a été généré pour cette expérience. L’icône d’horloge indique que le trafic diffusé n’a pas été suffisant pour générer le modèle.

   * Étant donné que le modèle est construit par l’expérience, il est possible de voir un modèle avec certaines expériences comportant une coche verte et d’autres avec une icône d’horloge.
   * Dans ce cas, pour augmenter la rapidité de construction des modèles par l’activité pour toutes les expériences, le trafic supplémentaire est envoyé aux expériences associées à des modèles non construits.
   * Il doit exister au moins deux expériences comportant des modèles construits (identifiés par une coche verte) pour que la personnalisation puisse débuter.

* Le fait de comparer le taux de conversion de l’expérience A à celui de l’expérience B ne génère pas la comparaison adéquate dans le ciblage automatique. La question est de savoir si l’expérience A fonctionne mieux lorsqu’elle est servie de manière intelligente que de manière aléatoire (autrement dit, par rapport au témoin). Les spécialistes marketing doivent également être prudents dans leur interprétation des effets élévateurs émanant des expériences individuelles, car l’algorithme de personnalisation cherche à optimiser la mesure de succès sur l’ensemble de l’activité, et non sur chaque expérience individuelle.
* Les expériences présentant l’effet élévateur le plus élevé peuvent être interprétées comme ayant la différenciation la plus élevée dans la population. Ceci indique que l’algorithme a trouvé un segment qui aime davantage cette expérience particulière.
* Les différentes colonnes du tableau indiquent le nombre de visites, le taux de conversion, l’effet élévateur et le degré de confiance moyens, ainsi que le degré de confiance. Pour plus d’informations, voir [Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Vue graphique

L’illustration suivante présente l’aspect d’un rapport de synthèse standard dans la &quot;vue graphique&quot; lors de l’utilisation de la Cible automatique :

![Rapport de vue de graphique à Cible automatique](/help/c-reports/assets/at-graph-view.png)

Comme illustré ci-dessous, vous pouvez utiliser les deux listes déroulantes pour choisir les mesures de votre choix, la méthodologie de comptage, etc. Pour plus d’informations, voir Présentation [des paramètres de](/help/c-reports/c-report-settings/report-settings.md) rapport :

![Rapport de vue de graphique à Cible automatique](/help/c-reports/assets/at-graph-view-2.png)

## Segments automatisés

Cliquez sur l’icône Segments automatisés. Ce rapport montre comment les différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

![Icône Segments automatisés](/help/c-reports/assets/icon-automated-sements.png)

Pour plus d’informations, voir rapport [Segments](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatisés.

## Attributs importants

Cliquez sur l’icône Attributs importants. Ce rapport montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

![Icône des attributs importants](/help/c-reports/assets/icon-important-attributes.png)

Pour plus d’informations, voir Rapport [Attributs](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)importants.
