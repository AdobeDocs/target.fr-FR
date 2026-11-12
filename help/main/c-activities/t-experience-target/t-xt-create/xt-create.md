---
keywords: Ciblage d’expérience;xt;créer
description: Découvrez comment utiliser le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer une activité de [!UICONTROL ciblage d’expérience] (XT).
title: Comment créer une activité de [!UICONTROL ciblage d’expérience] ?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
TQID: 'https://experienceleague.adobe.com/RKSF7zTO3lb4hs1VaJuTUR9v8AnOlCjHkp-whqBIcKo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: b6f5758b-84f7-4943-8b05-1297a046943c
    internal-label: Experience target
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: af388cf398e03e4ec7b4c5c44b03f772eacedf51
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 32%
---
# Créer une activité de [!UICONTROL Ciblage d’expérience] (XT) {#create-xt-activity}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer une activité de **[!UICONTROL ciblage d’expérience]** (XT) dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC). Créez l’activité, ajoutez des expériences ciblées sur différentes audiences, puis configurez les objectifs et les paramètres.

>[!ENDSHADEBOX]

Utilisez le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) pour créer une activité de **[!UICONTROL ciblage d’expérience]** (XT) sur une page compatible avec [!DNL Target] et pour modifier des parties de la page dans [!DNL Adobe Target].

**[!UICONTROL Le ciblage d’expérience]** (XT) diffuse du contenu à une audience spécifique selon un ensemble de règles et de critères définis par les spécialistes marketing. Il est utile pour définir des règles qui ciblent une expérience ou un contenu spécifique sur une audience particulière, y compris le [géociblage](/help/main/c-target/c-audiences/c-target-rules/geo.md). Plusieurs règles peuvent être définies au sein d’une même activité afin de fournir différentes variations de contenu à des audiences différentes.

Pour plus d’informations sur le **[!UICONTROL ciblage d’expérience]**, un scénario d’utilisation et des vidéos de formation, consultez [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md).

1. Dans la liste **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]** > **[!UICONTROL Ciblage d’expérience]**.

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, **[!UICONTROL Automated Personalization]** est une fonctionnalité [Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Pour plus d’informations sur les différents types d’activité disponibles dans [!DNL Target] et leurs différences, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Reportez-vous à la section [Types d’activité Target](/help/main/c-activities/target-activities-guide.md) pour déterminer les types d’activité qui conviennent le mieux à vos besoins.

   ![](../../assets/create-xt-1.png)

1. Dans la boîte de dialogue **[!UICONTROL Créer une activité de ciblage d’expérience]**, choisissez votre compositeur d’expérience :

   * **[!UICONTROL Visuel]**.
   * **[!UICONTROL Compositeur d’expérience d’après les formulaires]**, voir [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le compositeur d’expérience visuelle et le **[!UICONTROL compositeur d’expérience d’après les formulaires]**, [!DNL Target] propose le compositeur d’expérience visuelle d’application d’une seule page. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le VEC, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes un client [!DNL Target Premium], [choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Spécifiez votre [URL d&#39;activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#ab-activity-url), puis cliquez sur **[!UICONTROL Créer]**. Le VEC s’ouvre, affichant la page indiquée dans l’URL.

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Vous pouvez passer de la valeur par défaut à une autre URL, si nécessaire.

1. Pour nommer l’activité, cliquez sur l’icône **[!UICONTROL Modifier]** ( ![Icône Modifier](/help/main/assets/icons/Edit.svg) ) et spécifiez un nom explicite pour l’activité, puis cliquez sur **[!UICONTROL Enregistrer]**.

   {{activity-name-rules}}

   ![](../../assets/create-xt-2.png)

1. Créez de nouvelles expériences ciblées sur différentes audiences. Pour obtenir des instructions pas à pas, voir [Ajouter une expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md#xt-add-experience).

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#ab-goals-and-settings) pour l’activité.
