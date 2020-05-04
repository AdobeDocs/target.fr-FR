---
keywords: troubleshooting;metric discrepancies;FAQ;reports
description: Liste des questions fréquentes sur la création de rapports dans Adobe Target.
title: FAQ sur la création de rapports dans Adobe Target
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 9168a8f14ad45dfc48ad5c314df61ee8c02156d5

---


# FAQ sur la création de rapports{#reporting-faq}

Liste des questions fréquentes sur la création de rapports dans [!DNL Target].

## Pourquoi les rapports [!UICONTROL Ciblage d’expérience] (XT) contiennent-ils des mesures pour les expériences de contrôle ?

Les activités de ciblage d’expérience doivent toujours comporter une expérience de contrôle. Si vous utilisez une activité de ciblage d’expérience de la même manière qu’une activité de [!UICONTROL test A/B], ce qui est relativement courant, les données de contrôle d’expérience s’avèrent utiles. Vous pouvez ignorer les données de contrôle d’expérience si elles ne sont pas utiles dans vos rapports.

## Pourquoi le nombre de visites est-il plus bas dans [!DNL Target] que dans les autres solutions [!DNL Adobe Experience Cloud] ?{#section_7E626FDB417E41B8B58BBF30FB207409}

Les chiffres de mesure signalés par [!DNL Target], par exemple le nombre de visites, seront toujours inférieurs aux chiffres signalés dans les autres solutions [!DNL Experience Cloud] pour plusieurs raisons :

* [!DNL Target] comptabilise uniquement les visites des visiteurs qui remplissent les critères de l’activité. Les autres solutions comptabilisent les visites des visiteurs qui affichent la page, indépendamment de l’activité qui les a amenés à la page.
* Il peut y avoir des cas où plusieurs activités (mutuellement exclusives) sont en concurrence pour le même emplacement. Les visiteurs voient donc des contenus différents sur une même page web, ce qui affecte les chiffres de mesure signalés par [!DNL Target].

## Pourquoi n’existe-t-il pas de données disponibles pour le rapport de mon activité ?{#section_E4722F6445884130951DF79981C8289B}

Si le contenu d’une activité a été correctement diffusé aux utilisateurs mais que son rapport ne contient aucune donnée, assurez-vous que l’environnement correct ([groupe d’hôtes](/help/administrating-target/hosts.md)) est sélectionné dans les paramètres du rapport.

Si un environnement de développement est sélectionné, le message suivant peut s’afficher : « Aucune donnée n’est disponible pour les paramètres des rapports sélectionnés. »

Pour modifier l’environnement pour le rapport d’une activité :

1. Cliquez sur **[!UICONTROL Activités]**, sélectionnez l’activité souhaitée dans la liste, puis cliquez sur l’onglet **** Rapports.
1. Cliquez sur l’engrenage pour configurer les paramètres des rapports.

   ![Boîte de dialogue Paramètres A/B](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >L’icône représentant un engrenage n’est pas disponible pour les rapports de [!UICONTROL personnalisation automatisée.]

1. Dans la liste déroulante **[!UICONTROL Environnement]**, sélectionnez **[!UICONTROL Production]**.

   Les données de rapport peuvent ne pas être disponibles si vous avez sélectionné un environnement de développement.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour plus d’informations sur les environnements, voir [Hôtes](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## Pourquoi le trafic est-il divisé entre mes expériences de manière inégale dans mon activité A/B ou MVT ? {#uneven}

Par exemple, j&#39;ai défini la répartition du trafic sur 50/50 ou 33/33/33, mais je vois une répartition très différente entre les expériences dans le rapports.

Il existe un certain nombre de raisons explicables de divisions de trafic inégales dans le [!DNL Target] rapports :

* Lorsqu’une [!DNL Target] activité est lancée pour la première fois, la répartition du trafic peut être inégale en raison de l’architecture de noeud Edge [!DNL Target] utilisée pour optimiser la diffusion d’expérience. La meilleure pratique consiste à donner à une activité du temps pour collecter des données supplémentaires et la distribution se normalisera. Pour plus d’informations sur [!DNL Adobe Target] l’architecture et les noeuds Edge, voir [Fonctionnement](/help/c-intro/how-target-works.md)d’Adobe Cible.
* Quelle mesure de normalisation utilisez-vous ? Si vous êtes dans [!DNL Target] ou [!DNL Analytics] et que vous utilisez la mesure **[!UICONTROL Visites]** , n’oubliez pas qu’il s’agit [!DNL Target] d’un système basé sur un visiteur et que la répartition du trafic pour un test A/B ou MVT est affectée au niveau du visiteur. Par conséquent, si vous examinez les résultats des activités à l’aide de la mesure **[!UICONTROL Visites]** , la répartition du trafic peut s’afficher inégalement car certains visiteurs peuvent avoir plusieurs visites.
* La meilleure pratique pour les tests A/B et MVT consiste à maintenir les divisions de trafic égales. La modification de la répartition du trafic entre les expériences (disons de 90/10 à 50/50) au cours d’un test peut générer des visiteurs inégalement d’une expérience à l’autre.
* Si vous suivez les bonnes pratiques ci-dessus et que la répartition du trafic ne se normalise pas au fil du temps, vérifiez les points suivants :

   * Utilisez-vous la dernière bibliothèque at.js ? Pour plus d’informations sur la version actuelle et les notes de mise à jour associées, voir les détails [de la version](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)at.js.

   * Est-ce un test de redirection ? Le minutage incorrect des balises se déclenchant sur la page peut entraîner des divisions de trafic inégales, en particulier lors [!DNL Analytics] de l’utilisation comme source de données pour une [!DNL Target] activité. Pour plus d’informations sur la résolution des problèmes de distribution inégale du trafic lors d’une activité de redirection avec Analytics pour la Cible (A4T), consultez la FAQ [sur les offres de](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)redirection - A4T.
