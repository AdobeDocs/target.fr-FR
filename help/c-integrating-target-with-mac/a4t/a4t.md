---
keywords: a4t ; analytics ; analytics pour cible ; source du rapports analytics ; adobe analytics en tant que source de rapports pour cible ; atjs ; at.js ; adobe experience platform web sdk ; platform web sdk ; platform web sdk ; platform sdk
description: Utilisez les rapports  [!DNL Analytics] for [!DNL Target] (A4T) to create activities based on [!DNL Analytics] conversion metrics and audience segments and use [!DNL Analytics] pour examiner les résultats.
title: Qu’est-ce que  [!DNL Analytics] for [!DNL Target] (A4T) ?
feature: 'Analytics for Target (A4T) '
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 32%

---

# [!DNL Adobe Analytics] en tant que source de rapports pour  [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) est une intégration inter-solutions qui vous permet de créer des activités basées sur des mesures de  [!DNL Analytics] conversion et des segments d’audience. L’intégration A4T vous permet d’utiliser des rapports [!DNL Analytics] pour examiner vos résultats. Si vous utilisez [!DNL Analytics] comme source de rapports pour une activité, tous les rapports et segmentations pour cette activité sont basés sur la collecte de données [!DNL Analytics].

>[!NOTE]
>
>La prise en charge d’A4T dans une mise en oeuvre [!DNL Adobe Experience Platform Web SDK] décrite dans cet article devrait être disponible avec la version [!DNL Platform Web SDK] 2.5.0 (24 mai 2021).

## Aperçu {#section_92B66069210C40DBA937790E8CC596CF}

L&#39;intégration [!DNL Analytics for Target] entre [!DNL Analytics] et [!DNL Target] fournit de puissantes outils d&#39;analyse et d&#39;économie de temps pour votre programme d&#39;optimisation.

Les trois avantages Principaux de l&#39;utilisation des données [!DNL Analytics] dans [!DNL Target] sont les suivants :

* Les marketeurs peuvent appliquer dynamiquement des mesures de réussite ou des segments de rapports [!DNL Analytics] aux rapports d’activité [!DNL Target] à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source de données unique élimine la variance qui survient lorsque les données sont collectées dans deux systèmes distincts.
* Votre implémentation [!DNL Analytics] existante collecte toutes les données requises. Il n’est pas nécessaire d’implémenter des mbox sur les pages dans le seul but de collecter des données pour les rapports.

Si vous utilisez [!DNL Analytics] comme source de rapports pour une activité, tous les rapports et segmentations pour cette activité sont basés sur [!DNL Analytics].

Toutes les mesures [!DNL Analytics], y compris les mesures calculées, sont disponibles dans [!DNL Target] et le rapport [!UICONTROL Activités de Cible] dans [!DNL Analytics], à une exception près. Les mesures calculées pour [!UICONTROL Effet élévateur et degré de confiance] ne sont pas prises en charge. De même, tout segment disponible dans [!DNL Analytics] peut être appliqué aux deux solutions. Vous pouvez appliquer la mesure ou l&#39;audience au rapport dans [!DNL Target] après le démarrage de l&#39;activité, ou même après la fin de l&#39;activité.

Chaque mesure est incluse, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Gardez ce qui suit à l’esprit lorsque vous envisagez d’utiliser Analytics pour Target (A4T) :

