---
keywords: recommandations;activité de recommandations;critères;algorithme
description: Découvrez comment sélectionner les critères (règles qui déterminent quels produits ou contenus recommander) à utiliser dans votre activité Recommendations [!DNL Target] d’Adobe.
title: Comment sélectionner des critères pour une activité Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 62%
---
# Sélection de critères

Sélectionnez les [critères](/help/main/c-recommendations/c-algorithms/algorithms.md) à utiliser dans votre activité [!DNL Adobe Target Recommendations]. Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.

Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Si vous sélectionnez plusieurs critères, le trafic est réparti uniformément entre les critères sélectionnés. Par exemple, si vous avez sélectionné deux critères et que votre activité est conçue pour afficher le contenu par défaut à 20 % des participants à l’activité, alors 40 % des participants à l’activité verront les recommandations contrôlées par chaque critère. Il n’existe pas d’option permettant de modifier les pourcentages pour chaque critère.

* Pour rechercher un critère existant (par exemple si de nombreuses cartes de critères s’affichent), écrivez dans le champ de recherche jusqu’à ce que les critères souhaités apparaissent, puis sélectionnez le critère et cliquez sur **[!UICONTROL Terminé]**.

  Certains critères sont fournis avec [!DNL Recommendations]. Vous et votre équipe pouvez également créer des critères personnalisés.

* Pour créer un critère, cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer des critères]**, puis renseignez les informations pour le nouveau critère. Pour plus d’informations sur la création de nouveaux critères, voir [Création d’un critère](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#create-criteria).

**Pour sélectionner des critères :**

1. Lors de la création d’une [recommandation](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#create-recs-activity), dans la boîte de dialogue **[!UICONTROL Sélectionner les critères]**, recherchez et sélectionnez un ou plusieurs critères.

   Vous pouvez utiliser le filtre [!UICONTROL Type de secteur], le filtre [!UICONTROL Type de page] et la case à cocher [!UICONTROL Compatible] pour filtrer la liste des critères. Ces options vous aident à localiser les critères souhaités.

   * **Type de secteur industriel :** le type de secteur industriel permet de classer les critères [!DNL Recommendations]. Pour modifier le secteur d’activité vertical par défaut, cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Paramètres]** et sélectionnez le paramètre **[!UICONTROL Secteur vertical]** par défaut souhaité.
   * **Type de page :** le type de page vous aide à classer les recommandations. Il existe également des critères intégrés que vous pouvez choisir pour chaque type de page.
   * **Compatible :** affichez uniquement les critères pour lesquels la page sélectionnée transmet les données requises. Tous les critères ne s’exécuteront pas correctement sur chaque page. La page ou la mbox doit transmettre `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Néanmoins, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, désactivez la case à cocher **[!UICONTROL Compatible.]** Cette option peut être désactivée ou activée dans vos paramètres : **[!UICONTROL Recommendations]** > **[!UICONTROL Paramètres]**.

1. Cliquez sur **[!UICONTROL Suivant]** pour afficher la boîte de dialogue [Sélectionner la conception](/help/main/c-recommendations/c-design-overview/design-overview.md).
