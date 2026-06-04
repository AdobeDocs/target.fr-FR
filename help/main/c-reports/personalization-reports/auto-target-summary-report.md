---
keywords: rapports;ciblage automatique;ciblage automatique;AT;rapport
description: Découvrez comment interpréter le rapport de synthèse de ciblage automatique dans Adobe Target. Vous pouvez passer aux rapports Segments automatisés et Attributs importants à partir de ce rapport.
title: Comment utiliser le rapport de synthèse de ciblage automatique ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
TQID: https://experienceleague.adobe.com/de9ST0undYRSL-BMmwEhvbU7PsfHgYieNAWY-qsQ-Z8
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 666
ht-degree: 35%

---

# [!UICONTROL Rapport de synthèse de ciblage automatique]

Informations sur la façon d’interpréter les rapports [!UICONTROL Résumé de ciblage automatique] dans [!DNL Adobe Target].

>[!NOTE]
>
>Le [!UICONTROL ciblage automatique] est disponible dans le cadre de la solution [!DNL Target Premium]. Il n’est pas inclus dans [!DNL Target Standard] sans licence [Target Premium](/help/main/c-intro/intro.md#premium).

Pour afficher les rapports [!UICONTROL Résumé du ciblage automatique] :

1. Sur la page [!UICONTROL Activités], cliquez sur l’activité [!UICONTROL Ciblage automatique] souhaitée.

   Si vous avez de nombreuses activités, cliquez sur l’icône Filtrer ( ![icône Filtrer](/help/main/assets/icons/Filter.svg) ) pour filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Statut], [!UICONTROL Source de création de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesures] et [!UICONTROL Activity Source].

1. Cliquez sur l&#39;onglet **[!UICONTROL Rapports]**, puis sur l&#39;icône souhaitée :

   * **[!UICONTROL Vue Tableau]** ( ![icône Vue Tableau](/help/main/assets/icons/Table.svg) )
   * **[!UICONTROL Vue Graphique]** ( ![icône Vue Graphique](/help/main/assets/icons/GraphTrend.svg) )
   * **[!UICONTROL Segments automatisés]** ( ![Rapport Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) )
   * [!UICONTROL Attributs importants]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) )

## Vue Tableau

Quelques conseils et considérations lors de l’interprétation de vos rapports de [!UICONTROL ciblage automatique] :

* Les différentes lignes du tableau vous aident à comprendre les performances des activités.

   * Les deux premières lignes du tableau de la page de création de rapports affichent les résultats d’un test A/B entre les visiteurs affectés au contrôle (c’est-à-dire les expériences diffusées de manière aléatoire) et les visiteurs affectés à l’algorithme de personnalisation. Ces informations peuvent être utilisées pour mesurer la façon dont l’algorithme de personnalisation a été exécuté par rapport au contrôle diffusé de manière aléatoire.
   * Les lignes restantes affichent les résultats au niveau de l’expérience. Pour chaque expérience, il existe une comparaison entre la réponse moyenne des visiteurs qui ont assisté à cette expérience servie par un contrôle au hasard et la réponse moyenne des visiteurs qui ont assisté à l’expérience via l’algorithme de personnalisation.

* L’icône de vérification verte en regard du nom de chaque expérience dans le rapport indique qu’un modèle de machine learning personnalisé a été généré pour cette expérience. L’icône d’horloge indique que le trafic diffusé n’a pas été suffisant pour générer le modèle.

   * Étant donné que le modèle est construit par l’expérience, il est possible de voir un modèle avec certaines expériences comportant une coche verte et d’autres avec une icône d’horloge.
   * Dans ce cas, pour augmenter la rapidité de construction des modèles par l’activité pour toutes les expériences, le trafic supplémentaire est envoyé aux expériences associées à des modèles non construits.
   * Pour que la personnalisation commence, il doit y avoir au moins deux expériences avec des modèles créés (coche verte).

* Comparer le taux de conversion de l’expérience A à celui de l’expérience B n’est pas la bonne comparaison dans le [!UICONTROL &#x200B; Ciblage automatique &#x200B;]. La question est de savoir si l’expérience A fonctionne mieux lorsqu’elle est servie de manière intelligente que de manière aléatoire (autrement dit, par rapport au témoin). Les spécialistes marketing doivent également être prudents dans leur interprétation des effets élévateurs émanant des expériences individuelles, car l’algorithme de personnalisation cherche à optimiser la mesure de succès sur l’ensemble de l’activité, et non sur chaque expérience individuelle.
* Les expériences présentant l’effet élévateur le plus élevé peuvent être interprétées comme ayant la différenciation la plus élevée dans la population. En d’autres termes, l’algorithme a trouvé un segment qui aime le plus cette expérience particulière.
* Les différentes colonnes du tableau indiquent le nombre de visites, le taux de conversion, l’effet élévateur moyen et le niveau de confiance, ainsi que le degré de confiance. Pour plus d’informations, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Vue graphique

Utilisez les deux listes déroulantes pour choisir les mesures souhaitées, la méthodologie de comptage, etc. Voir [Présentation des paramètres du rapport](/help/main/c-reports/c-report-settings/report-settings.md) pour plus d’informations :

## Segments automatisés

Ce rapport montre comment différents visiteurs réagissent différemment aux offres/expériences dans votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres/expériences dans l’activité.

Pour plus d’informations, voir le rapport [&#x200B; Segments automatisés &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Attributs importants

Ce rapport montre comment, dans différentes activités, les différents attributs sont plus (ou moins) importants pour la manière dont le modèle décide d’effectuer la personnalisation. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

Pour plus d’informations, consultez le rapport [&#x200B; Attributs importants &#x200B;](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
