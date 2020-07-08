---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics
description: Dans l’Adobe Target, les mesures de réussite sont préconfigurées à des fins de rapports et de suivi.
title: Mesures de réussite dans l’Adobe Target
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: c7664f9674234565a3657f453541095811fa5aa6
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 83%

---


# Mesures de succès{#success-metrics}

Dans l’Adobe Target, les mesures de réussite sont préconfigurées à des fins de rapports et de suivi.

Les mesures de succès sont des paramètres utilisés pour mesurer le succès d’une activité. Les mesures de succès incluent des mesures commerciales clés qui permettent de déterminer le succès d’une expérience ou d’une offre donnée dans une activité Target. Par exemple, vous pouvez déterminer si une nouvelle offre ou l’ajout d’un article à un panier augmente les recettes par visiteur. Les mesures de succès peuvent s’avérer utiles pour identifier des problèmes liés à l’inscription, à la commande ou aux tunnels de vente, mais aussi avec l’engagement des visiteurs ou des clients.

Pour atteindre l’objectif de simplification de la création de tests de [!DNL Target Standard], l’application se charge de certaines configurations qui étaient définies manuellement dans [!DNL Target Classic]. Par exemple, les mesures de succès sont préconfigurées avec les options optimales.

By default, conversion events are set to &quot;Count once and keep the entrant in the activity&quot; in [!DNL Target Standard]. Les conversions sont comptabilisées une seule fois, aucune conversion répétée n’est comptabilisée et le visiteur voit toujours le contenu du test.

Les mesures Recettes définies sur « Incrémenter le décompte et laisser l’utilisateur dans l’activité » enregistrent les détails des commandes seulement pour la première commande effectuée par le même visiteur. Toutes les commandes ultérieures augmentent le nombre de conversions, mais n’apportent pas de recettes aux recettes par visite (RPV)/à la valeur de commande moyenne (AOV)/aux ventes et ne sont pas incluses dans le rapport Détails de la commande.

>[!NOTE]
>
>Le comportement par défaut des activités utilisant [Analytics comme source](/help/c-integrating-target-with-mac/a4t/a4t.md) de rapports (A4T) est &quot;Incrémenter le décompte et garder l’utilisateur dans l’activité&quot; avec &quot;Une fois par participant&quot;.

Les mesures de succès suivantes sont disponibles :

| Mesure de succès | Approche de mesure | Définition |
|--- |--- |--- |
| Conversion | Basée sur les conversions | Une conversion se produit lorsqu’un visiteur effectue une action que vous avez définie sur votre site (a cliqué sur un bouton, a affiché une page, a répondu à une enquête ou a effectué un achat). Une conversion peut être comptabilisée une fois par visiteur ou chaque fois qu’un visiteur effectue une conversion. |
| Recettes | Basée sur les conversions | Recettes générées par la visite. Vous pouvez effectuer un choix parmi les mesures de recettes suivantes :<ul><li>Recettes par visiteur (RPV)</li><li>Valeur de commande moyenne (AOV)</li><li>Total ventes</li></ul> |
| Pages vues | Basée sur les engagements | Chaque visite unique est comptabilisée comme une conversion |
| Temps passé sur le site | Basée sur les engagements | Durée de la visite (en secondes) entre le moment où l’visiteur voit la première demande de Cible d’affichage de l’activité et celui où la dernière page est chargée avec une demande dans la session. |
| Scores personnalisés | Basée sur les engagements | Aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the activity&#39;s first display [!DNL Target] request. |

Pour les mesures basées sur les engagements (à l’exception des mesures basées sur les conversions et basées sur les recettes), les visiteurs doivent se requalifier pour l’activité à chaque visite afin d’incrémenter le nombre de cette session. La mesure associée commence l’incrémentation après la requalification et s’arrête à la fin de la session de chaque visiteur. Une session s’arrête au bout de 30 minutes d’inactivité. Par conséquent, vous ne verrez pas les résultats immédiatement pendant le test, mais tous les résultats de cette session seront disponibles dans les minutes suivant la fin de la session.

