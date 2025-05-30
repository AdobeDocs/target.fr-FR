---
keywords: Créer un ciblage automatique;test A/B;activité de ciblage automatique;nouvelle activité a/b;ciblage automatique;ciblage automatique pour les expériences personnalisées;personnalisé;optimisation
description: Découvrez comment utiliser le [!UICONTROL Visual Experience Composer] (VEC) dans  [!DNL Adobe Target]  créer une activité de test A/B [!UICONTROL Auto-Target].
title: Comment créer une activité [!UICONTROL Auto-Target] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 43%

---

# Création d’une activité [!UICONTROL Auto-Target]

Utilisez le [!UICONTROL Visual Experience Composer] (VEC) de [!DNL Adobe Target] pour créer votre activité [!UICONTROL Auto-Target] [!UICONTROL A/B Test] directement sur une page compatible avec les [!DNL Target] et pour modifier des parties de la page dans [!DNL Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] est disponible dans le cadre de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md).

Pour créer une activité [!UICONTROL Auto-Target] :

1. Dans la liste **[!UICONTROL Activities]**, cliquez sur **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Liste déroulante Créer une activité](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL Recommendations] est une fonctionnalité [Target Premium](/help/main/c-intro/intro.md#premium). Pour plus d’informations sur les différents types d’activité, voir [Activités](/help/main/c-activities/activities.md) et le [Target activities guide (Guide des activités Target)](/help/main/c-activities/target-activities-guide.md).

1. Sélectionnez **[!UICONTROL Visual]**, si nécessaire.

   Si vous préférez utiliser le [!UICONTROL Form-Based Experience Composer], sélectionnez [!UICONTROL Form]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le compositeur d’expérience visuelle et le [!UICONTROL Form-Based Experience Composer], [!DNL Target] propose le compositeur d’expérience visuelle d’application monopage (VEC). Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes client [Target Premium](/help/main/c-intro/intro.md#premium), choisissez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Indiquez votre [URL d’activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) puis cliquez sur **[!UICONTROL Next]**.

   Si votre compte est configuré avec une URL par défaut, cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL.

   La [!UICONTROL Visual Experience Composer] s’ouvre et affiche la page spécifiée dans l’URL.

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Saisissez un nom pour l’activité dans l’espace fourni.

   ![Champ Nom](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   Le nom de l’activité ne peut pas commencer par l’un des caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

1. Créez des expériences en modifiant les éléments de la page.

   Le [!UICONTROL Visual Experience Composer] affiche deux onglets sur le côté gauche après la création d’une activité : Expérience A et Expérience B. L’expérience A est l’expérience de contrôle. Vous vous concentrez sur l’onglet Expérience B, que vous pouvez modifier selon vos besoins. L’expérience B est l’autre expérience que vous pouvez ajouter à votre test. Plusieurs expériences peuvent être ajoutées au test. Vous pouvez également supprimer l’Expérience A de l’activité si vous ne souhaitez pas que l’expérience de site par défaut soit une option possible.

   Pour plus d’informations sur l’ajout et la modification d’expériences dans le [!UICONTROL Visual Experience Composer], voir [Ajouter une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Pour modifier l’Expérience B, commencez à l’étape 2.

1. Cliquez sur **[!UICONTROL Targeting]** en haut de la [!UICONTROL Visual Experience Composer] pour passer à l’étape suivante du workflow guidé en trois étapes.

   Le diagramme de flux s’ouvre.

   ![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité et la configuration des expériences.

1. Dans la zone de [!UICONTROL Audience], cliquez sur l’icône de modification (les points de suspension verticaux), cliquez sur **[!UICONTROL Replace Audience]**, puis [sélectionnez l’audience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) pour votre activité.

   Par défaut, l’audience est définie sur [!UICONTROL All Visitors].

1. Sélectionnez le pourcentage de visiteurs admissibles qui doivent entrer dans l’activité.

   ![Pourcentage d’audience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Configurez l’affectation de votre trafic.

   Vous pouvez proposer plusieurs expériences à une même audience. Un diagramme affiche l’audience sélectionnée et les expériences que vous avez ajoutées à l’activité.

   Choisissez la méthode d’affectation du trafic souhaitée. Pour créer une activité [!UICONTROL Auto-Target], sélectionnez **[!UICONTROL Auto-Target for personalized experiences]**.

   Les trois types d’affectation du trafic sont décrits ci-dessous :

   * **[!UICONTROL Manual (Default)]** : indiquez le pourcentage de participants qui doivent voir chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %. Pour plus d’informations, voir [Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-Allocate to best experience]** : la plupart des participants aux activités sont automatiquement redirigés vers des expériences plus performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Pour plus d’informations, voir [ Aperçu de l’affectation automatique ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Auto-Target for personalized experiences]** : [!DNL Target] utilise un machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing, puis en offrant l’expérience la plus adaptée aux visiteurs et visiteuses en fonction de leurs profils clients individuels et des comportements passés de visiteurs et visiteuses similaires.

   Vous pouvez également cliquer sur **[!UICONTROL Add]** pour ajouter une autre expérience à l’activité.

1. Lorsque vous êtes satisfait de votre audience, de vos choix d’expérience et de vos choix d’affectation du trafic, cliquez sur **[!UICONTROL Next]** pour passer à la troisième étape du workflow guidé en trois étapes.

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) pour l’activité.

   >[!NOTE]
   >
   >Si vous souhaitez utiliser [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) avec cette activité, reportez-vous à la section informations importantes dans Prise en charge d’[A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Cliquez sur **[!UICONTROL Save & Close]** ou **[!UICONTROL Save]**.

Après avoir créé l’activité, l’onglet [!UICONTROL Overview] affiche des informations sur l’activité, y compris un diagramme de votre activité.

## Vidéo de formation : création de tests A/B (8 min 36)

Cette vidéo explique comment créer un test A/B à l’aide du processus assisté en trois étapes de [!DNL Target].

* Création d’une activité [!UICONTROL A/B Test] dans [!DNL Adobe Target]
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/29261?captions=fre_fr)
