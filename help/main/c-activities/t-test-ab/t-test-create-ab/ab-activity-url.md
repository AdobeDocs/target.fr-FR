---
keywords: url de l’activité;url;url différente
description: Découvrez comment définir l’[!UICONTROL URL de l’activité] dans une activité de test A/B, de ciblage d’expérience ou de test multivarié afin de définir des pages de test et de garantir une conception de test précise.
title: Quelle est l’URL de l’activité dans une activité de test A/B, de ciblage d’expérience ou multivarié ?
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: 'https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 25%
---
# URL d’activité {#ab-activity-url}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment spécifier l’URL d’activité d’une activité A/B, de ciblage d’expérience (XT) ou de test multivarié (MVT), comment afficher une autre page et comment ajouter des règles pour d’autres pages ou sections.

>[!ENDSHADEBOX]

L’[!UICONTROL URL de l’activité] détermine la page utilisée dans l’activité. Il s’agit de la page qui s’ouvre dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) ou dans le [!UICONTROL compositeur d’expérience d’après les formulaires] lorsque l’activité est conçue dans [!DNL Adobe Target].

## Spécifier l’URL de l’activité {#specify-url}

Lorsque vous y êtes invité au cours de la création de l’activité, spécifiez l’URL d’activité. Saisissez l’URL complète (y compris `https://`), puis cliquez sur **[!UICONTROL Créer]**.

>[!NOTE]
>
>[!DNL Target] ne fait pas de distinction entre les protocoles d&#39;URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com/fr`] et [!DNL `https://www.adobe.com/fr`] correspondent.

Si vous spécifiez une URL pour un site qui n’inclut pas la bibliothèque JavaScript [!DNL Target] [at.js ou [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=fr){target=_blank}, vous ne pouvez pas sélectionner d’éléments de page.

## Afficher une autre page {#different-page}

Par défaut, le VEC ou le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez spécifier une autre page au cours de la création de l’activité.

Pour afficher une autre page après l’ouverture du compositeur d’expérience visuelle :

1. Sur la page **[!UICONTROL Expériences]**, cliquez sur **[!UICONTROL Configurer]** en haut de la page, puis sélectionnez **[!UICONTROL Diffusion de page]**.

1. Spécifiez l’URL dans le champ **[!UICONTROL URL]**.

1. Cliquez sur **[!UICONTROL Enregistrer]** quand vous avez terminé.

Par défaut, le VEC n’autorise pas la modification d’éléments contenant du code JavaScript tels que les bannières rotatives. Vous pouvez désactiver le rendu **[!UICONTROL à l’aide de JavaScript]** si vous souhaitez pouvoir modifier ces éléments à l’aide du compositeur d’expérience visuelle.

>[!NOTE]
>
>Si vous modifiez l’URL après avoir apporté des modifications à une page pour une ou plusieurs expériences, l’expérience est réinitialisée sur la nouvelle page et les modifications sont perdues.

## Ajouter des règles pour d’autres pages ou sections {#add-rules}

Pour ajouter d’autres pages ou sections à l’activité, cliquez sur **[!UICONTROL Ajouter une règle]** dans les paramètres **[!UICONTROL Diffusion de la page]**, puis cliquez sur **[!UICONTROL Enregistrer]** lorsque vous avez terminé.

Les règles supplémentaires peuvent être basées sur les éléments suivants :

* URL
* Domaine
* Chemin
* Fragment de hachage (#)
* Requête
* Paramètre de mbox
* Valeur personnalisée

D’autres règles peuvent être jointes à l’URL de l’activité avec ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.
