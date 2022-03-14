---
keywords: Ciblage d’expérience;xt;créer
description: Découvrez comment utiliser le compositeur d’expérience visuelle (VEC) dans Adobe [!DNL Target] pour créer une activité de ciblage d’expérience (XT) sur une page activée pour Target.
title: Comment créer une activité de ciblage d’expérience ?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 89%

---

# Création d’une activité de ciblage d’expérience

Utilisation du [!UICONTROL compositeur d’expérience visuelle (VEC)] pour créer une activité de [!UICONTROL ciblage d’expérience] (XT) sur une page Target et pour modifier des parties de la page dans [!DNL Adobe Target].

Le ciblage d’expérience (XT) diffuse le contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables du marketing.

Le ciblage d’expérience, qui inclut le [géociblage](/help/main/c-target/c-audiences/c-target-rules/geo.md), présente un atout majeur pour la définition de règles ciblant une expérience ou un contenu spécifique pour une audience particulière. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes.

Pour plus d’informations sur le ciblage d’expérience, un scénario de cas d’utilisation et des vidéos de formation, voir [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md).

**Pour créer une activité de ciblage d’expérience :**

1. Depuis la liste [!UICONTROL Activités], cliquez sur **[!UICONTROL Créer l’activité]** > **[!UICONTROL Ciblage d’expérience]**.

   ![Créer une activité > Ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre compte Target. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL Automated Personalization] est une fonctionnalité [Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

1. Si nécessaire, sélectionnez **[!UICONTROL visuelle (défaut)]**.

   ![Boîte de dialogue Créer une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez l’option [!UICONTROL Formulaire]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le VEC et le compositeur d’expérience d’après les formulaires, Target propose le compositeur d’expérience visuelle d’une seule page et le compositeur d’expérience visuelle pour les applications mobiles. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >L’option [!UICONTROL Choisir l’espace de travail] de l’illustration précédente est une fonction [Target Premium](/help/main/c-intro/intro.md). Votre entreprise dispose d’une licence Target Standard si vous ne voyez pas cette option.

1. (Conditionnel) Si vous êtes client Target Premium, [choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Spécifiez votre [URL d’activité](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), puis cliquez sur **[!UICONTROL Suivant]**.

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL, si nécessaire.

   Le VEC s’ouvre, affichant la page indiquée dans l’URL.

   ![Activité de ciblage d’expérience dans le VEC](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Saisissez un nom pour l’activité dans l’espace fourni.

   ![Champ Nom](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   Le nom de l’activité ne peut pas commencer par les caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

1. Créez de nouvelles expériences ciblées pour différencier les audiences.

   Pour obtenir des instructions pas à pas, voir [Ajouter une expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour l’activité.
