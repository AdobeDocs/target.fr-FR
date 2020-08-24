---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics;advanced settings
description: En Adobe Target, les mesures de réussite sont des paramètres utilisés pour mesurer la réussite d’une activité. Les mesures de succès incluent des mesures commerciales clés qui permettent de déterminer le succès d’une expérience ou d’une offre donnée dans une activité Target.
title: Mesures de réussite en Adobe Target
feature: success metrics
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: 61273ea3174f5b380a2d8d6b664584f4e3d7f6ff
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 47%

---


# Mesures de succès{#success-metrics}

In [!DNL Adobe Target] success metrics are parameters used to measure the success of an activity. Success metrics include key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity.

Par exemple, vous pouvez déterminer si une nouvelle offre ou l’ajout d’un article à un panier augmente les recettes par visiteur. Les mesures de succès peuvent s’avérer utiles pour identifier des problèmes liés à l’inscription, à la commande ou aux tunnels de vente, mais aussi avec l’engagement des visiteurs ou des clients.

## Aperçu

En [!DNL Target]effet, les mesures de réussite sont préconfigurées avec les options optimales à des fins de rapports et de suivi.

Par défaut, les événements de conversion sont définis sur &quot;[!UICONTROL Incrémenter le nombre et garder l’utilisateur en activité]&quot;. Les conversions ne sont comptabilisées qu’une seule fois, aucune conversion répétée n’est comptabilisée et le visiteur voit toujours le contenu de l’activité.

Revenue metrics that are set to &quot;[!UICONTROL Increment count &amp; keep user in activity]&quot; log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the [!UICONTROL Order Details] report.

>[!NOTE]
>
>Le comportement par défaut des activités utilisant [Analytics comme source](/help/c-integrating-target-with-mac/a4t/a4t.md) de rapports (A4T) est &quot;[!UICONTROL Incrémenter le décompte et garder l’utilisateur en activité]&quot; avec &quot;[!UICONTROL Une fois par participant]&quot;.

Les mesures de succès suivantes sont disponibles :

| Mesure de succès | Approche de mesure | Définition |
|--- |--- |--- |
| Conversion | Basée sur les conversions | La conversion se produit lorsqu’un visiteur effectue une action que vous avez définie sur votre site, telle que <ul><li>Cliquez sur un bouton.</li><li>A affiché une page</li><li>Questionnaire terminé</li><li>Effectué un achat</li></ul>Une conversion peut être comptabilisée une fois par visiteur ou chaque fois qu’un visiteur effectue une conversion. |
| Recettes | Basée sur les conversions | Recettes générées par la visite. Vous pouvez effectuer un choix parmi les mesures de recettes suivantes :<ul><li>Recettes par visiteur (RPV)</li><li>Valeur de commande moyenne (AOV)</li><li>Total ventes</li><li>Commandes</li></ul> |
| Pages vues | Basée sur les engagements | Chaque visite unique est comptabilisée comme une conversion |
| Scores personnalisés | Basée sur les engagements | Aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the activity&#39;s first display [!DNL Target] request. |
| Temps passé sur le site | Basée sur les engagements | Time spent in the visit (in seconds) from the point the visitor sees the activity&#39;s first display [!DNL Target] request to the load of the final page with a request in the session. |

Pour les mesures basées sur les engagements (à l’exception des mesures basées sur les conversions et basées sur les recettes), les visiteurs doivent se requalifier pour l’activité à chaque visite afin d’incrémenter le nombre de cette session. La mesure associée commence l’incrémentation après la requalification et s’arrête à la fin de la session de chaque visiteur. Une session s’arrête au bout de 30 minutes d’inactivité. Par conséquent, vous ne verrez pas les résultats immédiatement pendant le test ; toutefois, tous les résultats de cette session sont disponibles dans les quelques minutes qui suivent la fin de la session.

## Mesures de succès personnalisées

Vous pouvez également créer des mesures de succès personnalisées.

Une fois la mesure de succès sélectionnée, sélectionnez l’action effectuée par un visiteur pour atteindre l’objectif. For example, choose a [!UICONTROL Conversion] metric, set it to be counted once per visitor, then set whether success is achieved when a visitor views a certain page (or set of pages), views a specific [!DNL Target] request, or clicks a specific link.

