---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: Adobe « Analytics for Target » (A4T) est une intégration intersolutions permettant de créer des activités basées sur les mesures de conversion d’Analytics ainsi que sur les segments d’audience. Cette intégration permet d’utiliser les rapports Analytics pour étudier vos résultats. Si vous utilisez Analytics comme source de création de rapports pour une activité, toutes les créations de rapports et segmentations pour cette activité sont basées sur la collecte de données Analytics.
title: Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)
feature: a4t general
subtopic: Integrating
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: b69a34023466fa2e348ed77ee41bc1cfdeb4e6ab
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 49%

---


# Adobe Analytics comme source de création de rapports pour Adobe Target (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

[!DNL Adobe Analytics for Target] (A4T) est une intégration inter-solutions qui vous permet de créer des activités basées sur des mesures de [!DNL Analytics] conversion et des segments d’audience. The A4T integration lets you use [!DNL Analytics] reports to examine your results. If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics] data collection.

## Vue d’ensemble d’A4T {#section_92B66069210C40DBA937790E8CC596CF}

The [!DNL Analytics for Target] integration between [!DNL Analytics] and [!DNL Target] provides powerful analysis and timesaving tools for your optimization program.

The three primary benefits of using [!DNL Analytics] data in [!DNL Target] are:

* Marketers can dynamically apply [!DNL Analytics] success metrics or reporting segments to [!DNL Target] activity reports at any time. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source de données unique élimine la variance qui survient lorsque les données sont collectées dans deux systèmes distincts.
* Your existing [!DNL Analytics] implementation collects all required data. Il n’est pas nécessaire d’implémenter des mbox sur les pages dans le seul but de collecter des données pour les rapports. Although, it is still recommended that you implement an order confirmation mbox for [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) activities.

>[!IMPORTANT]
>
>Avant de commencer à utiliser A4T, vous devez demander que votre compte soit configuré pour l’intégration. Pour ce faire, utilisez [ce formulaire](https://www.adobe.com/go/audiences).
>
>The integration that enables [!DNL Analytics] as the data source for [!DNL Target] (A4T) represents the next generation of the Test&amp;Target to SiteCatalyst plug-in. Ce module externe est devenu obsolète mais est toujours pris en charge pour les clients qui l’utilisent déjà.

If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics].

All [!DNL Analytics] metrics, including calculated metrics, are available in [!DNL Target] and the [!UICONTROL Target Activities] report in [!DNL Analytics]. Likewise, any segment available in [!DNL Analytics] can be applied to both solutions. You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the activity has completed.

Chaque mesure est incluse, y compris toute mesure du client ou calculée intégrée à [!DNL Analytics].

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Gardez ce qui suit à l’esprit lorsque vous envisagez d’utiliser Analytics pour Target (A4T) :

