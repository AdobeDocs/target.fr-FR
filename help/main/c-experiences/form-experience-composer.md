---
keywords: compositeur d’expérience d’après les formulaires, compositeur basé sur les formulaires, ajustements
description: Découvrez comment utiliser le compositeur d’expérience d’après les formulaires  [!DNL Target] Adobe pour la création d’expériences non visuelles. Utilisez ce compositeur lorsque le compositeur d’expérience visuelle n’est pas disponible ou qu’il n’est pas pratique de l’utiliser.
title: Comment utiliser le compositeur d’expérience d’après les formulaires ?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 37%

---

# Compositeur d’expérience d’après les formulaires

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] est une interface de création d’expérience et d’offres non visuelles qui est utile pour créer des expériences à utiliser dans les activités [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] et [!UICONTROL Recommendations] lorsque le [!UICONTROL Visual Experience Composer] (VEC) n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le compositeur d’expérience d’après les formulaires pour créer des expériences et des offres à diffuser dans des emails, des kiosques et des assistants vocaux.

Si vous créez une activité [!UICONTROL Recommendations], il n’y a aucune expérience. Choisissez votre critère et votre conception. Si vous choisissez plusieurs critères ou conceptions, [!UICONTROL Target] génère automatiquement les expériences.

1. Cliquez sur **[!UICONTROL Create Activity]**, puis sélectionnez le type d’activité que vous souhaitez créer.

   [!UICONTROL Form-Based Experience Composer] est disponible pour les activités [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] et [!UICONTROL Recommendations].

1. Sélectionnez **[!UICONTROL Form]** dans la boîte de dialogue [!UICONTROL Create Activity].

1. (Conditionnel) Sélectionnez un espace de travail et une propriété.

1. Cliquez sur **[!UICONTROL Next]**.

   Le [!UICONTROL Form-Based Experience Composer] s’ouvre.

   ![location_raffiements image](assets/location_refinements.png)

   Cet écran est différent si vous créez une activité [!UICONTROL Recommendations]. Les activités [!UICONTROL Recommendations] n’incluent pas d’expériences.

1. Nommez l’activité en cliquant sur &quot;[!UICONTROL Untitled Activity]&quot;.
1. Sélectionnez un emplacement.

   Lorsque vous cliquez dans la zone [!UICONTROL Select Location], une liste des emplacements disponibles s’affiche. Sélectionnez l’un de ces emplacements.

   Vous pouvez également saisir un emplacement qui n’est pas répertorié ici. Ceci peut s’avérer utile lorsque la mbox n’a pas encore été créée ou consultée sur une page. Saisissez le nom de l’emplacement. Soyez prudent lorsque vous saisissez un emplacement qui n’existe pas encore. Si l’orthographe ou la capitalisation ne correspond pas à l’orthographe et à la capitalisation lorsque l’appel mbox est passé, l’activité ne sera pas diffusée. Les emplacements saisis manuellement sont enregistrés dans la liste des emplacements disponibles. La prochaine fois que vous tenterez de sélectionner un emplacement saisi manuellement, il sera disponible dans la liste déroulante [!UICONTROL Select Location] pour cette activité.

   >[!NOTE]
   >
   >La création d’un emplacement saisi manuellement lors de la création de l’activité ne crée pas automatiquement un nouvel emplacement. Le nom de l’emplacement est enregistré uniquement dans le contexte de l’activité. L’emplacement est créé en cas d’appel de diffusion de contenu. Après la création de l&#39;emplacement, il sera disponible dans d&#39;autres activités, pour la création d&#39;audiences, etc. dans la liste déroulante des emplacements disponibles.

