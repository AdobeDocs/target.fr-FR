---
keywords: Ciblage d’expérience;xt;créer
description: Découvrez comment utiliser le [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer un [!UICONTROL Ciblage d’expérience] (XT).
title: Comment créer une [!UICONTROL Ciblage d’expérience] Activité ?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 51%

---

# Créez un [!UICONTROL Ciblage d’expérience] Activité (XT)

Utilisez la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour créer une [!UICONTROL Ciblage d’expérience] (XT) sur une activité [!DNL Target]- et de modifier des parties de la page dans [!DNL Adobe Target].

Le [!UICONTROL ciblage d’expérience] (XT) diffuse un contenu à une audience spécifique selon un ensemble de règles et de critères définis par les spécialistes marketing.

Le ciblage d’expérience, qui inclut le [géociblage](/help/main/c-target/c-audiences/c-target-rules/geo.md), présente un atout majeur pour la définition de règles ciblant une expérience ou un contenu spécifique pour une audience particulière. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes.

Pour plus d’informations sur [!UICONTROL Ciblage d’expérience], un scénario de cas d’utilisation et des vidéos de formation, voir [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md).

**Pour créer une [!UICONTROL Ciblage d’expérience] activité :**

1. Depuis la liste [!UICONTROL Activités], cliquez sur **[!UICONTROL Créer l’activité]** > **[!UICONTROL Ciblage d’expérience]**.

   ![Créer une activité > Ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL Automated Personalization] est une fonctionnalité [Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

1. Si nécessaire, sélectionnez **[!UICONTROL visuelle (défaut)]**.

   Si vous préférez utiliser la variable [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez [!UICONTROL Formulaire].

   >[!NOTE]
   >
   >En plus du VEC et de [!UICONTROL Compositeur d’expérience d’après les formulaires], [!DNL Target] offre le compositeur d’expérience visuelle d’une seule page. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le compositeur d’expérience visuelle, voir [Résolution des problèmes du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes un [!DNL Target Premium] client, [choix d’un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   La variable [!UICONTROL Choisir l’espace de travail] est une [Target Premium](/help/main/c-intro/intro.md) fonction . Si votre organisation dispose d’un [!DNL Target Standard] si vous ne voyez pas cette option.

1. Spécifiez votre [URL d’activité](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), puis cliquez sur **[!UICONTROL Créer]**.

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

   Le nom de l’activité ne peut pas contenir l’une des séquences de caractères suivantes :

   | Séquence de caractères | Description |
   |--- |--- |
   | ;= | Point-virgule, égal à |
   | ;+ | Point-virgule, plus |
   | ;- | Point-virgule, moins |
   | ;@ | Point-virgule, signe At |
   | ,= | Virgule, Égal à |
   | ,+ | Virgule, Plus |
   | ,- | Virgule, Moins |
   | ,@ | Virgule, signe At |
   | `[`&quot; | Crochets droits ouverts, guillemets doubles |
   | &quot;`]` | Guillemets doubles, crochet fermant |

1. Créez de nouvelles expériences ciblées sur différentes audiences.

   Pour obtenir des instructions pas à pas, voir [Ajouter une expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour l’activité.
