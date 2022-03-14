---
keywords: Ciblage d’expérience;xt;url d’activité;url
description: Découvrez comment spécifier l’URL d’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque l’activité de ciblage d’expérience est conçue à l’aide d’Adobe Target.
title: Qu’est-ce que l’URL d’activité dans une activité de ciblage d’expérience (XT) ?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 63%

---

# URL d’activité dans les activités de ciblage d’expérience (XT)

Le [!UICONTROL URL d’activité] détermine la page qui est utilisée dans la variable [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] (XT), qui s’ouvre dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC) ou [!UICONTROL Compositeur d’expérience d’après les formulaires] lorsque l’activité est conçue.

1. Lorsque vous y êtes invité lors de la [création d’une activité XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), spécifiez l’URL de l’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer une activité]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] se correspondent.
   >
   >Par défaut, le VEC ou le compositeur d’expérience d’après les formulaires ouvre la page qui est spécifiée dans votre [Paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.
   >
   >Si vous spécifiez l’URL d’un site qui ne contient pas le code JavaScript de Target Standard, vous ne pouvez pas sélectionner d’éléments de page.

1. (Conditionnel) Pour afficher une autre page après l’ouverture du VEC, cliquez sur **[!UICONTROL Configurer]**, sélectionnez **[!UICONTROL Diffusion de page]** et spécifiez l’URL dans le champ [!UICONTROL URL].

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
