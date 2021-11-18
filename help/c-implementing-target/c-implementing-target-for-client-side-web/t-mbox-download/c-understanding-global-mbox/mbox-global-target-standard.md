---
keywords: mbox globale, target classic, utiliser mbox globale depuis target classic
description: Découvrez comment utiliser une mbox globale héritée pour votre Adobe [!DNL Target] activités si vous avez déjà créé une mbox globale sur vos pages pour vos implémentations héritées.
title: Puis-je utiliser une mbox globale depuis une mise en oeuvre héritée ?
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 36%

---

# Utilisation d’une mbox globale depuis une mise en oeuvre héritée

Par défaut, [!DNL Target] crée une mbox globale appelée target-global-mbox, qui est utilisée pour exécuter les activités créées dans [!DNL Target]. Néanmoins, si vous avez déjà créé une mbox globale sur vos pages pour vos mises en œuvre héritées, vous pouvez utiliser cette mbox pour vos activités [!DNL Target].

>[!NOTE]
>
>Vous ne pouvez avoir qu’une seule mbox globale par compte.

Pour utiliser votre mbox globale existante pour [!DNL Target] comme pour votre mise en œuvre héritée, vous devez définir quelques paramètres.

1. Accédez à [!DNL Target], puis cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.

   Par défaut, **[!UICONTROL Chargement de page activé (mbox globale de création automatique)]** est activé et la mbox globale personnalisée est nommée `target-global-mbox`.

1. Si vous souhaitez utiliser une mbox existante, désactivez **[!UICONTROL Chargement de page activé (mbox globale de création automatique)]**, puis spécifiez le nom d’une mbox globale créée précédemment dans la variable **[!UICONTROL Mbox globale]** champ .

   Le [!UICONTROL Mbox globale] liste déroulante de toutes les mbox de votre compte. Si vous souhaitez utiliser une mbox qui n’existe pas encore, créez la mbox.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Les paramètres pour votre compte sont mis à jour.

1. Téléchargez le nouveau fichier at.js et référencez-le sur votre site.

   Toutes les activités existantes se mettent à jour afin d’utiliser la mbox globale indiquée, notamment les activités créées et implémentées antérieurement.

## Dépannage de la mise en oeuvre globale de mbox

Les questions fréquentes suivantes peuvent être utilisées pour résoudre les problèmes liés à votre implémentation de mbox globale :

### Pourquoi la mbox globale ne se charge-t-elle pas ou pourquoi y-a-t-il une latence dans le chargement de la mbox globale lorsque la page se charge ?

Assurez-vous que la référence at.js est le premier appel JavaScript sur la page. Pour d’autres solutions à ce problème, voir [Questions fréquentes relatives aux mbox globales](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
