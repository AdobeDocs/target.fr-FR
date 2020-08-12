---
keywords: global mbox;target classic;use global mbox from target classic
description: Par défaut, Target Standard crée une mbox globale appelée target-global-mbox, qui est utilisée pour exécuter les activités créées dans Target Standard. Néanmoins, si vous avez déjà créé une mbox globale sur vos pages pour vos mises en œuvre héritées, vous pouvez utiliser cette mbox pour vos activités Target Standard.
title: Utilisation d’une mbox globale depuis une mise en œuvre héritée
feature: null
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 91%

---


# Utilisation d’une mbox globale depuis une mise en œuvre héritée{#use-a-global-mbox-from-a-legacy-implementation}

Par défaut, Target Standard crée une mbox globale appelée target-global-mbox, qui est utilisée pour exécuter les activités créées dans Target Standard. Néanmoins, si vous avez déjà créé une mbox globale sur vos pages pour vos mises en œuvre héritées, vous pouvez utiliser cette mbox pour vos activités Target Standard.

>[!NOTE]
>
>Vous ne pouvez avoir qu’une seule mbox globale par compte.

Pour utiliser votre mbox globale existante pour [!DNL Target Standard] comme pour votre mise en œuvre héritée, vous devez définir quelques paramètres.

1. Go to [!DNL Target Standard], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   Par défaut, l’option [!UICONTROL Créer automatiquement la mbox globale] est activée et la mbox globale personnalisée est nommée `target-global-mbox`.
1. Si vous souhaitez utiliser une mbox existante, désactivez l’option [!UICONTROL Créer automatiquement la mbox globale] et indiquez le nom d’une mbox globale créée antérieurement dans le champ [!UICONTROL Mbox globale personnalisée.]

   La liste déroulante [!UICONTROL Mbox globale personnalisée] répertorie toutes les mbox de votre compte. Si vous souhaitez utiliser une mbox qui n’existe pas encore, créez la mbox dans Target Classic.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   Les paramètres mbox.js pour votre compte sont mis à jour.
1. Téléchargez le nouveau fichier mbox.js et référencez-le sur votre site.

   Une fois que vous avez mis à jour votre site de production avec le nouveau fichier mbox.js, vous êtes prêt à définir vos préférences.
1. Cliquez sur **[!UICONTROL Administration]** > Compositeur **[!UICONTROL d’expérience]** visuelle.
1. In the [!UICONTROL Global Mbox] field, specify the name of the global mbox you selected on the Implementation page.
1. Cliquez sur **[!UICONTROL Envoyer]**.

   Toutes les activités existantes se mettent à jour afin d’utiliser la mbox globale indiquée, notamment les activités créées et implémentées antérieurement.
   **Résolution des problèmes d’implémentation de Global Mbox** *Pourquoi la mbox globale ne se charge-t-elle pas, ou pourquoi y-a-t-il une latence dans le chargement de la mbox globale lorsque la page se charge ?*

Assurez-vous que la référence mbox.js est le premier appel JavaScript sur la page. Pour obtenir d’autres solutions à ce problème, reportez-vous à la section [Implémentation de Mbox.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).
