---
keywords: analytics for target;a4t;analytics as the reporting source
description: L’utilisation d’Analytics en tant que source des rapports pour Target (A4T) vous donne accès aux rapports Analytics pour vos activités Target.
title: Rapports A4T
feature: a4t reports
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 40%

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

## Rapports dans Analytics {#analytics}

Dans [!DNL Analytics]le cas présent, plusieurs dimensions et mesures sont disponibles une fois l’intégration A4T activée.

### Dimensions

* [!UICONTROL Analytics pour la Cible] : identifiant parent transmis par l’intégration. Le format de cette dimension est `Activity ID:Experience ID:3rd ID`. Les dimensions ci-dessous sont des classifications de cette dimension.
* [!UICONTROL Activités Target]
* [!UICONTROL Contenus Target]
* [!UICONTROL Activité] cible > [!UICONTROL Expérience]
* [!UICONTROL 3e identifiant] - peut être ignoré

### Mesures

* [!UICONTROL Impressions] d’Activité : correspond au nombre de [!UICONTROL participants] dans le [!DNL Target] rapport.
* [!UICONTROL Conversions] des Activités : correspond au nombre de conversions  personnalisées dans le [!DNL Target] rapport.

Dans [!DNL Analysis Workspace], utilisez le panneau [!UICONTROL Analytics pour la Cible] pour analyser vos [!DNL Target] activités et expériences avec effet élévateur et fiabilité. Pour plus d’informations, voir Panneau [Analytics pour la Cible (A4T) dans le Guide](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) des outils ** Analytics.

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. Contactez l’assistance à la clientèle pour résoudre ce problème.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Rapports dans Target {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Chaque mesure est disponible, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

   Gardez à l’esprit que tout chiffre qui augmente est indiqué comme positif dans le rapport, même lorsque qu’une augmentation n’est en fait pas souhaitée. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. Il n’est pas nécessaire que vous sachiez exactement au préalable ce que vous voulez mesurer.

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Création de l’activité {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Au cours de la création de l’activité, vous devez indiquer un objectif pour cette dernière dans la page [!UICONTROL Paramètres]. Cet objectif devient la mesure par défaut du rapport et est systématiquement répertorié en tant que première option dans le sélecteur de mesures. Vous ne pouvez pas sélectionner de segments pour la création de rapports comme vous le feriez pour une activité classique Target. A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics].

Pour plus d’informations, voir [Réalisation de calculs hors ligne pour Analytics for Target (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
