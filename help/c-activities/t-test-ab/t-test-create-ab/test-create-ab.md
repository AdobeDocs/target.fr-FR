---
description: Utilisez le compositeur d’expérience visuelle de Target pour faciliter la création directe de votre test sur une page activée pour Target et la modification de parties de la page dans Target.
keywords: Créer A/B;test A/B;activité A/B;nouvelle activité A/B
seo-description: Utilisez le compositeur d’expérience visuelle de Target pour faciliter la création directe de votre test sur une page activée pour Target et la modification de parties de la page dans Target.
seo-title: Création d’un test A/B
solution: Target
title: Création d’un test A/B
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Création d’un test A/B{#create-an-a-b-test}

Utilisez le compositeur d’expérience visuelle de Target pour faciliter la création directe de votre test sur une page activée pour Target et la modification de parties de la page dans Target.

1. Depuis la liste [!UICONTROL Activités], cliquez sur **[!UICONTROL Créer une activité]** &gt; **[!UICONTROL Test A/B]**.

   ![](assets/ab_select.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste.

   Pour plus d’informations sur les différents types d’activité, voir  [Activités](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

   ![](assets/ab_newactivityurl.png)

1. Sélectionnez **[!UICONTROL Compositeur d’expérience visuelle]**, si nécessaire.

   Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez cette option. Voir [Compositeur d’expérience d’après les formulaires](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html).
1. Spécifiez votre [URL d’activité](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), puis cliquez sur **[!UICONTROL Créer]**.

   Si votre compte est configuré par une URL par défaut, cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL.

   Le [!UICONTROL compositeur d’expérience visuelle] s’ouvre, affichant la page indiquée dans l’URL.

   ![](assets/vec.png)

1. Saisissez un nom pour l’activité dans l’espace fourni.

   ![](assets/ab_newname.png)

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

   Pour plus d’informations sur l’ajout et la modification d’expériences dans le [!UICONTROL compositeur d’expérience visuelle], voir  [Ajout d’une expérience](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Pour modifier l’Expérience B, commencez à l’étape 3.

1. Cliquez sur **[!UICONTROL Target]** dans la partie supérieure du [!UICONTROL Compositeur d’expérience visuelle] pour passer à l’étape suivante du flux de tâches guidé en trois étapes.

   Le diagramme de flux s’ouvre.

   ![](assets/ab_flow.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité et la configuration des expériences.
1. Dans la partie [!UICONTROL Audience], cliquez sur l’icône de modification, puis [sélectionnez l’audience](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) pour votre activité.

   Par défaut, l’audience est définie sur Tous les visiteurs. 1. Sélectionnez le pourcentage de visiteurs admissibles qui doivent entrer dans l’activité.

   ![](assets/audperc.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».
1. Configurez l’affectation de votre trafic.

   Vous pouvez proposer plusieurs expériences à une même audience. Un diagramme s’affiche pour indiquer l’audience sélectionnée et les expériences ajoutées à l’activité.

   Si vous sélectionnez **[!UICONTROL Manuel]**, spécifiez le pourcentage souhaité de participants qui visualiseront chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %.

   Si vous sélectionnez **[!UICONTROL Affecter automatiquement à la meilleure expérience], la plupart des participants aux activités sont automatiquement dirigés vers les expériences les plus performantes.** Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Voir [Affectation automatisée du trafic](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   Lorsque vous sélectionnez **[!UICONTROL Ciblage automatique pour optimiser]**, Target utilise des algorithmes avancés d’apprentissage pour cibler automatiquement les visiteurs avec la meilleure expérience afin d’optimiser vos objectifs.

   >[!NOTE]
   >
   >Cette offre de « premier regard » est activée pour quelques clients seulement dans cette version, à des fins de test et réactions.

   Pour plus d’informations, voir [Ciblage automatique pour optimiser](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

   Vous pouvez également cliquer sur **[!UICONTROL Ajouter une expérience]** pour ajouter une autre expérience à l’activité.
1. Une fois satisfait de votre audience et de vos choix d’expérience, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième et dernière étape du flux de tâches guidé en trois étapes.
1. Spécifiez les [objectifs et paramètres](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour l’activité.

   ![](assets/ab_settings.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Une fois que vous avez créé l’activité, l’onglet Aperçu affiche des informations sur cette dernière, notamment un diagramme.

## Vidéo de formation : création de tests A/B (8 min 36)

Cette vidéo explique comment créer un test A/B à l’aide du processus assisté en trois étapes de [!DNL Target].

* Créer une activité A/B dans Adobe Target
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/17391)
