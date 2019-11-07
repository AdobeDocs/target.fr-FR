---
keywords: serveur de suivi Analytics;A4T;débogueur Adobe Experience Cloud;source de rapports
description: Si vous utilisez une ancienne version de at.js ou de mbox.js, vous devez spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics for Target (A4T).
title: Utilisation d’un serveur de suivi Analytics
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Utilisation d’un serveur de suivi Analytics{#use-an-analytics-tracking-server}

Si vous utilisez une ancienne version de at.js ou de mbox.js, vous devez spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics for Target (A4T).

>[!NOTE]
>
>Si vous utilisez Adobe Analytics comme source des rapports de votre activité, vous ne devez pas spécifier de serveur de suivi durant la création d’activités si vous utilisez mbox.js version 61 (ou ultérieure) ou at.js version 0.9.1 (ou ultérieure). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

Afin de garantir que les données de Target sont transférées dans l’emplacement approprié dans Analytics, A4T requiert un serveur de suivi Analytics à envoyer dans tous les appels de Modstats depuis Target. Pour les implémentations ayant recours à plusieurs serveurs de suivi, vous pouvez utiliser le débogueur Adobe Experience Cloud afin de déterminer quel serveur convient à votre activité.

Le débogueur doit être affiché sur une page où l’activité sera diffusée afin de garantir la sélection du serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Depuis la page sur laquelle vous créez votre activité, ouvrez le débogueur Adobe Experience Cloud.

   Si vous n’avez pas installé le débogueur, voir [Installation du débogueur](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html)Experience Cloud.

   ![](assets/Screen_DebuggerTrackServ.png)

   Le serveur de suivi d’Analytics se trouve dans la section Image de SiteCatalyst du débogueur. Le champ porte le nom de *Cookies propriétaires* ou *Cookies tiers* en fonction de l’implémentation, et la valeur du serveur de suivi Analytics se présentera sous l’un des formats suivants :

   * (pour les implémentations CNAME)
   * (pour les implémentations non RDC)
   * (pour les implémentations RDC)
   *Entreprise* représente le nom de l’entreprise Analytics, *mesures* est un exemple de valeur CNAME et *d1* est l’exemple d’un centre de données Analytics.
1. Copiez en entier le contenu du champ.
1. Dans la section [!UICONTROL Paramètres de création de rapports] de l’écran [!UICONTROL Objectifs et paramètres]**de votre activité, collez les informations du serveur de suivi dans le champ[!UICONTROL Serveur de suivi.]**

   >[!NOTE]
   >
   >Vous devez sélectionner Adobe Analytics comme Source de création de rapports pour votre activité afin que le champ Serveur de suivi soit disponible.

