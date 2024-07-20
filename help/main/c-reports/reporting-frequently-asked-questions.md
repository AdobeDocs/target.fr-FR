---
keywords: résolution des problèmes;divergences de mesures;FAQ;rapports;nouveau visiteur;nouveau visiteur;visiteur récurrent;visiteurs récurrents;visite renouvelée;nouvelle visite
description: Consultez la liste des questions fréquentes et des réponses sur la création de rapports Adobe [!DNL Target] .
title: Où puis-je trouver des réponses aux questions sur la création de rapports  [!DNL Target] ?
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 20%

---

# FAQ sur la création de rapports

Liste des questions fréquentes sur la création de rapports dans [!DNL Adobe Target].

## Comment les mesures Nouveaux visiteurs et Visiteurs récurrents sont-elles comptabilisées ? {#methodology}

La première visite d’un nouveau visiteur dure tant qu’il est actif sur le site.
Si l’utilisateur est inactif pendant 30 minutes ou plus, la session est réinitialisée. La réinitialisation de la session signifie que ce visiteur devient un visiteur récurrent lors de la prochaine visite ou qu’il redevient actif après 30 minutes d’inactivité.
Si le visiteur se déplace sur le site toutes les 29 minutes pendant une journée entière, il est compté comme un nouveau visiteur toute la journée. La session n’a jamais été réinitialisée, car le visiteur n’a jamais dépassé le seuil de 30 minutes.

Les informations suivantes expliquent de manière plus détaillée comment sont comptabilisés les nouveaux visiteurs et les visiteurs récurrents. Des exemples sont également inclus pour expliquer pourquoi la somme de ces deux segments ne correspond pas toujours au nombre total de visiteurs.

### Nouveaux visiteurs

Le segment des nouveaux visiteurs comprend un visiteur si l’une des conditions suivantes est remplie :

* Il s’agit de la première visite du visiteur sur le site.
* Il s’agit de sa première visite sur le site depuis l’effacement des cookies.
* Il s’agit de la première visite du visiteur sur le site depuis l’expiration de la [durée de vie du profil du visiteur](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md).

### Visiteurs récurrents

Le segment des visiteurs récurrents comprend un visiteur si l’utilisateur a déjà consulté le site et l’a quitté depuis au moins 30 minutes avant d’y revenir avec les mêmes cookies. Tant que le visiteur revient pendant la durée de vie du profil, il est considéré comme un visiteur récurrent.

Supposons que la durée de vie de votre profil soit définie sur 14 jours (valeur par défaut). Un visiteur est inclus dans le segment Visiteurs récurrents si les conditions suivantes sont remplies :

* Un visiteur consulte le site pour la première fois et est enregistré comme un nouveau visiteur.
* Le visiteur quitte le site, mais revient six jours plus tard.

La durée de vie du profil étant définie sur 14 jours, ce visiteur est inclus dans le segment Visiteurs récurrents . Si le visiteur a supprimé les cookies au cours de cette période de six jours, il est inclus dans le segment Nouveaux visiteurs.

### Exemples expliquant les incohérences entre les nombres de mesures

**Exemple 1** : si ces deux segments sont appliqués à une activité, les segments Nouveaux visiteurs et Visiteurs récurrents ne totalisent pas toujours le nombre total de visiteurs.

Prenons l’exemple suivant, en prenant en compte les conditions mentionnées ci-dessus pour les nouveaux visiteurs et les visiteurs récurrents :

* Un visiteur consulte le site pour la première fois et est compté comme un nouveau visiteur.
* Le visiteur revient sur le site une fois que les conditions sont remplies pour les visiteurs récurrents et est comptabilisé comme visiteur récurrent.

Ce visiteur est comptabilisé comme un seul visiteur dans le nombre total de visiteurs de l’activité, même s’il est comptabilisé dans les segments Nouveaux visiteurs et Visiteurs récurrents .

