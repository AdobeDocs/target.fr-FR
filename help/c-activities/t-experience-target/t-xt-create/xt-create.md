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
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# Création d’une activité de ciblage d’expérience{#create-an-experience-targeting-activity}

Utilisez [!UICONTROL le compositeur] d&#39;expérience visuelle pour créer une [!UICONTROL activité de ciblage] d&#39;expérience sur une page compatible Target et pour modifier des parties de la page dans [!DNL Adobe Target].

1. Depuis la liste [!UICONTROL Activités], cliquez sur **[!UICONTROL Créer l’activité]** &gt; **[!UICONTROL Ciblage d’expérience]**.

   ![Créer une activité &gt; Ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre compte Target. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, la personnalisation automatisée est une fonctionnalité [Target Premium](/help/c-intro/intro.md#premium).

   Pour plus d&#39;informations sur les types d&#39;activité, voir [Activités](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) et [types d&#39;activités Target](/help/c-activities/target-activities-guide.md).

1. Si nécessaire, sélectionnez **[!UICONTROL Visual (]** Valeur par défaut).

   ![Boîte de dialogue Créer une activité de ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez cette option. Voir [Compositeur d’expérience d’après les formulaires](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html).

   >[!NOTE]
   >
   >Outre le compositeur d&#39;expérience visuelle et le compositeur d&#39;expérience d&#39;après les formulaires, Target propose le compositeur d&#39;expérience visuelle d&#39;une seule page et le compositeur d&#39;expérience visuelle pour les applications mobiles. Pour plus d&#39;informations sur les divers compositeurs, voir [Expériences et offres](/help/c-experiences/experiences.md).

   Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).

1. Spécifiez l&#39;URL [de l&#39;activité](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), puis cliquez sur **[!UICONTROL Suivant]**.

   Si votre compte est configuré par une URL par défaut, cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL.

   Le compositeur d’expérience visuelle s’ouvre, affichant la page indiquée dans l’URL.

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

1. Créez de nouvelles expériences en modifiant les éléments sur la page.

   Pour obtenir des instructions pas à pas, voir [Ajouter une expérience](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

   Par défaut, le compositeur d’expérience visuelle n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez choisir de désactiver JavaScript si vous souhaitez pouvoir modifier ces éléments à l’aide du compositeur d’expérience visuelle.

   Lorsque vous pointez sur les éléments de votre page, ils sont mis en surbrillance. Tout élément surligné peut être modifié à l&#39;aide du compositeur d&#39;expérience visuelle. Pour obtenir la liste des actions pouvant être exécutées sur un élément pour modifier l&#39;expérience, voir [Options du compositeur d&#39;expérience visuelle](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Si vous créez une mbox sur la page à l’aide de Target Classic (anciennement Test&amp;Target), celle-ci apparaît comme un élément qui indique le nom de la mbox et qui peut être modifié comme tout autre élément.

1. Spécifiez les [objectifs et paramètres](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour l’activité.