1. Cliquez sur **[!UICONTROL Add Audience Refinements]**, sélectionnez une ou plusieurs [audience](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) pour cette activité, puis cliquez sur **[!UICONTROL Done]**.

   ![location_raffments_2 image](assets/location_refinements_2.png)

   Dans le [!UICONTROL Form-based Experience Composer], les perfectionnements ont été remplacés par une fonctionnalité d’audience complète. Les perfectionnements pour les activités existantes ont été migrés vers les [audiences d’activité uniques](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Sélectionnez le type de contenu que vous souhaitez voir à cet emplacement.

   ![image form_content](assets/form_content.png)

1. Pour le type de contenu que vous avez sélectionné, indiquez le contenu.

   **Modifier l’offre HTML :** choisissez une offre HTML.

   **Modifier une offre d’images :** sélectionnez une image enregistrée dans la bibliothèque de contenu de Target.

   Vous pouvez également ajouter un lien à une image (clic publicitaire, destination, entrée, etc.)

   1. Cliquez sur [!UICONTROL Change Image Offer].
   1. Sélectionnez l’image souhaitée, puis cliquez sur [!UICONTROL Edit Links].
   1. Spécifiez l’URL ou la page de votre site, puis cliquez sur [!UICONTROL Update].

   **Modifier l’offre JSON :** choisissez une offre json.

   **Modifier le fragment d’expérience :** choisissez un fragment d’expérience. Pour plus d’informations, voir [Fragment d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Modifier l’offre de redirection :** choisissez une offre de redirection. Pour plus d’informations, voir [Création d’offres de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Modifier l’offre distante :** choisissez une offre distante. Pour plus d’informations, voir [Créer des offres distantes](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Créer une offre HTML :**

   1. Cliquez sur [!UICONTROL Offers], puis sélectionnez l’onglet [!UICONTROL Code Offers].
   1. Cliquez sur [!UICONTROL Create] > [!UICONTROL HTML Offer].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code HTML dans la zone Code.
   1. Cliquez sur [!UICONTROL Save].

   **Création d’offres JSON :**

   1. Cliquez sur [!UICONTROL Offers], puis sélectionnez l’onglet [!UICONTROL Code Offers].
   1. Cliquez sur [!UICONTROL Create] > [!UICONTROL JSON Offer].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code JSON dans la zone Code.
   1. Cliquez sur [!UICONTROL Save].

   **Ajouter une recommandation :**

   Pour une activité Recommendations, la liste déroulante Contenu vous donne l’option [!UICONTROL Add Recommendation]. Cliquez sur **[!UICONTROL Add Recommendation]**, puis sélectionnez le type de page. Suivez ensuite les étapes habituelles telles que définies dans l’interface pour [créer une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Lors de la sélection de critères de recommandation dans le compositeur d’expérience d’après les formulaires, il existe désormais un lien direct vers la carte de critère sélectionnée, ce qui vous permet de modifier rapidement et facilement les critères.

   ![image change_critères ](assets/change_criteria.png)

   Dans la page Ciblage du processus assisté en trois étapes Target :

   ![change_critères_2 image](assets/change_criteria_2.png)

   **Ajouter une décision d’offre :**

   Ajoutez une offre créée dans [!DNL Adobe Journey Optimizer] (AJO) à une activité [!DNL Adobe Target] afin de présenter la meilleure offre et la meilleure expérience dynamique aux visiteurs de votre site web ou mobile en utilisant offer decisioning. Cette option est disponible uniquement pour les activités [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] manuelles (XT).

   Pour plus d’informations, voir [Utiliser les décisions d’offre](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Facultatif, pour les activités [!UICONTROL A/B Test], [!UICONTROL Automated Personalization] et [!UICONTROL Experience Targeting]) Pour répéter ce processus pour des emplacements supplémentaires, cliquez sur **[!UICONTROL Add Location]** et configurez l’emplacement et le contenu.
1. Cliquez sur **[!UICONTROL Next]**, puis effectuez les étapes de création de l’activité comme vous le faites habituellement pour votre type d’activité.

* [Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Création d’une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vidéo de formation : Compositeur d’après les formulaires ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit une démonstration du compositeur d’après les formulaires.

* Création d’une activité à l’aide du compositeur d’expérience d’après les formulaires
* Comprendre à quel moment utiliser le compositeur d’expérience d’après les formulaires et le compositeur d’expérience visuelle
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)
