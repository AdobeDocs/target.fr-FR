---
keywords: Ciblage d’expérience;xt;url d’activité;url
description: Découvrez comment spécifier la variable [!UICONTROL URL d’activité] qui détermine la page utilisée dans le test et qui s’ouvre lorsque la variable [!UICONTROL Ciblage d’expérience] l’activité est conçue à l’aide de [!DNL Adobe Target].
title: Qu’est-ce que la variable [!UICONTROL URL d’activité] Dans un [!UICONTROL Ciblage d’expérience] (XT) Activité ?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 24513d8cb39d38dcfbc74bf40961d5517cc90a4b
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 48%

---

# URL d’activité dans [!UICONTROL Ciblage d’expérience] Activités (XT)

La variable [!UICONTROL URL d’activité] détermine la page utilisée dans une [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] (XT). Il s’agit de la page qui s’ouvre dans la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC) ou [!UICONTROL Compositeur d’expérience d’après les formulaires] lorsque l’activité est conçue.

1. Lorsque vous y êtes invité lors de la [création d’une activité XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), spécifiez l’URL de l’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer une activité]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] se correspondent.
   >
   >Par défaut, le VEC ou [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) ouvre la page qui est spécifiée dans votre [Paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.
   >
   >Si vous spécifiez une URL pour un site qui ne comprend pas de [[!DNL Target] Bibliothèque JavaScript at.js ou [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=fr){target=_blank}, vous ne pouvez pas sélectionner d’éléments de page.

1. (Conditionnel) Pour afficher une autre page après l’ouverture du VEC, cliquez sur **[!UICONTROL Configurer]**, sélectionnez **[!UICONTROL Diffusion de page]**, puis spécifiez l’URL dans la variable [!UICONTROL URL] champ .

   ![Boîte de dialogue Diffusion de page](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

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
