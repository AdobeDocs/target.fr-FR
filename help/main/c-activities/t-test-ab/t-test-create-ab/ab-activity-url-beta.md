---
keywords: url de l’activité;url;url différente
description: Découvrez comment définir les [!UICONTROL Activity URL] pour définir des pages de test et garantir une conception de test précise.
title: Quelle est l’URL de l’activité dans une activité A/B ?
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
source-git-commit: d92c09b905b10c6d0175a5de137d573f8cd475d7
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 32%

---

# URL d’activité

L’URL de l’activité détermine la page utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide de [!DNL Adobe Target].

Lorsque vous y êtes invité au cours de la création de l’activité, spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://www.adobe.com`] correspondent.

## Spécification d’une URL différente

Par défaut, le [!UICONTROL Visual Experience Composer] ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

1. (Conditionnel) Pour afficher une autre page après l’ouverture de la [!UICONTROL Visual Experience Composer], sur la page **[!UICONTROL Experiences]**, cliquez sur **[!UICONTROL Configure]** en haut de la page, puis sélectionnez **[!UICONTROL Page Delivery]**.

1. Spécifiez l’URL dans le champ **[!UICONTROL URL]** .

1. (Conditionnel) Cliquez sur **[!UICONTROL Add Rule]** pour ajouter d’autres pages ou sections à l’activité.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox
   * Valeur personnalisée

   D’autres règles peuvent être jointes à l’URL de l’activité avec ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

   Si vous avez saisi une URL pour un site qui n’inclut pas le code JavaScript du [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.

   Par défaut, le [!UICONTROL Visual Experience Composer] n’autorise pas les modifications apportées aux éléments contenant JavaScript, tels que la rotation des bannières. Vous pouvez désactiver **[!UICONTROL Render using JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du [!UICONTROL Visual Experience Composer].—>

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