* Pour utiliser [!DNL Analytics] comme source de rapports pour [!DNL Target], vous et votre société devez avoir accès à [!DNL Analytics] et à [!DNL Target]. [Contactez votre gestionnaire de compte](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si vous avez besoin de l’une des solutions.
* La source de création de rapports est définie pour chaque activité. [!DNL Target][!DNL Target] continue à collecter les données à utiliser dans la création de rapports et les données sont toujours disponibles si vous préférez baser une activité sur les données collectées par [!DNL Target].
* Utilisez une source de rapports ou l’autre. Vous ne pouvez pas collecter de données des deux sources pour une même activité.
* Lors de l’utilisation d’A4T, toutes les mesures de réussite disponibles pour vos activités sont des mesures [!DNL Analytics]. Cependant, votre mesure d’objectif peut être basée sur un appel de mbox si vous utilisez at.js. Par exemple, vous pouvez utiliser les fonctionnalités de suivi des clics prêtes à l’emploi de la Cible avec A4T au lieu d’avoir à implémenter [!DNL Analytics] code de suivi des clics.
* Lors de l’affichage du rapports d’une activité A4T dans l’interface utilisateur [!DNL Target], vous consultez les données [!DNL Analytics]. Par exemple, si vous utilisez la mesure [!UICONTROL Visiteur] dans [!DNL Target], vous utilisez la mesure [!DNL Analytics] [!UICONTROL Visiteur], et non la mesure [!DNL Target] [!UICONTROL Visiteurs], qui est maintenant appelée [!UICONTROL Participants]. Cette différence est particulièrement importante pour les mesures de trafic de base ([!UICONTROL Visiteurs], [!UICONTROL Visites], [!UICONTROL Vues de page]) et les mesures de conversion.
* Toutes les activités [!DNL Target] existantes continuent d’utiliser la collecte de données [!DNL Target] et ne sont pas affectées par l’activation d’A4T.
* Une seule mesure basée sur une mbox est autorisée lors de l’utilisation d’A4T.
* Un appel serveur à serveur de [!DNL Target] à [!DNL Analytics] envoie les informations d&#39;activité et d&#39;expérience à [!DNL Analytics]. Cette intégration n’entraîne pas d’appels de serveur supplémentaires pour [!DNL Target] ou [!DNL Analytics].

   Dans certains cas, les classifications de [!DNL Target] à [!DNL Analytics] échouent et les activités n&#39;affichent pas les données dans [!DNL Analytics]. Voir [Résolution des problèmes d’intégration d’Analytics et de Cible (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Vous pouvez également [contacter le service à la clientèle](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) pour obtenir de l’aide.

## Mise en oeuvre d’A4T

Pour plus d’informations sur l’implémentation d’A4T avec at.js et la [!DNL Adobe Experience Platform Web SDK], voir [Analytics pour [!DNL Target] l’implémentation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Types d’activité pris en charge {#section_F487896214BF4803AF78C552EF1669AA}

Les sections suivantes contiennent des informations sur les types d’activité pris en charge lors de l’utilisation de [!DNL Adobe Experience Platform Web SDK] ou at.js :

| Types d’activité | Compatible avec A4T ? | Remarques, le cas échéant |
|--- |--- |--- |
| [Activité A/B avec fractionnement manuel du trafic](/help/c-activities/t-test-ab/test-ab.md) | Oui |  |
| [Activité A/B avec affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Oui | Voir [Prise en charge d’A4T pour les activités d’affectation automatique et de Cible automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [Activité A/B avec ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) | Oui | Voir [Prise en charge d’A4T pour les activités d’affectation automatique et de Cible automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [Ciblage d’expérience (XT)](/help/c-activities/t-experience-target/experience-target.md) | Oui |  |
| [Test multivarié (MVT)](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | Oui | Requiert l’objectif de la mesure d’objectif mbox pour obtenir le rapport [!UICONTROL Contribution des éléments]. Le rapport [!UICONTROL Contribution des éléments] ne prend actuellement pas en charge les mesures [!DNL Analytics]. |
| [Activité d’Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) | Non |  |
| [Activité de recommandations](/help/c-recommendations/recommendations.md) | Oui |  |

Comme tous les types d’activités ne prennent pas encore en charge A4T, il est recommandé de conserver ou d’implémenter des mbox de conversion importantes, telles que la mbox `orderConfirmPage`.

## Exemples de rapports A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Pour vue des rapports A4T dans [!DNL Target], cliquez sur **[!UICONTROL Activités]**, cliquez sur l’activité de votre choix dans la liste qui utilise [!DNL Analytics] comme source de rapports, puis cliquez sur l’onglet **[!UICONTROL Rapports]**.

>[!NOTE]
>
>Vous pouvez utiliser la liste déroulante [!UICONTROL Source du Rapports] en haut de la page [!UICONTROL Activités] pour n’afficher que les activités qui utilisent A4T.

Vous pouvez permuter entre la [!UICONTROL Vue de tableau] et la [!UICONTROL Vue graphique] du rapport en cliquant sur l’icône appropriée dans l’angle supérieur droit du rapport.

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Mesure du rapport] répertoriant les mesures d’objectifs [!DNL Analytics] disponibles :

![](assets/a4t_report_graph1.png)

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Audience] répertoriant les audiences [!DNL Analytics] disponibles :

![](assets/a4t_report_graph2.png)

L’illustration suivante présente la [!UICONTROL vue Tableau] d’un rapport A4T :

![](assets/a4t_report_table.png)

Pour afficher le rapport dans [!DNL Analytics] plutôt que dans [!DNL Target], cliquez sur **[!UICONTROL Afficher dans Analytics]** en haut du rapport.

## Tutoriel Analytics et Target : bonnes pratiques relatives à l’analyse {#section_3438E6E77A464424B717A4FD333B84B2}

Ouvrez [Analytics &amp; Cible : Didacticiel sur les meilleures pratiques en matière d’Analyse ](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par [!DNL Adobe Experience League].

## Vidéos de formation :

Les vidéos suivantes contiennent plus d&#39;informations sur les concepts abordés dans cette rubrique.

### Analytics pour Adobe Target (A4T) (4:32) ![badge Aperçu](/help/assets/overview.png)

Cette vidéo explique comment utiliser [!DNL Analytics] comme source de rapports dans [!DNL Target] pour générer l&#39;analyse de votre programme d&#39;optimisation.

* Présentation d’A4T et des raisons pour lesquelles l’utiliser
* Explication du fonctionnement d’A4T
* Compréhension des conditions préalables requises pour pouvoir utiliser A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics / Intégration Adobe Target (A4T) (40:33) ![Badge du didacticiel](/help/assets/tutorial.png)

Cette vidéo est un enregistrement de « [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Comment configurer et confirmer que l’intégration fonctionne
* Fonctionnement de l’intégration
* Découvrez les rapports idéaux à utiliser dans Analytics
* Réponses aux questions courantes sur A4T

[Heures de bureau d’intégration Analytics/Cible (A4T)](https://helpx.adobe.com/fr/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [Analytics  [!DNL Target] pour la mise en oeuvre](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) : Contient des informations d’implémentation pour at.js et le SDK Web de la plate-forme.
>* [FAQ sur les offres de redirection - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
* [Qu’est-ce que le SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) Web Adobe Experience Platform ? Contient des informations d’aperçu sur le SDK Web de la plate-forme.
* [Présentation](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) de la cible : Contient des informations spécifiques à  [!DNL Target] et au  [!DNL Platform Web SDK].