* To use [!DNL Analytics] as the reporting source for [!DNL Target], both you and your company must have access to [!DNL Analytics] and to [!DNL Target]. [Contactez votre gestionnaire de compte](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si vous avez besoin de l’une des solutions.
* La source de création de rapports est définie pour chaque activité. [!DNL Target][!DNL Target] continue à collecter les données à utiliser dans la création de rapports et les données sont toujours disponibles si vous préférez baser une activité sur les données collectées par [!DNL Target].
* Vous devez utiliser une source de création de rapports ou l’autre. Vous ne pouvez pas collecter de données des deux sources pour une même activité.
* When using A4T, all success metrics available to your activities are [!DNL Analytics] metrics. Cependant, votre mesure d’objectif peut être basée sur un appel de mbox. For example, you can use Target&#39;s out-of-the-box click-tracking capabilities with A4T instead of having to implement [!DNL Analytics] click-tracking code.
* When viewing reporting of an A4T activity in the [!DNL Target] UI, you are viewing [!DNL Analytics] data. For example, if you use the [!UICONTROL Visitor] metric in [!DNL Target], you are using the [!DNL Analytics] [!UICONTROL Visitor] metric, not the [!DNL Target] [!UICONTROL Visitors] metric, which is now called [!UICONTROL Entrants]. This difference is especially important for basic traffic metrics ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) and conversion metrics.
* Any existing [!DNL Target] activities continue to use [!DNL Target] data collection and are not affected by enabling A4T.
* Only one mbox-based metric is allowed when using [!DNL Analytics] as the reporting source.
* A server-to-server call from [!DNL Target] to [!DNL Analytics] sends activity and experience information to [!DNL Analytics]. This integration does not result in additional server calls for either [!DNL Target] or [!DNL Analytics].

   Dans certains cas, l’appel de classification de [!DNL Target] à [!DNL Analytics] peut échouer et les activités n’affichent pas les données dans [!DNL Analytics]. Si tel est le cas, voir [Résolution des problèmes liés à l’intégration d’Analytics et de Cible (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Vous pouvez également [contacter le service à la clientèle](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) pour obtenir de l’aide.

## Supported activity types {#section_F487896214BF4803AF78C552EF1669AA}

The following table shows you which activity types support [!DNL Analytics] as the reporting source in [!DNL Target] (A4T):

| Types d’activité | Compatible avec A4T ? | Remarques, le cas échéant |
|--- |--- |--- |
| Activité A/B avec fractionnement manuel du trafic | Oui |  |
| Activité A/B avec affectation automatique | Oui | Voir Prise en charge des activités [d’affectation automatique et d’Cible automatique dans](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)Analytics pour la Cible (A4T). |
| Activité A/B avec ciblage automatique | Oui | Voir Prise en charge des activités [d’affectation automatique et d’Cible automatique dans](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)Analytics pour la Cible (A4T). |
| Ciblage d’expérience (XT) | Oui |  |
| Test multivarié (MVT) | Oui | Requires mbox-based goal metric goal to get the [!UICONTROL Element Contribution] report.  The [!UICONTROL Element Contribution] report does not currently support [!DNL Analytics] metrics. |
| Activité d’Automated Personalization | Non |  |
| Activité de recommandations | Oui |  |
| Applications mobiles | Oui | Prise en charge avec le SDK Mobile Services, version 4.13.1 ou ultérieure. Pour plus d’informations, consultez la [documentation sur Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html). |
| Courrier électronique | Non |  |
| API de diffusion côté serveur | Oui | Pour plus d’informations, voir [Côté serveur : mise en œuvre de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK NodeJS | Oui | Pour plus d’informations, voir [Côté serveur : mise en œuvre de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Intégration du service cloud AEM 6.1 (ou version antérieure) | Non |  |
| Intégration du service cloud AEM 6.2 (ou version ultérieure) | Oui | For more information, see [Integrating with Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) in the [!DNL Adobe Experience Manager] 6.2 documentation. |
| Toute activité utilisant une offre de redirection | Oui | Les exigences minimales requises sont plus strictes pour l’utilisation des offres de redirection avec A4T. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Oui |  |

Because all activity types do not yet support A4T, it is recommended that you keep or implement important conversion mboxes, such as the `orderConfirmPage` mbox.

## Examples of A4T reports {#section_F0A43A1CB2F04E8282B909E4D7034361}

To view A4T reports in [!DNL Target], click **[!UICONTROL Activities]**, click the desired activity from the list that uses [!DNL Analytics] as its reporting source, then click the **[!UICONTROL Reports]** tab.

>[!NOTE]
>
>Vous pouvez utiliser la liste déroulante [!UICONTROL Source de reporting] en haut de la page [!UICONTROL Activités] pour afficher seulement les activités qui utilisent [!DNL Analytics] comme source de reporting.

You can toggle between the [!UICONTROL Table View] and [!UICONTROL Graph View] of the report by clicking the appropriate icon at the top right side of the report.

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Mesure du rapport] répertoriant les mesures d’objectifs [!DNL Analytics] disponibles :

![](assets/a4t_report_graph1.png)

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Audience] répertoriant les audiences [!DNL Analytics] disponibles :

![](assets/a4t_report_graph2.png)

L’illustration suivante présente la [!UICONTROL vue Tableau] d’un rapport A4T :

![](assets/a4t_report_table.png)

Pour afficher le rapport dans [!DNL Analytics] plutôt que dans [!DNL Target], cliquez sur **[!UICONTROL Afficher dans Analytics]** en haut du rapport.

## Tutoriel Analytics et Target : bonnes pratiques relatives à l’analyse {#section_3438E6E77A464424B717A4FD333B84B2}

Open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by [!DNL Adobe Experience League].

## Vidéos de formation :

Les vidéos suivantes contiennent plus d&#39;informations sur les concepts abordés dans cette rubrique.

### Badge de ![présentation d’Analytics for Cible (A4T) (4:32)](/help/assets/overview.png)

This video explains how to use [!DNL Analytics] as a reporting source in [!DNL Target] to drive the analysis of your optimization program.

* Présentation d’A4T et des raisons pour lesquelles l’utiliser
* Explication du fonctionnement d’A4T
* Compréhension des conditions préalables requises pour pouvoir utiliser A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Balise de ![didacticiel Analytics / Cible Integration (A4T) (40:33)](/help/assets/tutorial.png)

Cette vidéo est un enregistrement de « [Office Hours](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Comment configurer et confirmer que l’intégration fonctionne
* Fonctionnement de l’intégration
* Découvrez les rapports idéaux à utiliser dans Analytics
* Réponses aux questions courantes sur A4T

[Heures de bureau d’intégration Analytics/Cible (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)