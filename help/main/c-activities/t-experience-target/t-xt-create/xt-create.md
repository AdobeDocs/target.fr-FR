---
keywords: Ciblage d’expérience;xt;créer
description: Découvrez comment utiliser le [!UICONTROL Visual Experience Composer] (VEC) dans  [!DNL Adobe Target]  pour créer une activité [!UICONTROL Experience Targeting] (XT).
title: Comment créer une activité [!UICONTROL Experience Targeting] ?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# Créer une activité [!UICONTROL Experience Targeting] (XT)

Utilisez le [!UICONTROL Visual Experience Composer] (VEC) pour créer une activité [!UICONTROL Experience Targeting] (XT) sur une page [!DNL Target] et pour modifier des parties de la page dans [!DNL Adobe Target].

[!UICONTROL Experience Targeting] (XT) diffuse du contenu à une audience spécifique selon un ensemble de règles et de critères définis par le marketeur.

[!UICONTROL Experience Targeting], y compris le [géociblage](/help/main/c-target/c-audiences/c-target-rules/geo.md), est utile pour définir des règles qui ciblent une expérience ou un contenu spécifique pour une audience particulière. Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes.

Pour plus d’informations sur [!UICONTROL Experience Targeting], un scénario de cas d’utilisation et des vidéos de formation, voir [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md).

**Pour créer une activité [!UICONTROL Experience Targeting] :**

1. Dans la liste [!UICONTROL Activities], cliquez sur **[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]**.

   ![Créer une activité > Ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL Automated Personalization] est une [fonctionnalité Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

1. Sélectionnez **[!UICONTROL Visual (Default)]**, si nécessaire.

   Si vous préférez utiliser le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez [!UICONTROL Form].

   >[!NOTE]
   >
   >Outre le VEC et [!UICONTROL Form-Based Experience Composer], [!DNL Target] offre le VEC d’application d’une seule page. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le compositeur d’expérience visuelle, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes un client [!DNL Target Premium], [choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   L’option [!UICONTROL Choose Workplace] est une fonctionnalité [Target Premium](/help/main/c-intro/intro.md). Si votre entreprise dispose d’une licence [!DNL Target Standard], si cette option ne s’affiche pas.

1. Spécifiez votre [URL d’activité](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), puis cliquez sur **[!UICONTROL Create]**.

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
   | ; - | Point-virgule, moins |
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
