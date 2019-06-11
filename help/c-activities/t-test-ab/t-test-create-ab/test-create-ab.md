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
source-git-commit: 634ea3ccbd875aff27391e79812028f236f53608

---


# Création d’un test A/B{#create-an-a-b-test}

Utilisez le compositeur d’expérience visuelle de Target pour faciliter la création directe de votre test sur une page activée pour Target et la modification de parties de la page dans Target.

1. Depuis la liste [!UICONTROL Activités], cliquez sur **[!UICONTROL Créer une activité]** &gt; **[!UICONTROL Test A/B]**.

   ![Liste déroulante Créer une activité](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple [!UICONTROL , Recommandations] est une [fonctionnalité Target Premium](/help/c-intro/intro.md#premium).

   Pour plus d&#39;informations sur les différents types d&#39;activité, voir [Activités](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) et Guide des activités [Target](/help/c-activities/target-activities-guide.md).

   ![Créer une boîte de dialogue Activité de test A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newactivityurl-new.png)

1. Si nécessaire, sélectionnez **[!UICONTROL Visual (]** Valeur par défaut).

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez l’option [!UICONTROL Formulaire]. Voir [Compositeur d&#39;expérience d&#39;après les formulaires](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) pour en savoir plus.

   >[!NOTE]
   >
   >Outre le compositeur d&#39;expérience visuelle et le compositeur d&#39;expérience visuelle d&#39;après les formulaires, Target propose le compositeur d&#39;expérience visuelle d&#39;une seule page et le compositeur d&#39;expérience visuelle pour les applications mobiles. Pour plus d&#39;informations sur les différents vecteurs, voir [Expériences et offres](/help/c-experiences/experiences.md).

   Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).

1. (Conditionnel) Si vous êtes client [Target Premium](/help/c-intro/intro.md#premium) , choisissez un [espace de travail](/help/administrating-target/c-user-management/property-channel/property-channel.md).


1. Spécifiez l&#39;URL [de l&#39;activité](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), puis cliquez sur **[!UICONTROL Suivant]**.

   Si votre compte est configuré par une URL par défaut, cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL.

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

   Pour plus d’informations sur l’ajout et la modification d’expériences dans le [!UICONTROL compositeur d’expérience visuelle], voir [Ajout d’une expérience](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Pour modifier l’Expérience B, commencez à l’étape 3.

1. Cliquez **[!UICONTROL sur Ciblage]** dans la partie supérieure du compositeur d&#39;expérience [!UICONTROL visuelle] pour passer à l&#39;étape suivante du workflow assisté en trois étapes.

   Le diagramme de flux s’ouvre.

   ![Étape Ciblage des tests A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité et la configuration des expériences.
1. Dans la partie [!UICONTROL Audience], cliquez sur l’icône de modification, puis [sélectionnez l’audience](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) pour votre activité.

   Par défaut, l’audience est définie sur Tous les visiteurs.

1. Sélectionnez le pourcentage de visiteurs admissibles qui doivent entrer dans l’activité.

   ![Pourcentage d&#39;audience](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Configurez l’affectation de votre trafic.

   Vous pouvez proposer plusieurs expériences à une même audience. Un diagramme s’affiche pour indiquer l’audience sélectionnée et les expériences ajoutées à l’activité.

   Choisissez la méthode d&#39;affectation du trafic souhaitée :

   * **[!UICONTROL Manuel (par défaut)]**: Indiquez le pourcentage de participants à afficher chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %.

   * **[!UICONTROL Affectation automatique à la meilleure expérience]**: La plupart des participants à l&#39;activité sont automatiquement dirigés vers les expériences hautement performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Voir [Affectation automatisée du trafic](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Ciblage automatique pour les expériences personnalisées]**: Target utilise des algorithmes avancés d&#39;apprentissage automatique pour cibler automatiquement les visiteurs avec la meilleure expérience pour optimiser vos objectifs. Pour plus d’informations, voir [Ciblage automatique pour optimiser](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).
   Vous pouvez également cliquer sur **[!UICONTROL Ajouter une expérience]** pour ajouter une autre expérience à l’activité.

1. Une fois satisfait de votre audience et de vos choix d’expérience, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième et dernière étape du flux de tâches guidé en trois étapes.

1. Spécifiez les [objectifs et paramètres](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour l’activité.

   ![Paramètres d&#39;activité A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Une fois que vous avez créé l’activité, l’onglet Aperçu affiche des informations sur cette dernière, notamment un diagramme.

## Vidéo de formation : création de tests A/B (8 min 36)

Cette vidéo explique comment créer un test A/B à l’aide du processus assisté en trois étapes de [!DNL Target].

* Créer une activité A/B dans Adobe Target
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/17391?captions=fre_fr)
