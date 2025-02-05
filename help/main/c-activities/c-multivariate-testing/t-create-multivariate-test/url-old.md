---
keywords: Tests multivariés;URL de l’activité
description: Découvrez comment spécifier l’URL de l’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque l’activité [!UICONTROL Multivariate Test] est conçue à l’aide de  [!DNL Adobe Target].
title: Qu’est-ce que l’URL d’activité dans une activité [!UICONTROL Multivariate Test] (MVT) ?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 34%

---

# URL d’activité

L’URL de l’activité détermine la page utilisée dans le [!UICONTROL Multivariate Test] (MVT) et qui s’ouvre lorsque le test est conçu dans [!DNL Adobe Target].

Lorsque vous y êtes invité au cours de la [création de l’activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] correspondent.

Par défaut, le [!UICONTROL Visual Experience Composer] (VEC) ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

Pour afficher une autre page après l’ouverture du compositeur d’expérience visuelle, cliquez sur l’icône **[!UICONTROL Configure]**, sélectionnez **[!UICONTROL Page Delivery]**, puis spécifiez l’URL.

![Boîte de dialogue Diffusion de page](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Cliquez sur **[!UICONTROL Add Template Rule]** pour ajouter d’autres pages ou sections à l’activité.

Les règles supplémentaires peuvent être basées sur les éléments suivants :

* URL
* Domaine
* Chemin
* Fragment de hachage (#)
* Requête
* Paramètre

D’autres règles peuvent être jointes à l’URL de l’activité avec ET ou OU. Toutes les règles que vous ajoutez sont évaluées les unes par rapport aux autres avec ET.

Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

>[!NOTE]
>
>Si vous avez saisi une URL pour un site qui n’inclut pas le code JavaScript [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez **[!UICONTROL Render using JavaScript]** désactiver si vous souhaitez pouvoir modifier ces éléments à l’aide de l’[!UICONTROL Visual Experience Composer] .

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