Vous pouvez également créer des mesures de succès personnalisées.

Une fois la mesure de succès sélectionnée, sélectionnez l’action effectuée par un visiteur pour atteindre l’objectif. For example, choose a Conversion metric, set it to be counted once per visitor, then set whether success is achieved when a visitor views a certain page (or set of pages), views a specific [!DNL Target] request, or clicks a specific link.

S’il est activé, le champ Valeur estimée de la conversion (indisponible pour les mesures Note de page) fournit une valeur pour votre objectif (mais pas pour les autres mesures). Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes (Recettes par visiteur, Valeur de commande moyenne, Total ventes et Commandes), l’estimation utilise la mesure Recettes par visiteur. Les données sont de type devise. Voir [Estimation de l’effet élévateur dans les recettes](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

Les mesures de succès que vous choisissez pour votre activité sont disponibles dans les paramètres des rapports lorsque vous consultez un rapport pour l’activité.

Certaines mesures telles que Scores personnalisés et Recettes par visiteur requièrent une implémentation personnalisée qui transmet des informations comme les ID de commande et les totaux des commandes.

## Paramètres avancés {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Utilisez les paramètres avancés pour gérer la façon dont vous mesurez le succès. Les options incluent la comptabilisation de la mesure par impression ou une fois par visiteur, et le choix de garder l’utilisateur dans l’activité ou de l’en supprimer.

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option Paramètres avancés n’est pas disponible.

![Menu déroulant Paramètres avancés](/help/c-activities/r-success-metrics/assets/Menu_AdvancedSettings.png)

Vous pouvez également utiliser les paramètres avancés pour créer des mesures de succès dépendantes, en incrémentant uniquement une mesure lorsqu’un visiteur atteint d’abord une autre mesure.

![Ajouter une dépendance](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Par exemple, une conversion de test peut être valide uniquement si un visiteur clique sur l’offre ou atteint une page spécifique avant la conversion.

Les mesures de succès dépendantes sont prises en charge dans les activités de test A/B, d’Automated Personalization, de ciblage d’expérience et de test multivarié. Les activités de recommandation ne prennent pas actuellement en charge les mesures de succès dépendantes.

>[!NOTE]
>
>Les mesures de succès dépendantes ne seront pas converties dans les cas suivants :

* Si vous créez une dépendance circulaire dans laquelle mesure1 dépend de mesure2 et mesure2 dépend de mesure1, aucune mesure ne peut être convertie.
* Les activités d’Automated Personalization libèrent les utilisateurs et redémarrent l’activité une fois les mesures de conversion atteintes. Par conséquent, les mesures qui dépendent de la mesure de conversion ne pourront pas être converties.

Utilisez les paramètres avancés pour déterminer ce qu’il se produit une fois qu’un utilisateur atteint la mesure d’objectif. Le tableau suivant présente les options disponibles.

| Une fois que l’utilisateur a rencontré cette mesure d’objectif | Options |
|--- |--- |
| Incrémenter le décompte et laisser l’utilisateur dans l’activité | Indiquez comment le décompte est incrémenté :<ul><li>Une fois par participant (valeur par défaut)</li><li>À chaque impression (actualisations de page exclues)</li><li>À chaque impression</li></ul> |
| Incrémenter le décompte, libérer l’utilisateur et autoriser le retour | Sélectionnez l’expérience que le visiteur voit s’il retourne à l’activité :<ul><li>Même expérience (valeur par défaut)</li><li>Expérience aléatoire</li><li>Expérience non vue</li></ul> |
| Incrémenter le décompte, libérer l’utilisateur et bloquer le retour | Déterminez ce que l’utilisateur voit à la place du contenu de l’activité :<ul><li>Même expérience (sans suivi) (valeur par défaut)</li><li>Par défaut/autre contenu d’activité</li></ul> |

## Vidéo de formation : Mesures d’activité

Cette vidéo indique comment utiliser les mesures d’activité.

* Comprendre les mesures d’« objectif »
* Comprendre et créer des mesures de conversion, de recettes et d’engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)