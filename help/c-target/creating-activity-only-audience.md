---
description: Créez des audiences d’activité uniques depuis le processus assisté en trois étapes lors de la création d’une activité. Ces audiences ad hoc peuvent être utilisées à d’autres endroits dans la même activité, mais ne sont pas enregistrées dans la bibliothèque d’audiences en vue d’être utilisées dans d’autres activités.
keywords: audience;règles d’audience;créer une audience;création d’audience;activité unique;ad hoc
seo-description: Créez des audiences d'activité uniquement depuis le workflow assisté Adobe Target à trois étapes lors de la création d'une activité. Ces audiences ad hoc peuvent être utilisées à d’autres endroits dans la même activité, mais ne sont pas enregistrées dans la bibliothèque d’audiences en vue d’être utilisées dans d’autres activités.
seo-title: Création d’une audience d’activité unique dans Adobe Target
solution: Target
title: Création d’une audience d’activité unique
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: c853ac9a9447a10b753e53fd707f6f72db2889b0

---


# Création d’une audience d’activité unique{#create-an-activity-only-audience}

Créez des audiences d’activité uniques depuis le processus assisté en trois étapes lors de la création d’une activité. Ces audiences ad hoc peuvent être utilisées à d&#39;autres emplacements dans la même activité, mais ne sont pas stockées dans la bibliothèque [!UICONTROL d&#39;audiences] pour être utilisées dans d&#39;autres activités.

Les audiences d’activité uniques présentent les avantages suivants :

* Vous pouvez utiliser les audiences réservées aux activités pour créer une audience que vous souhaitez utiliser une seule fois et que vous ne souhaitez pas stocker dans la bibliothèque [!UICONTROL d&#39;audiences]. Cela évite que [!UICONTROL la bibliothèque] d&#39;audiences ne soit encombrée avec des audiences que vous ne souhaitez plus utiliser.
* Les audiences réservées aux activités ne sont pas visibles dans la bibliothèque [!UICONTROL d&#39;audiences]. Elles sont ainsi protégées de toute modification involontaire par d’autres membres de l’organisation.

1. Lors de la création d&#39; [une activité](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), sur la **[!UICONTROL page Target]** , cliquez sur les trois points de suspension verticaux, puis cliquez **[!UICONTROL sur Remplacer l&#39;audience]**.

   ![Résultat d’étape](assets/edit_audience.png)

1. On the [!UICONTROL Choose Audience] page, click **[!UICONTROL Activity Only Audience]**.

   ![](assets/activity-only-aud.png)

1. Cliquez sur **[!UICONTROL Créer une audience]**.
1. Saisissez un nom d’audience descriptif.
1. Cliquez sur **[!UICONTROL +Ajouter une règle]**.

   Les règles permettent de limiter votre audience à un sous-ensemble des visiteurs de votre site.

1. Sélectionnez un type de règle.

   Chaque type de règle possède ses propres paramètres. Voir [Catégories d’audiences](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) pour plus d’informations sur la configuration de chaque type de règle d’audience.

1. Définissez les paramètres des règles.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Considérations

Gardez les informations suivantes à l’esprit lorsque vous travaillez avec des audiences d’activité uniques :

* Vous pouvez créer des audiences d’activité uniques dans le compositeur d’expérience visuelle (VEC) ou dans le compositeur d’expérience d’après les formulaires. Cette fonctionnalité remplace les règles de perfectionnement des précédentes versions de Target.
* Vous pouvez créer une activité à stocker dans la bibliothèque [!UICONTROL d&#39;audiences] pour une réutilisation dans d&#39;autres activités ou pour créer une audience d&#39;activité uniquement. Une fois l’audience enregistrée, vous ne pouvez plus modifier le type d’audience.
* Les perfectionnements pour les activités existantes sont transférés vers les audiences d’activité uniques.
* Les audiences de type Activité uniquement ont un état [!UICONTROL Utilisé] ou [!UICONTROL Inconnu]. Les audiences d’activité uniques non utilisées s’affichent jusqu’à ce que l’activité soit enregistrée. Si elles sont toujours non utilisées lorsque vous enregistrez l’activité, un message d’avertissement vous informe que les audiences d’activité non utilisées seront supprimées.
* Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle accessible depuis le sélecteur d’audiences, sans ouvrir l’audience.
* Vous pouvez [combiner plusieurs audiences](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer des audiences d’activité uniques.

