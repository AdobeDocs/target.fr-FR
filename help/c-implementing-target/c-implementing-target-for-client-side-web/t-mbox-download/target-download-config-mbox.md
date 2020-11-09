---
keywords: Implementation;Mbox;mbox.js;download mbox.js;configure mbox.js
description: Target Standard et Premium utilisent une version modifiée du fichier mbox.js d’Adobe Target.
title: Téléchargement de mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 94%

---


# Téléchargement de mbox.js{#download-mbox-js}

Target Standard et Premium utilisent une version modifiée du fichier mbox.js d’Adobe Target.

Pour utiliser le [!DNL Adobe Target] [!UICONTROL nouvel Éditeur visuel d’expérience d’], vous devez inclure une ligne supplémentaire de code JavaScript dans votre fichier [!DNL mbox.js].

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** dans [!DNL Target Standard].
1. Cliquez sur **[!UICONTROL Télécharger mbox.js]**, puis suivez le texte affiché à l’écran pour enregistrer le fichier.
1. (Conditionnel) Si vous utilisez [!DNL mbox.js] version 60 ou ultérieure, vous pouvez configurer la bibliothèque pour masquer automatiquement le contenu des pages par défaut jusqu’au chargement des mbox afin de réduire le scintillement sur les sites réactifs.

   Pour plus d’informations, voir « Suppression du scintillement de chargement de page » dans les [paramètres avancés de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Créez la référence au fichier [!DNL mbox.js] sur le site web.

   En commençant avec [!DNL mbox.js] version 57, la référence [!DNL mbox.js] peut être placée n’importe où dans la section `<head>` de la page.

   >[!IMPORTANT]
   >
   >Si vous utilisez une version de [!DNL mbox.js] antérieure à la version 57, la référence doit être le dernier élément dans la section `<head>` de vos pages. Si ce n’est pas le cas, de graves problèmes d’affichage ou de performance peuvent se produire. Voir [Ce que fait](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) mbox.js pour plus d’informations.

1. Téléchargez le fichier [!DNL mbox.js] enregistré vers l’emplacement de l’environnement d’hébergement spécifié dans le code.
