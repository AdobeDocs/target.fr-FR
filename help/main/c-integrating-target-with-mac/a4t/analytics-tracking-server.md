---
keywords: serveur de suivi analytics;A4T;débogueur Adobe Experience Cloud;débogueur Adobe Experience Platform;source de création de rapports;outils de développement
description: 'Découvrez comment spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics pour [!DNL Target] (A4T) si vous utilisez une ancienne version d’at.js. '
title: Comment utiliser un serveur de suivi Analytics ?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 19%

---

# Utilisation d’un serveur de suivi Analytics

Si vous utilisez une ancienne version d’at.js, vous devez spécifier un serveur de suivi Analytics pour les activités qui utilisent [!DNL Adobe Analytics] pour [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>Vous n’avez pas besoin de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].
>
>Le [!DNL Target] L’équipe prend en charge at.js 1.*x* et at.js 2.*x*. Effectuez la mise à niveau vers la mise à jour la plus récente de l’une des principales versions d’at.js pour vous assurer que vous utilisez une version prise en charge. Pour plus d’informations, voir [Informations détaillées sur les versions du fichier at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Pour garantir que les données de [!DNL Target] se rend à l’emplacement correct dans [!DNL Analytics], A4T nécessite qu’un serveur de suivi Analytics soit envoyé dans tous les appels vers Modstats depuis [!DNL Target]. Pour les implémentations utilisant plusieurs serveurs de suivi, utilisez la variable [!DNL Adobe Experience Platform Debugger] ou des outils de développement de votre navigateur pour déterminer le serveur de suivi approprié pour votre activité.

## Obtention du serveur de suivi Analytics à l’aide du débogueur Adobe Experience Platform

Le débogueur doit être affiché sur une page où l’activité est diffusée afin de vous assurer que vous sélectionnez le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Depuis la page sur laquelle vous créez votre activité, ouvrez le [!DNL Adobe Experience Platform Debugger].

   Si vous n’avez pas installé le débogueur, voir [Présentation du débogueur Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Cliquez sur **[!UICONTROL Analytics]** dans le menu de navigation de gauche.

   Le serveur de suivi Analytics se trouve dans la variable [!UICONTROL Hostname] du débogueur.

   * **Serveur de suivi propriétaire**: Si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous utilisez `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur de suivi tiers**: Un serveur de suivi tiers est généralement `[company].sc.omtrdc.net` où la société est le nom de votre société, mais se termine toujours par `sc.omtrdc.net`.
   * **Implémentations CNAME**: `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une requête https (sécurisée). `stats.adobe.com` est un exemple de requête propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Paramètres de création de rapports]** de l’écran **[!UICONTROL Objectifs et paramètres]****[!UICONTROL de votre activité, collez les informations du serveur de suivi dans le champ Serveur de suivi.]**

   >[!NOTE]
   >
   >Sélectionner [!UICONTROL Analytics comme source de création de rapports] pour votre activité pour la variable [!UICONTROL Serveur de suivi] pour être disponible.

## Obtention du serveur de suivi Analytics à l’aide des outils de développement de votre navigateur

Les outils de développement doivent être affichés sur une page où l’activité est diffusée afin de vous assurer que vous sélectionnez le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Dans la page sur laquelle vous créez votre activité, ouvrez les outils de développement du navigateur (dans Google Chrome, cliquez sur les trois points alignés verticalement dans le coin supérieur droit > Plus d’outils > Outils de développement).

   ![Outils de développement Chrome](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Cliquez sur le bouton **[!UICONTROL Réseau]** .

1. Filtrer pour `/ss,` pour afficher les requêtes Analytics.

   ![Outils de développement Chrome avec recherche /ss](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   Le serveur de suivi est le nom d’hôte de la demande.

   * **Serveur de suivi propriétaire**: Si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous utilisez `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur de suivi tiers**: Un serveur de suivi tiers est généralement `[company].sc.omtrdc.net` où la société est le nom de votre société, mais se termine toujours par `sc.omtrdc.net`.
   * **Implémentations CNAME**: `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une requête https (sécurisée). `stats.adobe.com` est un exemple de requête propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Paramètres de création de rapports]** de l’écran **[!UICONTROL Objectifs et paramètres]****[!UICONTROL de votre activité, collez les informations du serveur de suivi dans le champ Serveur de suivi.]**

   >[!NOTE]
   >
   >Sélectionner [!UICONTROL Analytics comme source de création de rapports] pour votre activité pour la variable [!UICONTROL Serveur de suivi] pour être disponible.
