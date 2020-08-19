---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: Informations destinées à vous aider à personnaliser une mbox globale pour at.js.
title: Personnalisation d’une mbox globale
feature: null
subtopic: Getting Started
topic: Standard
uuid: 0f784d6e-8f36-4c26-adbf-0d56b7d6d390
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 59%

---


# Personnalisation d’une mbox globale{#customize-a-global-mbox}

Informations destinées à vous aider à personnaliser une mbox globale pour at.js.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.

1. Disable **[!UICONTROL Page load enabled (Auto create global mbox)]**, then add the name of the custom global mbox that you would like to use to deliver activities from [!DNL Target].

   Cette mbox globale personnalisée est également utilisée pour le suivi des clics.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** lorsque vous avez terminé.

1. Implement the [!DNL at.js] library on your site.

   Voir [Comment déployer at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) pour en savoir plus.

1. Synchronisation de la transition avec votre publication.

   Dès que vous êtes prêt à ce que [!DNL Target] utilise votre mbox globale pour toutes les activités à venir, vous pouvez effectuer cette étape.

   Mettez à jour le nom de la mbox globale personnalisée afin qu’il corresponde au nom utilisé dans l’étape 2 ci-dessus.

   >[!IMPORTANT]
   >
   >Lors de l’enregistrement, toutes les activités de votre compte sont synchronisées avec cette mbox. Si elle ne se trouve pas sur votre site, toutes les activités cesseront de fonctionner.

