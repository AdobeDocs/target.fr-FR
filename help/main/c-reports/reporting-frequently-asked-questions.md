---
keywords: résolution de problèmes;incohérences entre les mesures;FAQ;rapports;nouveau visiteur;nouveaux visiteurs;visiteur récurrent;visiteurs récurrents;visite récurrente;nouvelle visite
description: Explorez une liste de questions fréquentes sur les rapports Adobe [!DNL Target] .
title: Où puis-je trouver des réponses aux questions sur le reporting  [!DNL Target]  ?
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

La première visite d’un nouveau visiteur ou d’une nouvelle visiteuse dure aussi longtemps que celui-ci ou celle-ci est actif sur le site.
Si l’utilisateur reste inactif pendant 30 minutes ou plus, la session est réinitialisée. La réinitialisation de la session signifie que ce visiteur devient un visiteur récurrent lors de la visite suivante ou qu’il redevient actif après 30 minutes d’inactivité.
Si le visiteur se déplace sur le site toutes les 29 minutes pendant une journée entière, il est comptabilisé comme un nouveau visiteur cette journée entière. La session n’a jamais été réinitialisée, car le visiteur n’a jamais dépassé le seuil de 30 minutes.

Les informations suivantes expliquent de manière plus détaillée comment les nouveaux visiteurs et les visiteurs récurrents sont comptabilisés. Des exemples sont également inclus pour expliquer pourquoi la somme de ces deux segments ne s’additionne pas toujours au nombre total de visiteurs.

### Nouveaux visiteurs

Le segment des nouveaux visiteurs comprend un visiteur si l’une des conditions suivantes est remplie :

* Il s’agit de sa première visite sur le site.
* Il s’agit de sa première visite sur le site depuis l’effacement des cookies.
* Il s’agit de sa première visite sur le site depuis l’expiration de la [durée de vie du profil du visiteur](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md).

### Visiteurs récurrents

Le segment des visiteurs récurrents comprend un visiteur si l’utilisateur a déjà consulté le site et l’a quitté depuis au moins 30 minutes avant d’y revenir avec les mêmes cookies. Tant que le visiteur revient pendant la durée de vie du profil, il est considéré comme un visiteur récurrent.

Supposons que la durée de vie de votre profil soit définie sur 14 jours (valeur par défaut). Un visiteur est inclus dans le segment Visiteurs récurrents si les conditions suivantes sont remplies :

* Un visiteur visite le site pour la première fois et est enregistré en tant que Nouveau visiteur.
* Le visiteur quitte le site, mais y revient six jours plus tard.

Comme la durée de vie du profil est définie sur 14 jours, ce visiteur est inclus dans le segment Visiteurs récurrents. Si le visiteur a supprimé des cookies au cours de cette période de six jours, il est inclus dans le segment Nouveaux visiteurs .

### Exemples expliquant les écarts entre les nombres de mesures

**Exemple 1** : si ces deux segments sont appliqués à une activité, le segment Nouveaux visiteurs et le segment Visiteurs récurrents ne s’additionnent pas toujours au nombre total de visiteurs.

Prenons l’exemple suivant, en tenant compte des conditions mentionnées ci-dessus pour les nouveaux visiteurs et les visiteurs récurrents :

* Un visiteur visite le site pour la première fois et est comptabilisé comme un nouveau visiteur.
* Le visiteur revient sur le site une fois que les conditions sont remplies pour les visiteurs récurrents et est comptabilisé comme un visiteur récurrent.

Ce visiteur est comptabilisé comme un seul visiteur dans le nombre total de visiteurs de l’activité, même s’il est comptabilisé dans les segments Nouveaux visiteurs et Visiteurs récurrents .

**Exemple 2** : les écarts entre le nombre de nouveaux visiteurs et de visiteurs récurrents dépendent également de la manière dont vous configurez les [mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md) de l’activité.

Par exemple :

Plusieurs nouveaux visiteurs visitent votre site et sont qualifiés pour une activité. Ces nouveaux visiteurs sont comptabilisés dans le segment Nouveaux visiteurs . Tous ces visiteurs ont également enregistré une visite à cette activité.

Certains visiteurs accèdent à la mesure de conversion, qui a été configurée comme « Incrémenter le décompte et maintenir l’utilisateur dans l’activité ». Supposons que certains de ces utilisateurs accèdent à la mesure de conversion plusieurs fois, la mesure de conversion n’augmente pas. Cependant, compte tenu de cette configuration, certains utilisateurs peuvent accéder à la mesure de conversion, puis revenir à la page d’accueil, se qualifiant à nouveau pour l’activité afin d’enregistrer une nouvelle visite.

## Pourquoi mes rapports [!UICONTROL Experience Targeting] (XT) contiennent-ils des mesures pour les expériences de contrôle ?

Les activités de ciblage d’expérience doivent toujours comporter une expérience de contrôle. Si vous utilisez une activité XT de la même manière qu’une activité [!UICONTROL A/B Test], ce qui correspond à un scénario assez courant, les données d’expérience de contrôle sont utiles. Vous pouvez ignorer les données de contrôle d’expérience si elles ne sont pas utiles dans vos rapports.

## Pourquoi le nombre de visites est-il plus faible dans [!DNL Target] que dans d’autres solutions [!DNL Adobe Experience Cloud] ? {#section_7E626FDB417E41B8B58BBF30FB207409}

Les nombres de mesures, par exemple les visites, signalés par [!DNL Target] sont toujours inférieurs aux nombres signalés dans d’autres solutions [!DNL Experience Cloud], et ce pour plusieurs raisons :

