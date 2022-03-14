---
keywords: recommandations;activité de recommandations;critères;algorithme
description: Découvrez comment sélectionner les critères (règles qui déterminent quels produits ou contenus recommander) utiliser dans votre Adobe. [!DNL Target] Activité Recommendations .
title: Comment sélectionner des critères pour une activité Recommendations ?
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 72%

---

# ![PREMIUM](/help/main/assets/premium.png) Sélectionner des critères

Sélectionnez la [critères](/help/main/c-recommendations/c-algorithms/algorithms.md) à utiliser dans votre [!DNL Adobe Target Recommendations] activité. Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.

Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Si vous sélectionnez plusieurs critères, le trafic est réparti uniformément entre les critères sélectionnés. Par exemple, si vous avez sélectionné deux critères et que votre activité est conçue pour afficher le contenu par défaut à 20 % des participants à l’activité, alors 40 % des participants à l’activité verront les recommandations contrôlées par chaque critère. Il n’existe pas d’option permettant de modifier les pourcentages pour chaque critère.

* Pour rechercher un critère existant (par exemple si de nombreuses cartes de critères s’affichent), écrivez dans le champ de recherche jusqu’à ce que les critères souhaités apparaissent, puis sélectionnez le critère et cliquez sur **[!UICONTROL Terminé]**.

   Certains critères sont fournis avec [!DNL Recommendations]. Vous et votre équipe pouvez également créer des critères personnalisés.

* Pour créer un nouveau critère, cliquez sur **[!UICONTROL Création de critères]** > **[!UICONTROL Création de critères]**, puis renseignez les informations du nouveau critère. Pour plus d’informations sur la création de nouveaux critères, voir [Création d’un critère](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Pour sélectionner des critères :**

1. while [création d’une recommandation](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), dans la variable **[!UICONTROL Sélectionner des critères]** , recherchez et sélectionnez un ou plusieurs critères.

   ![Boîte de dialogue Sélection de critères](/help/main/c-recommendations/t-create-recs-activity/assets/filters.png)

   Vous pouvez utiliser le filtre [!UICONTROL Type de secteur], le filtre [!UICONTROL Type de page] et la case à cocher [!UICONTROL Compatible] pour filtrer la liste des critères. Ces options vous aident à localiser les critères souhaités.

   * **Type de secteur industriel :** le type de secteur industriel permet de classer les critères [!DNL Recommendations]. Pour modifier votre secteur industriel vertical par défaut, cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Paramètres]** et sélectionnez la valeur par défaut de votre choix. **[!UICONTROL Secteur industriel vertical]** .
   * **Type de page :** le type de page vous aide à classer les recommandations. Il existe également des critères intégrés que vous pouvez choisir pour chaque type de page.
   * **Compatible :** affichez uniquement les critères pour lesquels la page sélectionnée transmet les données requises. Tous les critères ne s’exécuteront pas correctement sur chaque page. La page ou la mbox doit transmettre `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Néanmoins, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, désactivez la case à cocher **[!UICONTROL Compatible]**. Cette option peut être désactivée ou activée dans vos paramètres : **[!UICONTROL Recommendations]** > **[!UICONTROL Paramètres]**.

1. Cliquez sur **[!UICONTROL Suivant]** pour ouvrir la boîte de dialogue [Sélectionner la conception](/help/main/c-recommendations/c-design-overview/design-overview.md).
