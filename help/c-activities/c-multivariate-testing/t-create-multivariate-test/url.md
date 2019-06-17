---
description: L'URL d'activité détermine la page utilisée dans le test multivarié (MVT), qui s'ouvre lorsque le test est conçu dans Target.
keywords: Ciblage
seo-description: L'URL d'activité détermine la page utilisée dans le test multivarié (MVT), qui s'ouvre lorsque le test est conçu dans Adobe Target.
seo-title: URL d’activité
solution: Target
title: URL d’activité
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 0730d5f8f6aa2b72c2069c81d6e5a0183489e91c

---


# URL d’activité{#activity-url}

L&#39;URL d&#39;activité détermine la page utilisée dans le test [!Multivariate (] MVT), qui s&#39;ouvre lorsque le test est conçu dans [!DNL Adobe Target].

Lorsque vous y êtes invité lors [de la création de l&#39;activité](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), indiquez l&#39;URL de l&#39;activité. Saisissez l&#39;URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Suivant]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `https://www.adobe.com`] et [!DNL `http://www.adobe.com`] se correspondent.

Par défaut, le [!UICONTROL compositeur] d&#39;expérience visuelle ouvre la page spécifiée dans vos préférences [de compte](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

Pour afficher une autre page après l&#39;ouverture du compositeur d&#39;expérience visuelle, cliquez sur l&#39;icône **[!UICONTROL Configurer]** , puis sélectionnez **[!UICONTROL Diffusion de page]**, puis précisez l&#39;URL.

![Boîte de dialogue Diffusion de page](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Pour ajouter des pages ou des sections supplémentaires à l’activité, cliquez sur **[!UICONTROL Ajouter une règle de modèle].**

Les règles supplémentaires peuvent être basées sur les éléments suivants :

* URL
* Domaine
* Chemin
* Fragment de hachage (#)
* Requête
* Paramètre

Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

Cliquez sur **[!UICONTROL Enregistrer]quand vous avez terminé.**

>[!NOTE]
>
>Si vous avez saisi l’URL d’un site qui ne contient pas le code JavaScript de Target Standard, vous ne pouvez pas sélectionner d’éléments de page.

Par défaut, le compositeur d&#39;expérience visuelle n&#39;autorise pas les modifications apportées aux éléments contenant du code JavaScript, comme les bannières rotatives. Vous pouvez activer l’option **[!UICONTROL Rendu avec JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du [!UICONTROL compositeur d’expérience visuelle].

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.