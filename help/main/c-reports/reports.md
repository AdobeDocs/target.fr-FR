---
keywords: rapports;bloquer une adresse ip;bloquer un visiteur à partir d’une adresse ip;télécharger des rapports;csv;création de rapports
description: Découvrez comment utiliser les fonctionnalités de reporting dans Adobe [!DNL Target] pour examiner les performances de vos activités. Prenez de meilleures décisions en fonction de vos données pour augmenter le retour sur investissement.
title: Comment Afficher Les Rapports ?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: a7a03cba466fbe7abfc8eb1f80292e1a2de7fe2d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 41%

---

# Rapports

Les rapports fournissent des informations sur la progression et les résultats de votre [!DNL Adobe Target] activités qui vous aident à prendre des décisions en fonction de vos données. Les données des rapports peuvent vous aider à décider quand terminer une activité, vous montrer quelle expérience d’offre est gagnante et fournir des informations ou des enseignements dont vous avez besoin pour déterminer les actions suivantes.

## Afficher un rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Cliquez sur **[!UICONTROL Activities]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant des options dans la [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], et [!UICONTROL Activity Source] listes déroulantes.

   Par exemple, vous pouvez sélectionner [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] de la [!UICONTROL Type] Liste déroulante et [!UICONTROL Live] de la [!UICONTROL Status] Liste déroulante pour afficher uniquement les tests A/B et les activités de ciblage d’expérience à l’état actif.

   L’illustration suivante présente la variable [!UICONTROL Type] liste déroulante avec deux types sélectionnés : [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting]. Notez que les trois types de tests A/B (Manuel, [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) et [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) sont sélectionnés par défaut. Vous pouvez désélectionner un ou plusieurs types si nécessaire.

   ![Filtre des activités par type](/help/main/c-reports/assets/report_filters-new.png)

1. Cliquez sur le bouton **[!UICONTROL Reports]** .

   Chaque rapport contient une légende qui permet de comprendre le rapport.

   ![Légende du rapport](/help/main/c-reports/assets/report_menu_bar-new.png)

   La légende contient les informations suivantes :

   * État de l’activité, notamment la période d’exécution de celle-ci.
   * La variable [expérience gagnante estimée](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (le cas échéant).

   >[!NOTE]
   >
   >Les résultats de l’expérience apparaissent une fois qu’au moins un participant a vu l’expérience.

1. (Facultatif) [Configurez le rapport](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA), suivant vos besoins.
1. (Facultatif) [Téléchargez le rapport au format CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) en vue d’une analyse dans Excel et d’autres outils.

   Les options disponibles sont les suivantes :

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Facultatif) Cliquez sur le **[!UICONTROL Table View]** et **[!UICONTROL Graph View]** pour basculer entre les formats de rapports.

   ![Icônes des vues Tableau et Graphique](/help/main/c-reports/assets/table-and-graph-icons.png)

   Selon le type de rapport sélectionné, d’autres vues et rapports peuvent être disponibles :

   | Type de rapport | Affichage |
   | --- | --- |
   | [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Cliquez sur le bouton **[!UICONTROL Automated Segments]** ou **[!UICONTROL Important Attributes]** icônes.<ul><li>La variable [Rapport Segments automatisés](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) indique comment différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.</li><li>La variable [Rapport Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) indique comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | En plus de la variable [Rapports de synthèse Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md), vous pouvez cliquer sur le bouton **[!UICONTROL Automated Segments]** ou **[!UICONTROL Important Attributes]** icônes.<ul><li>La variable [Rapport Segments automatisés](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) indique comment différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.</li><li>La variable [Rapport Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | En plus de la variable [Rapport Performance de l’expérience](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), vous pouvez cliquer sur le bouton [Contribution des emplacements](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) pour que le rapport affiche la contribution par emplacement. |

## Informations supplémentaires sur les rapports pour des types d’activité spécifiques {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Outre les informations générales sur les rapports figurant dans cette rubrique et ses sous-rubriques, des informations supplémentaires spécifiques aux différents types d’activité sont disponibles à d’autres endroits de ce guide :

| Type d’activité | Détails |
|--- |--- |
| [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Pour comprendre l’effet élévateur et le degré de confiance, ainsi que les différentes approches statistiques utilisées dans [!DNL Target], voir [Planification d’un test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interprétation des rapports d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interprétation des résultats d’une [!UICONTROL Auto-Allocate] l’activité A/B en examinant les indicateurs importants, y compris l’effet élévateur et le degré de confiance, dans la variable [!DNL Target] Interface utilisateur. |
| [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Informations sur la variable [!UICONTROL Summary] rapport pour les activités AT. Pour plus d’informations, voir [Rapport de synthèse de ciblage automatique](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Informations sur les deux [!UICONTROL Personalization Insights] rapports pour les activités AT et AP : [!UICONTROL Automated Segments] rapport et [!UICONTROL Important Attributes] rapport. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informations sur les deux [!UICONTROL Automated Personalization Summary] rapports pour les activités AP : [!UICONTROL Activity Level] rapport et [!UICONTROL Offer Level] rapport. Pour plus d’informations, voir [Rapports Synthèse de la personnalisation automatisée](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Informations sur les deux [!UICONTROL Personalization Insights] rapports pour les activités AT et AP : [!UICONTROL Automated Segments] rapport et [!UICONTROL Important Attributes] rapport. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informations sur les deux rapports pour les activités MVT : [!UICONTROL Experience Performance] rapport et [!UICONTROL Location Contribution] rapport. Pour plus d’informations, consultez les sections [Rapport Performance de l’expérience](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) et [Rapport Contribution des emplacements](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics comme source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informations sur l’utilisation d’[!DNL Adobe Analytics] comme source des rapports pour [!DNL Target]. A4T vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] création de rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Informations sur l’intégration entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} et [!DNL Target] qui fournit de puissants outils d’analyse et d’économie de temps pour votre programme d’optimisation. |

## Bloquer les données de création de rapports à partir d’adresses IP spécifiées

Vous pouvez empêcher le décompte dans les rapports de visiteurs provenant d’adresses IP spécifiées. Cela s’avère utile, par exemple, pour bloquer les données de création de rapports de vos visiteurs internes.

[Contacter le service à la clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour configurer des filtres d’adresses IP. Ce filtrage ne s’applique pas lorsque vous utilisez [Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) comme source des rapports.
