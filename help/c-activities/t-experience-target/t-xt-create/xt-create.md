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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Création d’une activité de ciblage d’expérience{#create-an-experience-targeting-activity}

Use the [!UICONTROL Visual Experience Composer] (VEC) to create an [!UICONTROL Experience Targeting] (XT) activity on a Target-enabled page and to modify portions of the page within [!DNL Adobe Target].

Le ciblage d’expérience (XT) diffuse le contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables du marketing.

Experience Targeting, including [geo-targeting](/help/c-target/c-audiences/c-target-rules/geo.md), is valuable for defining rules that target a specific experience or content to a particular audience. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes.

For more information about Experience Targeting, a use-case scenario, and training videos, see [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md).

**Pour créer une activité de ciblage d&#39;expérience :**

1. Depuis la liste [!UICONTROL Activités], cliquez sur **[!UICONTROL Créer l’activité]** &gt; **[!UICONTROL Ciblage d’expérience]**.

   ![Créer une activité &gt; Ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre compte Target. Certains types d’activité peuvent ne pas apparaître dans votre liste. For example, [!UICONTROL Automated Personalization] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For more information about the various activity types available in [!DNL Target] and their differences, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). See [Target Activity types](/help/c-activities/target-activities-guide.md) to help you decide which activity type best suites your needs.

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![Boîte de dialogue Créer une activité de ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez l’option [!UICONTROL Formulaire]. See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >Outre le compositeur d&#39;expérience visuelle et le compositeur d&#39;expérience d&#39;après les formulaires, Target propose le compositeur d&#39;expérience visuelle d&#39;une seule page et le compositeur d&#39;expérience visuelle pour les applications mobiles. For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [!UICONTROL Choose Workplace] option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Votre entreprise dispose d&#39;une licence Target Standard si vous ne voyez pas cette option.]

1. (Conditional) If you are a Target Premium customer, [choose a workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Specify your [activity URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), then click **[!UICONTROL Next]**.

   If your account is [configured with a default URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md), that URL appears by default. Si nécessaire, vous pouvez passer de la valeur par défaut à une autre URL.

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

   For step-by-step instructions, see [Add experience](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Spécifiez les [objectifs et paramètres](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour l’activité.