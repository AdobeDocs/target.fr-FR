---
keywords: Tests multivariés, URL d’activité
description: Découvrez comment spécifier l’URL d’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque l’activité [!UICONTROL Multivariate Test] est conçue à l’aide de [!DNL Adobe Target].
title: Quelle est l’URL d’activité dans une activité [!UICONTROL Multivariate Test] (MVT) ?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 34%

---

# URL d’activité

L’URL d’activité détermine la page qui est utilisée dans le [!UICONTROL Multivariate Test] (MVT) et qui s’ouvre lorsque le test est conçu dans le [!DNL Adobe Target].

Lorsque vous y êtes invité au cours de la [création de l’activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] correspondent tous les deux.

Par défaut, le [!UICONTROL Visual Experience Composer] (VEC) ouvre la page qui est spécifiée dans vos [ paramètres du compositeur d’expérience visuelle ](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

Pour afficher une autre page après l’ouverture du VEC, cliquez sur l’icône **[!UICONTROL Configure]**, puis sélectionnez **[!UICONTROL Page Delivery]**, puis spécifiez l’URL.

![Boîte de dialogue Diffusion de page](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Cliquez sur **[!UICONTROL Add Template Rule]** pour ajouter d’autres pages ou sections à l’activité.

Les règles supplémentaires peuvent être basées sur les éléments suivants :

* URL
* Domaine
* Chemin
* Fragment de hachage (#)
* Requête
* Paramètre

Des règles supplémentaires peuvent être jointes à l’URL de l’activité avec l’opérateur ET ou OU. Toutes les règles que vous ajoutez sont évaluées les unes par rapport aux autres avec l’opérateur ET.

Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

>[!NOTE]
>
>Si vous avez saisi l’URL d’un site qui ne contient pas le code JavaScript [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez désactiver **[!UICONTROL Render using JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide de [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
