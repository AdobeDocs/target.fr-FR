---
keywords: compositeur d’expérience d’après les formulaires, compositeur basé sur les formulaires, ajustements
description: Découvrez comment utiliser l’Adobe [!DNL Target] Compositeur d’expérience d’après les formulaires pour la création d’expérience non visuelle. Utilisez ce compositeur lorsque le compositeur d’expérience visuelle n’est pas disponible ou qu’il n’est pas pratique de l’utiliser.
title: Comment utiliser le compositeur d’expérience d’après les formulaires ?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 46%

---

# Compositeur d’expérience d’après les formulaires

Le [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience d’après les formulaires] est une interface de création d’expériences et d’offres non visuelles utile pour créer des expériences à utiliser dans [!UICONTROL Test A/B], [!UICONTROL Ciblage d’expérience], [!UICONTROL Automated Personalization], et [!UICONTROL Recommendations] lorsque la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC) n’est pas disponible ni pratique à utiliser. Par exemple, vous pouvez utiliser le compositeur d’expérience d’après les formulaires pour créer des expériences et des offres à diffuser dans des emails, des kiosques et des assistants vocaux.

Si vous créez une [!UICONTROL Recommendations] , il n’existe aucune expérience. Choisissez votre critère et votre conception. Si vous choisissez plusieurs critères ou conceptions, [!UICONTROL Cible] génère automatiquement les expériences.

1. Cliquez sur **[!UICONTROL Créer l’activité]**, puis sélectionnez le type d’activité que vous souhaitez créer.

   Le [!UICONTROL Compositeur d’expérience d’après les formulaires] est disponible pour [!UICONTROL Test A/B], [!UICONTROL Ciblage d’expérience], [!UICONTROL Automated Personalization], et [!UICONTROL Recommendations] activités.

1. Sélectionner **[!UICONTROL Formulaire]** de la [!UICONTROL Création d’une activité] de la boîte de dialogue

1. (Conditionnel) Sélectionnez un espace de travail et une propriété.

1. Cliquez sur **[!UICONTROL Suivant]**.

   Le [!UICONTROL Compositeur d’expérience d’après les formulaires] s’ouvre.

   ![](assets/location_refinements.png)

   Cet écran est différent si vous créez une [!UICONTROL Recommendations] activité. [!UICONTROL Les activités de recommandations n’incluent pas d’expériences.]

1. Nommez l’activité en cliquant sur &quot;[!UICONTROL Activité sans titre].&quot;
1. Sélectionnez un emplacement.

   Lorsque vous cliquez sur dans le [!UICONTROL Sélectionner un emplacement] , une liste des emplacements disponibles s’affiche. Sélectionnez un de ces emplacements.

   Vous pouvez également saisir un emplacement qui n’est pas répertorié ici. Ceci peut s’avérer utile lorsque la mbox n’a pas encore été créée ou consultée sur une page. Saisissez le nom de l’emplacement. Soyez prudent lorsque vous saisissez un emplacement qui n’existe pas encore. Si l’orthographe ou la capitalisation ne correspond pas à l’orthographe et à la capitalisation lorsque l’appel mbox est passé, l’activité ne sera pas diffusée. Les emplacements saisis manuellement sont enregistrés dans la liste des emplacements disponibles. La prochaine fois que vous tenterez de sélectionner un emplacement saisi manuellement, il sera disponible dans la variable [!UICONTROL Sélectionner un emplacement] liste déroulante de cette activité.

   >[!NOTE]
   >
   >La création d’un emplacement saisi manuellement lors de la création de l’activité ne crée pas automatiquement un nouvel emplacement. Le nom de l’emplacement est enregistré uniquement dans le contexte de l’activité. L’emplacement est créé en cas d’appel de diffusion de contenu. Une fois l&#39;emplacement créé, il sera disponible pour une utilisation dans d&#39;autres activités, pour la création d&#39;audiences, etc. dans la liste déroulante des emplacements disponibles.

