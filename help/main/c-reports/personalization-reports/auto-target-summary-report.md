---
keywords: rapports;ciblage automatique;ciblage automatique;AT;rapport
description: Découvrez comment interpréter le rapport de synthèse de ciblage automatique dans Adobe Target. Vous pouvez passer aux rapports Segments automatisés et Attributs importants à partir de ce rapport.
title: Comment utiliser le rapport de synthèse de ciblage automatique ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 52%

---

# Rapport de synthèse de ciblage automatique

Informations sur la manière d’interpréter les rapports [!UICONTROL Auto-Target Summary] dans [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] est disponible dans le cadre de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une [licence Target Premium](/help/main/c-intro/intro.md#premium).

Pour afficher les rapports [!UICONTROL Auto-Target Summary] :

1. Sur la page [!UICONTROL Activities], cliquez sur l’activité [!UICONTROL Auto-Target] souhaitée.

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Property], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] et [!UICONTROL Activity Source].

1. Cliquez sur l’onglet [!UICONTROL Reports] , puis sur l’icône de votre choix :

   * Vue Tableau
   * Vue graphique
   * Segments automatisés
   * Attributs importants

## Vue Tableau

L’illustration suivante montre à quoi ressemble un rapport de synthèse type dans [!UICONTROL Table View] lors de l’affichage d’un rapport d’activité [!UICONTROL Auto-Target] :

![Rapport d’affichage de table de ciblage automatique](/help/main/c-reports/assets/at-table-view.png)

Quelques conseils et remarques lors de l’interprétation de vos rapports [!UICONTROL Auto-Target] :

* Les différentes lignes du tableau vous aident à comprendre les performances de l’activité.

   * Les deux premières lignes du tableau affiché sur la page du rapport présentent les résultats d’un test A/B entre les visiteurs qui ont été affectés au groupe témoin (c’est-à-dire des expériences livrées au hasard) et les visiteurs qui ont été affectés à l’algorithme de personnalisation. Ces informations permettent de mesurer les performances de l’algorithme de personnalisation par rapport au contrôle délivré au hasard.
   * Les lignes restantes affichent les résultats au niveau de l’expérience. Pour chaque expérience, il existe une comparaison entre la réponse moyenne des visiteurs qui ont assisté à cette expérience servie par un contrôle au hasard et la réponse moyenne des visiteurs qui ont assisté à l’expérience via l’algorithme de personnalisation.

* L’icône de vérification verte en regard du nom de chaque expérience dans le rapport indique qu’un modèle de machine learning personnalisé a été généré pour cette expérience. L’icône d’horloge indique que le trafic diffusé n’a pas été suffisant pour générer le modèle.

   * Étant donné que le modèle est construit par l’expérience, il est possible de voir un modèle avec certaines expériences comportant une coche verte et d’autres avec une icône d’horloge.
   * Dans ce cas, pour augmenter la rapidité de construction des modèles par l’activité pour toutes les expériences, le trafic supplémentaire est envoyé aux expériences associées à des modèles non construits.
   * Il doit exister au moins deux expériences comportant des modèles construits (identifiés par une coche verte) pour que la personnalisation puisse débuter.

* Comparer le taux de conversion de l’expérience A à celui de l’expérience B n’est pas la bonne comparaison dans [!UICONTROL Auto-Target]. La question est de savoir si l’expérience A fonctionne mieux lorsqu’elle est servie de manière intelligente que de manière aléatoire (autrement dit, par rapport au témoin). Les spécialistes marketing doivent également être prudents dans leur interprétation des effets élévateurs émanant des expériences individuelles, car l’algorithme de personnalisation cherche à optimiser la mesure de succès sur l’ensemble de l’activité, et non sur chaque expérience individuelle.
* Les expériences présentant l’effet élévateur le plus élevé peuvent être interprétées comme ayant la différenciation la plus élevée dans la population. Ceci indique que l’algorithme a trouvé un segment qui aime davantage cette expérience particulière.
* Les différentes colonnes du tableau indiquent le nombre de visites, le taux de conversion, l’effet élévateur moyen, le degré de confiance et le degré de confiance. Pour plus d’informations, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Vue graphique

L’illustration suivante montre à quoi ressemble un rapport de synthèse type dans [!UICONTROL Graph View] lors de l’affichage d’un rapport d’activité [!UICONTROL Auto-Target] :

![Rapport de vue de graphique de ciblage automatique](/help/main/c-reports/assets/at-graph-view.png)

Comme illustré ci-dessous, vous pouvez utiliser les deux listes déroulantes pour choisir les mesures souhaitées, la méthodologie de calcul, etc. Pour plus d’informations, consultez la [présentation des paramètres de rapport](/help/main/c-reports/c-report-settings/report-settings.md) :

![Rapport de vue de graphique de ciblage automatique](/help/main/c-reports/assets/at-graph-view-2.png)

## Segments automatisés

Cliquez sur l’icône [!UICONTROL Automated Segments] . Ce rapport montre comment différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

![Icône Segments automatisés](/help/main/c-reports/assets/icon-automated-sements.png)

Pour plus d’informations, voir [Rapport Segments automatisés](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Attributs importants

Cliquez sur l’icône [!UICONTROL Important Attributes] . Ce rapport montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

![Icône Attributs importants](/help/main/c-reports/assets/icon-important-attributes.png)

Pour plus d’informations, voir [Rapport Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
