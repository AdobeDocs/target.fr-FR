---
keywords: global mbox;target classic;use global mbox from target classic
description: Par défaut, Target Standard crée une mbox globale appelée target-global-mbox, qui est utilisée pour exécuter les activités créées dans Target Standard. Néanmoins, si vous avez déjà créé une mbox globale sur vos pages pour vos mises en œuvre héritées, vous pouvez utiliser cette mbox pour vos activités Target Standard.
title: Utilisation d’une mbox globale depuis une mise en œuvre héritée
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 50%

---


# Utilisation d’une mbox globale à partir d’une implémentation héritée

Par défaut, [!DNL Target] crée une mbox globale appelée cible-global-mbox, qui est utilisée pour exécuter les activités créées dans [!DNL Target]. Néanmoins, si vous avez déjà créé une mbox globale sur vos pages pour vos mises en œuvre héritées, vous pouvez utiliser cette mbox pour vos activités [!DNL Target].

>[!NOTE]
>
>Vous ne pouvez avoir qu’une seule mbox globale par compte.

Pour utiliser votre mbox globale existante pour [!DNL Target] comme pour votre mise en œuvre héritée, vous devez définir quelques paramètres.

1. Accédez à [!DNL Target], puis cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.

   Par défaut, **[!UICONTROL Le chargement de page est activé (la création automatique de la mbox globale]** est activée et la mbox globale personnalisée est nommée `target-global-mbox`.

1. Si vous souhaitez utiliser une mbox existante, désactivez le chargement de page **[!UICONTROL activé (créez automatiquement la mbox globale]**, puis indiquez le nom d’une mbox globale créée précédemment dans le champ **[!UICONTROL Mbox globale]**.

   La liste déroulante [!UICONTROL Mbox globale] liste toutes les mbox de votre compte. Si vous souhaitez utiliser une mbox qui n’existe pas encore, créez-la.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Les paramètres mbox.js pour votre compte sont mis à jour.

1. Téléchargez le nouveau fichier at.js et référencez-le sur votre site.

   Toutes les activités existantes se mettent à jour afin d’utiliser la mbox globale indiquée, notamment les activités créées et implémentées antérieurement.

## Dépannage de l’implémentation des mbox globales

Les questions fréquentes suivantes peuvent être utilisées pour résoudre les problèmes liés à votre implémentation de mbox globale :

### Pourquoi la mbox globale ne se charge-t-elle pas ou pourquoi y-a-t-il une latence dans le chargement de la mbox globale lorsque la page se charge ?

Assurez-vous que la référence à at.js est le premier appel JavaScript sur la page. Pour d’autres solutions à ce problème, voir [Questions fréquentes sur la mbox globale](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
