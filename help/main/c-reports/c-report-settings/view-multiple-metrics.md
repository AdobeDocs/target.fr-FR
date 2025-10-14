---
keywords: Cible;rapports;paramètres des rapports;mesures multiples;mesures;mesures affichées;mesures masquées
description: Découvrez comment sélectionner plusieurs mesures à afficher dans un rapport à l’aide d’Adobe Target.
title: Comment afficher plusieurs mesures dans un rapport ?
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 12%

---

# Affichage de plusieurs mesures dans un rapport

Vous pouvez sélectionner plusieurs mesures à afficher dans un rapport [!DNL Adobe Target].

Tenez compte des informations suivantes lorsque vous utilisez plusieurs mesures dans les rapports :

* La possibilité d’afficher plusieurs mesures est disponible pour les activités [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md), [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) et [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) (XT) uniquement.
* Vous ne pouvez pas ajouter plus de 20 mesures à un rapport pour une activité qui utilise [&#x200B; Analytics for Target &#x200B;](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Vous pouvez ajouter autant de mesures que vous en avez dans votre activité aux rapports pour les activités qui n’utilisent *pas* A4T.
* Vous ne pouvez pas utiliser l’option [Télécharger](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) pour télécharger des rapports au format CSV si vous avez sélectionné plusieurs mesures. Vous ne devez sélectionner qu’une seule mesure pour activer l’option [!UICONTROL Download].
* Vous ne pouvez pas afficher plusieurs mesures pour les activités créées avant la version [!DNL Target] de juillet 2015 (30 juillet 2015).

**Pour sélectionner plusieurs mesures à afficher dans le rapport, procédez comme suit :**

1. Pour afficher un rapport, cliquez sur **[!UICONTROL Activities]**, puis sur l&#39;activité souhaitée dans la liste et enfin sur l&#39;onglet **[!UICONTROL Reports]** .
1. Cliquez sur la liste déroulante **[!UICONTROL Report Metric]** pour afficher les listes [!UICONTROL Shown Metrics] et [!UICONTROL Hidden Metrics].

   Vous pouvez utiliser la zone de [!UICONTROL Search] pour rechercher rapidement les mesures disponibles à ajouter à la liste [!UICONTROL Shown Metrics].

   Notez que vous pouvez sélectionner plusieurs mesures à la fois dans les modes [!UICONTROL Table View] et [!UICONTROL Graph View] du rapport.

1. Placez le pointeur de la souris sur les mesures souhaitées dans la liste [!UICONTROL Hidden Metrics], puis cliquez sur **[!UICONTROL Select]** pour les déplacer vers la liste [!UICONTROL Shown Metrics].

   Ou

   Effectuez un glisser-déposer des mesures souhaitées de la liste [!UICONTROL Hidden Metrics] vers la liste [!UICONTROL Shown Metrics].

   La liste de [!UICONTROL Shown Metrics] doit contenir au moins une mesure.

   Vous pouvez réorganiser les mesures en les faisant glisser et en les déposant dans l’ordre souhaité dans la liste de [!UICONTROL Shown Metrics]. L’ordre sélectionné sera reflété dans les [!UICONTROL Table View] et les [!UICONTROL Graph View]. Pour supprimer une mesure de la liste [!UICONTROL Shown Metrics], placez le pointeur de la souris sur la mesure, puis cliquez sur l’icône **X**.

1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.
1. (Conditionnel) Lors de l’affichage du rapport dans la [!UICONTROL Table View], placez le pointeur de la souris sur l’en-tête de colonne d’une mesure pour afficher une flèche bleue. Cliquez sur la flèche pour développer le tableau afin d’afficher les [!UICONTROL Lift] et les [!UICONTROL Confidence] de cette mesure.

   Vous pouvez développer une seule mesure/colonne à la fois. Cliquez de nouveau sur la flèche pour réduire les colonnes.

1. (Conditionnel) Lors de l’affichage du rapport dans la [!UICONTROL Graph View], vous pouvez sélectionner des mesures individuelles à afficher dans la liste déroulante.
