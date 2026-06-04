---
keywords: mvt;test multivarié;créer un test multivarié;création de test multivarié;créer un mvt;création de mvt;comment mvt;comment test multivarié
description: Découvrez comment utiliser le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans  [!DNL Adobe Target]  pour créer un [!UICONTROL test multivarié] (MVT).
title: Comment créer un [!UICONTROL test multivarié] ?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 809
ht-degree: 23%

---

# Création d’un test multivarié

Le [!UICONTROL compositeur d’expérience visuelle] (VEC) d’[!DNL Adobe Target] facilite la création d’un [!UICONTROL test multivarié] et la modification de parties de la page dans [!DNL Target].

L’éditeur [!DNL Target] de pointer-cliquer vous permet de sélectionner n’importe quel emplacement et d’ajouter plusieurs offres.

Le [!UICONTROL test multivarié] (MVT) prend un rapport page par page. En d’autres termes, le test s’exécute sur une URL spécifique, avec des expériences que vous concevez pour cette page.

1. Cliquez sur **[!UICONTROL Créer une activité]** > **[!UICONTROL Test multivarié]**.

   >[!NOTE]
   >
   >Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

1. (Conditionnel) Choisissez le type de diffusion : [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL E-mail] ou [!UICONTROL Autre/API].

1. (Conditionnel) Si vous êtes un client [&#128279;](/help/main/c-intro/intro.md#premium), [choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Spécifiez l’URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) de la page à tester, puis cliquez sur **[!UICONTROL Créer]**.

   >[!NOTE]
   >
   >Utilisez une URL complète, en commençant par HTTP ou HTTPS.

   Si un message s’affiche vous demandant d’activer votre navigateur pour le contenu mixte, suivez les instructions du message. Après avoir activé votre navigateur pour le contenu mixte, recommencez à l’étape 1.

   Le [!UICONTROL compositeur d’expérience visuelle] s’ouvre.

1. Pour nommer l’activité, cliquez sur l’icône **[!UICONTROL Modifier]** ( ![icône Modifier](/help/main/assets/icons/Edit.svg) ) en regard de « [!UICONTROL Activité sans titre] », spécifiez un nom explicite pour l’activité, puis cliquez sur **[!UICONTROL Enregistrer]**.

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
   | `[`&quot; | Crochet ouvert, guillemets doubles |
   | &quot;`]` | Guillemets doubles, crochet fermant |

1. [Créez les offres à chaque emplacement](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Vous pouvez ajouter les types d’offres suivants :

   * HTML
   * Image
   * Texte

1. Cliquez sur **[!UICONTROL Aperçu]** pour [prévisualiser vos expériences](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Cliquez sur l’icône **[!UICONTROL Afficher les expériences]** ( ![Icône Afficher les expériences](/help/main/assets/icons/WebPages.svg) ) pour afficher la liste de toutes les expériences dans le cadre de gauche.

1. Cliquez sur une expérience spécifique dans la liste pour l’afficher.

1. (Conditionnel) Pour exclure une ou plusieurs expériences de l’activité, cliquez sur l’icône **[!UICONTROL Gérer le contenu]** ( ![icône Gérer les expériences](/help/main/assets/icons/Experience.svg) ) pour afficher la boîte de dialogue [!UICONTROL Gérer les expériences].

1. (Conditionnel) Dans la boîte de dialogue [!UICONTROL Gérer les expériences], cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) à côté de l’expérience à exclure, puis cliquez sur **[!UICONTROL Exclure]**.

   Vous pouvez choisir d’exclure une expérience qui affiche des variations en conflit ou une expérience qui n’est pas équilibrée esthétiquement.

1. (Conditionnel) Pour exclure plusieurs expériences, cochez les cases correspondant aux expériences souhaitées, puis cliquez sur **[!UICONTROL Exclure]**.

1. [Utilisez l’estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) afin de tester la faisabilité de votre plan de test.

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder à la page [!UICONTROL Ciblage].

   L’étape **Ciblage** vous est familière si vous avez utilisé d’autres types d’activités [!DNL Target]. Ici, vous pouvez sélectionner une audience et spécifier le pourcentage de visiteurs et visiteuses qui voient chaque expérience.

   Le diagramme de flux vous guide tout au long des étapes d’affectation d’une audience et de son pourcentage de trafic, de sélection de la méthode d’affectation du trafic et de spécification de l’affectation du trafic pour chaque expérience de l’activité.

1. (Conditionnel) Cliquez sur la commande **[!UICONTROL Tous les visiteurs]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL Tous les visiteurs] est définie par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

   1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Remplacer]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.
   1. Dans la boîte de dialogue [!UICONTROL Ajouter une audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) puis cliquez sur **[!UICONTROL Attribuer l’audience]**.

      Vous pouvez cliquer sur **Combiner les audiences** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

      Si vous devez créer une nouvelle audience qui ne figure pas encore dans la [!UICONTROL Bibliothèque d’audiences], cliquez sur **Créer une audience**. Au cours du workflow [création d’audience](/help/main/c-target/c-audiences/audiences.md) vous pouvez choisir parmi les options suivantes :

      * **[!UICONTROL Bibliothèque d’audiences]** : créez une audience à la demande enregistrée dans la [!UICONTROL Bibliothèque d’audiences] qui peut être réutilisée dans d’autres activités.
      * **[!UICONTROL Cette activité uniquement]** : créez une [audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans la [!UICONTROL bibliothèque d’audiences] et qui ne peut être utilisée que dans l’activité en cours.

   1. Cliquez sur **[!UICONTROL Pourcentage de visiteurs]** dans le cadre de droite, puis choisissez le pourcentage de visiteurs qualifiés qui doivent rejoindre l’activité.

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. [Consultez le résumé du test](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) apportez les modifications souhaitées, puis cliquez sur **[!UICONTROL Suivant]**.

1. [Spécifiez les objectifs et paramètres](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour le test.

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** pour créer l’activité.

## Vidéo de formation : Création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du workflow guidé en trois étapes [!DNL Target].

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/30144?captions=fre_fr)
