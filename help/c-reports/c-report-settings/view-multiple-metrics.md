---
keywords: Target;reports;report settings;multiple metrics;metrics
description: Sélectionnez plusieurs mesures à vue dans un rapport à l’aide de Adobe Target.
title: Vue de plusieurs mesures dans un rapport à l’aide de Adobe Target
feature: report settings
uuid: f3ea7313-0f98-4b58-88aa-e2438c06e739
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 70%

---


# Affichage de plusieurs mesures dans un rapport{#view-multiple-metrics-in-a-report}

Sélectionnez plusieurs mesures à afficher dans un rapport.

Tenez compte des informations suivantes lorsque vous utilisez plusieurs mesures dans les rapports :

* The ability to view multiple metrics is available for [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT) activities only.
* You cannot add more than 20 metrics to a report for an activity that uses [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). You can add as many metrics as you have in your activity to reports for activities that do *not* use A4T.
* Vous ne pouvez pas utiliser l’option [](/help/c-reports/downloading-data-in-csv-file.md)Télécharger pour télécharger des rapports au format CSV si vous avez sélectionné plusieurs mesures. Vous devez sélectionner une seule mesure pour activer l’option [!UICONTROL Télécharger].
* Vous ne pouvez pas afficher plusieurs mesures pour les activités créées avant la version de Target de juillet 2015 (30 juillet 2015).

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

   Vous pouvez réorganiser les mesures en les faisant glisser et en les déposant dans l’ordre souhaité dans la liste [!UICONTROL Mesures affichées]. L’ordre sélectionné sera reflété dans la vue Tableau et la vue graphique. Pour supprimer une mesure de la liste [!UICONTROL Mesures affichées], placez le pointeur de la souris sur la mesure, puis cliquez sur l’icône **X**.

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.
1. (Conditionnel) Lors de l’affichage du rapport dans la Vue de tableau, placez le pointeur de la souris sur l’en-tête de colonne d’une mesure pour afficher une flèche bleue. Cliquez sur la flèche pour développer le tableau afin d’afficher l’[!UICONTROL Effet élévateur] et le [!UICONTROL Degré de confiance] pour cette mesure.

   ![](assets/multiple_metrics_table.png)

   Vous pouvez développer une seule mesure/colonne à la fois. Cliquez de nouveau sur la flèche pour réduire les colonnes.

1. (Conditionnel) Lors de l’affichage du rapport dans la Vue Graphique, vous pouvez sélectionner des mesures individuelles à afficher dans la liste déroulante :

   ![](assets/multiple_metrics_graph.png)

