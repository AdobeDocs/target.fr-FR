---
description: L'URL d'activité détermine la page utilisée dans l'activité Ciblage d'expérience, qui s'ouvre dans le compositeur d'expérience visuelle (VEC) ou dans le compositeur d'expérience d'après les formulaires lorsque l'activité est conçue.
keywords: Ciblage
seo-description: L'URL d'activité détermine la page utilisée dans l'activité Ciblage d'expérience et qui s'ouvre dans le compositeur d'expérience visuelle d'Adobe Target ou dans le compositeur d'expérience d'après les formulaires lorsque l'activité est conçue.
seo-title: URL d’activité
solution: Target
title: URL d’activité
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# URL d’activité{#activity-url}

L'URL d'activité détermine la page utilisée dans l'activité de ciblage d'expérience, qui s'ouvre dans le compositeur d'expérience visuelle (VEC) ou dans le compositeur d'expérience d'après les formulaires lorsque l'activité est conçue.

1. When prompted while [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), specify the activity URL. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer une activité]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d‘URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] se correspondent.
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.
   >
   >Si vous spécifiez une URL pour un site qui n'inclut pas le code JavaScript Target Standard, vous ne pouvez pas sélectionner d'éléments de page.

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![Boîte de dialogue Diffusion de page](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.

1. (Conditional) Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox
   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Enregistrer]quand vous avez terminé.**