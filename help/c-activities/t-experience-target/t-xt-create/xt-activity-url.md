---
description: L'URL d'activité détermine la page utilisée dans l'activité Ciblage d'expérience, qui s'ouvre dans le compositeur d'expérience visuelle (VEC) ou dans le compositeur d'expérience d'après les formulaires lorsque l'activité est conçue.
keywords: Ciblage
seo-description: L'URL d'activité détermine la page utilisée dans l'activité Ciblage d'expérience et qui s'ouvre dans le compositeur d'expérience visuelle d'Adobe Target ou dans le compositeur d'expérience d'après les formulaires lorsque l'activité est conçue.
seo-title: URL d’activité
solution: Target
title: URL d’activité
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: ca9639ccca286dac182728f7bbd43fac78217209

---


# URL d’activité{#activity-url}

L&#39;URL d&#39;activité détermine la page utilisée dans l&#39;activité de ciblage d&#39;expérience, qui s&#39;ouvre dans le compositeur d&#39;expérience visuelle (VEC) ou dans le compositeur d&#39;expérience d&#39;après les formulaires lorsque l&#39;activité est conçue.

1. Lorsque vous y êtes invité lors [de la création d&#39;une activité XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), spécifiez l&#39;URL de l&#39;activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer une activité]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d‘URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] se correspondent.
   >
   >Par défaut, le compositeur d&#39;expérience visuelle ou d&#39;expérience d&#39;après les formulaires ouvre la page spécifiée dans vos préférences [de compte](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.
   >
   >Si vous spécifiez une URL pour un site qui n&#39;inclut pas le code JavaScript Target Standard, vous ne pouvez pas sélectionner d&#39;éléments de page.

1. (Conditionnel) Pour afficher une autre page après l&#39;ouverture du compositeur d&#39;expérience visuelle, cliquez **[!UICONTROL sur Configurer]**, sélectionnez **[!UICONTROL Diffusion]** de page et spécifiez l&#39;URL dans le champ [!UICONTROL URL] .

   ![Boîte de dialogue Diffusion de page](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.

1. (Conditionnel) Cliquez sur **[!UICONTROL Ajouter une règle]** de modèle pour ajouter d&#39;autres pages ou sections à l&#39;activité.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox
   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Enregistrer]quand vous avez terminé.**