If enabled, the [!UICONTROL Estimated Value of one conversion] field (not available for the [!UICONTROL Page Score] metrics) provides a value for your goal, but not for other metrics. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. For all revenue metrics ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], and [!UICONTROL Orders]), the estimate uses [!UICONTROL Revenue per Visitor]. Les données sont de type devise. Voir [Estimation de l’effet élévateur dans les recettes](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

Les mesures de succès que vous choisissez pour votre activité sont disponibles dans les paramètres des rapports lorsque vous consultez un rapport pour l’activité.

Some metrics, such as [!UICONTROL Custom Scoring] and [!UICONTROL Revenue Per Visitor], require a customized implementation that passes in information such as order totals and order IDs.

## Paramètres avancés {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Utilisez les paramètres avancés pour gérer la façon dont vous mesurez le succès. Les options incluent l’ajout de dépendances, la sélection de l’option permettant de conserver ou de supprimer l’utilisateur dans l’activité et la comptabilisation de la mesure une fois par participant ou sur chaque impression.

Pour accéder aux options Paramètres  avancés, cliquez sur les ellipses **** verticales > Paramètres **** avancés.

![Menu Paramètres avancés](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. The [!UICONTROL Advanced Settings] option will not be available. For more information, see [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

### Dépendance d&#39;Ajoute

Vous pouvez utiliser les paramètres avancés pour créer des mesures de réussite dépendantes, en incrémentant une mesure uniquement si un visiteur atteint d’abord une autre mesure.

![Ajouter une dépendance](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Par exemple, une conversion de test peut être valide uniquement si un visiteur clique sur l’offre ou atteint une page spécifique avant la conversion.

Dependency functionality is *not* supported for the following:

* [!UICONTROL Les activités de recommandations. ] Cette fonctionnalité est prise en charge pour tous les autres types d’activité.
* If you use [Analytics as your reporting source](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Le type de mesure « A affiché une page ».
* Le type de mesure « A cliqué sur un élément » pour les activités du compositeur d’expérience visuelle.

Les mesures de succès dépendantes ne seront pas converties dans les cas suivants :

* Si vous créez une dépendance circulaire dans laquelle mesure1 dépend de mesure2 et mesure2 dépend de mesure1, aucune mesure ne peut être convertie.
* Les activités d’Automated Personalization libèrent les utilisateurs et redémarrent l’activité une fois les mesures de conversion atteintes. Par conséquent, les mesures qui dépendent de la mesure de conversion ne pourront pas être converties.

### Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ?

Utilisez les paramètres avancés pour déterminer ce qu’il se produit une fois qu’un utilisateur atteint la mesure d’objectif. Le tableau suivant présente les options disponibles:

| Une fois que l’utilisateur a rencontré cette mesure d’objectif | Options |
|--- |--- |
| [!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité] | Indiquez comment le décompte est incrémenté :<ul><li>Une fois par participant (valeur par défaut)</li><li>À chaque impression (actualisations de page exclues)</li><li>À chaque impression</li></ul> |
| [!UICONTROL Incrémenter le décompte, libérer l’utilisateur et autoriser le retour] | Sélectionnez l’expérience que le visiteur voit s’il retourne à l’activité :<ul><li>Même expérience (valeur par défaut)</li><li>Expérience aléatoire</li><li>Expérience non vue</li></ul> |
| [!UICONTROL Incrémenter le décompte, libérer l’utilisateur et bloquer le retour] | Déterminez ce que l’utilisateur voit à la place du contenu de l’activité :<ul><li>Même expérience (sans suivi) (valeur par défaut)</li><li>Par défaut/autre contenu d’activité</li></ul> |

>[!NOTE]
>
>Si vous configurez une mesure sur l’une des options [!UICONTROL Incrémenter le décompte] (mentionnées ci-dessus), le décompte des mesures est incrémenté correctement une fois par participant au niveau du visiteur uniquement. Le nombre de mesures est incrémenté une fois par visite pour chaque nouvelle session au niveau de la visite.

### Comment le décompte sera-t-il incrémenté ?

Choisissez le comportement de votre choix :

* Une fois par participant
* Sur chaque impression (à l’exclusion des actualisations de page)
* À chaque impression

## Vidéo de formation : Mesures d’activité

Cette vidéo indique comment utiliser les mesures d’activité.

* Comprendre les mesures d’« objectif »
* Comprendre et créer des mesures de conversion, de recettes et d’engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)