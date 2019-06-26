---
description: Les paramètres personnalisés sont des paramètres mbox. Si vous transférez des paramètres mbox à des mbox ou utilisez la fonction targetPageParams, ces paramètres apparaissent ici pour utilisation dans les audiences.
keywords: paramètres personnalisés;paramètres personnalisés target;targetpageparams;ciblage des paramètres mbox
seo-description: Les paramètres personnalisés sont des paramètres mbox. Si vous transférez des paramètres mbox à des mbox ou utilisez la fonction targetPageParams, ces paramètres apparaissent ici pour utilisation dans les audiences.
seo-title: Paramètres personnalisés
solution: Target
title: Paramètres personnalisés
topic: Standard
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Paramètres personnalisés{#custom-parameters}

Les paramètres personnalisés sont des paramètres mbox. Si vous transférez des paramètres mbox à des mbox ou utilisez la fonction targetPageParams, ces paramètres apparaissent ici pour utilisation dans les audiences.

Pour plus d’informations, voir [Transfert de paramètres à une mbox globale](https://marketing.adobe.com/resources/help/en_US/target/ov/c_pass_parameters_to_global_mbox.html).

Lors de la création d’une audience personnalisée basée sur un paramètre mbox, `mboxParameter` ne vous demande plus le `mboxName`. Le nom de mbox est désormais optionnel. Cette modification vous permet d’utiliser les paramètres de plusieurs mbox ou de référencer un paramètre qui n’a pas encore été enregistré.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** &gt; **[!UICONTROL Créer une audience]**.
1. Donnez un nom à l’audience.
1. Click **[!UICONTROL Add Rule]** &gt; **[!UICONTROL Custom]**.

   Pour sélectionner le paramètre désiré :

   * Lors de la création d’une nouvelle audience, sélectionnez un nom de paramètre dans la liste, puis commencez à taper les premiers caractères du nom de paramètre souhaité ou tapez le nom complet.
   * Si vous vous souvenez du nom de mbox, mais pas du nom du paramètre, utilisez la case à cocher pour filtrer une mbox connue qui transmet le paramètre désiré.
   Quelle que soit la méthode, il n’existe aucun lien entre la mbox et le paramètre. L’audience travaille sur la base du paramètre au niveau de toutes les mboxes qui transmettent ce paramètre.

   Si vous modifiez une audience existante, le critère de filtrage s’affiche avec le nom de mbox fourni lors de la création.

1. Sélectionnez un évaluateur:

   * Contient (non-respect de la casse)
   * Ne contient pas (non-respect de la casse)
   * Est égal
   ![Audience de paramètre personnalisé](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. Entrez chaque valeur dans une nouvelle ligne.
1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]**, puis définissez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

La [carte contextuelle de détails de définition](../../../c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) affiche le nom du paramètre dans la section Règles. Il n’y a aucune référence à la mbox utilisée pour le filtrage.

>[!NOTE]
>
>Pour les audiences personnalisées dont la création est antérieure à la version Target 18.5.1 (22 mai 2018), les noms de mbox ne s’affichent pas dans la carte contextuelle de définition de l’audience. Vous devez à nouveau enregistrer l’audience personnalisée pour que le nom de la mbox s’affiche dans la carte.

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=fre_fr)