---
keywords: résolution des problèmes;divergences de mesures;FAQ;rapports;nouveau visiteur;nouveau visiteur;visiteur récurrent;visiteurs récurrents;visite renouvelée;nouvelle visite
description: 'Consultez la liste des questions fréquentes et des réponses sur les rapports d’Adobe. [!DNL Target] '
title: Où puis-je trouver des réponses aux questions sur la création de rapports  [!DNL Target] ?
feature: Rapports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: bdf8fdc0c7d92cb59270518861693ec22eb596f2
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 30%

---

# FAQ sur la création de rapports

Liste des questions fréquentes sur la création de rapports dans [!DNL Adobe Target].

## Quelle est la durée de conservation des données pour les modèles [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage automatique] ?

[!UICONTROL Automated Personalization]  (AP) et les modèles de  [!UICONTROL ciblage ] automatique sont formés sur les 45 derniers jours du comportement des utilisateurs (profils utilisateur, événements d’impression et événements de conversion) de l’activité.

[!UICONTROL Automated Personalization]  (AP) et les modèles de  [!UICONTROL ciblage ] automatique conservent le comportement des utilisateurs, les enregistrements de formation et les données de décision de modèle pendant 90 jours afin de produire des rapports   d’analyse. Au bout de 90 jours, les enregistrements de formation et les décisions de modèle sont ignorés. [!UICONTROL Automated Personalization]  (AP) et les modèles de  [!UICONTROL ciblage ] automatique conservent également les données d’impression et de conversion agrégées au niveau de l’expérience/de l’offre à des fins de création de rapports pendant deux ans. Ces données sont uniquement des données au niveau agrégé et ne contiennent aucune donnée de profil au niveau individuel.

## Comment les mesures Nouveaux visiteurs et Visiteurs récurrents sont-elles comptabilisées ? {#methodology}

La première visite d’un nouveau visiteur dure tant que le visiteur est principal sur le site.
Si l’utilisateur est inactif pendant 30 minutes ou plus, la session est réinitialisée. La réinitialisation de la session signifie que ce visiteur devient un visiteur régulier lors de la prochaine visite ou qu’il redevient principal après 30 minutes d’inactivité.
Si le visiteur se déplace sur le site toutes les 29 minutes pendant une journée entière, il est compté comme un nouveau visiteur toute la journée. La session n’a jamais été réinitialisée, car le visiteur n’a jamais dépassé le seuil de 30 minutes.

Les informations suivantes expliquent de manière plus détaillée comment sont comptabilisés les nouveaux visiteurs et les visiteurs récurrents. Des exemples sont également inclus pour expliquer pourquoi la somme de ces deux segments ne correspond pas toujours au nombre total de visiteurs.

### Nouveaux visiteurs

Le segment des nouveaux visiteurs comprend un visiteur si l’une des conditions suivantes est remplie :

* Il s’agit de sa première visite sur le site.
* Il s’agit de sa première visite sur le site depuis l’effacement des cookies.
* Il s’agit de sa première visite sur le site depuis l’expiration de la [durée de vie du profil du visiteur](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md).

### Visiteurs récurrents

Le segment des visiteurs récurrents comprend un visiteur si l’utilisateur a déjà consulté le site et l’a quitté depuis au moins 30 minutes avant d’y revenir avec les mêmes cookies. Tant que le visiteur revient pendant la durée de vie du profil, il est considéré comme un visiteur récurrent.

Supposons que la durée de vie de votre profil soit définie sur 14 jours (valeur par défaut). Un visiteur est inclus dans le segment Visiteurs récurrents si les conditions suivantes sont remplies :

* Un visiteur consulte le site pour la première fois et est enregistré comme un nouveau visiteur.
* Le visiteur quitte le site, mais revient six jours plus tard.

La durée de vie du profil étant définie sur 14 jours, ce visiteur est inclus dans le segment Visiteurs récurrents . Si le visiteur a supprimé les cookies au cours de cette période de six jours, il est inclus dans le segment Nouveaux visiteurs.

### Exemples expliquant les incohérences entre les nombres de mesures

**Exemple 1** : Si ces deux segments sont appliqués à une activité, les segments Nouveaux visiteurs et Visiteurs récurrents ne totalisent pas toujours le nombre total de visiteurs.

Prenons l’exemple suivant, en prenant en compte les conditions mentionnées ci-dessus pour les nouveaux visiteurs et les visiteurs récurrents :

* Un visiteur consulte le site pour la première fois et est compté comme un nouveau visiteur.
* Le visiteur revient sur le site une fois que les conditions sont remplies pour les visiteurs récurrents et est comptabilisé comme visiteur récurrent.

Ce visiteur est comptabilisé comme un seul visiteur dans le nombre total de visiteurs de l’activité, même s’il est comptabilisé dans les segments Nouveaux visiteurs et Visiteurs récurrents .

**Exemple 2** : Les écarts entre les nombres de nouveaux visiteurs et de visiteurs récurrents dépendent également de la manière dont vous configurez les mesures [ de ](/help/c-activities/r-success-metrics/success-metrics.md)succès de l’activité.

