---
keywords: Ciblage d’expérience;xt;url d’activité;url
description: Découvrez comment spécifier la [!UICONTROL Activity URL] qui détermine la page utilisée dans le test et qui s’ouvre lorsque l’activité de [!UICONTROL Experience Targeting] est conçue à l’aide de  [!DNL Adobe Target].
title: Quel est le [!UICONTROL Activity URL] d’une activité [!UICONTROL Experience Targeting] (XT) ?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 38%

---

# URL de l’activité dans les activités [!UICONTROL Experience Targeting] (XT)

L’[!UICONTROL Activity URL] détermine la page utilisée dans une activité [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT). Il s’agit de la page qui s’ouvre dans le [!UICONTROL Visual Experience Composer] (VEC) ou le [!UICONTROL Form-Based Experience Composer] lors de la conception de l’activité.

1. Lorsque vous y êtes invité lors de la [création d’une activité XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), spécifiez l’URL de l’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] correspondent.
   >
   >Par défaut, le compositeur d’expérience visuelle ou le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.
   >
   >Si vous spécifiez une URL pour un site qui n’inclut pas de bibliothèque JavaScript [[!DNL Target] at.js ou  [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}, vous ne pouvez pas sélectionner d’éléments de page.

1. (Conditionnel) Pour afficher une autre page après l’ouverture du VEC, cliquez sur **[!UICONTROL Configure]**, sélectionnez **[!UICONTROL Page Delivery]**, puis spécifiez l’URL dans le champ [!UICONTROL URL] .

   >[!NOTE]
   >
   >Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.

1. (Conditionnel) Cliquez sur **[!UICONTROL Add Rule]** pour ajouter d’autres pages ou sections à l’activité.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox

   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.
