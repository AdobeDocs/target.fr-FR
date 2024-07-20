---
keywords: audience;règles d’audience;créer une audience;création d’audience;activité unique;ad hoc
description: Découvrez comment créer des audiences d’activité uniques dans Adobe [!DNL Target] pour une utilisation unique.
title: Puis-je créer une audience à utiliser une seule fois ?
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 31%

---

# Création d’une audience d’activité unique

Créez des audiences d’activité uniques à partir du workflow assisté en trois étapes [!DNL Adobe Target] lors de la création d’une activité. Ces audiences ad hoc peuvent être utilisées à d’autres endroits dans la même activité, mais ne sont pas stockées dans la [!UICONTROL Audiences Library] pour être utilisées dans d’autres activités.

Les audiences d’activité uniques présentent les avantages suivants :

* Vous pouvez utiliser des audiences d’activité uniques pour créer une audience que vous ne souhaitez utiliser qu’une seule fois et que vous ne souhaitez pas la stocker dans le [!UICONTROL Audiences Library]. Les audiences d’activité uniques permettent d’éviter que le [!UICONTROL Audiences Library] ne soit encombré avec des audiences que vous ne souhaitez plus jamais utiliser.
* Les audiences d’activité uniques ne sont pas visibles dans [!UICONTROL Audiences Library]. Comme ces audiences ne sont pas visibles dans la bibliothèque, elles sont protégées des modifications indésirables par d’autres membres de votre organisation.

1. Lors de la création d’une [activité](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), sur la page **[!UICONTROL Targeting]**, cliquez sur les trois points alignés verticalement, puis sur **[!UICONTROL Replace Audience]**.

   ![Résultat d’étape](assets/edit_audience.png)

1. Cliquez sur **[!UICONTROL Create Audience]**.

1. Cliquez sur **[!UICONTROL This activity only]**.

   ![image activité-seule-aud](assets/activity-only-aud.png)

1. Saisissez un nom d’audience descriptif.
1. Faites glisser et déposez les attributs de votre choix dans le créateur d’audiences.

   Les règles permettent de limiter votre audience à un sous-ensemble de visiteurs de votre site. Chaque type de règle possède ses propres paramètres. Voir [Catégories d’audiences](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) pour plus d’informations sur la configuration de chaque type de règle d’audience.

1. Cliquez sur **[!UICONTROL Done]**.

## Considérations

Gardez les informations suivantes à l’esprit lorsque vous travaillez avec des audiences d’activité uniques :

* Vous pouvez créer des audiences d’activité uniques dans le [!UICONTROL Visual Experience Composer] (VEC) ou dans le [!UICONTROL Form-Based Experience Composer]. Cette fonctionnalité remplace les règles d’amélioration des versions précédentes de [!DNL Target].
* Vous pouvez créer une activité à stocker dans le [!UICONTROL Audience Library] en vue de la réutiliser dans d’autres activités ou créer une audience d’activité unique. Une fois l’audience enregistrée, vous ne pouvez plus modifier le type d’audience.
* Les perfectionnements pour les activités existantes sont transférés vers les audiences d’activité uniques.
* Les audiences d’activité uniques ont un état de [!UICONTROL Used] ou [!UICONTROL Unused]. Les audiences d’activité uniques non utilisées s’affichent jusqu’à ce que l’activité soit enregistrée. Si elles sont toujours non utilisées lorsque vous enregistrez l’activité, un message d’avertissement vous informe que les audiences d’activité non utilisées seront supprimées.
* Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle accessible depuis le sélecteur d’audiences, sans ouvrir l’audience.
* Vous pouvez [combiner plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer des audiences d’activité uniques.
* Les audiences d’activité uniques ne prennent pas en charge les règles d’exclusion.

  Vous pouvez utiliser les alternatives suivantes pour utiliser les règles d’exclusion :

   * [Créez et utilisez une audience de bibliothèque](/help/main/c-target/c-audiences/create-audience.md) au lieu d’une audience d’activité unique.
   * [Combinez plusieurs ](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) (jusqu’à 20) audiences de bibliothèque en une audience d’activité unique. Lors de la combinaison d’audiences, les règles d’inclusion et d’exclusion dans les audiences de bibliothèque individuelles peuvent être utilisées même lorsque l’audience combinée est enregistrée en tant qu’audience d’activité unique.
