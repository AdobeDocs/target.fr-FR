---
description: Le compositeur d’expérience d’après les formulaires fournit une création d’expériences non visuelles.
keywords: compositeur d’expérience d’après les formulaires, compositeur basé sur les formulaires, ajustements
seo-description: Le compositeur d’expérience d’après les formulaires fournit une création d’expériences non visuelles.
seo-title: Compositeur d’expérience d’après les formulaires
solution: Target
title: Compositeur d’expérience d’après les formulaires
topic: Standard
uuid: 6791ed6f-69d0-4ec4-9ea4-47aa92b2a4c9
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Compositeur d’expérience d’après les formulaires{#form-based-experience-composer}

Le compositeur d’expérience d’après les formulaires est une interface de création d’expérience et d’offres qui est utile pour créer des expériences à utiliser dans les activités de tests A/B, de ciblage d’expérience, d’Automated Personalization et recommandations lorsque le compositeur d’expérience visuelle n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le compositeur basé sur les formulaires pour créer des expériences et des offres pour une diffusion dans des courriels, des bornes et des assistants vocaux.

Si vous créez une activité de recommandations, il n’y a pas d’expériences. Choisissez votre critère et votre conception. Si vous choisissez plusieurs critères ou conceptions, Target génère automatiquement les expériences.

1. Cliquez sur **[!UICONTROL Créer l’activité]**, puis sélectionnez le type d’activité que vous souhaitez créer.

   Le compositeur d’expérience d’après les formulaires est disponible pour les activités de tests A/B, de ciblage d’expérience, d’Automated Personalization et de recommandations.
1. Sélectionnez **[!UICONTROL Compositeur d’expérience d’après les formulaires]** depuis la boîte de dialogue [!UICONTROL Nouvelle Activité.]

   Le compositeur d’expérience d’après les formulaires s’ouvre.

   ![](assets/location_refinements.png)

   Cet écran est différent si vous créez une activité de recommandations. Les activités de recommandations n’incluent pas d’expériences.
1. Nommez l’activité.
1. Sélectionnez un emplacement.

   Lorsque vous cliquez dans la zone Sélectionner l’emplacement, une liste des emplacements disponibles s’affiche. Sélectionnez un de ces emplacements. Pour sélectionner l’emplacement global fourni via target.js, sélectionnez « target-global-mbox ».

   Vous pouvez également saisir un emplacement qui n’est pas répertorié ici. Ceci peut s’avérer utile lorsque la mbox n’a pas encore été créée ou consultée sur une page. Saisissez le nom de l’emplacement. Soyez prudent lorsque vous saisissez un emplacement qui n’existe pas encore. Si l’orthographe ou la capitalisation ne correspond pas à l’orthographe et à la capitalisation lorsque l’appel mbox est passé, l’activité ne sera pas diffusée. Les emplacements saisis manuellement sont enregistrés dans la liste.
1. Cliquez sur **[!UICONTROL Ajouter des ajustements d’audience]**, puis choisissez une ou plusieurs [audience(s)](../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) pour l’activité.

   ![](assets/location_refinements_2.png)

   Dans le compositeur d’expérience d’après les formulaires, les perfectionnements ont été remplacés par une fonctionnalité d’audience complète. Les perfectionnements pour les activités existantes ont été transférés vers [les audiences d’activité uniques](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).
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

   **Modifier le fragment d’expérience :** choisissez un fragment d’expérience.

   **Modifier l’offre de redirection :** choisissez une offre de redirection.

   **Modifier l’offre à distance :** choisissez une offre à distance.

   **Créer une offre HTML :**

   1. Cliquez sur [!UICONTROL Offres], puis sélectionnez l’onglet [!UICONTROL Offres (code)].
   1. Cliquez sur [!UICONTROL Créer] &gt; [!UICONTROL Offre HTML].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code HTML dans la zone Code.
   1. Cliquez sur [!UICONTROL Enregistrer].
   **Création d’offres JSON :**

   1. Cliquez sur [!UICONTROL Offres], puis sélectionnez l’onglet [!UICONTROL Offres (code)].
   1. Cliquez sur [!UICONTROL Créer] &gt; [!UICONTROL Offre JSON].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code JSON dans la zone Code.
   1. Cliquez sur [!UICONTROL Enregistrer].
   Pour une activité de recommandation, le menu déroulant Contenu fournit l’option Ajouter une recommandation. Cliquez sur **[!UICONTROL Ajouter une recommandation]**, puis sélectionnez le type de page. Suivez ensuite les étapes habituelles telles que définies dans l’interface pour [créer une activité de recommandations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Lors de la sélection de critères de recommandation dans le compositeur d’expérience d’après les formulaires, il existe désormais un lien direct vers la carte de critère sélectionnée, ce qui vous permet de modifier rapidement et facilement les critères.

   ![](assets/change_criteria.png)

   Dans la page Ciblage du processus assisté en trois étapes Target :

   ![](assets/change_criteria_2.png)

1. (Facultatif, pour les activités AB, la Personnalisation Automatisée et le Ciblage d’Expérience) Pour répéter ce processus pour des emplacements supplémentaires, cliquez `Add Location` sur et configurez l’emplacement et le contenu.
1. Cliquez sur **[!UICONTROL Continuer]**, puis effectuez les étapes de création de l’activité comme vous le faites d’ordinaire pour votre type d’activité.

* [Création d’un test A/B](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
* [Création d’une activité de ciblage d’expérience](../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Création d’une activité de recommandations](../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vidéo de formation : compositeur d’après les formulaires

Cette vidéo fournit une démonstration du compositeur d’après les formulaires.

* Création d’une activité à l’aide du compositeur d’expérience d’après les formulaires
* Comprendre à quel moment utiliser le compositeur d’expérience d’après les formulaires et le compositeur d’expérience visuelle
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390?captions=fre_fr)