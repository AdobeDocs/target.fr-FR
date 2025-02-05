---
keywords: url de l’activité;url;url différente
description: Découvrez comment spécifier l’URL d’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide de  [!DNL Adobe Target].
title: Quelle est l’URL de l’activité dans une activité A/B ?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 44%

---

# URL d’activité

L’URL de l’activité détermine la page utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide d’Adobe Target.

Lorsque vous y êtes invité au cours de la création de l’activité, spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://www.adobe.com`] correspondent.

## Spécification d’une URL différente

Par défaut, le [!UICONTROL Visual Experience Composer] ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

1. Pour afficher une autre page après l’ouverture de la [!UICONTROL Visual Experience Composer], sur la page **[!UICONTROL Experiences]**, cliquez sur l’icône de l’engrenage **[!UICONTROL Configure]**, puis sélectionnez **[!UICONTROL Page Delivery]**.

1. Spécifiez l’URL dans le champ **[!UICONTROL URL]** .

   ![Boîte de dialogue Diffusion de page](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

1. (Conditionnel) Cliquez sur **[!UICONTROL Add Template Rule]** pour ajouter d’autres pages ou sections à l’activité.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox

   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

Si vous avez saisi l’URL d’un site qui ne contient pas le code JavaScript de Standard [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le [!UICONTROL Visual Experience Composer] n’autorise pas les modifications apportées aux éléments contenant JavaScript, tels que la rotation des bannières. Vous pouvez **[!UICONTROL Render using JavaScript]** désactiver si vous souhaitez pouvoir modifier ces éléments à l’aide de l’[!UICONTROL Visual Experience Composer] .

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
