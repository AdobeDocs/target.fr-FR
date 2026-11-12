---
keywords: ciblage;expérience;ajouter une expérience;ajout d’une expérience
description: Utilisez le [!UICONTROL compositeur d’expérience visuelle] (VEC) pour ajouter des expériences aux activités.
title: Comment ajouter des expériences dans une activité A/B ?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
TQID: 'https://experienceleague.adobe.com/7qEiUXkfMbPmtB2eMio0LztOYM3naHxG-WRQZOyMmlU'
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
source-git-commit: 9f1aaf5c0b172b4bbe89266800708881306e4592
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 25%
---
# Ajout d’une expérience {#ab-add-experience}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment ajouter et concevoir une expérience dans une activité A/B et comment la renommer, la rediriger, la dupliquer ou la supprimer.

>[!ENDSHADEBOX]

Le [!DNL Adobe Target] **[!UICONTROL compositeur d’expérience visuelle]** (VEC) fournit une interface visuelle pour ajouter et modifier les expériences sur votre page. Pour plus d’informations sur les expériences, voir [Expériences](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

## Ajouter et concevoir une expérience {#add-experience}

Pour ajouter une expérience et modifier la page correspondant à cette expérience :

1. Dans la page **[!UICONTROL Expériences]** du VEC, cliquez sur l’icône **[!UICONTROL Ajouter]** ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ) en haut du volet **[!UICONTROL Expériences]**.

   Après avoir créé une activité, le compositeur d’expérience visuelle affiche deux onglets sur le côté gauche : Expérience A et Expérience B. L’expérience A est l’expérience de contrôle. Plusieurs expériences peuvent être ajoutées au test.

1. Sélectionnez les éléments à modifier et apportez les modifications souhaitées.

   Lorsque vous passez la souris sur les éléments de la page, les éléments sont mis en surbrillance. Vous pouvez modifier un élément en surbrillance à l’aide du VEC. Si vous avez créé une requête [!DNL Target] sur la page à l’aide de [!DNL Target Classic] (anciennement [!DNL Test&Target]), cette requête [!DNL Target] apparaît comme un élément qui affiche le nom de la requête et peut être modifiée comme tout autre élément.

   Pour obtenir la liste des actions pouvant être exécutées sur un élément de la page affichée pour modifier l’expérience, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Cliquez sur **[!UICONTROL Suivant]** lorsque vous avez terminé de concevoir l’expérience.

>[!NOTE]
>
>Si vous publiez une image provenant d’une source autre que votre page principale (une image hébergée sur `akamai.net` et publiée sur `example.com`, par exemple), cette image ne s’affiche pas dans la miniature de la page dans le diagramme de flux.

## Renommer une expérience {#rename-experience}

Pour donner un nouveau nom à une expérience :

1. Cliquez sur l’icône **[!UICONTROL Renommer l’expérience]** ( ![Icône Renommer](/help/main/assets/icons/Rename.svg) ) en regard de l’expérience.

1. Indiquez un nouveau nom, puis cliquez sur **[!UICONTROL Enregistrer]**.

Lorsque vous nommez ou renommez une expérience, les caractères suivants ne sont pas autorisés :

| Caractère | Description |
|--- |--- |
| `/` | Barre oblique |
| `?` | Point d’interrogation |
| `#` | Croisillon |
| `:` | Deux-points |
| `=` | Égal |
| `+` | Plus |
| `-` | Moins |
| `@` | Arobase |

## Rediriger une expérience vers une URL {#redirect-to-url}

Pour envoyer les visiteurs d’une expérience vers une autre URL, consultez également [Rediriger vers l’URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md) :

1. Dans le volet **[!UICONTROL Expériences]**, cliquez sur l’icône **[!UICONTROL Plus]** ( ![Icône Plus](/help/main/assets/icons/MoreSmall.svg) ) à côté de l’expérience, puis cliquez sur **[!UICONTROL Rediriger vers l’URL]**.

1. Indiquez l’URL vers laquelle vous souhaitez rediriger l’expérience.

1. (Conditionnel) Cochez la case **[!UICONTROL Inclure les paramètres de requête actuels]**.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Duplication d’une expérience {#duplicate-experience}

Vous pouvez copier une expérience dans un test A/B afin d’y apporter des modifications mineures sans avoir à recréer l’expérience. Dans le volet **[!UICONTROL Expériences]**, cliquez sur l’icône **[!UICONTROL Plus]** ( ![Icône Plus](/help/main/assets/icons/MoreSmall.svg) ) à côté de l’expérience, puis cliquez sur **[!UICONTROL Dupliquer]**.

## Suppression d’une expérience {#delete-experience}

Dans le volet **[!UICONTROL Expériences]**, cliquez sur l’icône **[!UICONTROL Plus]** ( ![Icône Plus](/help/main/assets/icons/MoreSmall.svg) ) à côté de l’expérience, cliquez sur **[!UICONTROL Supprimer]**, puis cliquez sur **[!UICONTROL Supprimer]** pour confirmer l’action.