Par exemple :

Plusieurs nouveaux visiteurs visitent votre site et sont qualifiés pour une activité. Ces nouveaux visiteurs sont comptabilisés dans le segment Nouveaux visiteurs . Tous ces visiteurs ont également enregistré une visite dans cette activité.

Certains visiteurs ont atteint la mesure de conversion, qui a été configurée comme &quot;Incrémenter le décompte et laisser l’utilisateur dans l’activité&quot;. Supposons que certains de ces utilisateurs atteignent la mesure de conversion plusieurs fois ; la mesure de conversion n’augmente pas. Toutefois, dans cette configuration, certains utilisateurs peuvent accéder à la mesure de conversion, puis revenir à la page d’accueil, se qualifiant à nouveau à l’activité pour enregistrer une nouvelle visite.

## Pourquoi les rapports [!UICONTROL Ciblage d’expérience] (XT) contiennent-ils des mesures pour les expériences de contrôle ?

Les activités de ciblage d’expérience doivent toujours comporter une expérience de contrôle. Si vous utilisez une activité de ciblage d’expérience de la même manière qu’une activité de [!UICONTROL test A/B], ce qui est relativement courant, les données de contrôle d’expérience s’avèrent utiles. Vous pouvez ignorer les données de contrôle d’expérience si elles ne sont pas utiles dans vos rapports.

## Pourquoi le nombre de visites est-il plus bas dans [!DNL Target] que dans les autres solutions [!DNL Adobe Experience Cloud] ? {#section_7E626FDB417E41B8B58BBF30FB207409}

Les chiffres de mesure signalés par [!DNL Target], par exemple les visites, sont toujours inférieurs aux chiffres signalés dans les autres solutions [!DNL Experience Cloud] pour plusieurs raisons :

* [!DNL Target] comptabilise uniquement les visites des visiteurs qui remplissent les critères de l’activité. Les autres solutions comptabilisent les visites des visiteurs qui affichent la page, indépendamment de l’activité qui les a amenés à la page.
* Il peut y avoir des cas où plusieurs activités (mutuellement exclusives) sont en concurrence pour le même emplacement. Les visiteurs voient donc des contenus différents sur une même page web, ce qui affecte les chiffres de mesure signalés par [!DNL Target].

## Pourquoi n’existe-t-il pas de données disponibles pour le rapport de mon activité ? {#section_E4722F6445884130951DF79981C8289B}

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

Pour plus d’informations sur les environnements, voir [Hôtes](/help/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## Pourquoi le trafic est-il inégal entre mes expériences dans mon activité A/B ou MVT ? {#uneven}

Par exemple, j’ai défini la répartition du trafic sur 50/50 ou 25/25/25/25, mais je vois une répartition très différente entre les expériences dans les rapports. Dans les rapports [!DNL Target], plusieurs raisons peuvent expliquer les écarts entre les nombres de visiteurs :

* Lorsqu’une activité [!DNL Target] est lancée pour la première fois, la distribution du trafic peut être inégale en raison de l’architecture du noeud de périphérie que [!DNL Target] utilise pour optimiser la diffusion de l’expérience. La bonne pratique consiste à donner à une activité un certain temps pour collecter plus de données et la distribution se normalisera. Pour plus d’informations sur l’architecture [!DNL Adobe Target] et les noeuds Edge, voir [Fonctionnement d’Adobe Target](/help/c-intro/how-target-works.md).
* Si vous vous trouvez dans [!DNL Target] ou [!DNL Analytics] et que vous utilisez la mesure **[!UICONTROL Visites]**, n’oubliez pas que [!DNL Target] est un système basé sur les visiteurs et que la distribution du trafic pour un test A/B ou MVT est affectée au niveau des visiteurs. Par conséquent, si vous examinez les résultats de l’activité à l’aide de la mesure **[!UICONTROL Visites]**, la répartition du trafic peut apparaître inégale, car certains visiteurs peuvent avoir plusieurs visites. Visiteurs est la mesure de normalisation standard lors de l’évaluation des performances de l’activité.
* La bonne pratique des tests A/B et MVT consiste à maintenir les divisions de trafic. La modification de la distribution du trafic entre les expériences (du 90/10 au 50/50, par exemple) au cours d’un test peut entraîner des visiteurs inégaux entre les expériences. L’expérience de trafic plus faible risque de ne jamais &quot;rattraper&quot;.
* Si vous suivez les bonnes pratiques ci-dessus et que la répartition du trafic ne se normalise pas au fil du temps, vérifiez les points suivants :

   * Utilisez-vous la dernière bibliothèque at.js ? Pour plus d’informations sur la version actuelle et les notes de mise à jour associées, voir [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

   * S’agit-il d’un test de redirection ? Un minutage incorrect des balises se déclenchant sur la page peut entraîner des divisions de trafic inégales, en particulier lors de l’utilisation de [!DNL Analytics] comme source de données pour une activité [!DNL Target]. Pour plus d’informations sur la façon de remédier à une distribution inégale du trafic sur une activité de redirection avec Analytics for Target (A4T), voir [FAQ sur les offres de redirection - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
