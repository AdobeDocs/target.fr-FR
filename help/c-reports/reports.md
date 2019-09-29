---
description: Les rapports fournissent des informations sur les performances de vos activités.
keywords: rapports;bloquer une adresse ip;bloquer un visiteur provenant d’une adresse ip;télécharger des rapports;csv
seo-description: Les rapports fournissent des informations sur les performances de vos activités
seo-title: Rapports
solution: Target
subtopic: Test multivarié
title: Rapports
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Rapports{#reports}

Les rapports fournissent des informations sur la progression et les résultats de vos activités, afin de vous aider à prendre des décisions basées sur vos données. Les données des rapports peuvent vous aider à décider à quel moment terminer un test, vous montrer quelle expérience d’offre est gagnante et fournir des informations ou des leçons dont vous avez besoin pour déterminer les actions suivantes.

>[!NOTE]
>
>Vous pouvez empêcher le décompte dans les rapports de visiteurs provenant d’adresses IP spécifiées. Contactez le service à la clientèle pour configurer les filtres d’adresses IP. Ce filtrage ne s’applique pas lorsque vous utilisez [Analytics for Target](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) comme source de création des rapports.

## Transmission d’informations pour des types d’activités spécifiques {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Outre les informations générales sur les rapports figurant dans cette rubrique et ses sous-rubriques, des informations supplémentaires spécifiques aux différents types d’activité sont disponibles à d’autres endroits de ce guide :

| Type d’activité | Détails |
|--- |--- |
| [Test A/B](/help/c-activities/t-test-ab/test-ab.md) | Pour comprendre l’effet élévateur et le degré de confiance, ainsi que les différentes approches statistiques utilisées dans [!DNL Target], voir [Planification d’un test A/B](/help/c-activities/t-test-ab/sample-size-determination.md). |
| [Ciblage automatique](/help/c-activities/auto-target-to-optimize.md) (AT) | Informations sur le rapport de [!UICONTROL synthèse] pour les activités AT. Pour plus d’informations, voir [Rapport de synthèse de ciblage automatique](/help/c-reports/auto-target-summary-report.md).<br>Informations sur les deux rapports [!UICONTROL Informations sur la personnalisation] pour les activités AT et AP : rapport [!UICONTROL Segments automatisés] et rapport [!UICONTROL Attributs importants]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informations sur les deux rapports [!UICONTROL Synthèse de la personnalisation automatisée] pour les activités AP : rapport [!UICONTROL Niveau d’activité] et rapport [!UICONTROL Niveau d’offre]. Pour plus d’informations, voir [Rapports Synthèse de la personnalisation automatisée](/help/c-reports/reports-ap.md).<br>Informations sur les deux rapports [!UICONTROL Informations sur la personnalisation] pour les activités AT et AP : rapport [!UICONTROL Segments automatisés] et rapport [!UICONTROL Attributs importants]. Pour plus d’informations, voir [Rapports Informations sur la personnalisation](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informations sur les deux rapports des activités MVT : rapport [!UICONTROL Performance de l’expérience] et rapport [!UICONTROL Contribution des emplacements]. Pour plus d’informations, consultez les sections [Rapport Performance de l’expérience](/help/c-reports/experience-performance-report.md) (MVT) et [Rapport Contribution des emplacements](/help/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics comme source de création de rapports pour Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informations sur l’utilisation d’[!DNL Adobe Analytics] comme source des rapports pour [!DNL Target]. A4T vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target]. Pour plus d’informations, voir [Rapports Analytics for Target (A4T)](/help/c-reports/analytics-for-target-a4t-reporting.md). |

## Affichage d’un rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Cliquez sur **[!UICONTROL Activités]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous avez beaucoup d’activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL État], [!UICONTROL Source de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesure] et [!UICONTROL Source d’activité].

   Par exemple, vous pouvez sélectionner [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] dans la liste déroulante [!UICONTROL Type], puis [!UICONTROL Actif] dans la liste déroulante [!UICONTROL État] afin d’afficher uniquement les activités de tests A/B et de ciblage d’expérience à l’état actif.

   L’illustration suivante présente la liste déroulante [!UICONTROL Type] avec deux types sélectionnés : Tests A/B et ciblage d’expérience. Notez que les trois types de tests A/B (Manuel, [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) et [Ciblage automatique](/help/c-activities/auto-target-to-optimize.md)) sont sélectionnés par défaut. Vous pouvez désélectionner un ou plusieurs types si nécessaire.

   ![Filtre des activités par type](/help/c-reports/assets/report_filters-new.png)

1. Cliquez sur l’onglet **[!UICONTROL Rapports].**

   Chaque rapport contient une légende qui permet de comprendre le rapport.

   ![Légende du rapport](/help/c-reports/assets/report_menu_bar-new.png)

   La légende contient les informations suivantes :

   * État de l’activité, notamment la période d’exécution de celle-ci.
   * Expérience gagnante estimée (le cas échéant).
   >[!NOTE]
   >
   >Les résultats de l’expérience apparaissent une fois qu’au moins un participant a vu l’expérience.

1. (Facultatif) [Configurez le rapport](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA), suivant vos besoins.
1. (Facultatif) [Téléchargez le rapport au format CSV](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) en vue d’une analyse dans Excel et d’autres outils.

   Les options disponibles sont les suivantes :

   * [!UICONTROL Exportation du rapport au format CSV]
   * [!UICONTROL Exportation des détails des commandes au format CSV]

1. (Facultatif) Cliquez sur les icônes **[!UICONTROL Vue Tableau]** et **[!UICONTROL Vue graphique]** pour passer d’un format de rapport à un autre.

   Pour les tests multivariés uniquement, cliquez sur l’icône **[!UICONTROL Contribution des emplacements]** ( ![Icône contribution des emplacements](assets/icon_location_contribution.png) ) pour que le rapport affiche la contribution par emplacement.
