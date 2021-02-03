---
keywords: serveur de suivi Analytics ; A4T ; débogueur Adobe Experience Cloud ; débogueur Adobe Experience Platform ; source de rapports ; outils de développement
description: Si vous utilisez une ancienne version de at.js ou de mbox.js, vous devez spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics for Target (A4T).
title: Utilisation d’un serveur de suivi Analytics
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 25%

---


# Utilisation d’un serveur de suivi Analytics

Si vous utilisez une ancienne version de at.js ou mbox.js, vous devez spécifier un serveur de suivi Analytics pour les activités qui utilisent [!DNL Analytics] pour [!DNL Target] (A4T).

>[!NOTE]
>
>Si vous utilisez [!DNL Analytics] comme source de rapports de votre activité, il n’est pas nécessaire de spécifier un serveur de suivi lors de la création d’activités si vous utilisez mbox.js version 61 (ou ultérieure) ou at.js version 0.9.1 (ou ultérieure). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].
>
>L’équipe [!DNL Target] prend en charge at.js 1.*x* et at.js 2.*x*. Effectuez la mise à niveau vers la mise à jour la plus récente de l’une des versions majeures d’at.js pour vous assurer que vous exécutez une version prise en charge. Pour plus d’informations, voir [détails de la version d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Pour s’assurer que les données de [!DNL Target] se rendent à l’emplacement correct dans [!DNL Analytics], A4T nécessite l’envoi d’un serveur de suivi Analytics dans tous les appels aux modèles à partir de [!DNL Target]. Pour les implémentations utilisant plusieurs serveurs de suivi, vous pouvez utiliser [!DNL Adobe Experience Platform Debugger] ou les outils de développement de votre navigateur pour déterminer le serveur de suivi approprié pour votre activité.

## Obtention du serveur de suivi Analytics à l’aide du débogueur Adobe Experience Platform

Le débogueur doit être affiché sur une page où l’activité sera diffusée afin de garantir la sélection du serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Dans la page sur laquelle vous créez votre activité, ouvrez [!DNL Adobe Experience Platform Debugger].

   Si vous n’avez pas installé le débogueur, voir [Introduction au débogueur Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Cliquez sur **[!UICONTROL Analytics]** dans le menu de navigation de gauche.

   Le serveur de suivi Analytics se trouve dans la section [!UICONTROL Nom d’hôte] du débogueur.

   * **Serveur** de suivi propriétaire : Si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous vous trouvez sur `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur** de suivi tiers : Un serveur de suivi tiers est généralement  `[company].sc.omtrdc.net` où la société correspond au nom de votre société, mais se termine toujours  `sc.omtrdc.net`par.
   * **Implémentations** CNAME :  `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une demande https (sécurisée). `stats.adobe.com` est un exemple de demande propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Paramètres de création de rapports]** de l’écran **[!UICONTROL Objectifs et paramètres]****[!UICONTROL de votre activité, collez les informations du serveur de suivi dans le champ Serveur de suivi.]**

   >[!NOTE]
   >
   >Vous devez sélectionner [!UICONTROL Analytics en tant que source du Rapports] pour votre activité pour que le champ [!UICONTROL Serveur de suivi] soit disponible.

## Procurez-vous le serveur de suivi Analytics à l’aide des outils de développement de votre navigateur.

Les outils de développement doivent être affichés sur une page sur laquelle l’activité sera diffusée afin de vous assurer que vous sélectionnez le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Dans la page sur laquelle vous créez votre activité, ouvrez les outils de développement du navigateur (dans Google Chrome, cliquez sur les trois points de suspension verticaux dans le coin supérieur droit > Autres outils > Outils de développement).

   ![Outils de développement Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Cliquez sur l&#39;onglet **[!UICONTROL Réseau]**.

1. Filtrer `/ss,` pour afficher les requêtes Analytics.

   ![Outils de développement Chrome avec recherche /ss](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   Le serveur de suivi est le nom d’hôte de la demande.

   * **Serveur** de suivi propriétaire : Si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous vous trouvez sur `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur** de suivi tiers : Un serveur de suivi tiers est généralement  `[company].sc.omtrdc.net` où la société correspond au nom de votre société, mais se termine toujours  `sc.omtrdc.net`par.
   * **Implémentations** CNAME :  `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une demande https (sécurisée). `stats.adobe.com` est un exemple de demande propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Paramètres de création de rapports]** de l’écran **[!UICONTROL Objectifs et paramètres]****[!UICONTROL de votre activité, collez les informations du serveur de suivi dans le champ Serveur de suivi.]**

   >[!NOTE]
   >
   >Vous devez sélectionner [!UICONTROL Analytics en tant que source du Rapports] pour votre activité pour que le champ [!UICONTROL Serveur de suivi] soit disponible.

