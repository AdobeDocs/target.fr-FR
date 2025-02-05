---
keywords: mvt;test multivarié;créer un test multivarié;création de test multivarié;créer un mvt;création de mvt;comment mvt;comment test multivarié
description: Découvrez comment utiliser le [!UICONTROL Visual Experience Composer] (VEC) dans  [!DNL Adobe Target]  créer un [!UICONTROL Multivariate Test] (MVT).
title: Comment créer un [!UICONTROL Multivariate Test] ?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: be118753eed999ce24d547c90ac9d195cce7e9e9
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 26%

---

# Création d’un test multivarié

Le [!UICONTROL Visual Experience Composer] (VEC) d’[!DNL Adobe Target] facilite la création d’un [!UICONTROL Multivariate Test] et la modification de parties de la page dans [!DNL Target].

L’éditeur [!DNL Target] de pointer-cliquer vous permet de sélectionner n’importe quel emplacement et d’ajouter plusieurs offres.

Le [!UICONTROL Multivariate Test] (MVT) prend un rapport page-première. En d’autres termes, le test s’exécute sur une URL spécifique, avec des expériences que vous concevez pour cette page.

1. Cliquez sur **[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**.

   >[!NOTE]
   >
   >Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

1. (Conditionnel) Choisissez le type de diffusion : [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL Email] ou [!UICONTROL Other/API].

1. (Conditionnel) Si vous êtes un client [Target Premium](/help/main/c-intro/intro.md#premium), [choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Spécifiez l’URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) de la page à tester, puis cliquez sur **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >Utilisez une URL complète, en commençant par HTTP ou HTTPS.

   Si un message s’affiche vous demandant d’activer votre navigateur pour le contenu mixte, suivez les instructions du message. Après avoir activé votre navigateur pour le contenu mixte, recommencez à l’étape 1.

   La [!UICONTROL Visual Experience Composer] s’ouvre.

1. 
   1. Cliquez sur l’icône **[!UICONTROL Rename]** ( ![Icône Renommer](/help/main/assets/icons/MoreSmallListVert.svg) ), cliquez sur **[!UICONTROL Rename]**, attribuez un nom à l’activité, puis cliquez sur **[!UICONTROL Save]**.

   Le nom de l’activité ne peut pas commencer par l’un des caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

   Le nom de l’activité ne peut pas contenir l’une des séquences de caractères suivantes :

   | Séquence De Caractères | Description |
   |--- |--- |
   | ;= | Point-virgule, égal à |
   | ;+ | Point-virgule plus |
   | ;- | Point-virgule, moins |
   | ;@ | Point-virgule, signe At |
   | ,= | Virgule, est égal à |
   | ,+ | Virgule, Plus |
   | ,- | Virgule, Moins |
   | ,@ | Virgule, Au signe |
   | `[` » | Crochet ouvert, guillemets doubles |
   |  »`]` | Guillemets doubles, crochet fermant |

1. [Créez les offres à chaque emplacement](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Vous pouvez ajouter les types d’offres suivants :

   * HTML
   * Image
   * Texte

1. Cliquez sur **[!UICONTROL Preview]** pour [prévisualiser vos expériences](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Cliquez sur l’icône **[!UICONTROL Show Experiences]** ( ![icône Afficher les expériences](/help/main/assets/icons/WebPages.svg) ) pour afficher la liste de toutes les expériences dans le cadre de gauche.

1. Cliquez sur une expérience spécifique dans la liste pour l’afficher.

1. (Conditionnel) Pour exclure une ou plusieurs expériences de l’activité, cliquez sur l’icône **[!UICONTROL Manage Content]** ( ![icône Gérer les expériences](/help/main/assets/icons/Experience.svg) ) pour afficher la boîte de dialogue [!UICONTROL Manage Experiences].

1. (Conditionnel) Dans la boîte de dialogue [!UICONTROL Manage Experiences], cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de l’expérience à exclure, puis cliquez sur **[!UICONTROL Exclude]**.

   Vous pouvez choisir d’exclure une expérience qui affiche des variations en conflit ou une expérience qui n’est pas équilibrée esthétiquement.

1. (Conditionnel) Pour exclure plusieurs expériences, cochez les cases correspondant aux expériences souhaitées, puis cliquez sur **[!UICONTROL Exclude]**.

1. [Utilisez l’estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) afin de tester la faisabilité de votre plan de test.

1. Cliquez sur **[!UICONTROL Next]** pour accéder à la page [!UICONTROL Targeting].

   L’étape **Ciblage** vous est familière si vous avez utilisé d’autres types d’activités [!DNL Target]. Ici, vous pouvez sélectionner une audience et spécifier le pourcentage de visiteurs et visiteuses qui voient chaque expérience.

   Le diagramme de flux vous guide tout au long des étapes d’affectation d’une audience et de son pourcentage de trafic, de sélection de la méthode d’affectation du trafic et de spécification de l’affectation du trafic pour chaque expérience de l’activité.

1. (Conditionnel) Cliquez sur le contrôle **[!UICONTROL All Visitors]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL All Visitors] est définie comme audience par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

   1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Replace]** ( ![icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.
   1. Dans la boîte de dialogue [!UICONTROL Add Audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) puis cliquez sur **[!UICONTROL Assign Audience]**.

      Vous pouvez cliquer sur **Combiner les audiences** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

      Si vous devez créer une nouvelle audience qui n’est pas encore dans le [!UICONTROL Audience Library], cliquez sur **Créer une audience**. Au cours du workflow [création d’audience](/help/main/c-target/c-audiences/audiences.md) vous pouvez choisir parmi les options suivantes :

      * **[!UICONTROL Audience Library]** : créez une audience à la demande qui est enregistrée dans le [!UICONTROL Audience Library] et qui peut être réutilisée dans d’autres activités.
      * **[!UICONTROL This activity only]** : créez une [audience spécifique à l’activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans le [!UICONTROL Audience Library] et qui ne peut être utilisée que dans l’activité actuelle.

   1. Cliquez sur **[!UICONTROL Visitor Percentage]** dans le cadre de droite, puis choisissez le pourcentage de visiteurs qualifiés qui souhaitent rejoindre l’activité.

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. [Consultez le résumé du test](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) apportez les modifications souhaitées, puis cliquez sur **[!UICONTROL Next]**.

1. [Spécifiez les objectifs et paramètres](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour le test.

1. Cliquez sur **[!UICONTROL Save and Close]** pour créer l’activité.

## Vidéo de formation : Création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du workflow guidé en trois étapes [!DNL Target].

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)
