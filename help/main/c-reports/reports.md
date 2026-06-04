---
keywords: rapports;bloquer l’adresse ip;bloquer l’adresse ip aux visiteurs;télécharger des rapports;csv;création de rapports
description: Optimisez vos activités en maîtrisant les fonctionnalités de reporting de  [!DNL Adobe Target] pour améliorer la prise de décision et accroître le retour sur investissement.
title: Comment Afficher Les Rapports ?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
TQID: https://experienceleague.adobe.com/aRp-t-Z-Hfu5O01RqfxnKyHHL2suM2ahkteDQJShGQI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 947
ht-degree: 25%

---

# Rapports

Les rapports fournissent des informations sur la progression et les résultats de vos activités [!DNL Adobe Target], ce qui vous aide à prendre des décisions basées sur les données. Les données des rapports peuvent vous aider à décider à quel moment terminer une activité, vous montrer quelle expérience ou offre est gagnante et fournir des informations ou des enseignements dont vous avez besoin pour déterminer les actions suivantes.

## Affichage d’un rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Cliquez sur **[!UICONTROL Activités]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous disposez de nombreuses activités, vous pouvez cliquer sur l’icône de filtre ( ![icône de filtre](/help/main/assets/icons/Filter.svg) ) pour filtrer la liste en sélectionnant des options dans les listes [!UICONTROL Type], [!UICONTROL Statut], [!UICONTROL Source de création de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Metrics Type], [!UICONTROL Méthode de prise de décision] et [!UICONTROL Activity Source].

   Par exemple, vous pouvez sélectionner [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] dans la liste déroulante [!UICONTROL Type] et [!UICONTROL Actif] dans la liste déroulante [!UICONTROL Statut] pour afficher uniquement les activités [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] qui sont à l’état actif.

   L’illustration suivante présente la liste déroulante [!UICONTROL Type] avec deux types sélectionnés : [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience]. Notez que les trois types de tests A/B (Manuel, [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) et [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) sont sélectionnés par défaut. Vous pouvez désélectionner un ou plusieurs types si nécessaire.

   ![Filtre des activités par type](/help/main/c-reports/assets/report-filters-refresh.png)

1. Cliquez sur l’activité souhaitée dans la liste pour afficher sa page [!UICONTROL Aperçu].

1. Cliquez sur l’onglet **[!UICONTROL Rapports]** dans le rail de gauche.

   ![Rapport A/B](/help/main/c-reports/assets/reports-refresh.png)

   Chaque rapport contient une légende qui permet de comprendre le rapport.

   La légende contient les informations suivantes :

   * État de l’activité, notamment la période d’exécution de celle-ci.
   * L’[expérience gagnante prévue](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (si disponible).

   >[!NOTE]
   >
   >Les résultats de l’expérience apparaissent une fois qu’au moins un participant a vu l’expérience.

1. (Facultatif) [Configurez le rapport](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) en cliquant sur l’icône Paramètres des rapports ( ![icône Paramètres des rapports](/help/main/assets/icons/Setting.svg) ).
1. (Facultatif) Cliquez sur l’icône Télécharger les rapports ( ![icône Télécharger les rapports](/help/main/assets/icons/Download.svg) ) pour [télécharger le rapport au format CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) afin de l’analyser dans Excel et d’autres outils.

   Les options disponibles sont les suivantes :

   * [!UICONTROL Exportation du rapport au format CSV]
   * [!UICONTROL Exportation des détails des commandes au format CSV]

1. (Facultatif) Cliquez sur les icônes **[!UICONTROL Vue Tableau]** ( ![icône Vue Tableau](/help/main/assets/icons/Table.svg) ) et **[!UICONTROL Vue Graphique]** ( ![icône Vue Graphique](/help/main/assets/icons/GraphTrend.svg) ) pour basculer entre les formats de création de rapports.

   Selon le type de rapport sélectionné, d&#39;autres vues et rapports peuvent être disponibles :

   | Type de rapport | Affichage |
   | --- | --- |
   | [[!UICONTROL ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Cliquez sur les icônes **[!UICONTROL Segments automatisés]** ( ![Rapport Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) ) ou **[!UICONTROL Attributs importants]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ).<ul><li>Le rapport [[!UICONTROL Segments automatisés] ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) montre comment différents visiteurs répondent différemment aux offres et aux expériences dans votre activité de [!UICONTROL Automated Personalization] ou de [!UICONTROL ciblage automatique]. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres et aux expériences dans l’activité.</li><li>Le rapport [[!UICONTROL Attributs importants] ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) montre comment, dans différentes activités, les différents attributs sont plus (ou moins) importants par rapport à la façon dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Outre les rapports [[!UICONTROL Résumé ]](/help/main/c-reports/personalization-reports/reports-ap.md), vous pouvez cliquer sur les icônes **[!UICONTROL Segments automatisés]** ( ![Rapport Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) ) ou **[!UICONTROL Attributs importants]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ).<ul><li>Le rapport [[!UICONTROL Segments automatisés] ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) montre comment différents visiteurs répondent différemment aux offres et aux expériences dans votre activité de [!UICONTROL Automated Personalization] ou de [!UICONTROL ciblage automatique]. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres et aux expériences dans l’activité.</li><li>Le rapport [[!UICONTROL Attributs importants] ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) montre comment, dans différentes activités, les différents attributs sont plus (ou moins) importants par rapport à la façon dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [[!UICONTROL Test multivarié]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Outre le rapport [[!UICONTROL Performances d’expérience]](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), vous pouvez cliquer sur l’icône [[!UICONTROL Contribution de l’emplacement]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![icône Contribution de l’emplacement](/help/main/assets/icons/LocationContribution.svg) ) pour changer le rapport et afficher la contribution par emplacement. |

## Informations de reporting supplémentaires pour des types d’activité spécifiques {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Outre les informations générales sur les rapports figurant dans cette rubrique et ses sous-rubriques, des informations supplémentaires spécifiques aux différents types d’activité sont disponibles à d’autres endroits de ce guide :

| Type d’activité | Détails |
|--- |--- |
| [[!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/test-ab.md) | Pour comprendre l’effet élévateur et le degré de confiance, ainsi que les différentes approches statistiques utilisées dans [!DNL Target], voir [Planification d’un test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interprétation [!UICONTROL Affectation automatique] rapports](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interprétez les résultats d’une activité A/B [!UICONTROL  Affectation automatique ] en examinant des indicateurs importants, notamment l’effet élévateur et le degré de confiance, dans l’interface utilisateur de [!DNL Target]. |
| [[!UICONTROL Ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Informations sur le rapport [!UICONTROL Résumé] pour les activités AT. Pour plus d’informations, consultez [[!UICONTROL Résumé du ciblage automatique] Rapport](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Informations sur les deux rapports [!UICONTROL Personalization Insights] pour les activités AT et AP : [!UICONTROL Segments automatisés] rapport et [!UICONTROL Attributs importants] rapport. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informations sur les deux rapports [!UICONTROL Automated Personalization Summary] pour les activités AP : rapport [!UICONTROL Activity Level] et rapport [!UICONTROL Offer Level]. Pour plus d’informations, consultez [Rapports de synthèse d’](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Informations sur les deux rapports [!UICONTROL Personalization Insights] pour les activités AT et AP : [!UICONTROL Segments automatisés] rapport et [!UICONTROL Attributs importants] rapport. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Test multivarié]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informations sur les deux rapports relatifs aux activités MVT : rapport [!UICONTROL  Performance de l’expérience ] et rapport [!UICONTROL  Contribution de l’emplacement ]. Pour plus d’informations, consultez les sections [Rapport de performance d’expérience](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) et [Rapport de contribution de l’emplacement](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [[!DNL Adobe Analytics] as the Reporting Source for Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informations sur l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Target] (A4T). A4T vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] création de rapports dans  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Informations sur l’intégration entre [](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics){target=_blank} et [!DNL Target], qui fournit de puissants outils d’analyse et de gain de temps pour votre programme d’optimisation. |

## Bloquer les données de rapport des adresses IP spécifiées

Vous pouvez empêcher le décompte dans les rapports de visiteurs provenant d’adresses IP spécifiées. Cette option s’avère utile, par exemple, pour bloquer les données de rapport de vos visiteurs internes.

[Contactez l’assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour configurer des filtres IP. Ce filtrage ne s’applique pas lorsque vous utilisez [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) comme source de création de rapports.
