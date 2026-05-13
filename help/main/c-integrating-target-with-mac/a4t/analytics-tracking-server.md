---
keywords: serveur de suivi Analytics;A4T;débogueur Adobe Experience Cloud;débogueur Adobe Experience Platform;source de rapports;outils de développement
description: Découvrez comment spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics for  [!DNL Target] (A4T) si vous utilisez une ancienne version d’at.js.
title: Comment utiliser un serveur de suivi Analytics ?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
TQID: https://experienceleague.adobe.com/mJM5kZPQfnWodzwQ3qDKxu1e1Oq2Y53fA2LpSB4SVSc
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 675
ht-degree: 15%

---

# Utiliser un serveur de tracking [!DNL Analytics]

Si vous utilisez une ancienne version d’at.js, vous devez spécifier un serveur de suivi [!DNL Analytics] pour les activités qui utilisent [!DNL Adobe Analytics] for [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>Vous n’avez pas besoin de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Lors de la création de l&#39;activité, vous pouvez laisser le champ [!UICONTROL Tracking Server] vide sur la page [!UICONTROL Goals & Settings].
>
>L’équipe [!DNL Target] prend en charge at.js 1.*x* et at.js 2.*x*. Effectuez la mise à niveau vers la mise à jour la plus récente de l’une des versions majeures d’at.js pour vous assurer que vous exécutez une version prise en charge. Pour plus d’informations, voir [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.

Pour s’assurer que les données de [!DNL Target] sont envoyées à l’emplacement correct dans [!DNL Analytics], A4T exige qu’un serveur de suivi [!DNL Analytics] soit envoyé dans tous les appels à Modstats depuis [!DNL Target]. Pour les implémentations utilisant plusieurs serveurs de suivi, utilisez le [!DNL Adobe Experience Platform Debugger] ou les outils de développement de votre navigateur pour déterminer le serveur de suivi approprié à votre activité.

## Obtenir le serveur de suivi des [!DNL Analytics] à l’aide de l’[!DNL Adobe Experience Platform Debugger]

Le débogueur doit être affiché sur une page où l’activité est diffusée pour vous assurer de sélectionner le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Ouvrez le [!DNL Adobe Experience Platform Debugger] à partir de la page sur laquelle vous créez votre activité.

   Si vous n’avez pas installé le débogueur, consultez la [présentation d’](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html).

1. Cliquez sur **[!UICONTROL Analytics]** dans le menu de navigation de gauche.

   ![Image Screen_DebuggerTrackServ](assets/Screen_DebuggerTrackServ.png)

   Le serveur de suivi [!DNL Analytics] se trouve dans la section [!UICONTROL Hostname] du débogueur.

   * **Serveur de suivi propriétaire** : si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous êtes sur `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur de suivi tiers** : un serveur de suivi tiers est généralement `[company].sc.omtrdc.net` où la société correspond au nom de votre société, mais se termine toujours par `sc.omtrdc.net`.
   * **Implémentations CNAME** : `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une requête https (sécurisée). `stats.adobe.com` est un exemple de requête propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Reporting Settings]** de l’écran de **[!UICONTROL Goal & Settings]** de votre activité, collez les informations du serveur de tracking dans le champ **[!UICONTROL Tracking Server]** .

   >[!NOTE]
   >
   >Sélectionnez les [!UICONTROL Analytics as the Reporting Source] de votre activité pour que le champ [!UICONTROL Tracking Server] soit disponible.

## Obtenez le serveur de suivi [!DNL Analytics] à l’aide des outils de développement de votre navigateur

Les outils de développement doivent être affichés sur une page où l’activité est diffusée afin de vous assurer de sélectionner le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. À partir de la page sur laquelle vous créez votre activité, ouvrez les outils de développement du navigateur (dans Google Chrome, cliquez sur les trois ellipses verticales dans le coin supérieur droit > Plus d’outils > Outils de développement).

   ![Outils de développement ](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Cliquez sur l’onglet **[!UICONTROL Network]** .

1. Filtrez les `/ss,` d’affichage des requêtes [!DNL Analytics].

   ![Outils de développement Chrome avec recherche /ss](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   Le serveur de suivi est le nom d’hôte de la requête.

   * **Serveur de suivi propriétaire** : si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous êtes sur `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur de suivi tiers** : un serveur de suivi tiers est généralement `[company].sc.omtrdc.net` où la société correspond au nom de votre société, mais se termine toujours par `sc.omtrdc.net`.
   * **Implémentations CNAME** : `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une requête https (sécurisée). `stats.adobe.com` est un exemple de requête propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Reporting Settings]** de l’écran de **[!UICONTROL Goal & Settings]** de votre activité, collez les informations du serveur de tracking dans le champ **[!UICONTROL Tracking Server]** .

   >[!NOTE]
   >
   >Sélectionnez les [!UICONTROL Analytics as the Reporting Source] de votre activité pour que le champ [!UICONTROL Tracking Server] soit disponible.
