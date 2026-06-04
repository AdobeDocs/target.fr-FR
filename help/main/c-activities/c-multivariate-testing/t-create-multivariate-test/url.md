---
keywords: Tests multivariés;URL de l’activité
description: Découvrez comment spécifier l’URL de l’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque l’activité [!UICONTROL Test multivarié] est conçue à l’aide de  [!DNL Adobe Target].
title: Qu’est-ce que l’URL de l’activité dans une activité [!UICONTROL test multivarié] (MVT) ?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
TQID: https://experienceleague.adobe.com/oQKwrlZ95XKEKSJIUiWqXXo9AJJzCb20gfS1rtwGImM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 38%

---

# URL d’activité

L’URL de l’activité détermine la page utilisée dans le [!UICONTROL test multivarié] (MVT) et qui s’ouvre lorsque le test est conçu dans [!DNL Adobe Target].

1. Lorsque vous y êtes invité au cours de la [création de l’activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] correspondent.

   Par défaut, le [!UICONTROL compositeur d’expérience visuelle] (VEC) ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

1. (Conditionnel) Pour afficher une autre page après l’ouverture du compositeur d’expérience visuelle, cliquez sur l’icône **[!UICONTROL Configurer]**, puis sélectionnez **[!UICONTROL Diffusion de page]** et spécifiez l’URL.

1. (Conditionnel) Cliquez sur **[!UICONTROL Ajouter une règle]** pour ajouter d’autres pages ou sections à l’activité.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * [!UICONTROL &#x200B; URL]
   * [!UICONTROL Domaine]
   * [!UICONTROL Chemin]
   * [!UICONTROL Fragment de hachage (#)]
   * [!UICONTROL Requête]
   * [!UICONTROL Personnalisé]

   D’autres règles peuvent être jointes à l’URL de l’activité avec ET ou OU. Toutes les règles que vous ajoutez sont évaluées les unes par rapport aux autres avec ET.

   Cliquez sur **[!UICONTROL Enregistrer]** quand vous avez terminé.

>[!NOTE]
>
>Si vous avez saisi une URL pour un site qui n’inclut pas le code JavaScript [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.
>
>Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez activer l’option **[!UICONTROL Rendu avec JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du [!UICONTROL compositeur d’expérience visuelle].

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
