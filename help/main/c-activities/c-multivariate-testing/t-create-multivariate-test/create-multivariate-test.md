---
keywords: mvt;test multivarié;créer un test multivarié;création de test multivarié;créer un mvt;création de mvt;comment mvt;comment test multivarié
description: Découvrez comment utiliser le [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer un [!UICONTROL Test multivarié] (MVT).
title: Comment créer une [!UICONTROL Test multivarié]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 63%

---

# Création d’un test multivarié

La variable [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] facilite la création d’un [!UICONTROL Test multivarié] et de modifier des parties de la page dans [!DNL Target].

La variable [!DNL Target] l’éditeur pointer-cliquer permet de sélectionner n’importe quel emplacement et d’ajouter plusieurs offres.

Le [!UICONTROL test multivarié] (MVT) utilise un rapport de type « page-premier ». En d’autres termes, le test s’exécute sur une URL spécifique, avec des expériences que vous concevez pour cette page.

1. Cliquez sur **[!UICONTROL Créer l’activité]** > **[!UICONTROL Test multivarié]**.

   ![Création d’un test multivarié](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

1. (Conditionnel) Choisissez le type de diffusion : [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL Email], ou [!UICONTROL Autre/API].

1. (Conditionnel) Si vous êtes un [Target Premium](/help/main/c-intro/intro.md#premium) client, [choix d’un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Définition de l’URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) pour la page à tester, puis cliquez sur **[!UICONTROL Suivant]**.

   >[!NOTE]
   >
   >Utilisez une URL complète, y compris HTTP ou HTTPS au début.

   Si un message s’affiche vous demandant d’activer votre navigateur pour le contenu mixte, suivez les instructions du message. Après avoir activé votre navigateur pour le contenu mixte, recommencez à l’étape 1.

   La variable [!UICONTROL Compositeur d’expérience visuelle] s’ouvre.

1. Entrez le nom de l’activité.

   ![Champ Nom de l’activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

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

1. [Créez les offres à chaque emplacement](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   ![Boîte de dialogue Modifier le texte/HTML](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Vous pouvez ajouter les types d’offres suivants :

   * HTML
   * Image
   * Texte

1. Cliquez sur **[!UICONTROL Aperçu]** pour [prévisualiser vos expériences](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![Aperçu des expériences](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   Vous pouvez afficher chaque expérience et exclure toute expérience que vous ne souhaitez pas inclure dans votre test. Pour exclure une ou plusieurs expériences, cochez les cases de votre choix, puis cliquez sur **[!UICONTROL Exclure]**.

   ![Exclusion d’expériences](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [Utilisez l’estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) afin de tester la faisabilité de votre plan de test.

   ![Indicateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   L’illustration suivante indique que le trafic de l’activité n’est pas suffisant.

   ![image estimateur](assets/estimator.png)

   L’illustration suivante indique que le trafic de l’activité n’est pas suffisant.

   ![image estimator2](assets/estimator2.png)

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder à la page [!UICONTROL Ciblage.]

1. Sélectionnez l’audience et le pourcentage des visiteurs admissibles qui doivent entrer dans l’activité.

   ![Page de ciblage dans l’activité MVT](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. [Révisez le résumé du test](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) et apportez toute modification souhaitée, puis cliquez sur **[!UICONTROL Continuer]**.

1. [Spécifiez les objectifs et paramètres](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour le test.

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** afin de créer l’activité.

## Vidéo de formation : création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du [!DNL Target] processus assisté en trois étapes.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)
