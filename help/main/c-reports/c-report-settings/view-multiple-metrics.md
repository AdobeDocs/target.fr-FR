---
keywords: Target;rapports;paramètres de rapport;mesures multiples;mesures;mesures affichées;mesures masquées
description: Découvrez comment sélectionner plusieurs mesures à afficher dans un rapport avec Adobe Target.
title: Comment afficher plusieurs mesures dans un rapport ?
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 12%

---

# Affichage de plusieurs mesures dans un rapport

Vous pouvez sélectionner plusieurs mesures à afficher dans un rapport [!DNL Adobe Target].

Tenez compte des informations suivantes lorsque vous utilisez plusieurs mesures dans les rapports :

* La possibilité d’afficher plusieurs mesures est disponible uniquement pour les activités [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md), [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) et [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) (XT).
* Vous ne pouvez pas ajouter plus de 20 mesures à un rapport pour une activité qui utilise [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Vous pouvez ajouter autant de mesures que vous en avez dans votre activité aux rapports pour les activités qui n’utilisent *pas* A4T.
* Vous ne pouvez pas utiliser l’ [option de téléchargement](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) pour télécharger des rapports au format CSV si vous avez sélectionné plusieurs mesures. Vous ne devez sélectionner qu’une seule mesure pour activer l’option [!UICONTROL Download].
* Vous ne pouvez pas afficher plusieurs mesures pour les activités créées avant la version de juillet 2015 [!DNL Target] (30 juillet 2015).

**Pour sélectionner plusieurs mesures à afficher dans le rapport, procédez comme suit :**

1. Pour afficher un rapport, cliquez sur **[!UICONTROL Activities]**, sélectionnez l’activité souhaitée dans la liste, puis cliquez sur l’onglet **[!UICONTROL Reports]** .
1. Cliquez sur la liste déroulante **[!UICONTROL Report Metric]** pour afficher les listes [!UICONTROL Shown Metrics] et [!UICONTROL Hidden Metrics].

   ![image multiple_metrics](assets/multiple_metrics.png)

   Vous pouvez utiliser la zone [!UICONTROL Search] pour rechercher rapidement les mesures disponibles à ajouter à la liste [!UICONTROL Shown Metrics].

   Notez que vous pouvez sélectionner plusieurs mesures dans les modes [!UICONTROL Table View] et [!UICONTROL Graph View] du rapport.

1. Pointez votre souris sur les mesures souhaitées de la liste [!UICONTROL Hidden Metrics], puis cliquez sur **[!UICONTROL Select]** pour les déplacer vers la liste [!UICONTROL Shown Metrics].

   Ou

   Faites glisser les mesures souhaitées de la liste [!UICONTROL Hidden Metrics] vers la liste [!UICONTROL Shown Metrics].

   Il doit y avoir au moins une mesure dans la liste [!UICONTROL Shown Metrics].

   Vous pouvez réorganiser les mesures en les faisant glisser et en les déposant dans l’ordre souhaité dans la liste [!UICONTROL Shown Metrics]. L’ordre sélectionné sera reflété dans les [!UICONTROL Table View] et [!UICONTROL Graph View]. Pour supprimer une mesure de la liste [!UICONTROL Shown Metrics], placez le pointeur de la souris sur la mesure, puis cliquez sur l’icône **X** .

1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.
1. (Conditionnel) Lors de l’affichage du rapport dans [!UICONTROL Table View], placez le pointeur de la souris sur l’en-tête de colonne d’une mesure pour afficher une flèche bleue. Cliquez sur la flèche pour développer le tableau afin d’afficher les [!UICONTROL Lift] et [!UICONTROL Confidence] pour cette mesure.

   ![image multiple_metrics_table](assets/multiple_metrics_table.png)

   Vous pouvez développer une seule mesure/colonne à la fois. Cliquez de nouveau sur la flèche pour réduire les colonnes.

1. (Conditionnel) Lors de l’affichage du rapport dans la vue Graphique, vous pouvez sélectionner des mesures individuelles à afficher dans la liste déroulante :

   ![image multiple_metrics_graph](assets/multiple_metrics_graph.png)
