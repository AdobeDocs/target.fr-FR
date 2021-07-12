---
keywords: mbox globale;personnaliser la mbox globale;modifier at.js;at.js;implémenter at.js
description: Découvrez comment personnaliser une mbox globale pour at.js sur la page Administration-Mise en oeuvre d’Adobe Target.
title: Comment personnaliser une mbox globale ?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: fb0a62ecc5609e7b8ef5f6a4fb5a94f8ba025fec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 22%

---

# Personnalisation d’une mbox globale

Informations relatives à la personnalisation d’une mbox globale pour at.js.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.

1. Désactivez **[!UICONTROL Chargement de page activé (créer automatiquement la mbox globale)]**, puis ajoutez le nom de la mbox globale personnalisée que vous souhaitez utiliser pour diffuser des activités à partir de [!DNL Target].

   >[!IMPORTANT]
   >
   >La modification est automatiquement enregistrée lorsque vous sélectionnez une autre mbox globale.

   Cette mbox globale personnalisée est également utilisée pour le suivi des clics.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Implémentez la bibliothèque [!DNL at.js] sur votre site.

   Voir [Comment déployer at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) pour plus d’informations.

1. Synchronisation de la transition avec votre publication.

   Lorsque vous êtes prêt à ce que [!DNL Target] commence à utiliser votre mbox globale pour toutes les activités à l’avenir, vous pouvez passer à cette étape.

   Mettez à jour le nom de la mbox globale personnalisée afin qu’il corresponde au nom utilisé dans l’étape 2 ci-dessus.

   >[!IMPORTANT]
   >
   >Toutes les activités de votre compte sont synchronisées avec cette mbox. Si cette mbox ne se trouve pas sur votre site, toutes les activités cessent de fonctionner.
