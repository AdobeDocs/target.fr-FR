---
keywords: recommendations;recommendations activity;criteria;algorithm
description: Sélectionnez les critères à utiliser dans votre activité Adobe Target Recommandations.
title: Sélection de critères
feature: recs creation
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 80%

---


# ![PREMIUM](/help/assets/premium.png) Sélectionner des critères{#select-criteria}

Select the [criteria](/help/c-recommendations/c-algorithms/algorithms.md) to use in your [!DNL Adobe Target Recommendations] activity. Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.

Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Si vous sélectionnez plusieurs critères, le trafic est réparti uniformément entre les critères sélectionnés. Par exemple, si vous avez sélectionné deux critères et que votre activité est conçue pour afficher le contenu par défaut à 20 % des participants à l’activité, alors 40 % des participants à l’activité verront les recommandations contrôlées par chaque critère. Il n’existe pas d’option permettant de modifier les pourcentages pour chaque critère.

* Pour rechercher un critère existant (par exemple si de nombreuses cartes de critères s’affichent), écrivez dans le champ de recherche jusqu’à ce que les critères souhaités apparaissent, puis sélectionnez le critère et cliquez sur **[!UICONTROL Terminé]**.

   Certains critères sont fournis avec [!DNL Recommendations]. Vous et votre équipe pouvez également créer des critères personnalisés.

* To create a new criteria, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. Pour plus d’informations sur la création de nouveaux critères, voir [Création d’un critère](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Pour sélectionner des critères :**

1. While [creating a new recommendation](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), in the **[!UICONTROL Select Criteria]** dialog box, locate and select one or more criteria.

   ![Boîte de dialogue Sélection de critères](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   Vous pouvez utiliser le filtre [!UICONTROL Type de secteur], le filtre [!UICONTROL Type de page] et la case à cocher [!UICONTROL Compatible] pour filtrer la liste des critères. Ces options vous aident à localiser les critères souhaités.

   * **Type de secteur industriel :** le type de secteur industriel permet de classer les critères [!DNL Recommendations]. To change your default industry vertical, click **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** and select your desired default **[!UICONTROL Industry Vertical]** setting.
   * **Type de page :** le type de page vous aide à classer les recommandations. Il existe également des critères intégrés que vous pouvez choisir pour chaque type de page.
   * **Compatible :** affichez uniquement les critères pour lesquels la page sélectionnée transmet les données requises. Tous les critères ne s’exécuteront pas correctement sur chaque page. La page ou la mbox doit transmettre `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Néanmoins, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, désactivez la case à cocher **[!UICONTROL Compatible]**. This option can be disabled or enabled in your settings: **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

1. Cliquez sur **[!UICONTROL Suivant]** pour ouvrir la boîte de dialogue [Sélectionner la conception](/help/c-recommendations/c-design-overview/design-overview.md).
