---
keywords: rapports;bloquer une adresse ip;bloquer un visiteur à partir d’une adresse ip;télécharger des rapports;csv;création de rapports
description: Optimisez vos activités en maîtrisant les fonctionnalités de création de rapports de  [!DNL Adobe Target] afin d'améliorer la prise de décision et le retour sur investissement.
title: Comment Afficher Les Rapports ?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: 5c963e97dae11326396a5c1c5e32d19f4d463c74
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 32%

---

# Rapports

Les rapports fournissent des informations sur la progression et les résultats de vos activités [!DNL Adobe Target] qui vous aident à prendre des décisions basées sur des données. Les données des rapports peuvent vous aider à décider quand terminer une activité, vous montrer quelle expérience ou offre est gagnante et fournir des informations ou des enseignements dont vous avez besoin pour déterminer les actions suivantes.

## Afficher un rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Cliquez sur **[!UICONTROL Activities]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Method] et [!UICONTROL Activity Source].

   Par exemple, vous pouvez sélectionner [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] dans la liste déroulante [!UICONTROL Type] et [!UICONTROL Live] dans la liste déroulante [!UICONTROL Status] pour afficher uniquement les activités [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] à l’état actif.

   L’illustration suivante présente la liste déroulante [!UICONTROL Type] avec deux types sélectionnés : [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting]. Notez que les trois types de tests A/B (Manuel, [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) et [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) sont sélectionnés par défaut. Vous pouvez désélectionner un ou plusieurs types si nécessaire.

   ![Filtre des activités par type](/help/main/c-reports/assets/report_filters-new.png)

1. Sélectionnez l’activité souhaitée dans la liste.

1. Cliquez sur l’onglet **[!UICONTROL Reports]** dans le rail de gauche.

   Chaque rapport contient une légende qui permet de comprendre le rapport.

   La légende contient les informations suivantes :

   * État de l’activité, notamment la période d’exécution de celle-ci.
   * [Expérience gagnante estimée](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (si disponible).

   >[!NOTE]
   >
   >Les résultats de l’expérience apparaissent une fois qu’au moins un participant a vu l’expérience.

1. (Facultatif) [Configurez le rapport](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA), suivant vos besoins.
1. (Facultatif) [Téléchargez le rapport au format CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) en vue d’une analyse dans Excel et d’autres outils.

   Les options disponibles sont les suivantes :

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Facultatif) Cliquez sur les icônes **[!UICONTROL Table View]** et **[!UICONTROL Graph View]** pour passer d’un format de rapport à un autre.

   ![ Icônes de vue Tableau et Graphique ](/help/main/c-reports/assets/table-and-graph-icons.png)

   Selon le type de rapport sélectionné, d’autres vues et rapports peuvent être disponibles :

   | Type de rapport | Affichage |
   | --- | --- |
   | [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Cliquez sur les icônes **[!UICONTROL Automated Segments]** ou **[!UICONTROL Important Attributes]** .<ul><li>Le rapport [[!UICONTROL Automated Segments] ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) montre comment différents visiteurs répondent différemment aux offres et expériences de votre activité [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target]. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres et expériences de l’activité.</li><li>Le [[!UICONTROL Important Attributes] rapport ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Outre les [[!UICONTROL Automated Personalization Summary] rapports](/help/main/c-reports/personalization-reports/reports-ap.md), vous pouvez cliquer sur les icônes **[!UICONTROL Automated Segments]** ou **[!UICONTROL Important Attributes]** .<ul><li>Le rapport [[!UICONTROL Automated Segments] ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) montre comment différents visiteurs répondent différemment aux offres et expériences de votre activité [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target]. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation [!DNL Target] ont répondu aux offres et expériences de l’activité.</li><li>Le [[!UICONTROL Important Attributes] rapport ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Outre le rapport [[!UICONTROL Experience Performance] ](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), vous pouvez cliquer sur l’icône [[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) pour que le rapport affiche la contribution par emplacement. |

## Informations supplémentaires sur les rapports pour des types d’activité spécifiques {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Outre les informations générales sur les rapports figurant dans cette rubrique et ses sous-rubriques, des informations supplémentaires spécifiques aux différents types d’activité sont disponibles à d’autres endroits de ce guide :

| Type d’activité | Détails |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | Pour comprendre l’effet élévateur et le degré de confiance, ainsi que les différentes approches statistiques utilisées dans [!DNL Target], voir [Planification d’un test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpréter les [!UICONTROL Auto-Allocate] rapports](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interprétez les résultats d’une activité A/B [!UICONTROL Auto-Allocate] en examinant des indicateurs importants, y compris l’effet élévateur et le degré de confiance, dans l’interface utilisateur de [!DNL Target]. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Informations sur le rapport [!UICONTROL Summary] pour les activités AT. Pour plus d’informations, voir [[!UICONTROL Auto-Target Summary] Rapport](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Informations sur les deux rapports [!UICONTROL Personalization Insights] pour les activités AT et AP : rapport [!UICONTROL Automated Segments] et rapport [!UICONTROL Important Attributes]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informations sur les deux rapports [!UICONTROL Automated Personalization Summary] pour les activités AP : rapport [!UICONTROL Activity Level] et rapport [!UICONTROL Offer Level]. Pour plus d’informations, voir [Rapports Synthèse de la personnalisation automatisée](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Informations sur les deux rapports [!UICONTROL Personalization Insights] pour les activités AT et AP : rapport [!UICONTROL Automated Segments] et rapport [!UICONTROL Important Attributes]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informations sur les deux rapports pour les activités MVT : rapport [!UICONTROL Experience Performance] et rapport [!UICONTROL Location Contribution]. Pour plus d’informations, consultez les sections [Rapport Performance de l’expérience](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) et [Rapport Contribution des emplacements](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [[!DNL Adobe Analytics]  comme Source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informations sur l’utilisation de [!DNL Adobe Analytics] comme source des rapports pour [!DNL Target] (A4T). A4T vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] création de rapports dans  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Informations sur l’intégration entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics){target=_blank} et [!DNL Target] qui fournit de puissantes analyses et des outils d’économie de temps pour votre programme d’optimisation. |

## Bloquer les données de création de rapports à partir d’adresses IP spécifiées

Vous pouvez empêcher le décompte dans les rapports de visiteurs provenant d’adresses IP spécifiées. Cela s’avère utile, par exemple, pour bloquer les données de création de rapports de vos visiteurs internes.

[Contactez le service à la clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour configurer des filtres IP. Ce filtrage ne s’applique pas lorsque vous utilisez [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) comme source des rapports.
