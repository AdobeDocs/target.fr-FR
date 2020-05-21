---
keywords: analytics for target;a4t;analytics as the reporting source
description: L’utilisation d’Analytics en tant que source des rapports pour Target (A4T) vous donne accès aux rapports Analytics pour vos activités Target.
title: Rapports A4T
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 48%

---


# Rapports A4T{#a-t-reporting}

Using [!DNL Analytics] as your reporting source for [!DNL Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Aperçu {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] appelle également [!DNL Analytics] chaque fois que la conversion est effectuée. [!DNL Analytics][!DNL Analytics] ajoute la conversion en tant que nouvel événement spécifique nommé « Conversion des activités », qui est suivi avec d’autres données collectées par [!DNL Analytics].

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. Les données collectées au cours de ces premières 24 heures sont toujours exactes et sont affectées à l’expérience appropriée.

## Rapports dans Analytics {#section_F6884872DC864AE7913587FAED4CD11C}

In [!DNL Analytics], click **[!UICONTROL Target]** > **[!UICONTROL Target Activities]** in the left menu. In [!DNL Target], the activity&#39;s reports automatically show [!DNL Analytics] data, metrics, and segments. Les données s’affichent dans ces rapports environ une heure après leur collecte auprès du site. Toutes les mesures, audiences et valeurs des rapports proviennent de la suite de rapports sélectionnée lorsque vous configurez l’activité.

In [!DNL Analytics], use the [!UICONTROL Target Activities] report to view the results of your [!DNL Target] activity. Test&amp;Target (Legacy) Reports provides information about your old Test&amp;Target plug-in style page integrations and does not include [!DNL Analytics] for [!DNL Target] data. In the [!UICONTROL Activities] report, view information about your [!DNL Target] experiences. Cliquez sur **[!UICONTROL Mesures]**, puis sélectionnez le type de mesure **[!UICONTROL Target]**. Deux mesures sont disponibles pour votre rapport :

* **Entrées d’activité**[!DNL Target] : correspond au nombre de participants du rapport 
* **Conversions des activités**[!DNL Target] : correspond au nombre de conversions personnalisées du rapport 

>[!NOTE]
>
>[!DNL Target] les détails de l’effet élévateur et de la fiabilité sont également disponibles dans [!DNL Analytics]. Pour plus d’informations, voir Effet élévateur et degré de confiance [des](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html) Cibles dans le Guide *des composants d’* Analytics.

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. Contactez l’assistance à la clientèle pour résoudre ce problème.

## Rapports dans Target {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Chaque mesure est disponible, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

   Gardez à l’esprit que tout chiffre qui augmente est indiqué comme positif dans le rapport, même lorsque qu’une augmentation n’est en fait pas souhaitée. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. Il n’est pas nécessaire que vous sachiez exactement au préalable ce que vous voulez mesurer.

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Rapports dans Analysis Workspace {#reports-in-analysis-workspace}

Vous pouvez utiliser [!DNL Adobe Analysis Workspace] pour effectuer une analyse plus approfondie et visualiser les données ou découvrir les informations masquées sous la surface.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by [!DNL Adobe Experience League].

## Création de l’activité {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Au cours de la création de l’activité, vous devez indiquer un objectif pour cette dernière dans la page [!UICONTROL Paramètres]. Cet objectif devient la mesure par défaut du rapport et est systématiquement répertorié en tant que première option dans le sélecteur de mesures. Vous ne pouvez pas sélectionner de segments pour la création de rapports comme vous le feriez pour une activité classique Target. A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics].

Pour plus d’informations, voir [Réalisation de calculs hors ligne pour Analytics for Target (A4T)](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