**Exemple 2** : les écarts entre les nombres de nouveaux visiteurs et de visiteurs récurrents dépendent également de la manière dont vous configurez les [mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md) de l’activité.

Par exemple :

Plusieurs nouveaux visiteurs visitent votre site et sont qualifiés pour une activité. Ces nouveaux visiteurs sont comptabilisés dans le segment Nouveaux visiteurs . Tous ces visiteurs ont également enregistré une visite dans cette activité.

Certains visiteurs ont atteint la mesure de conversion, qui a été configurée comme &quot;Incrémenter le décompte et laisser l’utilisateur dans l’activité&quot;. Supposons que certains de ces utilisateurs atteignent la mesure de conversion plusieurs fois ; la mesure de conversion n’augmente pas. Toutefois, dans cette configuration, certains utilisateurs peuvent accéder à la mesure de conversion, puis revenir à la page d’accueil, se qualifiant à nouveau à l’activité pour enregistrer une nouvelle visite.

## Pourquoi mes rapports [!UICONTROL Experience Targeting] (XT) contiennent-ils des mesures pour les expériences de contrôle ?

Les activités de ciblage d’expérience doivent toujours comporter une expérience de contrôle. Si vous utilisez une activité XT de la même manière qu’une activité [!UICONTROL A/B Test], ce qui est un scénario assez courant, les données d’expérience de contrôle sont utiles. Vous pouvez ignorer les données de contrôle d’expérience si elles ne sont pas utiles dans vos rapports.

## Pourquoi le nombre de visites est-il plus bas dans [!DNL Target] que dans les autres solutions [!DNL Adobe Experience Cloud] ? {#section_7E626FDB417E41B8B58BBF30FB207409}

Les chiffres de mesure signalés par [!DNL Target], par exemple les visites, sont toujours inférieurs aux chiffres signalés dans les autres solutions [!DNL Experience Cloud] pour plusieurs raisons :

* [!DNL Target] comptabilise uniquement les visites des visiteurs qui remplissent les critères de l’activité. Les autres solutions comptabilisent les visites des visiteurs qui affichent la page, indépendamment de l’activité qui les a amenés à la page.
* Il peut y avoir des cas où plusieurs activités (mutuellement exclusives) sont en concurrence pour le même emplacement. Les visiteurs voient donc des contenus différents sur une même page web, ce qui affecte les chiffres de mesure signalés par [!DNL Target].

## Pourquoi n’existe-t-il pas de données disponibles pour le rapport de mon activité ? {#section_E4722F6445884130951DF79981C8289B}

Si le contenu d’une activité a été correctement diffusé aux visiteurs mais que son rapport ne contient aucune donnée, le message d’erreur suivant peut s’afficher : &quot;Aucune donnée n’est disponible pour les paramètres de rapport sélectionnés&quot;.

Il existe plusieurs raisons pour lesquelles les données sont manquantes dans les rapports d’activité :

* L’environnement correct n’est pas sélectionné dans les paramètres du rapport.
* Aucun trafic n’est affecté à l’expérience de contrôle.

### L’environnement correct n’est pas sélectionné dans les paramètres du rapport :

Si le contenu d’une activité a été correctement diffusé aux utilisateurs mais que son rapport ne contient aucune donnée, assurez-vous que l’environnement correct ([groupe d’hôtes](/help/main/administrating-target/hosts.md)) est sélectionné dans les paramètres du rapport.

Pour modifier l’environnement pour le rapport d’une activité :

