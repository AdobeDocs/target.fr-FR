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


# ![Rapport ](/help/assets/premium.png) PREMIUMAuto-Cible Résumé{#auto-target-summary-report}

Informations sur la façon d’interpréter les rapports [!UICONTROL Résumé de la Cible automatique] dans [!DNL Adobe Target].

>[!NOTE]
>
>Le [!UICONTROL ciblage automatique] fait partie de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une licence [Target Premium](/help/c-intro/intro.md#premium).

Pour afficher les rapports [!UICONTROL Résumé de la Cible automatique] :

1. Dans la page [!UICONTROL Activités], cliquez sur l&#39;activité [!UICONTROL Cible automatique] de votre choix.

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant des options dans [!UICONTROL Type], [!UICONTROL État], [!UICONTROL Propriété], [!UICONTROL Source du Rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesures] et [!UICONTROL listes déroulantes Source de l&#39;Activité].

1. Cliquez sur l&#39;onglet [!UICONTROL Rapports], puis sur l&#39;icône de votre choix :

   * Vue Tableau
   * Vue graphique
   * Segments automatisés
   * Attributs importants

## Vue Tableau

L’illustration suivante présente l’aspect d’un rapport de synthèse type dans [!UICONTROL Vue de tableau] lors de l’affichage d’un rapport d’activité d’[!UICONTROL Cible automatique] :

![Rapport de vue de tableau à Cible automatique](/help/c-reports/assets/at-table-view.png)

Voici quelques conseils et considérations à prendre en compte lorsque vous interprétez vos rapports [!UICONTROL Cible automatique] :

* Les différentes lignes du tableau vous aident à comprendre les performances des activités.

   * Les deux premières lignes du tableau affiché sur la page du rapport présentent les résultats d’un test A/B entre les visiteurs qui ont été affectés au groupe témoin (c’est-à-dire des expériences livrées au hasard) et les visiteurs qui ont été affectés à l’algorithme de personnalisation. Ces informations permettent de mesurer les performances de l’algorithme de personnalisation par rapport au contrôle délivré au hasard.
   * Les lignes restantes affichent les résultats au niveau de l’expérience. Pour chaque expérience, il existe une comparaison entre la réponse moyenne des visiteurs qui ont assisté à cette expérience servie par un contrôle au hasard et la réponse moyenne des visiteurs qui ont assisté à l’expérience via l’algorithme de personnalisation.

* L’icône de vérification verte en regard du nom de chaque expérience dans le rapport indique qu’un modèle d’apprentissage automatique personnalisé a été généré pour cette expérience. L’icône d’horloge indique que le trafic diffusé n’a pas été suffisant pour générer le modèle.

   * Étant donné que le modèle est construit par l’expérience, il est possible de voir un modèle avec certaines expériences comportant une coche verte et d’autres avec une icône d’horloge.
   * Dans ce cas, pour augmenter la rapidité de construction des modèles par l’activité pour toutes les expériences, le trafic supplémentaire est envoyé aux expériences associées à des modèles non construits.
   * Il doit exister au moins deux expériences comportant des modèles construits (identifiés par une coche verte) pour que la personnalisation puisse débuter.

* Comparer le taux de conversion de l’expérience A à celui de l’expérience B n’est pas la bonne comparaison dans [!UICONTROL Cible automatique]. La question est de savoir si l’expérience A fonctionne mieux lorsqu’elle est servie de manière intelligente que de manière aléatoire (autrement dit, par rapport au témoin). Les spécialistes marketing doivent également être prudents dans leur interprétation des effets élévateurs émanant des expériences individuelles, car l’algorithme de personnalisation cherche à optimiser la mesure de succès sur l’ensemble de l’activité, et non sur chaque expérience individuelle.
* Les expériences présentant l’effet élévateur le plus élevé peuvent être interprétées comme ayant la différenciation la plus élevée dans la population. Ceci indique que l’algorithme a trouvé un segment qui aime davantage cette expérience particulière.
* Les différentes colonnes du tableau indiquent le nombre de visites, le taux de conversion, l’effet élévateur et le degré de confiance moyens, ainsi que le degré de confiance. Pour plus d’informations, voir [Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Vue graphique

L’illustration suivante présente l’aspect d’un rapport de synthèse type dans [!UICONTROL Vue graphique] lors de l’affichage d’un rapport d’activité d’[!UICONTROL Cible automatique] :

![Rapport de vue de graphique à Cible automatique](/help/c-reports/assets/at-graph-view.png)

Comme illustré ci-dessous, vous pouvez utiliser les deux listes déroulantes pour choisir les mesures de votre choix, la méthodologie de comptage, etc. Voir [Présentation des paramètres du rapport](/help/c-reports/c-report-settings/report-settings.md) pour plus d’informations.

![Rapport de vue de graphique à Cible automatique](/help/c-reports/assets/at-graph-view-2.png)

## Segments automatisés

Cliquez sur l&#39;icône [!UICONTROL Segments automatisés]. Ce rapport montre comment les différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

![Icône Segments automatisés](/help/c-reports/assets/icon-automated-sements.png)

Pour plus d’informations, voir [rapport Segments automatisés](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Attributs importants

Cliquez sur l&#39;icône [!UICONTROL Attributs importants]. Ce rapport montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

![Icône des attributs importants](/help/c-reports/assets/icon-important-attributes.png)

Pour plus d’informations, voir [Rapport Attributs importants](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md).
