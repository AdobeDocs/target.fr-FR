---
keywords: url d’activité;url;URL différente
description: Découvrez comment définir le [!UICONTROL Activity URL] pour définir des pages de test et garantir une conception de test exacte.
title: Quelle est l’URL d’activité dans une activité A/B ?
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
source-git-commit: d5bd3b0d7cdf6eb06175a6365da6b8173f76800f
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 40%

---

# URL d’activité

L’URL d’activité détermine la page qui est utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide de [!DNL Adobe Target].

Lorsque vous y êtes invité au cours de la création de l’activité, spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://www.adobe.com`] correspondent tous les deux.

## Spécification d’une URL différente

Par défaut, le [!UICONTROL Visual Experience Composer] ouvre la page qui est spécifiée dans vos [ paramètres du compositeur d’expérience visuelle ](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

1. (Conditionnel) Pour afficher une autre page après l’ouverture de [!UICONTROL Visual Experience Composer], sur la page **[!UICONTROL Experiences]**, cliquez sur **[!UICONTROL Configure]** en haut de la page, puis sélectionnez **[!UICONTROL Page Delivery]**.

1. Spécifiez l’URL dans le champ **[!UICONTROL URL]**.

1. (Conditionnel) Cliquez sur **[!UICONTROL Add Rule]** pour ajouter d’autres pages ou sections à l’activité.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox
   * Valeur personnalisée

   Des règles supplémentaires peuvent être jointes à l’URL de l’activité avec l’opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

<!-- If you entered a URL for a site that does not include the [!DNL Target]s JavaScript code, you cannot select page elements.

By default, the [!UICONTROL Visual Experience Composer] does not allow changes to elements containing JavaScript, such as rotating banners. You can toggle off **[!UICONTROL Render using JavaScript]** if you want to be able to alter those elements using the [!UICONTROL Visual Experience Composer].-->

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
