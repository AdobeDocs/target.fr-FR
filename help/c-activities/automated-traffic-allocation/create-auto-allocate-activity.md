---
keywords: Create auto-allocate;A/B test;auto-allocate activity;new a/b activity;auto allocate;auto-allocate to best experience;allocate
description: Utilisez le compositeur d’expérience visuelle en Adobe Target pour créer votre activité de test A/B d’affectation automatique directement sur une page compatible avec les Cibles et pour modifier des parties de la page dans la Cible.
title: Création d’une activité d’affectation automatique
feature: ab
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: fb4f43eef067a24f58ab8b53a7c8aa9c09392c9e
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 60%

---


# Création d’une activité d’affectation automatique

Utilisez le compositeur [!UICONTROL d’expérience] visuelle (VEC) dans [!DNL Adobe Target] pour créer votre activité de test  A/B [!UICONTROL AutoAffectation] directement sur une page  activée et pour modifier des parties de la page dans .[!DNL Target][!DNL Target]

>[!NOTE]
>
>Outre l’activité de test  A/B d’affectation [!UICONTROL automatique (présentée dans cet article),] fournit deux types supplémentaires d’activités de test [!DNL Target]  A/B : [!UICONTROL Manuel (par défaut)] et Cible automatique.
>
>Voir [Types d’activités](/help/c-activities/t-test-ab/test-ab.md#types) de test A/B dans la présentation *des tests* A/B.

Pour créer une activité d’affectation  automatique :

1. Depuis la liste **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer l’activité]** > **[!UICONTROL Test A/B]**.

   ![Liste déroulante Créer une activité](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL Recommandations] est une [fonctionnalité Target Premium](/help/c-intro/intro.md#premium).
   >
   >Pour plus d’informations sur les différents types d’activité, voir [Activités](/help/c-activities/activities.md) et le [Target activities guide (Guide des activités Target)](/help/c-activities/target-activities-guide.md).

1. Si nécessaire, sélectionnez **[!UICONTROL visuelle (défaut)]**.

   ![Créer une Activité de test A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   If you prefer to use the [!UICONTROL Form-Based Experience Composer], select [!UICONTROL Form]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le compositeur d’expérience d’expérience d’après les [!UICONTROL formulaires et le compositeur d’expérience]d’après les formulaires, [!DNL Target] offre le compositeur d’expérience visuelle d’application d’une seule page. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >L’option [[!UICONTROL Choisir l’espace de travail]](/help/administrating-target/c-user-management/property-channel/property-channel.md) de l’illustration précédente est une fonction [Target Premium](/help/c-intro/intro.md). Your organization has a [!UICONTROL Target Standard] license if you do not see this option.

1. (Conditionnel) Si vous êtes client [Target Premium](/help/c-intro/intro.md#premium), choisissez un [espace de travail](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Spécifiez votre [URL d’activité](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md), puis cliquez sur **[!UICONTROL Suivant]**.

   Si votre compte est configuré avec une URL par défaut, cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL.

   Le [!UICONTROL compositeur d’expérience visuelle] s’ouvre, affichant la page indiquée dans l’URL.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Saisissez un nom pour l’activité dans l’espace fourni.

   ![Champ Nom](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   Le nom de l’activité ne peut pas contenir les caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `/` | Barre oblique |
   | `?` | Point d’interrogation |
   | `#` | Croisillon |
   | `:` | Deux-points |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

1. Créez de nouvelles expériences en modifiant les éléments sur la page.

   Le [!UICONTROL compositeur d’expérience visuelle] affiche deux onglets sur le côté gauche dès lors qu’une activité est créée : Expérience A et Expérience B. Expérience A correspond à l’expérience de contrôle. Vous vous concentrerez sur l’onglet Expérience B, modifiable selon vos besoins. Expérience B correspond à l’expérience alternative que vous pouvez ajouter à votre test. Plusieurs expériences peuvent être ajoutées au test. Vous pouvez également supprimer l’Expérience A de l’activité si vous ne souhaitez pas que l’expérience de site par défaut soit une option possible.

   Pour plus d’informations sur l’ajout et la modification d’expériences dans le [!UICONTROL compositeur d’expérience visuelle], voir [Ajout d’une expérience](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Pour modifier l’Expérience B, commencez à l’étape 3.

1. Cliquez sur **[!UICONTROL Target]** dans la partie supérieure du [!UICONTROL Compositeur d’expérience visuelle] pour passer à l’étape suivante du flux de tâches guidé en trois étapes.

   Le diagramme de flux s’ouvre.

   ![Étape Ciblage des tests A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité et la configuration des expériences.

1. Dans la zone [!UICONTROL Audience] , cliquez sur l’icône Modifier (trois ellipses verticales), cliquez sur **[!UICONTROL Remplacer l’Audience]**, puis [sélectionnez l’audience](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) de votre activité.

   By default, the audience is set to [!UICONTROL All Visitors].

1. Sélectionnez le pourcentage de visiteurs admissibles qui doivent entrer dans l’activité.

   ![Pourcentage d’audience](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Configurez l’affectation de votre trafic.

   Vous pouvez proposer plusieurs expériences à une même audience. Un diagramme s’affiche pour indiquer l’audience sélectionnée et les expériences ajoutées à l’activité.

   Choisissez la méthode d’affectation du trafic souhaitée. Pour créer une activité d’affectation  automatique, sélectionnez l’option d’affectation **[!UICONTROL automatique pour optimiser l’expérience]**.

   Les trois types d’affectation du trafic sont décrits ci-dessous :

   * **[!UICONTROL Manuel (défaut)]** : Spécifiez le pourcentage souhaité de participants qui visualiseront chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %. For more information, see [Create an A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto affecter à la meilleure expérience]** : La plupart des participants aux activités sont automatiquement dirigés vers les expériences les plus performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances.

   * **[!UICONTROL Cible automatique pour les expériences]** personnalisées : [!DNL Target] utilise l’apprentissage automatique avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par les spécialistes du marketing, puis en offrant aux visiteurs l’expérience la plus adaptée en fonction de leurs profils clients individuels et des comportements passés de visiteurs similaires. For more information, see [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md).
   You can also click **[!UICONTROL Add]** to add another experience to the activity.

1. When you are satisfied with your audience, experience choices, and traffic allocation choices, click **[!UICONTROL Next]** to move to the third step of the three-step guided workflow.

1. Spécifiez les [objectifs et paramètres](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) pour l’activité.

   ![Paramètres de l’activité A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** ou **[!UICONTROL Enregistrer]**.

After you create the activity, the [!UICONTROL Overview] tab shows information about the activity, including a diagram of your activity.

## Training video: Creating A/B Tests (8:36) ![Tutorial badge](/help/assets/tutorial.png)

Cette vidéo explique comment créer un test A/B à l’aide du processus assisté en trois étapes de [!DNL Target].

* Création d’une activité de test  A/B dans [!DNL Adobe Target]
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/17391)