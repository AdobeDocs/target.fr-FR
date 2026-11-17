---
keywords: audience;sélection de l’audience;choix de l’audience;sélecteurs
description: Définissez les visiteurs du site qui rejoignent votre activité Adobe [!DNL Target] en fonction des critères d’audience.
title: Comment sélectionner une audience dans une activité A/B [!DNL Target] ?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: 'https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%
---
# Sélection de l’audience {#select-audience}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment sélectionner, créer, combiner, afficher, modifier et copier l’audience d’une activité A/B et comment définir le pourcentage de visiteurs à inclure.

>[!ENDSHADEBOX]

L&#39;audience détermine les visiteurs qualifiés qui sont entrés dans votre activité [!DNL Adobe Target].

L’étape de **[!UICONTROL ciblage]** du workflow guidé en trois parties lors de la [création d’une activité](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) affiche un diagramme de flux qui vous guide tout au long des étapes d’attribution d’une audience et de son pourcentage de trafic, de sélection de la méthode d’affectation du trafic et de spécification de l’affectation du trafic pour chaque expérience de l’activité.

![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Pour plus d’informations sur toutes les options du diagramme de flux, consultez [Création d’une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Sélectionner une audience pour l’activité

L’audience contrôle qui voit votre activité. Seuls les visiteurs correspondant à l’audience peuvent y accéder et vous décidez de la part de ces visiteurs à laquelle ils participent. Par défaut, l’activité cible tous les visiteurs.

1. Cliquez sur le contrôle **[!UICONTROL Tous les visiteurs]** pour sélectionner une autre audience pour l’activité.

   **[!UICONTROL Tous les visiteurs]** est l’audience par défaut. Pour un test A/B sans ciblage d’audience spécifique, conservez la valeur par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

1. Cliquez sur l’icône **[!UICONTROL Remplacer]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ).

   ![](../../assets/audience_activity.png)

1. Dans la boîte de dialogue **[!UICONTROL Ajouter une audience]**, parcourez les audiences sélectionnées dans la **[!UICONTROL Bibliothèque d’audiences]**, ou vous pouvez créer une audience d’activité unique.

   La **[!UICONTROL Bibliothèque d’audiences]** contient des audiences qui ont été définies précédemment, y compris certaines audiences courantes qui sont préconfigurées dans le cadre de [!DNL Target].

   ![](../../assets/audience_activity_2.png)

1. Cliquez sur l’icône **[!UICONTROL Informations]** ( ![Icône d’informations](/help/main/assets/icons/InfoOutline.svg) ) à côté d’une audience pour afficher les détails de cette audience, y compris sa source et ses attributs.

   ![](../../assets/audience_activity_3.png)

   Vous pouvez également cliquer sur **[!UICONTROL Afficher les détails complets]** pour afficher des détails supplémentaires sur l’audience.

1. (Conditionnel) Cliquez sur **[!UICONTROL Combiner des audiences]** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

   +++ Procédure de création d’une audience

   Pour créer une audience qui ne figure pas encore dans la **[!UICONTROL Bibliothèque d’audiences]**, cliquez sur **[!UICONTROL Créer une audience]**, définissez l’audience, puis cliquez sur **[!UICONTROL Terminé]**.

   Pendant le [workflow de création d’audience](/help/main/c-target/c-audiences/audiences.md), vous pouvez choisir parmi les options suivantes :

   * **[!UICONTROL Bibliothèque d’audiences]** : créez une audience à la demande qui est enregistrée dans la **[!UICONTROL Bibliothèque d’audiences]** et peut être réutilisée dans d’autres activités.
   * **[!UICONTROL Cette activité uniquement]** : créez une [audience spécifique à l’activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans la **[!UICONTROL bibliothèque d’audiences]** et qui ne peut être utilisée que dans l’activité actuelle.

   +++

1. Vous pouvez modifier ou copier une audience en cliquant sur l’icône **[!UICONTROL Plus d’actions]** (![Icône Plus d’actions](/help/main/assets/icons/More.svg) ) en regard de l’audience souhaitée.

1. Après avoir sélectionné votre audience, cliquez sur **[!UICONTROL Attribuer l’audience]**.

1. Cliquez sur **[!UICONTROL Pourcentage de visiteurs]** dans le volet de droite, puis spécifiez le pourcentage de visiteurs qualifiés à inclure dans l’activité.

1. Lorsque vous êtes satisfait(e) de votre audience, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième étape du workflow guidé en trois étapes.

>[!NOTE]
>
>Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste **[!UICONTROL Audience]** et que les audiences importées datent de plus de 10 minutes.