1. Cliquez sur **[!UICONTROL Ajout de perfectionnements d’audience]**, choisissez une ou plusieurs [audience](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) pour cette activité, puis cliquez sur **[!UICONTROL Terminé]**.

   ![](assets/location_refinements_2.png)

   Dans le [!UICONTROL Compositeur d’expérience d’après les formulaires], les perfectionnements ont été remplacés par une fonctionnalité d’audience complète. Les perfectionnements pour les activités existantes ont été transférés vers [les audiences d’activité uniques](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Sélectionnez le type de contenu que vous souhaitez voir à cet emplacement.

   ![](assets/form_content.png)

1. Pour le type de contenu que vous avez sélectionné, indiquez le contenu.

   **Modifier l’offre HTML :** choisissez une offre HTML.

   **Modifier une offre d’images :** sélectionnez une image enregistrée dans la bibliothèque de contenu de Target.

   Vous pouvez également ajouter un lien à une image (clic publicitaire, destination, entrée, etc.)

   1. Cliquez sur [!UICONTROL Modifier l’offre d’image].
   1. Sélectionnez l’image souhaitée, puis cliquez sur [!UICONTROL Modifier les liens].
   1. Précisez l’URL ou la page de votre site souhaitée, puis cliquez sur [!UICONTROL Mettre à jour].

   **Modifier l’offre JSON :** choisissez une offre json.

   **Modifier le fragment d’expérience :** choisissez un fragment d’expérience. Pour plus d’informations, voir [Fragment d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Modifier l’offre de redirection :** choisissez une offre de redirection. Pour plus d’informations, voir [Créer des offres de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Modifier l’offre à distance :** choisissez une offre à distance. Pour plus d’informations, voir [Créer des offres distantes](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Créer une offre HTML :**

   1. Cliquez sur [!UICONTROL Offres], puis sélectionnez l’onglet [!UICONTROL Offres (code)].
   1. Cliquez sur [!UICONTROL Créer] > [!UICONTROL Offre HTML].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code HTML dans la zone Code.
   1. Cliquez sur [!UICONTROL Enregistrer].

   **Création d’offres JSON :**

   1. Cliquez sur [!UICONTROL Offres], puis sélectionnez l’onglet [!UICONTROL Offres (code)].
   1. Cliquez sur [!UICONTROL Créer] > [!UICONTROL Offre JSON].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code JSON dans la zone Code.
   1. Cliquez sur [!UICONTROL Enregistrer].

   **Ajouter une recommandation :**

   Pour une activité Recommendations, la liste déroulante Contenu vous donne la valeur [!UICONTROL Ajouter une recommandation] . Cliquez sur **[!UICONTROL Ajouter une recommandation]**, puis sélectionnez le type de page. Suivez ensuite les étapes habituelles telles que définies dans l’interface pour [créer une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Lors de la sélection de critères de recommandation dans le compositeur d’expérience d’après les formulaires, il existe désormais un lien direct vers la carte de critère sélectionnée, ce qui vous permet de modifier rapidement et facilement les critères.

   ![](assets/change_criteria.png)

   Dans la page Ciblage du processus assisté en trois étapes Target :

   ![](assets/change_criteria_2.png)

   **Ajouter une décision d’offre :**

   Ajouter une offre créée dans [!DNL Adobe Journey Optimizer] (AJO) en [!DNL Adobe Target] pour présenter la meilleure offre et expérience dynamique aux visiteurs de votre site web ou mobile à l’aide d’offer decisioning. Cette option est disponible pour les opérations manuelles [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) uniquement.

   Pour plus d’informations, voir [Utilisation des décisions d’offre](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Facultatif, pour [!UICONTROL Test A/B], [!UICONTROL Automated Personalization], et [!UICONTROL Ciblage d’expérience] activités) Pour répéter ce processus pour des emplacements supplémentaires, cliquez sur **[!UICONTROL Ajouter un emplacement]** et configurez l’emplacement et le contenu.
1. Cliquez sur **[!UICONTROL Suivant]**, puis effectuez les étapes de création de l’activité comme vous le faites habituellement pour votre type d’activité.

* [Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Création d’une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vidéo de formation : Compositeur d’après les formulaires ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit une démonstration du compositeur d’après les formulaires.

* Création d’une activité à l’aide du compositeur d’expérience d’après les formulaires
* Comprendre à quel moment utiliser le compositeur d’expérience d’après les formulaires et le compositeur d’expérience visuelle
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)
