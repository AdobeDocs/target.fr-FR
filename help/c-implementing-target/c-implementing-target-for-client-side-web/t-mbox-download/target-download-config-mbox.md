---
keywords: Implémentation;mbox;mbox.js;télécharger mbox.js;configurer mbox.js
description: Target Standard et Premium utilisent une version modifiée du fichier mbox.js d’Adobe Target.
title: Téléchargement de mbox.js
subtopic: Prise en main
topic: Standard
uuid: b2a46321-cac7-4924-92dd-a80b50e27cee
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Téléchargement de mbox.js{#download-mbox-js}

Target Standard et Premium utilisent une version modifiée du fichier mbox.js d’Adobe Target.

Pour utiliser le [!DNL Adobe Target] [!UICONTROL nouvel Éditeur visuel d’expérience d’], vous devez inclure une ligne supplémentaire de code JavaScript dans votre fichier [!DNL mbox.js].

1. Cliquez sur **[!UICONTROL Configuration]** &gt; **[!UICONTROL Implémentation]** dans [!DNL Target Standard].
1. Cliquez sur **[!UICONTROL Télécharger mbox.js]**, puis suivez le texte affiché à l’écran pour enregistrer le fichier.
1. (Conditionnel) Si vous utilisez [!DNL mbox.js] version 60 ou ultérieure, vous pouvez configurer la bibliothèque pour masquer automatiquement le contenu des pages par défaut jusqu’au chargement des mbox afin de réduire le scintillement sur les sites réactifs.

   Pour plus d’informations, voir « Suppression du scintillement de chargement de page » dans les [paramètres avancés de mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Créez la référence au fichier [!DNL mbox.js] sur le site web.

   En commençant avec [!DNL mbox.js] version 57, la référence [!DNL mbox.js] peut être placée n’importe où dans la section `<head>` de la page.

   >[!IMPORTANT]
   >
   >Si vous utilisez une version de [!DNL mbox.js] antérieure à la version 57, la référence doit être le dernier élément dans la section `<head>` de vos pages. Si ce n’est pas le cas, de graves problèmes d’affichage ou de performance peuvent se produire. Pour plus d’informations, voir [Que fait](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) mbox.js.

1. Téléchargez le fichier [!DNL mbox.js] enregistré vers l’emplacement de l’environnement d’hébergement spécifié dans le code.
