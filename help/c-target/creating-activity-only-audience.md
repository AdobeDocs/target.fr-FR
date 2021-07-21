---
keywords: audience;règles d’audience;créer une audience;création d’audience;activité unique;ad hoc
description: Découvrez comment créer des audiences d’activité uniques dans Adobe [!DNL Target] qui sont destinées à une utilisation unique.
title: Puis-je créer une audience à utiliser une seule fois ?
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 20a5201b5c05b1f083252ac73b3b4bbc91e97aaa
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 64%

---

# Création d’une audience d’activité unique

Créez des audiences d’activité uniques à partir du processus assisté en trois étapes [!DNL Adobe Target] lors de la création d’une activité. Ces audiences ad hoc peuvent être utilisées à d’autres endroits dans la même activité, mais ne sont pas enregistrées dans la [!UICONTROL bibliothèque d’audiences] en vue d’être utilisées dans d’autres activités.

Les audiences d’activité uniques présentent les avantages suivants :

* Vous pouvez utiliser les audiences d’activité uniques pour créer une à usage unique que vous ne souhaitez pas enregistrer dans la [!UICONTROL bibliothèque d’audiences]. Les audiences d’activité uniques permettent d’éviter que la [!UICONTROL bibliothèque d’audiences] ne soit encombrée d’audiences que vous ne souhaitez plus jamais utiliser.
* Les audiences d’activité unique ne sont pas visibles dans la [!UICONTROL bibliothèque d’audiences]. Comme ces audiences ne sont pas visibles dans la bibliothèque, elles sont protégées des modifications indésirables par d’autres membres de votre organisation.

1. Lors de la création d’une [activité](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), sur la page **[!UICONTROL Ciblage]**, cliquez sur les trois points alignés verticalement, puis sur **[!UICONTROL Remplacer l’audience]**.

   ![Résultat d’étape](assets/edit_audience.png)

1. Cliquez sur **[!UICONTROL Créer une audience]**.

1. Cliquez sur **[!UICONTROL Cette activité uniquement]**.

   ![](assets/activity-only-aud.png)

1. Saisissez un nom d’audience descriptif.
1. Faites glisser les attributs de votre choix dans le créateur d’audiences.

   Les règles permettent de limiter votre audience à un sous-ensemble de visiteurs de votre site. Chaque type de règle possède ses propres paramètres. Voir [Catégories d’audiences](/help/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) pour plus d’informations sur la configuration de chaque type de règle d’audience.

1. Cliquez sur **[!UICONTROL Terminé]**.

## Considérations

Gardez les informations suivantes à l’esprit lorsque vous travaillez avec des audiences d’activité uniques :

* Vous pouvez créer des audiences d’activité uniques dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) ou dans le [!UICONTROL compositeur d’expérience d’après les formulaires]. Cette fonctionnalité remplace les règles de perfectionnement des précédentes versions de [!DNL Target].
* Vous pouvez créer une activité à enregistrer dans la [!UICONTROL bibliothèque d’audiences] en vue de la réutiliser dans d’autre activités ou créer une audience d’activité unique. Une fois l’audience enregistrée, vous ne pouvez plus modifier le type d’audience.
* Les perfectionnements pour les activités existantes sont transférés vers les audiences d’activité uniques.
* Les audiences d’activité unique ont le statut [!UICONTROL Utilisé] ou [!UICONTROL Non utilisé]. Les audiences d’activité uniques non utilisées s’affichent jusqu’à ce que l’activité soit enregistrée. Si elles sont toujours non utilisées lorsque vous enregistrez l’activité, un message d’avertissement vous informe que les audiences d’activité non utilisées seront supprimées.
* Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle accessible depuis le sélecteur d’audiences, sans ouvrir l’audience.
* Vous pouvez [combiner plusieurs audiences](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer des audiences d’activité uniques.
