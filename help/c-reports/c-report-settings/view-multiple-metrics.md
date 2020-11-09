---
keywords: Target;reports;report settings;multiple metrics;metrics;shown metrics;hidden metrics
description: Sélectionnez plusieurs mesures à vue dans un rapport à l’aide de Adobe Target.
title: Vue de plusieurs mesures dans un rapport à l’aide de Adobe Target
feature: report settings
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 61%

---


# Affichage de plusieurs mesures dans un rapport{#view-multiple-metrics-in-a-report}

Vous pouvez sélectionner plusieurs mesures à vue dans un [!DNL Adobe Target] rapport.

Tenez compte des informations suivantes lorsque vous utilisez plusieurs mesures dans les rapports :

* The ability to view multiple metrics is available for [A/B Test](/help/c-activities/t-test-ab/test-ab.md), [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md), and [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT) activities only.
* You cannot add more than 20 metrics to a report for an activity that uses [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). You can add as many metrics as you have in your activity to reports for activities that do *not* use A4T.
* Vous ne pouvez pas utiliser l’option [](/help/c-reports/downloading-data-in-csv-file.md)Télécharger pour télécharger des rapports au format CSV si vous avez sélectionné plusieurs mesures. Vous devez sélectionner une seule mesure pour activer l’option [!UICONTROL Télécharger].
* You cannot view multiple metrics for activities created before the July 2015 [!DNL Target] release (July 30, 2015).

**Pour sélectionner plusieurs mesures à afficher dans le rapport, procédez comme suit :**

1. Pour afficher un rapport, cliquez sur **[!UICONTROL Activités]**, sélectionnez une activité dans la liste, puis cliquez sur l’onglet **[!UICONTROL Rapports.]**
1. Cliquez sur la liste déroulante **[!UICONTROL Mesure du rapport]** pour afficher les listes [!UICONTROL Mesures affichées] et [!UICONTROL Mesures masquées].

   ![](assets/multiple_metrics.png)

   Vous pouvez utiliser la zone [!UICONTROL Rechercher] pour trouver rapidement les mesures disponibles à ajouter à la liste [!UICONTROL Mesures affichées].

   Vous pouvez sélectionner plusieurs mesures en mode [!UICONTROL Vue Tableau] et [!UICONTROL Vue graphique] du rapport.

1. Passez le pointeur de la souris sur les mesures souhaitées de la liste [!UICONTROL Mesures masquées], puis cliquez sur **[!UICONTROL Sélectionner]** pour les déplacer vers la liste [!UICONTROL Mesures affichées].

   OU

   Faites glisser les mesures souhaitées de la liste [!UICONTROL Mesures masquées] vers la liste [!UICONTROL Mesures affichées].

   Au moins une mesure doit figurer dans la liste [!UICONTROL Mesures affichées].

   Vous pouvez réorganiser les mesures en les faisant glisser et en les déposant dans l’ordre souhaité dans la liste [!UICONTROL Mesures affichées]. The selected order will be reflected in the [!UICONTROL Table View] and [!UICONTROL Graph View]. Pour supprimer une mesure de la liste [!UICONTROL Mesures affichées], placez le pointeur de la souris sur la mesure, puis cliquez sur l’icône **X**.

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.
1. (Conditional) While viewing the report in the [!UICONTROL Table View], hover your mouse pointer on any metric&#39;s column header to display a blue arrow. Cliquez sur la flèche pour développer le tableau afin d’afficher l’[!UICONTROL Effet élévateur] et le [!UICONTROL Degré de confiance] pour cette mesure.

   ![](assets/multiple_metrics_table.png)

   Vous pouvez développer une seule mesure/colonne à la fois. Cliquez de nouveau sur la flèche pour réduire les colonnes.

1. (Conditionnel) Lors de l’affichage du rapport dans la Vue Graphique, vous pouvez sélectionner des mesures individuelles à afficher dans la liste déroulante :

   ![](assets/multiple_metrics_graph.png)

