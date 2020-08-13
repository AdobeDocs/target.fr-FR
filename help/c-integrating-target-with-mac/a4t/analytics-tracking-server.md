---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
description: Si vous utilisez une ancienne version de at.js ou de mbox.js, vous devez spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics for Target (A4T).
title: Utilisation d’un serveur de suivi Analytics
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 53%

---


# Utilisation d’un serveur de suivi Analytics{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Cloud Debugger] to determine the correct tracking server for your activity.

Le débogueur doit être affiché sur une page où l’activité sera diffusée afin de garantir la sélection du serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Ouvrez la page sur laquelle vous créez votre activité, puis ouvrez la [!DNL Adobe Experience Cloud Debugger].

   Si vous n’avez pas installé le débogueur, voir [Installer l’Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

   The analytics tracking server is found in the [!UICONTROL SiteCatalyst Image] section of the debugger. Le champ porte le nom de *Cookies propriétaires* ou *Cookies tiers* en fonction de l’implémentation, et la valeur du serveur de suivi se présentera sous l’un des formats suivants :[!DNL Analytics]

   * (pour les implémentations CNAME)
   * (pour les implémentations non RDC)
   * (pour les implémentations RDC)

   *Entreprise*[!DNL Analytics] représente le nom de l’entreprise , *mesures* est un exemple de valeur CNAME et *d1* est l’exemple d’un centre de données [!DNL Analytics]
1. Copiez en entier le contenu du champ.
1. Dans la section [!UICONTROL Paramètres de création de rapports] de l’écran [!UICONTROL Objectifs et paramètres]**[!UICONTROL de votre activité, collez les informations du serveur de suivi dans le champ Serveur de suivi.]**

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