* [!DNL Target] comptabilise uniquement les visites des visiteurs qui remplissent les critères de l’activité. Les autres solutions comptabilisent les visites des visiteurs qui affichent la page, indépendamment de l’activité qui les a amenés à la page.
* Il peut y avoir des cas où plusieurs activités (mutuellement exclusives) sont en concurrence pour le même emplacement. Les visiteurs voient donc des contenus différents sur une même page web, ce qui affecte les chiffres de mesure signalés par [!DNL Target].

## Pourquoi n’existe-t-il pas de données disponibles pour le rapport de mon activité ? {#section_E4722F6445884130951DF79981C8289B}

Si le contenu d’une activité a été correctement diffusé aux visiteurs mais que son rapport ne contient aucune donnée, le message d’erreur suivant peut s’afficher : « Aucune donnée n’est disponible pour les paramètres de rapport sélectionnés ».

Il existe plusieurs raisons possibles à l’absence de données dans les rapports d’activité :

* L’environnement sélectionné dans les paramètres du rapport n’est pas correct
* Aucun trafic n’est affecté à l’expérience de contrôle

### L’environnement sélectionné dans les paramètres du rapport n’est pas correct :

Si le contenu d’une activité a été correctement diffusé aux utilisateurs mais que son rapport ne contient aucune donnée, assurez-vous que l’environnement correct ([groupe d’hôtes](/help/main/administrating-target/hosts.md)) est sélectionné dans les paramètres du rapport.

Pour modifier l’environnement pour le rapport d’une activité :

1. Cliquez sur **[!UICONTROL Activities]**, sur l’activité souhaitée dans la liste, puis sur l’onglet **[!UICONTROL Reports]** .
1. Cliquez sur l’engrenage pour configurer les paramètres des rapports.

   ![Boîte de dialogue Paramètres A/B](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

1. Dans la liste déroulante **[!UICONTROL Environment]** , sélectionnez **[!UICONTROL Production]**.

   Les données de rapport peuvent ne pas être disponibles si vous avez sélectionné un environnement de développement.

1. Cliquez sur **[!UICONTROL Save]**.

Pour plus d’informations sur les environnements, voir [Hôtes](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

### Aucun trafic n’est affecté à l’expérience de contrôle

Si le contenu d’une activité a été correctement diffusé aux utilisateurs mais que son rapport ne contient aucune donnée, assurez-vous d’utiliser une expérience avec le trafic comme expérience de contrôle.

1. Cliquez sur **[!UICONTROL Activities]**, sur l’activité souhaitée dans la liste, puis sur l’onglet **[!UICONTROL Reports]** .
1. Cliquez sur l’engrenage pour configurer les paramètres des rapports.

1. Dans la liste déroulante **[!UICONTROL Control]** , sélectionnez une expérience qui reçoit le trafic.

1. Cliquez sur **[!UICONTROL Save]**.

>[!NOTE]
>
>Pour plus d’informations sur la mise à jour d’une activité de [!UICONTROL Automated Personalization] (AP) et le remplacement de l’expérience de contrôle par une expérience qui reçoit du trafic, voir [Sélection du contrôle de votre activité d’Automated Personalization ou de ciblage automatique](/help/main/c-activities/t-automated-personalization/experience-as-control.md).


## Pourquoi la répartition du trafic entre mes expériences est-elle inégale dans mon activité A/B ou MVT ? {#uneven}

Par exemple, j’ai défini la répartition du trafic sur 50/50 ou 25/25/25/25, mais je constate une distribution très différente entre les expériences dans les rapports. Il existe plusieurs raisons expliquant l’inégalité du nombre de visiteurs dans les rapports [!DNL Target] :

* Lorsqu’une activité de [!DNL Target] est lancée pour la première fois, la distribution du trafic peut être inégale en raison de l’architecture de nœud de périphérie que [!DNL Target] utilise pour optimiser la diffusion de l’expérience. Il est recommandé de laisser un certain temps à une activité pour collecter davantage de données, ce qui normalisera la distribution. Pour plus d’informations sur [!DNL Adobe Target]’architecture et les nœuds Edge, voir [Fonctionnement d’Adobe Target](/help/main/c-intro/how-target-works.md).
* Si vous vous trouvez dans [!DNL Target] ou [!DNL Analytics] et que vous utilisez la mesure **[!UICONTROL Visits]**, n’oubliez pas que [!DNL Target] est un système basé sur les visiteurs et que la distribution du trafic pour un test A/B ou MVT est attribuée au niveau des visiteurs. Ainsi, si vous examinez les résultats de l’activité à l’aide de la mesure **[!UICONTROL Visits]**, la répartition du trafic peut sembler inégale, car certains visiteurs peuvent avoir plusieurs visites. Visiteurs est la mesure de normalisation standard lors de l’évaluation des performances des activités.
* La bonne pratique pour les tests A/B et MVT consiste à uniformiser les divisions de trafic. La modification de la répartition du trafic entre les expériences (de 90/10 à 50/50, par exemple) au cours d’un test peut entraîner des disparités entre les visiteurs et visiteuses d’expériences. L’expérience de trafic faible risque de ne jamais « rattraper » le retard.
* Si vous suivez les bonnes pratiques ci-dessus et que la répartition du trafic ne se normalise pas au fil du temps, vous devez vérifier les points suivants :

   * Utilisez-vous la dernière bibliothèque at.js ? Pour plus d’informations sur la version actuelle et les notes de mise à jour associées, voir [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.

   * S’agit-il d’un test de redirection ? Une synchronisation incorrecte du déclenchement des balises sur la page peut entraîner des divisions de trafic inégales, en particulier lors de l’utilisation de [!DNL Analytics] comme source de données pour une activité [!DNL Target]. Pour plus d’informations afin de corriger la répartition inégale du trafic sur une activité de redirection avec Analytics for Target (A4T), consultez la section [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
