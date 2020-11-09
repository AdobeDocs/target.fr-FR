---
keywords: global mbox;target classic;use global mbox from target classic
description: Par défaut, Target Standard crée une mbox globale appelée target-global-mbox, qui est utilisée pour exécuter les activités créées dans Target Standard. Néanmoins, si vous avez déjà créé une mbox globale sur vos pages pour vos mises en œuvre héritées, vous pouvez utiliser cette mbox pour vos activités Target Standard.
title: Utilisation d’une mbox globale depuis une mise en œuvre héritée
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# Utilisation d’une mbox globale depuis une mise en œuvre héritée{#use-a-global-mbox-from-a-legacy-implementation}

By default, [!DNL Target] creates a global mbox called target-global-mbox, which is used to run activities created in [!DNL Target]. Néanmoins, si vous avez déjà créé une mbox globale sur vos pages pour vos mises en œuvre héritées, vous pouvez utiliser cette mbox pour vos activités [!DNL Target].

>[!NOTE]
>
>Vous ne pouvez avoir qu’une seule mbox globale par compte.

Pour utiliser votre mbox globale existante pour [!DNL Target] comme pour votre mise en œuvre héritée, vous devez définir quelques paramètres.

1. Go to [!DNL Target], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   By default, **[!UICONTROL Page load enabled (Auto-create global mbox]** is enabled, and the custom global mbox is named `target-global-mbox`.

1. If you want to use an existing mbox, disable **[!UICONTROL Page load enabled (Auto-create global mbox]**, and specify the name of a previously created global mbox in the **[!UICONTROL Global Mbox]** field.

   The [!UICONTROL Global Mbox] drop-down lists all mboxes in your account. Si vous souhaitez utiliser une mbox qui n’existe pas encore, créez-la.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Les paramètres mbox.js pour votre compte sont mis à jour.

1. Téléchargez le nouveau fichier at.js et référencez-le sur votre site.

   Toutes les activités existantes se mettent à jour afin d’utiliser la mbox globale indiquée, notamment les activités créées et implémentées antérieurement.

## Dépannage de l’implémentation des mbox globales

Les questions fréquentes suivantes peuvent être utilisées pour résoudre les problèmes liés à votre implémentation de mbox globale :

### Pourquoi la mbox globale ne se charge-t-elle pas ou pourquoi y-a-t-il une latence dans le chargement de la mbox globale lorsque la page se charge ?

Assurez-vous que la référence à at.js est le premier appel JavaScript sur la page. Pour d’autres solutions à ce problème, voir Questions [fréquentes sur les mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)globales.
