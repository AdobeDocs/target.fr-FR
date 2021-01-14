---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: Les rapports fournissent des informations sur les performances de vos activités Adobe Target.
title: Rapports
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 66%

---


# Rapports{#reports}

Les rapports fournissent des informations sur les progrès et les résultats de vos activités [!DNL Adobe Target] qui vous aident à prendre des décisions en fonction de vos données. Les données des rapports peuvent vous aider à décider quand terminer une activité, à vous montrer quelle expérience d’offre est gagnante et à fournir des informations ou des informations sur lesquelles vous devez déterminer les actions suivantes.

## Afficher un rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Cliquez sur **[!UICONTROL Activités]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous avez beaucoup d’activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL État], [!UICONTROL Source de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesure] et [!UICONTROL Source d’activité].

   Par exemple, vous pouvez sélectionner [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] dans la liste déroulante [!UICONTROL Type], puis [!UICONTROL Actif] dans la liste déroulante [!UICONTROL État] afin d’afficher uniquement les activités de tests A/B et de ciblage d’expérience à l’état actif.

   L’illustration suivante présente la liste déroulante [!UICONTROL Type] avec deux types sélectionnés :  [!UICONTROL Test A/B ] et  [!UICONTROL ciblage d’expérience]. Notez que les trois types de tests A/B (Manuel, [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) et [Ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md)) sont sélectionnés par défaut. Vous pouvez désélectionner un ou plusieurs types si nécessaire.

   ![Filtre des activités par type](/help/c-reports/assets/report_filters-new.png)

1. Cliquez sur l’onglet **[!UICONTROL Rapports]**.

   Chaque rapport contient une légende qui permet de comprendre le rapport.

   ![Légende du rapport](/help/c-reports/assets/report_menu_bar-new.png)

   La légende contient les informations suivantes :

   * État de l’activité, notamment la période d’exécution de celle-ci.
   * Expérience gagnante [estimée](/help/c-activities/automated-traffic-allocation/determine-winner.md) (si disponible).

   >[!NOTE]
   >
   >Les résultats de l’expérience apparaissent une fois qu’au moins un participant a vu l’expérience.

1. (Facultatif) [Configurez le rapport](/help/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA), suivant vos besoins.
1. (Facultatif) [Téléchargez le rapport au format CSV](/help/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) en vue d’une analyse dans Excel et d’autres outils.

   Les options disponibles sont les suivantes :

   * [!UICONTROL Exportation du rapport au format CSV]
   * [!UICONTROL Exportation des détails des commandes au format CSV]

1. (Facultatif) Cliquez sur les icônes **[!UICONTROL Vue Tableau]** et **[!UICONTROL Vue graphique]** pour passer d’un format de rapport à un autre.

   ![Icônes de vue de tableau et de graphique](/help/c-reports/assets/table-and-graph-icons.png)

   Selon le type de rapport sélectionné, d’autres vues et rapports peuvent être disponibles :

   | Type de rapport | Affichage |
   | --- | --- |
   | [Ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) | Cliquez sur les icônes **[!UICONTROL Segments automatisés]** ou **[!UICONTROL Attributs importants]**.<ul><li>Le rapport [Segments automatisés](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) montre comment différents visiteurs répondent différemment aux offres/expériences de votre activité de personnalisation automatisée/contrôle. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.</li><li>Le rapport [Attributs importants](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la façon dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Outre les [rapports de synthèse Automated Personalization](/help/c-reports/reports-ap.md), vous pouvez cliquer sur les icônes **[!UICONTROL Segments automatisés]** ou **[!UICONTROL Attributs importants]**.<ul><li>Le rapport [Segments automatisés](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) montre comment différents visiteurs répondent différemment aux offres/expériences de votre activité de personnalisation automatisée/contrôle. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.</li><li>Le rapport [Attributs importants](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la façon dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.</li></ul> |
   | [Test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Outre le rapport [Performance de l’expérience](/help/c-reports/experience-performance-report.md), vous pouvez cliquer sur l’icône [Contribution de l’emplacement](/help/c-reports/location-contribution-report.md) pour changer le rapport et afficher la contribution par emplacement. |

## Informations rapports supplémentaires pour des types d&#39;activité spécifiques {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Outre les informations générales sur les rapports figurant dans cette rubrique et ses sous-rubriques, des informations supplémentaires spécifiques aux différents types d’activité sont disponibles à d’autres endroits de ce guide :

| Type d’activité | Détails |
|--- |--- |
| [Test A/B](/help/c-activities/t-test-ab/test-ab.md) | Pour comprendre l’effet élévateur et le degré de confiance, ainsi que les différentes approches statistiques utilisées dans [!DNL Target], voir [Planification d’un test A/B](/help/c-activities/t-test-ab/sample-size-determination.md). |
| [Interprétation des rapports d’affectation automatique](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Interprétez les résultats d&#39;une activité A/B [!UICONTROL Affectation automatique] en examinant des indicateurs importants, y compris l&#39;effet élévateur et la confiance, dans l&#39;interface utilisateur [!DNL Target]. |
| [Ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Informations sur le rapport de [!UICONTROL synthèse] pour les activités AT. Pour plus d’informations, voir [Rapport de synthèse de ciblage automatique](/help/c-reports/auto-target-summary-report.md).<br>Informations sur les deux rapports [!UICONTROL Informations sur la personnalisation] pour les activités AT et AP : rapport [!UICONTROL Segments automatisés] et rapport [!UICONTROL Attributs importants]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)  (AP) | Informations sur les deux rapports [!UICONTROL Synthèse de la personnalisation automatisée] pour les activités AP : rapport [!UICONTROL Niveau d’activité] et rapport [!UICONTROL Niveau d’offre]. Pour plus d’informations, voir [Rapports Synthèse de la personnalisation automatisée](/help/c-reports/reports-ap.md).<br>Informations sur les deux rapports [!UICONTROL Informations sur la personnalisation] pour les activités AT et AP : rapport [!UICONTROL Segments automatisés] et rapport [!UICONTROL Attributs importants]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informations sur les deux rapports des activités MVT : rapport [!UICONTROL Performance de l’expérience] et rapport [!UICONTROL Contribution des emplacements]. Pour plus d’informations, consultez les sections [Rapport Performance de l’expérience](/help/c-reports/experience-performance-report.md) (MVT) et [Rapport Contribution des emplacements](/help/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics comme source de création de rapports pour Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informations sur l’utilisation d’[!DNL Adobe Analytics] comme source des rapports pour [!DNL Target]. A4T vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](/help/c-reports/analytics-for-target-a4t-reporting.md). |

## Bloquer les données de rapports à partir d&#39;adresses IP spécifiées

Vous pouvez empêcher le décompte dans les rapports de visiteurs provenant d’adresses IP spécifiées. Cela s’avère utile, par exemple, pour bloquer les données de rapports de vos visiteurs internes.

[Contactez le service à la clientèle pour configurer les filtres d’adresses IP. ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Ce filtrage ne s’applique pas lorsque vous utilisez [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) comme source de création des rapports.
