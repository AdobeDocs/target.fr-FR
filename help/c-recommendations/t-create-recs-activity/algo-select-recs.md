---
description: Sélectionnez les critères à utiliser dans votre activité de recommandations.
keywords: recommandations, activité de recommandations, critères
seo-description: Sélectionnez les critères à utiliser dans votre activité Recommandations Adobe Target.
seo-title: Sélection de critères
solution: Target
title: Sélection de critères
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
translation-type: tm+mt
source-git-commit: e8e6dcadf307209abcc712798b714af0a5be2e7e

---


# ![PREMIUM](/help/assets/premium.png) Sélectionner des critères{#select-criteria}

Select the [criteria](/help/c-recommendations/c-algorithms/algorithms.md) to use in your Recommendations activity. Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.

Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Si vous sélectionnez plusieurs critères, le trafic est réparti uniformément entre les critères sélectionnés. Par exemple, si vous avez sélectionné deux critères et que votre activité est conçue pour afficher le contenu par défaut à 20 % des participants à l’activité, alors 40 % des participants à l’activité verront les recommandations contrôlées par chaque critère. Il n’existe pas d’option permettant de modifier les pourcentages pour chaque critère.

* Pour rechercher un critère existant (par exemple si de nombreuses cartes de critères s’affichent), écrivez dans le champ de recherche jusqu’à ce que les critères souhaités apparaissent, puis sélectionnez le critère et cliquez sur **[!UICONTROL Terminé]**.

   Certains critères sont fournis avec [!DNL Recommendations]. Vous et votre équipe pouvez également créer des critères personnalisés.

* To create a new criteria, click **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. Pour plus d’informations sur la création de nouveaux critères, voir [Création d’un critère](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Pour sélectionner des critères :**

1. While [creating a new recommendation](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), in the **[!UICONTROL Criteria]** dialog box, locate and select one or more criteria.

   ![Boîte de dialogue Sélectionner des critères](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   You can use the [!UICONTROL Industry Type] filter, [!UICONTROL Page Type] filter, and [!UICONTROL Compatible] checkbox to filter the list of criteria. Ces options vous aident à localiser les critères souhaités.

   * **Type de secteur industriel :** le type de secteur industriel permet de classer les critères [!DNL Recommendations]. Pour modifier votre secteur industriel vertical par défaut, cliquez sur **[!UICONTROL Paramètres]** et sélectionnez le paramètre **[!UICONTROL Secteur industriel vertical]** par défaut de votre choix.
   * **Type de page :** le type de page vous aide à classer les recommandations. Il existe également des critères intégrés que vous pouvez choisir pour chaque type de page.
   * **Compatible :** affichez uniquement les critères pour lesquels la page sélectionnée transmet les données requises. Tous les critères ne s’exécuteront pas correctement sur chaque page. La page ou la mbox doit transmettre `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Néanmoins, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, désactivez la case à cocher **[!UICONTROL Compatible]**. Cette option peut être désactivée ou activée dans vos [!DNL Target] [!UICONTROL préférences].

1. Click **[!UICONTROL Next]** to display the [Select Design](/help/c-recommendations/c-design-overview/design-overview.md) dialog box.
