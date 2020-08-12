---
keywords: global mbox;customize global mbox;edit mbox.js;edit at.js;at.js;implement mbox.js;implement at.js
description: Informations vous aidant à personnaliser une mbox globale pour at.js et mbox.js.
title: Personnalisation d’une mbox globale
feature: null
subtopic: Getting Started
topic: Standard
uuid: 0f784d6e-8f36-4c26-adbf-0d56b7d6d390
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 97%

---


# Personnalisation d’une mbox globale{#customize-a-global-mbox}

Informations vous aidant à personnaliser une mbox globale pour at.js et mbox.js.

1. Modification de mbox.js.

   Go to **[!UICONTROL Target]** > **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   * Pour mbox.js, cliquez sur **[!UICONTROL Modifier les paramètres de mbox.js]**.
   * Pour [!DNL at.js], sélectionnez **[!UICONTROL at.js]** sous la méthode d’implémentation, puis cliquez sur **[!UICONTROL Modifier les paramètres at.js]**.

   ![](assets/step-1-edit-mboxjs.png)

1. Modifiez [!DNL mbox.js] ou [!DNL at.js].

   Désactivez **[!UICONTROL Créer automatiquement la mbox globale]**, puis ajoutez le nom de la mbox globale personnalisée que vous souhaitez utiliser pour diffuser des activités à partir de [!DNL Target Standard/Premium]. Cette mbox globale personnalisée est également utilisée pour le suivi des clics.

   ![](assets/step-2-edit-mboxjs-or-atjs.png)

   Cliquez sur **[!UICONTROL Enregistrer]** lorsque vous avez terminé.
1. Implémentez la bibliothèque [!DNL mbox.js] ou [!DNL at.js] sur votre site.

* Pour mbox.js, voir [Implémentation de mbox.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).
* Pour at.js, voir [Implémentation d’at.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).

1. Synchronisation de la transition avec votre publication.

   Dès que vous êtes prêt à ce que [!DNL Target Standard/Premium] utilise votre mbox globale pour toutes les activités à venir, vous pouvez effectuer cette étape.

   Mettez à jour le nom de la mbox globale personnalisée afin qu’il corresponde au nom utilisé dans l’étape 2 ci-dessus.

   ![](assets/step-4-time-the-transition-with-your-release.png)

   >[!IMPORTANT]
   >
   >Lors de l’enregistrement, toutes les activités de votre compte sont synchronisées avec cette mbox. Si elle ne se trouve pas sur votre site, toutes les activités cesseront de fonctionner.

   Cliquez sur **[!UICONTROL Enregistrer]**.