1. Cliquez sur **[!UICONTROL Activities]**, cliquez sur l’activité souhaitée dans la liste, puis sur l’onglet **[!UICONTROL Reports]** .
1. Cliquez sur l’engrenage pour configurer les paramètres des rapports.

   ![Boîte de dialogue Paramètres A/B](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

1. Dans la liste déroulante **[!UICONTROL Environment]**, sélectionnez **[!UICONTROL Production]**.

   Les données de rapport peuvent ne pas être disponibles si vous avez sélectionné un environnement de développement.

1. Cliquez sur **[!UICONTROL Save]**.

Pour plus d’informations sur les environnements, voir [Hôtes](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

### Aucun trafic n’est affecté à l’expérience de contrôle.

Si le contenu d’une activité a été correctement diffusé aux utilisateurs mais que son rapport ne contient aucune donnée, veillez à utiliser une expérience avec le trafic comme expérience de contrôle.

1. Cliquez sur **[!UICONTROL Activities]**, cliquez sur l’activité souhaitée dans la liste, puis sur l’onglet **[!UICONTROL Reports]** .
1. Cliquez sur l’engrenage pour configurer les paramètres des rapports.

1. Dans la liste déroulante **[!UICONTROL Control]**, sélectionnez une expérience qui reçoit du trafic.

1. Cliquez sur **[!UICONTROL Save]**.

>[!NOTE]
>
>Pour plus d’informations sur la mise à jour d’une activité [!UICONTROL Automated Personalization] (AP) et la modification de l’expérience de contrôle en une expérience qui reçoit du trafic, voir [Sélection du contrôle pour votre activité Automated Personalization ou de ciblage automatique](/help/main/c-activities/t-automated-personalization/experience-as-control.md).


## Pourquoi le trafic est-il inégal entre mes expériences dans mon activité A/B ou MVT ? {#uneven}

Par exemple, j’ai défini la répartition du trafic sur 50/50 ou 25/25/25/25, mais je vois une répartition très différente entre les expériences dans les rapports. Il existe plusieurs raisons explicables pour des comptes de visiteurs inégaux dans les rapports [!DNL Target] :

* Lorsqu’une activité [!DNL Target] est lancée pour la première fois, la distribution du trafic peut être inégale en raison de l’architecture du noeud de périphérie que [!DNL Target] utilise pour optimiser la diffusion de l’expérience. La bonne pratique consiste à donner à une activité un certain temps pour collecter plus de données et la distribution se normalisera. Pour plus d’informations sur l’architecture [!DNL Adobe Target] et les noeuds Edge, voir [Fonctionnement d’Adobe Target](/help/main/c-intro/how-target-works.md).
* Si vous vous trouvez dans [!DNL Target] ou [!DNL Analytics] et que vous utilisez la mesure **[!UICONTROL Visits]**, n’oubliez pas que [!DNL Target] est un système basé sur les visiteurs et que la distribution du trafic pour un test A/B ou MVT est affectée au niveau des visiteurs. Par conséquent, si vous examinez les résultats de l’activité à l’aide de la mesure **[!UICONTROL Visits]**, la distribution du trafic peut apparaître inégale car certains visiteurs peuvent avoir plusieurs visites. Visiteurs est la mesure de normalisation standard lors de l’évaluation des performances de l’activité.
* La bonne pratique des tests A/B et MVT consiste à maintenir les divisions de trafic. La modification de la distribution du trafic entre les expériences (du 90/10 au 50/50, par exemple) au cours d’un test peut entraîner des visiteurs inégaux entre les expériences. L’expérience de trafic plus faible risque de ne jamais &quot;rattraper&quot;.
* Si vous suivez les bonnes pratiques ci-dessus et que la répartition du trafic ne se normalise pas au fil du temps, vérifiez les points suivants :

   * Utilisez-vous la dernière bibliothèque at.js ? Pour plus d’informations sur la version actuelle et les notes de mise à jour associées, voir [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.

   * S’agit-il d’un test de redirection ? Un minutage incorrect des balises se déclenchant sur la page peut entraîner des divisions de trafic inégales, en particulier lors de l’utilisation de [!DNL Analytics] comme source de données pour une activité [!DNL Target]. Pour plus d’informations sur la résolution des incohérences de la distribution du trafic sur une activité de redirection avec Analytics for Target (A4T), voir [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
