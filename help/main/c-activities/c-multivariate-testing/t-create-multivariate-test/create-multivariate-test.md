---
keywords: mvt;test multivarié;créer un test multivarié;création de test multivarié;créer un mvt;création de mvt;comment mvt;comment test multivarié
description: Découvrez comment utiliser le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer un [!UICONTROL test multivarié] (MVT).
title: Comment créer un [!UICONTROL test multivarié] ?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: 'https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 16%
---
# Création d’un test multivarié {#create-mvt}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer un **[!UICONTROL test multivarié]** (MVT) dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC). Vous créez l’activité, créez et passez en revue les expériences, définissez le ciblage, puis configurez les objectifs et les paramètres.

>[!ENDSHADEBOX]

Le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) dans [!DNL Adobe Target] facilite la création d’un **[!UICONTROL test multivarié]** et la modification de parties de la page dans [!DNL Target].

L’éditeur de pointage-clic [!DNL Target] vous permet de sélectionner n’importe quel emplacement et d’ajouter plusieurs offres.

Le **[!UICONTROL test multivarié]** (MVT) prend un rapport page première. En d’autres termes, le test s’exécute sur une URL spécifique, avec des expériences que vous concevez pour cette page.

Suivez les étapes ci-dessous pour créer un **[!UICONTROL test multivarié]** (MVT) :

