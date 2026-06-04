---
keywords: Cible;rapports;paramètres des rapports;mesures multiples;mesures;mesures affichées;mesures masquées
description: Découvrez comment sélectionner plusieurs mesures à afficher dans un rapport à l’aide d’Adobe Target.
title: Comment afficher plusieurs mesures dans un rapport ?
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
TQID: https://experienceleague.adobe.com/mXLlrS1wwfISfxWxq2c-sMDJP1vqxQjbqM-DsLJK9bY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 439
ht-degree: 55%

---

# Affichage de plusieurs mesures dans un rapport

Vous pouvez sélectionner plusieurs mesures à afficher dans un rapport [!DNL Adobe Target].

Tenez compte des informations suivantes lorsque vous utilisez plusieurs mesures dans les rapports :

* La possibilité d’afficher plusieurs mesures est disponible pour les activités [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md), [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) et [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) (XT) uniquement.
* Vous ne pouvez pas ajouter plus de 20 mesures à un rapport pour une activité qui utilise [&#x200B; Analytics for Target &#x200B;](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Vous pouvez ajouter autant de mesures que vous en avez dans votre activité aux rapports pour les activités qui n’utilisent *pas* A4T.
* Vous ne pouvez pas utiliser l’option [Télécharger](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) pour télécharger des rapports au format CSV si vous avez sélectionné plusieurs mesures. Vous devez sélectionner une seule mesure pour activer l’option [!UICONTROL Télécharger].
* Vous ne pouvez pas afficher plusieurs mesures pour les activités créées avant la version [!DNL Target] de juillet 2015 (30 juillet 2015).

**Pour sélectionner plusieurs mesures à afficher dans le rapport, procédez comme suit :**

1. Pour afficher un rapport, cliquez sur **[!UICONTROL Activités]**, sélectionnez une activité dans la liste, puis cliquez sur l’onglet **[!UICONTROL Rapports]**.
1. Cliquez sur la liste déroulante **[!UICONTROL Mesure du rapport]** pour afficher les listes [!UICONTROL Mesures affichées] et [!UICONTROL Mesures masquées].

   Vous pouvez utiliser la zone [!UICONTROL Rechercher] pour trouver rapidement les mesures disponibles à ajouter à la liste [!UICONTROL Mesures affichées].

   Vous pouvez sélectionner plusieurs mesures en mode [!UICONTROL Vue Tableau] et [!UICONTROL Vue graphique] du rapport.

1. Passez le pointeur de la souris sur les mesures souhaitées de la liste [!UICONTROL Mesures masquées], puis cliquez sur **[!UICONTROL Sélectionner]** pour les déplacer vers la liste [!UICONTROL Mesures affichées].

   OU

   Faites glisser les mesures souhaitées de la liste [!UICONTROL Mesures masquées] vers la liste [!UICONTROL Mesures affichées].

   Au moins une mesure doit figurer dans la liste [!UICONTROL Mesures affichées].

   Vous pouvez réorganiser les mesures en les faisant glisser et en les déposant dans l’ordre souhaité dans la liste [!UICONTROL Mesures affichées]. L’ordre sélectionné est reflété dans la [!UICONTROL Vue Tableau] et la [!UICONTROL Vue Graphique]. Pour supprimer une mesure de la liste [!UICONTROL Mesures affichées], placez le pointeur de la souris sur la mesure, puis cliquez sur l’icône **X**.

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.
1. (Conditionnel) Lors de l’affichage du rapport dans la vue [!UICONTROL Tableau], placez le pointeur de la souris sur l’en-tête de colonne d’une mesure pour afficher une flèche bleue. Cliquez sur la flèche pour développer le tableau afin d’afficher l’[!UICONTROL Effet élévateur] et le [!UICONTROL Degré de confiance] pour cette mesure.

   Vous pouvez développer une seule mesure/colonne à la fois. Cliquez de nouveau sur la flèche pour réduire les colonnes.

1. (Conditionnel) Lors de l’affichage du rapport dans la [!UICONTROL vue Graphique], vous pouvez sélectionner des mesures individuelles à afficher dans la liste déroulante.
