---
keywords: accélérateur d’expérimentation;espace de travail target;affectation de sandbox;adobe parcours optimizer;intégrations
description: Découvrez comment mapper les espaces de travail Adobe Target aux sandbox Experimentation Accelerator afin que les équipes puissent afficher les expériences d’Adobe Target et de Adobe Journey Optimizer à un seul endroit.
title: Comment intégrer  [!DNL Target]  à Experimentation Accelerator ?
feature: Integrations
source-git-commit: e6c1d1799a27130524b1965acaffc07e1d08377f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# Intégration de [!DNL Target] à Experimentation Accelerator

Experimentation Accelerator aide les administrateurs à gérer l’organisation et l’affichage des activités de l’espace de travail [!DNL Adobe Target] dans l’application. En mappant chaque espace de travail [!DNL Target] au sandbox Experimentation Accelerator approprié, les équipes peuvent afficher les expériences de [!DNL Adobe Target] et [!DNL Adobe Journey Optimizer] à un seul endroit.

➡️ [En savoir plus sur Adobe Experimentation Accelerator](https://experienceleague.adobe.com/fr/docs/experimentation-accelerator/using/overview)

## Avant de commencer

Avant de configurer des affectations de sandbox, vérifiez que vous disposez des autorisations requises. Pour accéder aux **[!UICONTROL Administration]** dans Experimentation Accelerator, vous devez disposer de l’autorisation **[!UICONTROL Manage configuration]** .

Les utilisateurs peuvent attribuer des espaces de travail [!DNL Target] aux sandbox uniquement lorsque les deux conditions sont remplies :

* L’utilisateur dispose de l’autorisation **[!UICONTROL Manage configuration]** dans Experimentation Accelerator.
* L’utilisateur est un administrateur de produit [!DNL Target].

## Configurer l’affectation de sandbox pour les espaces de travail [!DNL Target]

Avant d’affecter des espaces de travail, notez qu’[!DNL Target] espace de travail ne peut être affecté qu’à un seul sandbox afin d’éviter les entrées en double pour le même test.

Pour choisir le sandbox dans lequel chaque espace de travail [!DNL Target] apparaît :

1. Dans Experimentation Accelerator, ouvrez **[!UICONTROL Administration]**.

   ![](assets/experimentation-1.png)

1. Consultez le tableau des affectations actuelles de l’espace de travail [!DNL Target] au sandbox .

   ![](assets/experimentation-2.png)

1. Cliquez sur **[!UICONTROL Edit]**.

   ![](assets/experimentation-3.png)

1. Pour chaque sandbox, attribuez les espaces de travail [!DNL Target] appropriés.

   ![](assets/experimentation-4.png)

1. Cliquez sur **[!UICONTROL Save]** pour appliquer vos modifications.

Une fois la connexion initiale créée pour un espace de travail [!DNL Target], attendez jusqu’à 30 minutes pour que les mises à jour se propagent sur le système.
