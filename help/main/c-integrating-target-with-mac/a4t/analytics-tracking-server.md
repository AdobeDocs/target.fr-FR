---
keywords: serveur de suivi analytics;A4T;débogueur Adobe Experience Cloud;débogueur Adobe Experience Platform;source de création de rapports;outils de développement
description: Découvrez comment spécifier un serveur de suivi Analytics pour les activités qui utilisent Analytics for [!DNL Target] (A4T) si vous utilisez une ancienne version d’at.js.
title: Comment utiliser un serveur de suivi Analytics ?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 14%

---

# Utiliser un serveur de suivi [!DNL Analytics]

Si vous utilisez une ancienne version d’at.js, vous devez spécifier un serveur de suivi [!DNL Analytics] pour les activités qui utilisent [!DNL Adobe Analytics] pour [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>Vous n’avez pas besoin de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Tracking Server] vide sur la page [!UICONTROL Goals & Settings].
>
>L’équipe [!DNL Target] prend en charge at.js 1.*x* et at.js 2.*x*. Effectuez la mise à niveau vers la mise à jour la plus récente de l’une des principales versions d’at.js pour vous assurer que vous utilisez une version prise en charge. Pour plus d’informations, voir [détails de version at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.

Pour s’assurer que les données de [!DNL Target] vont à l’emplacement correct dans [!DNL Analytics], A4T nécessite qu’un serveur de suivi [!DNL Analytics] soit envoyé dans tous les appels aux modèles de [!DNL Target]. Pour les implémentations utilisant plusieurs serveurs de suivi, utilisez [!DNL Adobe Experience Platform Debugger] ou les outils de développement de votre navigateur afin de déterminer le serveur de suivi correct pour votre activité.

## Obtenez le serveur de suivi [!DNL Analytics] à l’aide de [!DNL Adobe Experience Platform Debugger]

Le débogueur doit être affiché sur une page où l’activité est diffusée afin de vous assurer que vous sélectionnez le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Depuis la page sur laquelle vous créez votre activité, ouvrez le [!DNL Adobe Experience Platform Debugger].

   Si vous n’avez pas installé le débogueur, reportez-vous à la section [Présentation de l’Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html?lang=fr).

1. Cliquez sur **[!UICONTROL Analytics]** dans le menu de navigation de gauche.

   ![&rbrace;Image Screen_DebuggerTrackKit](assets/Screen_DebuggerTrackServ.png)

   Le serveur de suivi [!DNL Analytics] se trouve dans la section [!UICONTROL Hostname] du débogueur.

   * **Serveur de suivi propriétaire** : si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous utilisez `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur de suivi tiers** : un serveur de suivi tiers est généralement `[company].sc.omtrdc.net` où la société est le nom de votre société, mais se termine toujours par `sc.omtrdc.net`.
   * **Mises en oeuvre CNAME** : `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une requête https (sécurisé). `stats.adobe.com` est un exemple de requête propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Reporting Settings]** de l&#39;écran **[!UICONTROL Goal & Settings]** de votre activité, collez les informations du serveur de suivi dans le champ **[!UICONTROL Tracking Server]** .

   >[!NOTE]
   >
   >Sélectionnez [!UICONTROL Analytics as the Reporting Source] pour votre activité afin que le champ [!UICONTROL Tracking Server] soit disponible.

## Procurez-vous le serveur de suivi [!DNL Analytics] à l’aide des outils de développement de votre navigateur

Les outils de développement doivent être affichés sur une page où l’activité est diffusée afin de vous assurer que vous sélectionnez le serveur de suivi approprié. Vous pouvez également spécifier un serveur de suivi par défaut pour chaque compte. Contactez l’Assistance clientèle pour spécifier ou modifier le serveur par défaut.

1. Sur la page sur laquelle vous créez votre activité, ouvrez les outils de développement du navigateur (dans Google Chrome, cliquez sur les trois points alignés verticalement dans le coin supérieur droit > Plus d’outils > Outils de développement).

   ![Outils de développement Chrome](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Cliquez sur l’onglet **[!UICONTROL Network]** .

1. Filtrez pour `/ss,` afin d’afficher les requêtes [!DNL Analytics].

   ![Outils de développement Chrome avec /ss search](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   Le serveur de suivi est le nom d’hôte de la demande.

   * **Serveur de suivi propriétaire** : si le nom d’hôte de la requête correspond au domaine sur lequel vous vous trouvez, il s’agit d’un serveur de suivi propriétaire. Par exemple, si vous utilisez `adobe.com`, `adobe.com` est le serveur de suivi propriétaire.
   * **Serveur de suivi tiers** : un serveur de suivi tiers est généralement `[company].sc.omtrdc.net` où la société est le nom de votre société, mais se termine toujours par `sc.omtrdc.net`.
   * **Mises en oeuvre CNAME** : `sstats.adobe.com` est un exemple de serveur de suivi propriétaire CNAME pour une requête https (sécurisé). `stats.adobe.com` est un exemple de requête propriétaire CNAME pour une page http (non sécurisée).

1. Copiez en entier le contenu du champ.

1. Dans la section **[!UICONTROL Reporting Settings]** de l&#39;écran **[!UICONTROL Goal & Settings]** de votre activité, collez les informations du serveur de suivi dans le champ **[!UICONTROL Tracking Server]** .

   >[!NOTE]
   >
   >Sélectionnez [!UICONTROL Analytics as the Reporting Source] pour votre activité afin que le champ [!UICONTROL Tracking Server] soit disponible.
