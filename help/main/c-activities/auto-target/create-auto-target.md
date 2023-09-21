---
keywords: Créer un ciblage automatique;test A/B;activité de ciblage automatique;nouvelle activité a/b;ciblage automatique;ciblage automatique pour les expériences personnalisées;personnalisé;optimisation
description: Découvrez comment utiliser le [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer un [!UICONTROL Ciblage automatique] Activité Test A/B.
title: Comment créer une [!UICONTROL Ciblage automatique] Activité ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 48%

---

# Créez un [!UICONTROL Ciblage automatique] activité

Utilisez la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer votre [!UICONTROL Ciblage automatique] [!UICONTROL Test A/B] une activité directement sur une [!DNL Target]- et de modifier des parties de la page dans [!DNL Target].

>[!NOTE]
>
>Le [!UICONTROL ciblage automatique] fait partie de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md).

Pour créer une [!UICONTROL Ciblage automatique] activité :

1. Depuis la liste **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer l’activité]** > **[!UICONTROL Test A/B]**.

   ![Liste déroulante Créer une activité](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL Recommandations] est une [fonctionnalité Target Premium](/help/main/c-intro/intro.md#premium). Pour plus d’informations sur les différents types d’activité, voir [Activités](/help/main/c-activities/activities.md) et le [Target activities guide (Guide des activités Target)](/help/main/c-activities/target-activities-guide.md).

1. Sélectionner **[!UICONTROL Visuel]**, si nécessaire.

   Si vous préférez utiliser la variable [!UICONTROL Compositeur d’expérience d’après les formulaires], sélectionnez [!UICONTROL Formulaire]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >En plus du VEC et de [!UICONTROL Compositeur d’expérience d’après les formulaires], [!DNL Target] offre le compositeur d’expérience visuelle d’une seule page. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes client [Target Premium](/help/main/c-intro/intro.md#premium), choisissez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Spécifiez votre [URL d’activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md), puis cliquez sur **[!UICONTROL Suivant]**.

   Si votre compte est configuré avec une URL par défaut, cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL.

   Le [!UICONTROL compositeur d’expérience visuelle] s’ouvre, affichant la page indiquée dans l’URL.

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Saisissez un nom pour l’activité dans l’espace fourni.

   ![Champ Nom](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   Le nom de l’activité ne peut pas commencer par les caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

1. Créez des expériences en modifiant les éléments sur la page.

   La variable [!UICONTROL Compositeur d’expérience visuelle] affiche deux onglets sur le côté gauche après la création d’une activité : Expérience A et Expérience B. Expérience A est l’expérience de contrôle. Vous vous concentrez sur l’onglet Expérience B, que vous pouvez modifier selon vos besoins. L’expérience B est l’autre expérience que vous pouvez ajouter à votre test. Plusieurs expériences peuvent être ajoutées au test. Vous pouvez également supprimer l’Expérience A de l’activité si vous ne souhaitez pas que l’expérience de site par défaut soit une option possible.

   Pour plus d’informations sur l’ajout et la modification d’expériences dans le [!UICONTROL compositeur d’expérience visuelle], voir [Ajout d’une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Pour modifier l’Expérience B, commencez à l’étape 2.

1. Cliquez sur **[!UICONTROL Target]** dans la partie supérieure du [!UICONTROL Compositeur d’expérience visuelle] pour passer à l’étape suivante du workflow de tâches guidé en trois étapes.

   Le diagramme de flux s’ouvre.

   ![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité et la configuration des expériences.

1. Dans le [!UICONTROL Audience] , cliquez sur l’icône d’édition (points de suspension alignés verticalement), puis sur **[!UICONTROL Remplacer l’audience]**, puis [sélectionner l&#39;audience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) pour votre activité.

   Par défaut, l’audience est définie sur [!UICONTROL Tous les visiteurs].

1. Sélectionnez le pourcentage de visiteurs admissibles qui doivent entrer dans l’activité.

   ![Pourcentage d’audience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Configurez l’affectation de votre trafic.

   Vous pouvez proposer plusieurs expériences à une même audience. Un diagramme s’affiche, indiquant l’audience sélectionnée et les expériences ajoutées à l’activité.

   Choisissez la méthode d’affectation du trafic souhaitée. Pour créer une [!UICONTROL Ciblage automatique] activité, sélectionnez **[!UICONTROL Ciblage automatique pour les expériences personnalisées]**.

   Les trois types d’affectation de trafic sont décrits ci-dessous :

   * **[!UICONTROL Manuel (par défaut)]**: spécifiez le pourcentage souhaité de participants qui visualiseront chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %. Pour plus d’informations, voir [Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Affectation automatique à la meilleure expérience]**: la plupart des participants à l’activité sont automatiquement dirigés vers des expériences hautement performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Pour plus d’informations, voir [Présentation de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Ciblage automatique pour les expériences personnalisées]**: [!DNL Target] utilise l’apprentissage automatique avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par les responsables du marketing, puis en diffusant l’expérience la plus personnalisée aux visiteurs en fonction de leurs profils client individuels et des comportements antérieurs de visiteurs similaires.

   Cliquez également sur **[!UICONTROL Ajouter]** pour ajouter une autre expérience à l’activité.

1. Lorsque vous êtes satisfait de votre audience, des choix d’expérience et des choix d’affectation du trafic, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième étape du processus assisté en trois étapes.

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) pour l’activité.

   >[!NOTE]
   >
   >Si vous souhaitez utiliser [Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) avec cette activité, reportez-vous à des informations importantes dans [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** ou **[!UICONTROL Enregistrer]**.

Une fois l’activité créée, la variable [!UICONTROL Présentation] affiche des informations sur l’activité, y compris un diagramme de votre activité.

## Vidéo de formation : création de tests A/B (8 min 36)

Cette vidéo explique comment créer un test A/B à l’aide du processus assisté en trois étapes de [!DNL Target].

* Créez un [!UICONTROL Test A/B] activité dans [!DNL Adobe Target]
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/17391)
