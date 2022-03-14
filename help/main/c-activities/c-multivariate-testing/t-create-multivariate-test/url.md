---
keywords: Tests multivariés, URL d’activité
description: Découvrez comment spécifier l’URL d’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque l’activité de test multivarié est conçue à l’aide d’Adobe Target.
title: Qu’est-ce que l’URL d’activité dans une activité multivariée (MVT) ?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 85%

---

# URL d’activité

L’URL d’activité détermine la page qui est utilisée dans le [!UICONTROL test multivarié] (MVT), et qui s’ouvre lorsque le test est conçu dans [!DNL Adobe Target].

Lorsque vous y êtes invité au cours de la [création de l’activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Suivant]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] se correspondent.

Par défaut, le [!UICONTROL compositeur dʼexpérience visuelle] (VEC) ouvre la page qui est spécifiée dans vos [paramètres du compositeur dʼexpérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

Pour afficher une autre page après l’ouverture du VEC, cliquez sur l’icône **[!UICONTROL Configurer]**, puis sélectionnez **[!UICONTROL Diffusion de page]**, puis spécifiez l’URL.

![Boîte de dialogue Diffusion de page](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Pour ajouter des pages ou des sections supplémentaires à l’activité, cliquez sur **[!UICONTROL Ajouter une règle de modèle]**.

Les règles supplémentaires peuvent être basées sur les éléments suivants :

* URL
* Domaine
* Chemin
* Fragment de hachage (#)
* Requête
* Paramètre

Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

Cliquez sur **[!UICONTROL Enregistrer]** quand vous avez terminé.

>[!NOTE]
>
>Si vous avez saisi l’URL d’un site qui ne contient pas le code JavaScript de Target Standard, vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez activer l’option **[!UICONTROL Rendu avec JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du [!UICONTROL compositeur d’expérience visuelle].

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
