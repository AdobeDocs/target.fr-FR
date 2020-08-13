---
keywords: troubleshooting;metric discrepancies;FAQ;reports;new visitor;new visitors;returning visitor;returning visitors;return visit;new visit
description: Liste des questions fréquentes sur la création de rapports dans Adobe Target.
title: FAQ sur la création de rapports dans Adobe Target
feature: reports
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 31%

---


# FAQ sur la création de rapports{#reporting-faq}

Liste des questions fréquentes sur la création de rapports dans [!DNL Target].

## Comment les mesures Nouveaux Visiteurs et Visiteurs récurrents sont-elles comptabilisées ?

Les informations suivantes expliquent comment les nouveaux Visiteurs et les Visiteurs récurrents sont comptabilisés et fournissent des exemples de raisons pour lesquelles la somme de ces deux segments ne correspond pas toujours au nombre total de visiteurs.

### Nouveaux visiteurs

Un visiteur est inclus dans le segment Nouveaux Visiteurs si l’une des conditions suivantes est remplie :

* Il s’agit de la première visite du visiteur sur le site.
* C&#39;est le premier visiteur à visiter le site depuis l&#39;effacement des cookies.
* Il s’agit de la première visite du visiteur sur le site depuis l’expiration de la durée de vie [du profil](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) Visiteur.

### Visiteurs récurrents

Le visiteur est inclus dans le segment Visiteurs récurrents si l’utilisateur a déjà visité le site, s’il a quitté le site pendant au moins 30 minutes et est revenu sur le site avec les mêmes cookies. Tant que le visiteur revient pendant la durée de vie du profil, il est considéré comme un visiteur récurrent.

Supposons que la durée de vie de votre profil soit définie sur 14 jours (valeur par défaut). Un visiteur est inclus dans le segment Visiteurs récurrents si les conditions suivantes sont remplies :

* Un visiteur visite le site pour la première fois et est enregistré comme nouveau Visiteur.
* Le visiteur quitte le site, mais revient six jours plus tard.

La durée de vie du profil étant définie sur 14 jours, ce visiteur est inclus dans le segment Visiteurs récurrents. Notez que si le visiteur a supprimé les cookies au cours de cette période de six jours, ce visiteur sera inclus dans le segment Nouveaux Visiteurs.

### Exemples expliquant les incohérences entre les décomptes de mesures

**Exemple 1**: Si ces deux segments sont appliqués à une activité, les segments Nouveaux Visiteurs et Visiteurs récurrents ne s’ajoutent pas toujours au nombre total de visiteurs.

Prenons l’exemple suivant, en prenant en compte les conditions mentionnées ci-dessus pour les nouveaux Visiteurs et les Visiteurs récurrents :

* Un visiteur visite le site pour la première fois et est comptabilisé comme nouveau Visiteur.
* Le visiteur revient sur le site une fois que les conditions sont remplies pour les Visiteurs récurrents et est comptabilisé comme Visiteur récurrent.

Ce visiteur est comptabilisé comme un seul visiteur dans le nombre total de visiteurs de l’activité, même s’il est comptabilisé dans les segments Nouveaux Visiteurs et Visiteurs récurrents.

**Exemple 2**: Les écarts entre les décomptes des nouveaux Visiteurs et des Visiteurs récurrents dépendent également de la manière dont vous configurez les mesures [de](/help/c-activities/r-success-metrics/success-metrics.md)réussite de l’activité.

Par exemple :

Un certain nombre de nouveaux visiteurs visitent votre site et sont qualifiés pour une activité. Ces nouveaux visiteurs sont comptabilisés dans le segment Nouveaux Visiteurs. Tous ces visiteurs ont également enregistré une visite dans cette activité.

Certains visiteurs ont atteint la mesure de conversion, configurée comme &quot;Incrémenter le décompte et laisser l’utilisateur en Activité&quot;. Supposons que certains de ces utilisateurs atteignent la mesure de conversion plusieurs fois, la mesure de conversion n’augmente pas. Toutefois, dans cette configuration, certains utilisateurs peuvent atteindre la mesure de conversion, puis revenir à la page d&#39;accueil, se qualifiant de nouveau dans l’activité pour enregistrer une nouvelle visite.

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

Par exemple, j&#39;ai défini la répartition du trafic sur 50/50 ou 25/25/25/25, mais je vois une répartition très différente entre les expériences dans le rapports. Il existe un certain nombre de raisons explicables pour un décompte inégal des visiteurs au [!DNL Target] rapports :

* Lorsqu’une [!DNL Target] activité est lancée pour la première fois, la répartition du trafic peut être inégale en raison de l’architecture de noeud Edge [!DNL Target] utilisée pour optimiser la diffusion d’expérience. La meilleure pratique consiste à donner à une activité du temps pour collecter des données supplémentaires et la distribution se normalisera. Pour plus d’informations sur [!DNL Adobe Target] l’architecture et les noeuds Edge, voir [Fonctionnement](/help/c-intro/how-target-works.md)de Adobe Target.
* Si vous êtes dans [!DNL Target] ou [!DNL Analytics] et que vous utilisez la mesure **[!UICONTROL Visites]** , n’oubliez pas qu’il s’agit [!DNL Target] d’un système basé sur un visiteur et que la répartition du trafic pour un test A/B ou MVT est affectée au niveau du visiteur. Par conséquent, si vous examinez les résultats des activités à l’aide de la mesure **[!UICONTROL Visites]** , la répartition du trafic peut s’afficher inégalement car certains visiteurs peuvent avoir plusieurs visites. Le visiteur est la mesure de normalisation standard lors de l’évaluation des performances des activités.
* La meilleure pratique pour les tests A/B et MVT consiste à maintenir les divisions de trafic égales. La modification de la répartition du trafic entre les expériences (disons de 90/10 à 50/50) au cours d’un test peut générer des visiteurs inégalement d’une expérience à l’autre. L’expérience de trafic la plus faible risque de ne jamais &quot;rattraper&quot;.
* Si vous suivez les bonnes pratiques ci-dessus et que la répartition du trafic ne se normalise pas au fil du temps, vérifiez les points suivants :

   * Utilisez-vous la dernière bibliothèque at.js ? Pour plus d’informations sur la version actuelle et les notes de mise à jour associées, voir les détails [de la version](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)at.js.

   * Est-ce un test de redirection ? Le minutage incorrect des balises se déclenchant sur la page peut entraîner des divisions de trafic inégales, en particulier lors [!DNL Analytics] de l’utilisation comme source de données pour une [!DNL Target] activité. Pour plus d’informations sur la résolution des problèmes de distribution inégale du trafic lors d’une activité de redirection avec Analytics pour la Cible (A4T), consultez la FAQ [sur les offres de](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)redirection - A4T.
