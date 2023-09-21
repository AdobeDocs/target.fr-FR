---
keywords: url d’activité;url;URL différente
description: Découvrez comment spécifier l’URL d’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide de [!DNL Adobe Target].
title: Quelle est l’URL d’activité dans une activité A/B ?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: 6bca763d24649349dbc7cdf6e5f2dbc4ac0a480d
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 64%

---

# URL d’activité

L’URL d’activité détermine la page qui est utilisée dans le test et qui s’ouvre lorsque le test est conçu à l’aide d’Adobe Target.

Lorsque vous y êtes invité au cours de la création de l’activité, spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://www.adobe.com`] se correspondent.

## Spécification d’une URL différente

Par défaut, la variable [!UICONTROL Compositeur d’expérience visuelle] ouvre la page qui est spécifiée dans votre [Paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

1. Pour afficher une autre page après l’événement [!UICONTROL Compositeur d’expérience visuelle] s’ouvre, sur la **[!UICONTROL Expériences]** , cliquez sur **[!UICONTROL Configurer]** icône d’engrenage, puis sélectionnez **[!UICONTROL Diffusion de page]**.

1. Spécifiez l’URL dans la variable **[!UICONTROL URL]** champ .

   ![Boîte de dialogue Diffusion de page](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

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

Si vous avez saisi l’URL d’un site qui ne contient pas le code JavaScript de Standard [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le [!UICONTROL compositeur d’expérience visuelle] n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez activer l’option **[!UICONTROL Rendu avec JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du [!UICONTROL compositeur d’expérience visuelle].

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
