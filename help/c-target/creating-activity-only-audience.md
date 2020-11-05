---
keywords: audience;audience rules;create audience;creating audience;activity only;activity-only;adhoc
description: Créez des audiences d’activité uniques depuis le processus assisté en trois étapes Adobe Target lors de la création d’une activité. Ces audiences ad hoc peuvent être utilisées à d’autres endroits dans la même activité, mais ne sont pas enregistrées dans la bibliothèque d’audiences en vue d’être utilisées dans d’autres activités.
title: Création d’une audience d’activité unique dans Adobe Target
feature: audiences
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 100%

---


# Création d’une audience d’activité unique{#create-an-activity-only-audience}

Créez des audiences d’activité uniques depuis le processus assisté en trois étapes lors de la création d’une activité. Ces audiences ad hoc peuvent être utilisées à d’autres endroits dans la même activité, mais ne sont pas enregistrées dans la [!UICONTROL bibliothèque d’audiences] en vue d’être utilisées dans d’autres activités.

Les audiences d’activité uniques présentent les avantages suivants :

* Vous pouvez utiliser les audiences d’activité uniques pour créer une à usage unique que vous ne souhaitez pas enregistrer dans la [!UICONTROL bibliothèque d’audiences]. Cela évite d’encombrer la [!UICONTROL bibliothèque d’audiences] avec des audiences que vous n’utiliserez plus.
* Les audiences d’activité unique ne sont pas visibles dans la [!UICONTROL bibliothèque d’audiences]. Elles sont ainsi protégées de toute modification involontaire par d’autres membres de l’organisation.

1. Lors de la création d’une [activité](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), sur la page **[!UICONTROL Target]**, cliquez sur les trois points alignés verticalement, puis sur **[!UICONTROL Remplacer l’audience]**.

   ![Résultat d’étape](assets/edit_audience.png)

1. Sur la page [!UICONTROL Choix de l’audience], cliquez sur **[!UICONTROL Audience d’activité unique]**.

   ![](assets/activity-only-aud.png)

1. Cliquez sur **[!UICONTROL Créer une audience]**.
1. Saisissez un nom d’audience descriptif.
1. Cliquez sur **[!UICONTROL +Ajouter une règle]**.

   Les règles permettent de limiter votre audience à un sous-ensemble des visiteurs de votre site.

1. Sélectionnez un type de règle.

   Chaque type de règle possède ses propres paramètres. Voir [Catégories d’audiences](/help/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) pour plus d’informations sur la configuration de chaque type de règle d’audience.

1. Définissez les paramètres des règles.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Considérations

Gardez les informations suivantes à l’esprit lorsque vous travaillez avec des audiences d’activité uniques :

* Vous pouvez créer des audiences d’activité uniques dans le compositeur d’expérience visuelle (VEC) ou dans le compositeur d’expérience d’après les formulaires. Cette fonctionnalité remplace les règles de perfectionnement des précédentes versions de Target.
* Vous pouvez créer une activité à enregistrer dans la [!UICONTROL bibliothèque d’audiences] en vue de la réutiliser dans d’autre activités ou créer une audience d’activité unique. Une fois l’audience enregistrée, vous ne pouvez plus modifier le type d’audience.
* Les perfectionnements pour les activités existantes sont transférés vers les audiences d’activité uniques.
* Les audiences d’activité unique ont le statut [!UICONTROL Utilisé] ou [!UICONTROL Non utilisé]. Les audiences d’activité uniques non utilisées s’affichent jusqu’à ce que l’activité soit enregistrée. Si elles sont toujours non utilisées lorsque vous enregistrez l’activité, un message d’avertissement vous informe que les audiences d’activité non utilisées seront supprimées.
* Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle accessible depuis le sélecteur d’audiences, sans ouvrir l’audience.
* Vous pouvez [combiner plusieurs audiences](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer des audiences d’activité uniques.

