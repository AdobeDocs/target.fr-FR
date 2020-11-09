---
keywords: reports;auto-target;auto target;AT;report
description: Informations relatives à l’interprétation du rapport Résumé de la Cible automatique dans Adobe Target.
title: Rapport de synthèse de ciblage automatique
feature: reports
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 57%

---


# ![Rapport de synthèse des Cibles automatiques PREMIUM](/help/assets/premium.png){#auto-target-summary-report}

Information about how to interpret the [!UICONTROL Auto-Target Summary] reports in [!DNL Adobe Target].

>[!NOTE]
>
>Le [!UICONTROL ciblage automatique] fait partie de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une licence [Target Premium](/help/c-intro/intro.md#premium).

Pour afficher les rapports Synthèse [!UICONTROL de la Cible] automatique :

1. Dans la page [!UICONTROL Activités] , cliquez sur l’activité de Cible  automatique de votre choix.

   If you have many activities, you can filter the list by selecting options from the [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Property], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], and [!UICONTROL Activity Source] drop-down lists.

1. Cliquez sur l’onglet [!UICONTROL Rapports] , puis sur l’icône de votre choix :

   * Vue Tableau
   * Vue graphique
   * Segments automatisés
   * Attributs importants

## Vue Tableau

L’illustration suivante présente l’aspect d’un rapport de synthèse type dans la Vue [!UICONTROL de] tableau lors de l’affichage d’un rapport d’activité [!UICONTROL de Cible] automatique :

![Rapport de vue de tableau à Cible automatique](/help/c-reports/assets/at-table-view.png)

Some tips and considerations as you interpret your [!UICONTROL Auto-Target] reports:

* Les différentes lignes du tableau vous aident à comprendre les performances des activités.

   * Les deux premières lignes du tableau affiché sur la page du rapport présentent les résultats d’un test A/B entre les visiteurs qui ont été affectés au groupe témoin (c’est-à-dire des expériences livrées au hasard) et les visiteurs qui ont été affectés à l’algorithme de personnalisation. Ces informations permettent de mesurer les performances de l’algorithme de personnalisation par rapport au contrôle délivré au hasard.
   * Les lignes restantes affichent les résultats au niveau de l’expérience. Pour chaque expérience, il existe une comparaison entre la réponse moyenne des visiteurs qui ont assisté à cette expérience servie par un contrôle au hasard et la réponse moyenne des visiteurs qui ont assisté à l’expérience via l’algorithme de personnalisation.

* L’icône de vérification verte en regard du nom de chaque expérience dans le rapport indique qu’un modèle d’apprentissage automatique personnalisé a été généré pour cette expérience. L’icône d’horloge indique que le trafic diffusé n’a pas été suffisant pour générer le modèle.

   * Étant donné que le modèle est construit par l’expérience, il est possible de voir un modèle avec certaines expériences comportant une coche verte et d’autres avec une icône d’horloge.
   * Dans ce cas, pour augmenter la rapidité de construction des modèles par l’activité pour toutes les expériences, le trafic supplémentaire est envoyé aux expériences associées à des modèles non construits.
   * Il doit exister au moins deux expériences comportant des modèles construits (identifiés par une coche verte) pour que la personnalisation puisse débuter.

* Comparing the conversion rate of experience A with that of experience B is not the right comparison in [!UICONTROL Auto-Target]. La question est de savoir si l’expérience A fonctionne mieux lorsqu’elle est servie de manière intelligente que de manière aléatoire (autrement dit, par rapport au témoin). Les spécialistes marketing doivent également être prudents dans leur interprétation des effets élévateurs émanant des expériences individuelles, car l’algorithme de personnalisation cherche à optimiser la mesure de succès sur l’ensemble de l’activité, et non sur chaque expérience individuelle.
* Les expériences présentant l’effet élévateur le plus élevé peuvent être interprétées comme ayant la différenciation la plus élevée dans la population. Ceci indique que l’algorithme a trouvé un segment qui aime davantage cette expérience particulière.
* Les différentes colonnes du tableau indiquent le nombre de visites, le taux de conversion, l’effet élévateur et le degré de confiance moyens, ainsi que le degré de confiance. Pour plus d’informations, voir [Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Vue graphique

L’illustration suivante présente l’aspect d’un rapport de synthèse typique dans la Vue  graphique lors de l’affichage d’un rapport d’activité [!UICONTROL de Cible] automatique :

![Rapport de vue de graphique à Cible automatique](/help/c-reports/assets/at-graph-view.png)

Comme illustré ci-dessous, vous pouvez utiliser les deux listes déroulantes pour choisir les mesures de votre choix, la méthodologie de comptage, etc. Pour plus d’informations, voir Présentation [des paramètres de](/help/c-reports/c-report-settings/report-settings.md) rapport :

![Rapport de vue de graphique à Cible automatique](/help/c-reports/assets/at-graph-view-2.png)

## Segments automatisés

Cliquez sur l’icône Segments  automatisés. Ce rapport montre comment les différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

![Icône Segments automatisés](/help/c-reports/assets/icon-automated-sements.png)

Pour plus d’informations, voir rapport [Segments](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatisés.

## Attributs importants

Cliquez sur l’icône Attributs  importants. Ce rapport montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

![Icône des attributs importants](/help/c-reports/assets/icon-important-attributes.png)

Pour plus d’informations, voir Rapport [Attributs](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)importants.
