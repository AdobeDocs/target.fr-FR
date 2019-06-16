---
description: Utilisation du compositeur d’expérience visuelle pour créer une activité de ciblage d’expérience sur une page Target et pour modifier des parties de la page dans Target.
seo-description: Utilisez le compositeur d'expérience visuelle pour créer une activité de ciblage d'expérience sur une page compatible Target et pour modifier des parties de la page dans Adobe Target.
seo-title: Création d’une activité de ciblage d’expérience
solution: Target
subtopic: Test multivarié
title: Création d’une activité de ciblage d’expérience
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: c6085fae6428cb837eed6eadd778140687348817

---


# Création d’une activité de ciblage d’expérience{#create-an-experience-targeting-activity}

Utilisez [!UICONTROL le compositeur] d&#39;expérience visuelle pour créer une [!UICONTROL activité de ciblage] d&#39;expérience sur une page compatible Target et pour modifier des parties de la page dans [!DNL Adobe Target].

Le ciblage d’expérience (XT) diffuse le contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables du marketing.

Le ciblage d&#39;expérience, y compris [le ciblage géographique](/help/c-target/c-audiences/c-target-rules/geo.md), est utile pour définir des règles qui ciblent une expérience ou un contenu spécifique à une audience particulière. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes.

Pour plus d&#39;informations sur le ciblage d&#39;expérience, un scénario de cas d&#39;utilisation et des vidéos de formation, voir [Ciblage d&#39;expérience](/help/c-activities/t-experience-target/experience-target.md).

**Pour créer une activité de ciblage d&#39;expérience :**

1. Depuis la liste [!UICONTROL Activités], cliquez sur **[!UICONTROL Créer l’activité]** &gt; **[!UICONTROL Ciblage d’expérience]**.

   ![Créer une activité &gt; Ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre compte Target. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL la personnalisation automatisée] est une fonctionnalité [Target Premium](/help/c-intro/intro.md#premium).
   >
   >Pour plus d&#39;informations sur les différents types d&#39;activité disponibles [!DNL Target] et leurs différences, voir [Activités](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Pour [plus d&#39;informations, reportez-vous à la](/help/c-activities/target-activities-guide.md) section Types d&#39;activité Target pour déterminer les types d&#39;activité qui conviennent le mieux à vos besoins.

1. Si nécessaire, sélectionnez **[!UICONTROL Visual (]** Valeur par défaut).

   ![Boîte de dialogue Créer une activité de ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez l’option [!UICONTROL Formulaire]. Voir [Compositeur d&#39;expérience d&#39;après les formulaires](/help/c-experiences/form-experience-composer.md) pour en savoir plus.

   >[!NOTE]
   >
   >Outre le compositeur d&#39;expérience visuelle et le compositeur d&#39;expérience d&#39;après les formulaires, Target propose le compositeur d&#39;expérience visuelle d&#39;une seule page et le compositeur d&#39;expérience visuelle pour les applications mobiles. Pour plus d&#39;informations sur les divers compositeurs, voir [Expériences et offres](/help/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >L&#39;option [!UICONTROL Choisir le lieu de travail] de l&#39;illustration précédente est une [fonction Target Premium](/help/c-intro/intro.md) . Votre entreprise dispose d&#39;une licence Target Standard si vous ne voyez pas cette option.]

1. (Conditionnel) Si vous êtes client Target Premium, [choisissez un espace de travail](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Spécifiez l&#39;URL [de l&#39;activité](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), puis cliquez sur **[!UICONTROL Suivant]**.

   Si votre compte est [configuré avec une URL par défaut](/help/administrating-target/r-target-account-preferences/target-account-preferences.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez passer de la valeur par défaut à une autre URL.

   Le compositeur d&#39;expérience visuelle s&#39;ouvre, montrant la page spécifiée dans l&#39;URL.

   ![Activité de ciblage d&#39;expérience dans le compositeur d&#39;expérience visuelle](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Saisissez un nom pour l’activité dans l’espace fourni.

   ![Champ Nom](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. Créez de nouvelles expériences ciblées sur les audiences de différence.

   Pour obtenir des instructions pas à pas, voir [Ajouter une expérience](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Spécifiez les [objectifs et paramètres](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour l’activité.