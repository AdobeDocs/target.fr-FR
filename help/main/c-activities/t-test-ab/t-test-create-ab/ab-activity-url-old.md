---
keywords: url de l’activité;url;url différente
description: Découvrez comment spécifier l’URL d’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide de  [!DNL Adobe Target].
title: Quelle est l’URL de l’activité dans une activité A/B ?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 55%

---

# URL d’activité

L’URL de l’activité détermine la page utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide d’Adobe Target.

Lorsque vous y êtes invité au cours de la création de l’activité, spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://www.adobe.com`] correspondent.

## Spécification d’une URL différente

Par défaut, le [!UICONTROL compositeur d’expérience visuelle] ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

1. Pour afficher une autre page après l’ouverture du [!UICONTROL compositeur d’expérience visuelle], sur la page **[!UICONTROL Expériences]**, cliquez sur l’icône d’engrenage **[!UICONTROL Configurer]**, puis sélectionnez **[!UICONTROL Diffusion de page]**.

1. Spécifiez l’URL dans le champ **[!UICONTROL URL]**.

   ![Boîte de dialogue Diffusion de page](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

1. (Conditionnel) Cliquez sur **[!UICONTROL Ajouter une règle de modèle]** pour ajouter d’autres pages ou sections à l’activité.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox

   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

1. Cliquez sur **[!UICONTROL Enregistrer]** quand vous avez terminé.

Si vous avez saisi l’URL d’un site qui ne contient pas le code JavaScript de Standard [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le [!UICONTROL compositeur d’expérience visuelle] n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez activer l’option **[!UICONTROL Rendu avec JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du [!UICONTROL compositeur d’expérience visuelle].

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
