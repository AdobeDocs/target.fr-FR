---
keywords: Tests multivariés;URL de l’activité
description: Découvrez comment spécifier l’URL de l’activité qui détermine la page utilisée dans le test et qui s’ouvre lorsque l’activité [!UICONTROL Test multivarié] est conçue à l’aide de [!DNL Adobe Target].
title: Qu’est-ce que l’URL de l’activité dans une activité [!UICONTROL test multivarié] (MVT) ?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 45%
---
# URL d’activité

L’URL de l’activité détermine la page utilisée dans le [!UICONTROL test multivarié] (MVT) et qui s’ouvre lorsque le test est conçu dans [!DNL Adobe Target].

Lorsque vous y êtes invité au cours de la [création de l’activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Suivant]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] correspondent.

Par défaut, le [!UICONTROL compositeur d’expérience visuelle] (VEC) ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

Pour afficher une autre page après l’ouverture du compositeur d’expérience visuelle, cliquez sur l’icône **[!UICONTROL Configurer]**, sélectionnez **[!UICONTROL Diffusion de page]**, puis spécifiez l’URL.

![Boîte de dialogue Diffusion de page](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Pour ajouter des pages ou des sections supplémentaires à l’activité, cliquez sur **[!UICONTROL Ajouter une règle de modèle]**.

Les règles supplémentaires peuvent être basées sur les éléments suivants :

* URL
* Domaine
* Chemin
* Fragment de hachage (#)
* Requête
* Paramètre

D’autres règles peuvent être jointes à l’URL de l’activité avec ET ou OU. Toutes les règles que vous ajoutez sont évaluées les unes par rapport aux autres avec ET.

Cliquez sur **[!UICONTROL Enregistrer]** quand vous avez terminé.

>[!NOTE]
>
>Si vous avez saisi une URL pour un site qui n’inclut pas le code JavaScript [!DNL Target], vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez activer l’option **[!UICONTROL Rendu avec JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du [!UICONTROL compositeur d’expérience visuelle].

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.
