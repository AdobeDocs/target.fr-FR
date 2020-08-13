---
keywords: Targeting
description: L’URL d’activité détermine la page utilisée dans l’activité de ciblage d’expérience, qui s’ouvre dans le Compositeur d’expérience visuelle (VEC) ou le compositeur d’expérience d’après les formulaires Adobe Target lorsque l’activité est conçue.
title: URL d’activité
feature: xt
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 92%

---


# URL d’activité{#activity-url}

L’URL d’activité détermine la page utilisée dans l’activité de ciblage d’expérience (XT), qui s’ouvre dans le Compositeur d’expérience visuelle (VEC) ou dans le compositeur d’expérience d’après les formulaires lorsque l’activité est conçue.

1. Lorsque vous y êtes invité lors de la [création d’une activité XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), spécifiez l’URL de l’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer une activité]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] se correspondent.
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Visual Experience Composer settings](/help/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.
   >
   >Si vous spécifiez l’URL d’un site qui ne contient pas le code JavaScript de Target Standard, vous ne pouvez pas sélectionner d’éléments de page.

1. (Conditionnel) Pour afficher une autre page après l’ouverture du VEC, cliquez sur **[!UICONTROL Configurer]**, sélectionnez **[!UICONTROL Diffusion de page]** et spécifiez l’URL dans le champ [!UICONTROL URL].

   ![Boîte de dialogue Diffusion de page](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.

1. (Conditionnel) Pour ajouter des pages ou des sections supplémentaires à l’activité, cliquez sur **[!UICONTROL Ajouter une règle de modèle]**.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox

   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Enregistrer]** quand vous avez terminé.