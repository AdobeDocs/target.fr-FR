---
keywords: créer des recommandations;activité de recommandations;nouvelles recommandations;présentation de recommandations
description: Découvrez comment utiliser le  [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) pour créer une activité  [!DNL Recommendations] .
title: Comment créer une activité  [!DNL Recommendations] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 77fc3215f20b0d5f6407fc07889748b5734ca9ea
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 52%

---

# Créer une activité [!DNL Recommendations]

Utilisez le [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) pour créer une activité [!DNL Recommendations] directement sur une page [!DNL Target] et pour modifier des parties de la page dans [!DNL Target].

1. Cliquez sur **[!UICONTROL Activities]** > **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**.

1. Sélectionnez **[!UICONTROL Visual]**, si nécessaire.

   ![Boîte de dialogue Création d’une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez [!UICONTROL Form]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le VEC et [!UICONTROL Form-Based Experience Composer], [!DNL Target] offre le VEC [!UICONTROL Single Page Application]. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >L’option [!UICONTROL [Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de l’illustration précédente est une fonction [Target Premium](/help/main/c-intro/intro.md). Votre entreprise dispose d’une licence [!UICONTROL Target Standard] si vous ne voyez pas cette option.

1. (Conditionnel) Si vous êtes client [Target Premium](/help/main/c-intro/intro.md#premium), choisissez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Spécifiez une URL d’activité, puis cliquez sur **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://wwww.adobe.com`] correspondent tous les deux.

   L’URL d’activité est la page sur laquelle s’affichent les recommandations.

   Lorsque vous cliquez sur [!UICONTROL Create], le VEC s’ouvre et affiche votre page. Vous pouvez remplacer un élément actuel par des recommandations ou insérer des recommandations.

1. Cliquez sur un élément de la page puis, si des recommandations sont disponibles là où cet élément est situé, cliquez sur **[!UICONTROL Replace w/ Recommendations]**, **[!UICONTROL Insert Recommendations Before]** ou **[!UICONTROL Insert Recommendations After]**.

   Les visiteurs de votre site ne verront le contenu recommandé que s’ils remplissent les critères de la recommandation. Les visiteurs qui ne remplissent pas les critères de la recommandation voient le contenu par défaut.

   ![Options de recommandations](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL Replace w/ Recommendations]** : le remplacement d’un élément par des recommandations supprime le contenu actuel et le remplace par vos recommandations. Lorsque les visiteurs visitent votre site et répondent aux critères de la recommandation, ils voient les éléments recommandés dans la zone spécifiée au lieu du contenu existant.
   * **[!UICONTROL Insert Recommendations Before]** : l’insertion de recommandations avant l’élément sélectionné place le contenu recommandé avant cet élément. Selon la construction de la page, la recommandation s’affiche au-dessus ou à gauche de l’élément sélectionné.
   * **[!UICONTROL Insert Recommendations After]** : l’insertion de recommandations après l’élément sélectionné place le contenu recommandé après cet élément. Selon la construction de votre page, la recommandation s’affiche en bas à droite ou à droite de l’élément sélectionné.

   L’option **[!UICONTROL Expand Selection]** vous permet de développer l’emplacement sélectionné (conteneur parent) pour vous aider à identifier et inclure plus facilement les éléments de page souhaités.

1. Sélectionnez un type de page.

   Les types de pages peuvent inclure :

   * Page Panier
   * Page de catégorie
   * Page d’accueil
   * Page de destination
   * Page de produit
   * Page Résultats de recherche
   * Page de remerciement
   * Les autres

   ![Sélection des options de type de page](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Sélectionnez un ou plusieurs [critères](/help/main/c-recommendations/c-algorithms/algorithms.md).

   Les critères s’affichent sous la forme de cartes qui présentent des informations sur chaque critère. Par défaut, l’écran [!UICONTROL Select Criteria] affiche les critères compatibles avec votre secteur industriel vertical et le type de page que vous avez sélectionné à l’étape précédente. Vous pouvez modifier ces options pour afficher d’autres critères.

   >[!NOTE]
   >
   >Tous les critères ne s’exécuteront pas correctement sur chaque page. La page ou la mbox doit transmettre `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Toutefois, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, décochez la case **[!UICONTROL Compatible]** . L’option [!UICONTROL Compatible] peut ne pas s’afficher, selon vos paramètres Recommendations ( **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** > **[!UICONTROL Filter Incompatible Criteria]**). Pour plus d’informations, voir [Paramètres](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}.

   ![Boîte de dialogue Sélection de critères](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Si vous sélectionnez plusieurs critères, le trafic est réparti uniformément entre les critères sélectionnés. Par exemple, si vous avez sélectionné deux critères et que votre activité est conçue pour afficher le contenu par défaut à 20 % des participants à l’activité, alors 40 % des participants à l’activité verront les recommandations contrôlées par chaque critère. Il n’existe pas d’option permettant de modifier les pourcentages pour chaque critère.

   * Pour rechercher un critère existant (par exemple, si un grand nombre de cartes de critères s’affichent), écrivez dans le champ de recherche jusqu’à ce que les critères souhaités apparaissent, puis sélectionnez le critère et cliquez sur **[!UICONTROL Next]**.

     Certains critères sont fournis avec [!DNL Recommendations]. Vous et votre équipe pouvez également créer des critères personnalisés.

   * Pour créer un nouveau critère, cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**, puis renseignez les informations du nouveau critère. Pour plus d’informations sur la création d’un nouveau critère, voir [Créer un critère](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).
   * Vous pouvez également regrouper les critères en séquences. Pour créer une nouvelle séquence de critères, cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Pour plus d’informations, voir [Création d’une séquence de critères](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md) .

1. Cliquez sur **[!UICONTROL Next]**.
1. Sélectionnez une [conception](/help/main/c-recommendations/c-design-overview/design-overview.md).

   Une conception est un modèle qui détermine l’apparence des emplacements sur votre page. [!DNL Target] comprend plusieurs conceptions préconfigurées. Vous pouvez également créer vos conceptions personnalisées. Pour plus d’informations, voir [Création d’une conception](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) et [Personnalisation d’une conception](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Boîte de dialogue Sélection d’une conception](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   Chaque conception affiche une représentation graphique de l’apparence qu’elle aura ainsi que des icônes qui montrent le nombre de vos activités actives et inactives qui utilisent cette conception.

   * Pour sélectionner une ou plusieurs conceptions existantes, cliquez sur les conceptions, puis sur **[!UICONTROL Next]**.

     Si vous avez sélectionné plusieurs critères, vous ne pouvez sélectionner qu’une seule conception.

   * Pour créer une conception personnalisée, cliquez sur **[!UICONTROL Create Design]**, puis renseignez le nom et le code de la nouvelle conception. Cliquez sur **[!UICONTROL Next]**, puis sélectionnez ou téléchargez une image et cliquez sur **[!UICONTROL Done]** > **[!UICONTROL Done]**. Pour plus d’informations sur la création d’un modèle, voir [Créer un modèle](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Cliquez sur **[!UICONTROL Next]**.

   Vous avez la possibilité d’ajouter des promotions à vos recommandations. Pour plus d’informations sur l’ajout de promotions avant et arrière, voir [Ajout de promotions](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Cliquez sur **[!UICONTROL Save]**.

   L’écran Compositeur d’expérience visuelle affiche la conception de recommandations sur votre page.

1. (Facultatif) Cliquez sur **[!UICONTROL Preview]** pour afficher l’activité aux visiteurs.

   Le mode [!UICONTROL Preview] vous permet d’interagir avec vos recommandations, comme un visiteur le ferait.

   Lorsque vous avez terminé de prévisualiser vos recommandations, cliquez sur **[!UICONTROL Compose]**.

1. Vérifiez votre recommandation dans le VEC, puis cliquez sur **[!UICONTROL Next]**.

1. Vérifiez votre activité [!DNL Recommendations] dans le diagramme de flux et apportez toute modification requise.

   ![Diagramme de flux Recommandations](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité, la configuration des expériences et la spécification des mesures de succès.

   Vous pouvez effectuer les opérations suivantes à partir du diagramme de flux :

   * Modifier l’audience qui verra les recommandations

     >[!NOTE]
     >
     >En plus de sélectionner une audience existante, vous pouvez [créer une audience destinée à une activité seulement](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) ou [combiner plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer des audiences ad hoc plutôt que d’en créer une nouvelle.

     Par défaut, tous les utilisateurs voient les recommandations. Néanmoins, vous pouvez cibler la recommandation sur une audience spécifique.

     Pour une activité [!DNL Recommendations], le groupe de contrôle voit la page sans les recommandations.

   * Afficher les critères
   * Modification de la collection (en regard de l’étiquette [!UICONTROL Criteria])
   * Modifier le pourcentage de participants qui voient l’expérience de contrôle
   * Afficher le code de la conception
   * Modifier ou supprimer une conception

1. Cliquez sur **[!UICONTROL Next]** lorsque vous avez terminé.
1. Spécifiez les paramètres de votre activité.

   Par exemple, saisissez un nom (obligatoire) et un objectif (facultatif) pour l’activité. Pour plus d’informations sur les paramètres, voir [Paramètres d’activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Si vous spécifiez un nom de [!DNL Recommendation] pour l’activité de recommandations qui existe déjà pour une autre activité dans [!DNL Recommendations Classic], la nouvelle activité est resynchronisée avec un nouveau nom. Le nouveau nom correspond au nom d’origine complété par un horodatage pour le rendre unique. Le nouveau nom est affiché dans [!DNL Target Standard/Premium] et dans [!DNL Recommendations Classic].

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Save & Close]**.

   Un aperçu de votre activité s’affiche.

   Sur la page [!UICONTROL Overview], vous pouvez :

   * activer l’activité ;
   * modifier l’activité ;
   * Partage de l’activité avec votre flux d’Experience Cloud
   * AQ de l’activité
   * afficher vos URL d’expérience ;
   * télécharger des données ;
   * modifier le pourcentage de participants à l’activité qui voient l’expérience de contrôle ;
   * afficher ou masquer les détails des critères ;
   * afficher le code de vos conceptions.

1. (Facultatif) Ouvrez la page [!UICONTROL Reports] pour afficher le rapport qui montre les performances de votre activité [!DNL Recommendations].

1. (Facultatif) Ouvrez la page [!UICONTROL Collisions] pour afficher toutes les [collisions d’activités](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md) qui peuvent se produire.

   Des collisions d’activités se produisent lorsque plusieurs activités sont configurées pour fournir du contenu à la même page, ce qui peut entraîner l’affichage d’un contenu inattendu.

## Vidéo de formation : Création d’une activité Recommendations (7:15) ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)