---
keywords: recommandations;activité de recommandations;critères;algorithme
description: Découvrez comment sélectionner les critères (règles qui déterminent quels produits ou contenus recommander) à utiliser dans votre activité Recommendations  [!DNL Target] Adobe.
title: Comment sélectionner des critères pour une activité Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 55%

---

# Sélection de critères

Sélectionnez les [critères](/help/main/c-recommendations/c-algorithms/algorithms.md) à utiliser dans votre activité [!DNL Adobe Target Recommendations]. Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.

Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Si vous sélectionnez plusieurs critères, le trafic est réparti uniformément entre les critères sélectionnés. Par exemple, si vous avez sélectionné deux critères et que votre activité est conçue pour afficher le contenu par défaut à 20 % des participants à l’activité, alors 40 % des participants à l’activité verront les recommandations contrôlées par chaque critère. Il n’existe pas d’option permettant de modifier les pourcentages pour chaque critère.

* Pour rechercher un critère existant (par exemple, si de nombreuses cartes de critères s’affichent), saisissez dans le champ de recherche jusqu’à ce que les critères souhaités apparaissent, puis sélectionnez le critère et cliquez sur **[!UICONTROL Done]**.

  Certains critères sont fournis avec [!DNL Recommendations]. Vous et votre équipe pouvez également créer des critères personnalisés.

* Pour créer un nouveau critère, cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**, puis renseignez les informations du nouveau critère. Pour plus d’informations sur la création de nouveaux critères, voir [Création d’un critère](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Pour sélectionner des critères :**

1. Lors de la [création d&#39;une recommandation](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), dans la boîte de dialogue **[!UICONTROL Select Criteria]**, recherchez et sélectionnez un ou plusieurs critères.

   ![Boîte de dialogue Sélection de critères](/help/main/c-recommendations/t-create-recs-activity/assets/filters.png)

   Vous pouvez utiliser le filtre [!UICONTROL Industry Type], le filtre [!UICONTROL Page Type] et la case à cocher [!UICONTROL Compatible] pour filtrer la liste des critères. Ces options vous aident à localiser les critères souhaités.

   * **Type de secteur industriel :** le type de secteur industriel permet de classer les critères [!DNL Recommendations]. Pour modifier votre secteur industriel vertical par défaut, cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** et sélectionnez le paramètre **[!UICONTROL Industry Vertical]** par défaut de votre choix.
   * **Type de page :** le type de page vous aide à classer les recommandations. Il existe également des critères intégrés que vous pouvez choisir pour chaque type de page.
   * **Compatible :** affichez uniquement les critères pour lesquels la page sélectionnée transmet les données requises. Tous les critères ne s’exécuteront pas correctement sur chaque page. La page ou la mbox doit transmettre `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Toutefois, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, décochez la case **[!UICONTROL Compatible]** . Cette option peut être désactivée ou activée dans vos paramètres : **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

1. Cliquez sur **[!UICONTROL Next]** pour afficher la boîte de dialogue [Sélectionner la conception](/help/main/c-recommendations/c-design-overview/design-overview.md).
