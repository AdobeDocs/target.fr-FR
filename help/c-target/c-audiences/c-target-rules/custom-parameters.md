---
keywords: paramètres personnalisés;paramètres personnalisés target;targetpageparams;ciblage des paramètres mbox
description: Les paramètres personnalisés sont des paramètres mbox. Si vous transférez des paramètres mbox à des mbox ou utilisez la fonction targetPageParams, ces paramètres apparaissent ici pour utilisation dans les audiences.
title: Paramètres personnalisés
feature: Audiences
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 90%

---


# Paramètres personnalisés{#custom-parameters}

Les paramètres personnalisés sont des paramètres mbox. Si vous transférez des paramètres mbox à des mbox ou utilisez la fonction targetPageParams, ces paramètres apparaissent ici pour utilisation dans les audiences.

Pour plus d’informations, voir [Transférer des paramètres à une mbox globale](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

Lors de la création d’une audience personnalisée basée sur un paramètre mbox, `mboxParameter` ne vous demande plus le `mboxName`. Le nom de mbox est désormais optionnel. Cette modification vous permet d’utiliser les paramètres de plusieurs mbox ou de référencer un paramètre qui n’a pas encore été enregistré.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Créer une audience]**.
1. Donnez un nom à l’audience.
1. Cliquez sur **[!UICONTROL Ajouter la règle]** > **[!UICONTROL Personnalisé]**.

   Pour sélectionner le paramètre désiré :

   * Lors de la création d’une nouvelle audience, sélectionnez un nom de paramètre dans la liste, puis commencez à taper les premiers caractères du nom de paramètre souhaité ou tapez le nom complet.
   * Si vous vous souvenez du nom de mbox, mais pas du nom du paramètre, utilisez la case à cocher pour filtrer une mbox connue qui transmet le paramètre désiré.

   Quelle que soit la méthode, il n’existe aucun lien entre la mbox et le paramètre. L’audience travaille sur la base du paramètre au niveau de toutes les mboxes qui transmettent ce paramètre.

   Si vous modifiez une audience existante, le critère de filtrage s’affiche avec le nom de mbox fourni lors de la création.

1. Sélectionnez un évaluateur :

   * Contient (non-respect de la casse)
   * Ne contient pas (non-respect de la casse)
   * Est égal

   ![Audience de paramètre personnalisé](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. Entrez chaque valeur sur une nouvelle ligne.
1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]**, puis définissez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

La [carte contextuelle de détails de définition](/help/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) affiche le nom du paramètre dans la section Règles. Il n’y a aucune référence à la mbox utilisée pour le filtrage.

>[!NOTE]
>
>Pour les audiences personnalisées dont la création est antérieure à la version Target 18.5.1 (22 mai 2018), les noms de mbox ne s’affichent pas dans la carte contextuelle de définition de l’audience. Vous devez à nouveau enregistrer l’audience personnalisée pour que le nom de la mbox s’affiche dans la carte.

## Considérations {#considerations}

* Les audiences et les activités sont évaluées pour une mbox spécifique. Par exemple, si la mbox globale transmet un certain paramètre mais que la mbox régionale ne le fait pas, l’activité/l’audience ciblant ce paramètre ne sera pas qualifiée dans la mbox régionale.
* Le ciblage n’est pas évalué sur les paramètres mbox internes, tels que mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId et mboxVersion.

## Vidéo de formation : Création d’Audiences ![badge didacticiel](/help/assets/tutorial.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
