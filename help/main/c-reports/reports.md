---
keywords: rapports;bloquer l’adresse ip;bloquer l’adresse ip aux visiteurs;télécharger des rapports;csv;création de rapports
description: Optimisez vos activités en maîtrisant les fonctionnalités de reporting de  [!DNL Adobe Target] pour améliorer la prise de décision et accroître le retour sur investissement.
title: Comment Afficher Les Rapports ?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: bd65cb9339dbe4b79d26c314cfb81d1fc7226fd2
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 26%

---

# Rapports

Les rapports fournissent des informations sur la progression et les résultats de vos activités [!DNL Adobe Target], ce qui vous aide à prendre des décisions basées sur les données. Les données des rapports peuvent vous aider à décider à quel moment terminer une activité, vous montrer quelle expérience ou offre est gagnante et fournir des informations ou des enseignements dont vous avez besoin pour déterminer les actions suivantes.

## Affichage d’un rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Cliquez sur **[!UICONTROL Activities]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous disposez de nombreuses activités, vous pouvez cliquer sur l’icône Filtrer ( ![icône Filtrer](/help/main/assets/icons/Filter.svg) ) pour filtrer la liste en sélectionnant des options dans les listes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Method] et [!UICONTROL Activity Source].

   Par exemple, vous pouvez sélectionner [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] dans la liste déroulante [!UICONTROL Type] et [!UICONTROL Live] dans la liste déroulante [!UICONTROL Status] pour n’afficher que les activités [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] dont l’état est actif.

   L’illustration suivante présente la liste déroulante [!UICONTROL Type] avec deux types sélectionnés : [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting]. Notez que les trois types de tests A/B (Manuel, [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) et [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) sont sélectionnés par défaut. Vous pouvez désélectionner un ou plusieurs types si nécessaire.

   ![Filtre des activités par type](/help/main/c-reports/assets/report-filters-refresh.png)

1. Cliquez sur l’activité souhaitée dans la liste pour afficher sa page [!UICONTROL Overview].

1. Cliquez sur l’onglet **[!UICONTROL Reports]** dans le rail de gauche.

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

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Facultatif) Cliquez sur les icônes **[!UICONTROL Table View]** ( ![icône Vue Tableau](/help/main/assets/icons/Table.svg) ) et **[!UICONTROL Graph View]** ( ![icône Vue Graphique](/help/main/assets/icons/GraphTrend.svg) ) pour basculer entre les formats de création de rapports.

   Selon le type de rapport sélectionné, d&#39;autres vues et rapports peuvent être disponibles :

   | Type de rapport | Affichage |
   | --- | --- |
   | [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Cliquez sur les icônes **[!UICONTROL Automated Segments]** ( ![Rapport Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) ) ou **[!UICONTROL Important Attributes]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ).<ul><li>Le rapport [[!UICONTROL Automated Segments] montre ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) les différentes réponses des visiteurs aux offres et aux expériences dans votre activité de [!UICONTROL Automated Personalization] ou de [!UICONTROL Auto-Target]. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres et aux expériences dans l’activité.</li><li>Le rapport [[!UICONTROL Important Attributes] montre ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) manière dont, dans différentes activités, les différents attributs sont plus (ou moins) importants pour la manière dont le modèle décide d’être personnalisé. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Outre les rapports [[!UICONTROL Automated Personalization Summary] , vous pouvez ](/help/main/c-reports/personalization-reports/reports-ap.md) cliquer sur les icônes **[!UICONTROL Automated Segments]** ( ![Rapport Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) ) ou **[!UICONTROL Important Attributes]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ).<ul><li>Le rapport [[!UICONTROL Automated Segments] montre ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) les différentes réponses des visiteurs aux offres et aux expériences dans votre activité de [!UICONTROL Automated Personalization] ou de [!UICONTROL Auto-Target]. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres et aux expériences dans l’activité.</li><li>Le rapport [[!UICONTROL Important Attributes] montre ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) manière dont, dans différentes activités, les différents attributs sont plus (ou moins) importants pour la manière dont le modèle décide d’être personnalisé. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (VMT) | En plus du rapport [[!UICONTROL Experience Performance]](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) vous pouvez cliquer sur l’icône [[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![Icône Contribution de l’emplacement](/help/main/assets/icons/LocationContribution.svg) ) pour changer le rapport et afficher la contribution par emplacement. |

## Informations de reporting supplémentaires pour des types d’activité spécifiques {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Outre les informations générales sur les rapports figurant dans cette rubrique et ses sous-rubriques, des informations supplémentaires spécifiques aux différents types d’activité sont disponibles à d’autres endroits de ce guide :

| Type d’activité | Détails |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | Pour comprendre l’effet élévateur et le degré de confiance, ainsi que les différentes approches statistiques utilisées dans [!DNL Target], voir [Planification d’un test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interprétation [!UICONTROL Auto-Allocate] rapports](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interprétez les résultats d’une activité A/B [!UICONTROL Auto-Allocate] en examinant des indicateurs importants, y compris l’effet élévateur et le degré de confiance, dans l’interface utilisateur de [!DNL Target]. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Informations sur le rapport [!UICONTROL Summary] pour les activités AT. Pour plus d’informations, consultez [[!UICONTROL Auto-Target Summary] rapport](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Informations sur les deux rapports [!UICONTROL Personalization Insights] pour les activités AT et AP : rapport [!UICONTROL Automated Segments] et rapport [!UICONTROL Important Attributes]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informations sur les deux rapports [!UICONTROL Automated Personalization Summary] pour les activités AP : rapport [!UICONTROL Activity Level] et rapport [!UICONTROL Offer Level]. Pour plus d’informations, voir [Rapports Synthèse de la personnalisation automatisée](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Informations sur les deux rapports [!UICONTROL Personalization Insights] pour les activités AT et AP : rapport [!UICONTROL Automated Segments] et rapport [!UICONTROL Important Attributes]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (VMT) | Informations sur les deux états pour les activités MVT : [!UICONTROL Experience Performance] et [!UICONTROL Location Contribution]. Pour plus d’informations, consultez les sections [Rapport de performance d’expérience](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) et [Rapport de contribution de l’emplacement](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [[!DNL Adobe Analytics] as the Reporting Source for Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informations sur l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Target] (A4T). A4T vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] création de rapports dans  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Informations sur l’intégration entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics){target=_blank} et [!DNL Target], qui fournit de puissants outils d’analyse et de gain de temps pour votre programme d’optimisation. |

## Bloquer les données de rapport des adresses IP spécifiées

Vous pouvez empêcher le décompte dans les rapports de visiteurs provenant d’adresses IP spécifiées. Cette option s’avère utile, par exemple, pour bloquer les données de rapport de vos visiteurs internes.

[Contactez l’assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour configurer des filtres IP. Ce filtrage ne s’applique pas lorsque vous utilisez [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) comme source de création de rapports.
