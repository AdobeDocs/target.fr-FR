---
keywords: Implémentation;mbox;mbox.js;télécharger mbox.js;configurer mbox.js
description: Découvrez l’implémentation héritée du fichier mbox.js d’Adobe Target. Migration vers le Adobe Experience Platform Web SDK (AEP Web SDK) ou vers la dernière version d’at.js.
title: Comment télécharger la bibliothèque mbox.js de Cible ?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 58%

---


# Téléchargement de mbox.js{#download-mbox-js}

Target Standard et Premium utilisent une version modifiée du fichier mbox.js d’Adobe Target.

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Pour utiliser le [!DNL Adobe Target] [!UICONTROL nouvel Éditeur visuel d’expérience d’], vous devez inclure une ligne supplémentaire de code JavaScript dans votre fichier [!DNL mbox.js].

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** dans [!DNL Target Standard].
1. Cliquez sur **[!UICONTROL Télécharger mbox.js]**, puis suivez le texte affiché à l’écran pour enregistrer le fichier.
1. (Conditionnel) Si vous utilisez [!DNL mbox.js] version 60 ou ultérieure, vous pouvez configurer la bibliothèque pour masquer automatiquement le contenu des pages par défaut jusqu’au chargement des mbox afin de réduire le scintillement sur les sites réactifs.

   Pour plus d’informations, voir « Suppression du scintillement de chargement de page » dans les [paramètres avancés de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Créez la référence au fichier [!DNL mbox.js] sur le site web.

   En commençant avec [!DNL mbox.js] version 57, la référence [!DNL mbox.js] peut être placée n’importe où dans la section `<head>` de la page.

   >[!IMPORTANT]
   >
   >Si vous utilisez une version de [!DNL mbox.js] antérieure à la version 57, la référence doit être le dernier élément dans la section `<head>` de vos pages. Si ce n’est pas le cas, de graves problèmes d’affichage ou de performance peuvent se produire. Voir [Ce que fait mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) pour plus d’informations.

1. Téléchargez le fichier [!DNL mbox.js] enregistré vers l’emplacement de l’environnement d’hébergement spécifié dans le code.
