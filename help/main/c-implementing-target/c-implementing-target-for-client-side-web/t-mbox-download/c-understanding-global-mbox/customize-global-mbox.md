---
keywords: mbox globale;personnaliser la mbox globale;modifier at.js;at.js;implémenter at.js
description: Découvrez comment personnaliser une mbox globale pour at.js sur la page Administration-Mise en oeuvre d’Adobe Target.
title: Comment personnaliser une mbox globale ?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 17%

---

# Personnalisation d’une mbox globale

Informations pour vous aider à personnaliser une [!DNL Adobe Target] mbox globale pour at.js.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.

1. Désactiver **[!UICONTROL Chargement de page activé (création automatique de mbox globale)]**, puis ajoutez le nom de la mbox globale personnalisée que vous souhaitez utiliser pour diffuser des activités à partir de [!DNL Target].

   >[!IMPORTANT]
   >
   >La modification est automatiquement enregistrée lorsque vous sélectionnez une autre mbox globale.

   Cette mbox globale personnalisée est également utilisée pour le suivi des clics.

   ![custom-global-mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Mettez en oeuvre le [!DNL at.js] de votre site.

   Voir [Déploiement d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/how-to-deployatjs/) pour plus d’informations.

1. Synchronisation de la transition avec votre publication.

   Lorsque vous êtes prêt pour [!DNL Target] pour commencer à utiliser votre mbox globale pour toutes les activités à l’avenir, vous pouvez passer à l’étape suivante.

   Mettez à jour le nom de la mbox globale personnalisée afin qu’il corresponde au nom utilisé dans l’étape 2 ci-dessus.

   >[!IMPORTANT]
   >
   >Toutes les activités de votre compte sont synchronisées avec cette mbox. Assurez-vous que la mbox globale est présente sur votre site afin que les activités continuent à fonctionner. Veillez à modifier et à enregistrer à nouveau les activités affectées créées avec le compositeur d’expérience visuelle (VEC) qui se synchronisent avec cette mbox. Il n’est pas nécessaire de réenregistrer les activités créées dans le compositeur d’expérience d’après les formulaires ou via l’API.

