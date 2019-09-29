---
description: Utilisez le compositeur d’expérience visuelle de Target (VEC) pour créer une activité de recommandations directement sur une page Target et pour modifier des parties de la page dans Target.
keywords: créer des recommandations;activité de recommandations;nouvelles recommandations;présentation de recommandations
seo-description: Utilisez le compositeur d’expérience visuelle de Target (VEC) pour créer une activité de recommandations directement sur une page Target et pour modifier des parties de la page dans Target.
seo-title: Création d’une activité de recommandations
solution: Target
title: Création d’une activité de recommandations
title-outputclass: premium
topic: Premium
uuid: c3f22cce-204a-4509-92c4-8fec43fbaebe
badge: premium
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# ![PREMIUM](/help/assets/premium.png) Création d’une activité de recommandations{#create-a-recommendations-activity}

Utilisez le compositeur d’expérience visuelle de Target (VEC) pour créer une activité de recommandations directement sur une page Target et pour modifier des parties de la page dans Target.

1. Cliquez sur **[!UICONTROL Créer une activité]** &gt; **[!UICONTROL Recommandations]**.

   ![Création d’une activité de recommandations](/help/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. Si nécessaire, sélectionnez **[!UICONTROL visuelle (défaut)]**.

   ![Boîte de dialogue Création d’une activité de recommandations](/help/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez l’option [!UICONTROL Formulaire]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le VEC et le compositeur d’expérience d’après les formulaires, Target propose le compositeur d’expérience visuelle d’une seule page et le compositeur d’expérience visuelle pour les applications mobiles. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [!UICONTROL [Choose Workplace](/help/administrating-target/c-user-management/property-channel/property-channel.md) option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Votre entreprise dispose d’une licence Target Standard si vous ne voyez pas cette option.]

1. (Conditionnel) Si vous êtes client [Target Premium](/help/c-intro/intro.md#premium), choisissez un [espace de travail](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Spécifiez une URL d’activité, puis cliquez sur **[!UICONTROL Suivant]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://wwww.adobe.com`] se correspondent.

   L’URL d’activité est la page sur laquelle les recommandations s’affichent.

   Lorsque vous cliquez sur [!UICONTROL Suivant], le compositeur d’expérience visuelle s’ouvre et affiche votre page. Vous pouvez remplacer un élément actuel par des recommandations ou insérer des recommandations.

1. Cliquez sur un élément de la page puis, si des recommandations sont disponibles là où cet élément est situé, cliquez sur **[!UICONTROL Remplacer par des recommandations]**, **[!UICONTROL Insérer les recommandations avant]**, ou **[!UICONTROL Insérer les recommandations après]**.

   ![Options de recommandations](/help/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   Le remplacement d’un élément par des recommandations supprime le contenu actuel et le remplace par vos recommandations.

1. Sélectionnez un type de page.

   Les types de pages peuvent inclure :

   * Page Panier
   * Page de catégorie
   * Page d’accueil
   * Page d’entrée
   * Page de produit
   * Page Résultats de recherche
   * Page de remerciement
   * Les autres
   ![Sélection des options de type de page](/help/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Sélectionnez un ou plusieurs [critères](/help/c-recommendations/c-algorithms/algorithms.md).

   Les critères s’affichent sous la forme de cartes qui présentent des informations sur chaque critère. Par défaut, l’écran [!UICONTROL Sélectionner les critères] affiche les critères compatibles avec votre secteur industriel vertical et le type de page que vous avez sélectionné. Vous pouvez modifier ces options pour afficher d’autres critères.

   >[!NOTE]
   >
   >Tous les critères ne s’exécuteront pas correctement sur chaque page. La page ou la mbox doit transmettre `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Néanmoins, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, désactivez la case à cocher **[!UICONTROL Compatible]**. L’option [!UICONTROL Compatible] peut ne pas s’afficher, selon vos paramètres de recommandations (**[!UICONTROL Recommandations]** &gt; **[!UICONTROL Paramètres]** &gt; **[!UICONTROL Filtrer les critères incompatibles]**). Pour plus d’informations, voir [Paramètres](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84).

   ![Boîte de dialogue Sélection de critères](/help/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Si vous sélectionnez plusieurs critères, le trafic est réparti uniformément entre les critères sélectionnés. Par exemple, si vous avez sélectionné deux critères et que votre activité est conçue pour afficher le contenu par défaut à 20 % des participants à l’activité, alors 40 % des participants à l’activité verront les recommandations contrôlées par chaque critère. Il n’existe pas d’option permettant de modifier les pourcentages pour chaque critère.

   * Pour rechercher un critère existant (par exemple si un grand nombre de cartes de critères s’affichent), écrivez dans le champ de recherche jusqu’à ce que les critères souhaités apparaissent, puis sélectionnez le critère et cliquez sur **[!UICONTROL Terminé]**.

      Certains critères sont fournis avec [!DNL Recommendations]. Vous et votre équipe pouvez également créer des critères personnalisés.

   * Pour créer un nouveau critère, cliquez sur **[!UICONTROL Créer un critère]** &gt; **[!UICONTROL Créer un critère]**, puis renseignez les informations du nouveau critère. Pour plus d’informations sur la création d’un nouveau critère, voir [Créer un critère](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).
   * Vous pouvez également regrouper les critères en séquences. Pour créer une nouvelle séquence de critères, cliquez sur **[!UICONTROL Créer un critère]** &gt; **[!UICONTROL Créer une séquence de critères]**. Voir [Création de séquences de critères](../../c-recommendations/c-algorithms/create-criteria-sequence.md#task_8A9CB465F28D44899F69F38AD27352FE) pour plus d’informations.

1. Cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez une [conception](/help/c-recommendations/c-design-overview/design-overview.md).

   Une conception est un modèle qui détermine l’apparence des emplacements sur votre page. [!DNL Target] inclut plusieurs modèles préconfigurés. Vous pouvez également créer vos conceptions personnalisées. Pour plus d’informations, voir [Créer un modèle](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) et [personnaliser un modèle](../../c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Boîte de dialogue Sélection d’une conception](/help/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   Chaque conception affiche une représentation graphique de l’apparence qu’elle aura ainsi que des icônes qui montrent le nombre de vos activités actives et inactives qui utilisent cette conception.

   * Pour sélectionner une ou plusieurs conceptions existantes, cliquez sur les conceptions, puis sur **[!UICONTROL Suivant]**.

      Si vous avez sélectionné plusieurs critères, vous ne pouvez sélectionner qu’une seule conception.

   * Pour créer un modèle personnalisé, cliquez sur **[!UICONTROL Créer une conception]**, puis renseignez les nom et code correspondant au nouveau modèle. Cliquez sur **[!UICONTROL Suivant]**, puis sélectionnez ou téléchargez une image et cliquez sur **[!UICONTROL Terminé]** &gt; **[!UICONTROL Terminé]**. Pour plus d’informations sur la création d’un modèle, voir [Créer un modèle](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Cliquez sur **[!UICONTROL Suivant]**.

   Vous avez la possibilité d’ajouter des promotions à vos recommandations. Pour plus d’informations sur l’ajout de promotions avant et arrière, reportez-vous à la section [Ajout de promotions](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   L’écran Compositeur d’expérience visuelle affiche la conception de recommandations sur votre page.

1. (Facultatif) Cliquez sur **[!UICONTROL Aperçu]** pour voir comment l’activité apparaît aux visiteurs.

   Le mode d’[!UICONTROL aperçu permet] d’interagir avec vos recommandations, comme un visiteur le ferait.

   Lorsque vous avez terminé de prévisualiser vos recommandations, cliquez sur **[!UICONTROL Composer]**.

1. Vérifiez votre recommandation dans le compositeur d’expérience visuelle, puis cliquez sur **[!UICONTROL Suivant]**.

1. Vérifiez votre activité [!DNL Recommendations] dans le diagramme de flux et apportez toute modification requise.

   ![Diagramme de flux Recommandations](/help/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité, la configuration des expériences et la spécification des mesures de succès.

   Vous pouvez effectuer les opérations suivantes à partir du diagramme de flux :

   * Modifier l’audience qui verra les recommandations

      >[!NOTE]
      >
      >En plus de sélectionner une audience existante, vous pouvez [créer une audience destinée à une activité seulement](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) ou [combiner plusieurs audiences](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer des audiences ad hoc plutôt que d’en créer une nouvelle.

      Par défaut, tous les utilisateurs voient les recommandations. Néanmoins, vous pouvez cibler la recommandation sur une audience spécifique.

      Pour une activité [!DNL Recommendations], le groupe de contrôle voit la page sans les recommandations.

   * Afficher les critères
   * Modifier la collection (en regard de l’étiquette [!UICONTROL Critères])
   * Modifier le pourcentage de participants qui voient l’expérience de contrôle
   * Afficher le code de la conception
   * Modifier ou supprimer une conception

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Suivant].**
1. Spécifiez les paramètres de votre activité.

   Par exemple, saisissez un nom (obligatoire) et un objectif (facultatif) pour l’activité. Pour plus d’informations sur les paramètres, voir [Paramètres d’activité de recommandations](../../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Si vous spécifiez un nom de [!DNL Recommendation] pour l’activité de recommandations qui existe déjà pour une autre activité dans [!DNL Recommendations Classic], la nouvelle activité est resynchronisée avec un nouveau nom. Le nouveau nom correspond au nom d’origine complété par un horodatage pour le rendre unique. Le nouveau nom est affiché dans [!DNL Target Standard/Premium] et dans [!DNL Recommendations Classic].

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer et fermer]**.

   Un aperçu de votre activité s’affiche.

   Sur la page d’[!UICONTROL aperçu], vous pouvez :

   * activer l’activité ;
   * modifier l’activité ;
   * épingler l’activité à votre tableau de bord Experience Cloud ;
   * afficher vos URL d’expérience ;
   * télécharger des données ;
   * modifier le pourcentage de participants à l’activité qui voient l’expérience de contrôle ;
   * afficher ou masquer les détails des critères ;
   * afficher le code de vos conceptions.

1. (Facultatif) Ouvrez la page [!UICONTROL Rapports] pour afficher le rapport qui présente les performances de votre activité de [!DNL Recommendations].
1. (Facultatif) Ouvrir l’onglet [!UICONTROL Collisions] pour afficher les [collisions d’activités](/help/c-experiences/c-visual-experience-composer/activity-collisions.md) qui peuvent se produire.

   Des collisions d’activités se produisent lorsque plusieurs activités sont configurées pour fournir du contenu à la même page, ce qui peut entraîner l’affichage d’un contenu inattendu.

## Vidéo de formation : Création d’une activité Recommendations (7:15)

>[!VIDEO](https://video.tv.adobe.com/v/27688?captions=fre_fr)