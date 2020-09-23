---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Cloud debugger;reporting source
description: Si vous utilisez une ancienne version de at.js ou de mbox.js, vous devez spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics for Target (A4T).
title: Utilisation d’un serveur de suivi Analytics
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 2f437e4cf33e4facba60d53ba545beb95c16f191
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 24%

---


# Utilisation d’un serveur de suivi Analytics{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].
>
>L’ [!DNL Target] équipe prend en charge at.js 1.*x* et at.js 2.*x*. Effectuez la mise à niveau vers la mise à jour la plus récente de l’une des versions majeures d’at.js pour vous assurer que vous exécutez une version prise en charge. For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Platform Debugger] or your browser&#39;s Developer Tools to determine the correct tracking server for your activity.

## Obtention du serveur de suivi Analytics à l’aide du débogueur Adobe Experience Platform

Le débogueur doit être affiché sur une page où l’activité sera diffusée afin de garantir la sélection du serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Ouvrez la page sur laquelle vous créez votre activité, puis ouvrez la [!DNL Adobe Experience Platform Debugger].

   Si vous n’avez pas installé le débogueur, voir [Présentation du débogueur](https://docs.adobe.com/content/help/en/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)Adobe Experience Platform.

   ![](assets/Screen_DebuggerTrackServ.png)

1. Cliquez sur **[!UICONTROL Analytics]** dans le menu de navigation de gauche.

   The analytics tracking server is found in the [!UICONTROL Hostname] section of the debugger.

   * **Serveur** de suivi propriétaire : Si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous êtes sur `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur** de suivi tiers : En règle générale, un serveur de suivi tiers est un serveur `[company].sc.omtrdc.net` où la société correspond au nom de votre société, mais se termine toujours `sc.omtrdc.net`par.
   * **Implémentations** CNAME : `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une demande https (sécurisée). `stats.adobe.com` est un exemple de demande propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.
1. Dans la section **[!UICONTROL Paramètres de création de rapports]** de l’écran **[!UICONTROL Objectifs et paramètres]****[!UICONTROL de votre activité, collez les informations du serveur de suivi dans le champ Serveur de suivi.]**

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

## Procurez-vous le serveur de suivi des analyses à l’aide des outils de développement de votre navigateur.

Les outils de développement doivent être affichés sur une page sur laquelle l’activité sera diffusée afin de vous assurer que vous sélectionnez le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Dans la page sur laquelle vous créez votre activité, ouvrez les outils de développement du navigateur (dans Google Chrome, cliquez sur les trois points de suspension verticaux dans le coin supérieur droit > Autres outils > Outils de développement).

   ![Outils de développement Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Click the **[!UICONTROL Network]** tab.

1. Filtrer pour &quot;/ss&quot; pour afficher les requêtes d’analyse.

   ![Outils de développement Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

   Le serveur de suivi est le nom d’hôte de la demande.

   * **Serveur** de suivi propriétaire : Si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous êtes sur `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur** de suivi tiers : En règle générale, un serveur de suivi tiers est un serveur `[company].sc.omtrdc.net` où la société correspond au nom de votre société, mais se termine toujours `sc.omtrdc.net`par.
   * **Implémentations** CNAME : `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une demande https (sécurisée). `stats.adobe.com` est un exemple de demande propriétaire CNAME pour une page http (non sécurisée).