1. [Création de l’activité](#create-activity)
1. [Création et révision des expériences](#build-experiences)
1. [Définir le ciblage](#set-targeting)
1. [Configurer les objectifs et les paramètres](#configure-goals-and-settings)

## Création de l’activité {#create-activity}

Choisissez le type d’activité et le type de diffusion, spécifiez la page à tester et attribuez un nom à l’activité.

1. Cliquez Sur **[!UICONTROL Créer Une Activité]** > **[!UICONTROL Test Multivarié]**.

   Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

   ![](../../assets/create-mvt-1.png)

1. Choisissez le type de diffusion : **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL E-mail]** ou **[!UICONTROL Autre/API]**.

1. (Conditionnel) Si vous êtes un client [Target Premium](/help/main/c-intro/intro.md#premium), [choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Spécifiez l&#39;URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#ab-activity-url) de la page que vous souhaitez tester. Utilisez une URL complète, en commençant par HTTP ou HTTPS.

1. Cliquez ensuite sur **[!UICONTROL Créer]**. Le **[!UICONTROL compositeur d’expérience visuelle]** s’ouvre.

1. Pour nommer l’activité, cliquez sur l’icône **[!UICONTROL Modifier]** ( ![Icône Modifier](/help/main/assets/icons/Edit.svg) ) et spécifiez un nom explicite pour l’activité, puis cliquez sur **[!UICONTROL Enregistrer]**.

   {{activity-name-rules}}

   ![](../../assets/create-mvt-2.png)

## Création et révision des expériences {#build-experiences}

Ajoutez des offres à chaque emplacement, prévisualisez les expériences obtenues et vérifiez que votre plan de test est réalisable.

1. [Créez les offres à chaque emplacement](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Vous pouvez ajouter les types d’offres suivants :

   * HTML
   * Image
   * Texte

1. Cliquez sur **[!UICONTROL Aperçu]** pour [prévisualiser vos expériences](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Cliquez sur l’icône **[!UICONTROL Afficher les expériences]** ( ![Icône Afficher les expériences](/help/main/assets/icons/WebPages.svg) ) pour afficher la liste de toutes les expériences dans le cadre de gauche, puis cliquez sur une expérience spécifique dans la liste pour afficher cette expérience.

1. [Utilisez l’estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) afin de tester la faisabilité de votre plan de test.

### Exclure des expériences (facultatif) {#exclude-experiences}

Vous pouvez choisir d’exclure une expérience qui affiche des variations en conflit ou une expérience qui n’est pas équilibrée esthétiquement.

1. Cliquez sur l’icône **[!UICONTROL Gérer le contenu]** ( ![Icône Gérer les expériences](/help/main/assets/icons/Experience.svg) ) pour afficher la boîte de dialogue **[!UICONTROL Gérer les expériences]**.

1. Pour exclure une expérience, cliquez sur l’icône **[!UICONTROL Autres actions]** ( ![Icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de cette expérience, puis cliquez sur **[!UICONTROL Exclure]**.

1. Pour exclure plusieurs expériences, cochez les cases correspondant aux expériences souhaitées, puis cliquez sur **[!UICONTROL Exclure]**.

## Définir le ciblage {#set-targeting}

Choisissez les visiteurs qui participent au test et passez en revue le résumé du test.

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder à la page **[!UICONTROL Ciblage]**.

   Le diagramme de flux vous guide tout au long des étapes d’affectation d’une audience et de son pourcentage de trafic, de sélection de la méthode d’affectation du trafic et de spécification de l’affectation du trafic pour chaque expérience de l’activité.

1. (Conditionnel) Cliquez sur la commande **[!UICONTROL Tous les visiteurs]** pour sélectionner une autre audience pour l’activité.

   L’audience **[!UICONTROL Tous les visiteurs]** est définie comme audience par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche. Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

   +++ Procédure de sélection d’une autre audience

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

   1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Remplacer]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.
   1. Dans la boîte de dialogue **[!UICONTROL Ajouter une audience]**, [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), puis cliquez sur **[!UICONTROL Attribuer l’audience]**.

      Pour créer une audience qui combine plusieurs audiences, cliquez sur **[!UICONTROL Combiner des audiences]**. Pour plus d’informations, consultez [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

      Pour créer une audience qui ne figure pas encore dans la **[!UICONTROL Bibliothèque d’audiences]**, cliquez sur **[!UICONTROL Créer une audience]**. Dans le workflow [créer une audience](/help/main/c-target/c-audiences/audiences.md), choisissez l’une des options suivantes :

      * **[!UICONTROL Bibliothèque d’audiences]** : créez une audience à la demande qui est enregistrée dans la **[!UICONTROL Bibliothèque d’audiences]** et peut être réutilisée dans d’autres activités.
      * **[!UICONTROL Cette activité uniquement]** : créez une [audience spécifique à l’activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans la **[!UICONTROL bibliothèque d’audiences]** et qui ne peut être utilisée que dans l’activité actuelle.

   1. Cliquez sur **[!UICONTROL Pourcentage de visiteurs]** dans le cadre de droite, puis choisissez le pourcentage de visiteurs qualifiés qui souhaitent rejoindre l’activité.

   +++

1. [Vérifiez le résumé du test](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) et apportez les modifications souhaitées, puis cliquez sur **[!UICONTROL Suivant]**.

## Configurer les objectifs et les paramètres {#configure-goals-and-settings}

Sur la page **[!UICONTROL Objectifs et paramètres]**, indiquez à [!DNL Target] comment mesurer le test. Les paramètres disponibles varient selon que vous utilisez [!DNL Target] ou [!DNL Analytics] comme source de création de rapports.

1. Consultez les sections de la page et définissez ce dont vous avez besoin. Voir [Ce que vous avez défini sur la page Objectifs et paramètres](#goals-settings-overview).


   | Section | Ce que vous avez défini |
   |---|---|
   | **[!UICONTROL Paramètres d’activité]** | Un objectif facultatif, la **[!UICONTROL Priorité]** (utilisée lorsque plusieurs activités partagent un emplacement et une audience) et la **[!UICONTROL Durée]** (dates de début et de fin). |
   | **[!UICONTROL Paramètres de création de rapports]** | La source de création de rapports, la mesure d’objectif (par exemple, une mesure **[!UICONTROL Conversion]**), les mesures supplémentaires et les audiences pour la création de rapports. Les paramètres avancés de la mesure d’objectif sont également disponibles ici. |
   | **[!UICONTROL Autres métadonnées]** | Notes sur l’activité qui sont utiles pour vous ou pour les autres membres de l’équipe. |

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** pour créer l’activité.

Pour plus d&#39;informations sur chaque option, voir [Objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#ab-goals-and-settings).

## Vidéo de formation : Création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du workflow guidé en trois étapes [!DNL Target].

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/30144?captions=fre_fr)
