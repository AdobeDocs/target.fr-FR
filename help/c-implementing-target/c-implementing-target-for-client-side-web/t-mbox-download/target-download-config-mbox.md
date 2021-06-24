---
keywords: Implémentation;mbox;mbox.js;télécharger mbox.js;configurer mbox.js
description: Découvrez l’implémentation héritée de mbox.js d’Adobe Target. Migrez vers le SDK Web Adobe Experience Platform (SDK Web AEP) ou vers la dernière version d’at.js.
title: Comment télécharger la bibliothèque  [!DNL Target] mbox.js ?
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 74%

---

# Téléchargement de mbox.js

Target Standard et Premium utilisent une version modifiée du fichier mbox.js d’Adobe Target.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel sur vos sites. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Pour utiliser le [!DNL Adobe Target] [!UICONTROL nouvel Éditeur visuel d’expérience d’], vous devez inclure une ligne supplémentaire de code JavaScript dans votre fichier [!DNL mbox.js].

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Mise en oeuvre]** dans [!DNL Target Standard].
1. Cliquez sur **[!UICONTROL Télécharger mbox.js]**, puis suivez le texte affiché à l’écran pour enregistrer le fichier.
1. (Conditionnel) Si vous utilisez [!DNL mbox.js] version 60 ou ultérieure, vous pouvez configurer la bibliothèque pour masquer automatiquement le contenu des pages par défaut jusqu’au chargement des mbox afin de réduire le scintillement sur les sites réactifs.

1. Créez la référence au fichier [!DNL mbox.js] sur le site web.

   En commençant avec [!DNL mbox.js] version 57, la référence [!DNL mbox.js] peut être placée n’importe où dans la section `<head>` de la page.

   >[!IMPORTANT]
   >
   >Si vous utilisez une version de [!DNL mbox.js] antérieure à la version 57, la référence doit être le dernier élément dans la section `<head>` de vos pages. Si ce n’est pas le cas, de graves problèmes d’affichage ou de performance peuvent se produire.

1. Téléchargez le fichier [!DNL mbox.js] enregistré vers l’emplacement de l’environnement d’hébergement spécifié dans le code.
