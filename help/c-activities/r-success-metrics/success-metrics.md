---
description: Dans Target Standard, les mesures de succès sont préconfigurées en vue de la création de rapports et du suivi.
keywords: ciblage;succès;mesures de conversion;mesures des scores de page;mesures des vues de pages;mesures des recettes;mesures du temps passé sur le site;valeur estimée;paramètres avancés
seo-description: Dans Target Standard, les mesures de succès sont préconfigurées en vue de la création de rapports et du suivi.
seo-title: Mesures de succès
solution: Target
title: Mesures de succès
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Mesures de succès{#success-metrics}

Dans Target Standard, les mesures de succès sont préconfigurées en vue de la création de rapports et du suivi.

Les mesures de succès sont des paramètres utilisés pour mesurer le succès d’une activité. Les mesures de succès incluent des mesures commerciales clés qui permettent de déterminer le succès d’une expérience ou d’une offre donnée dans une activité Target. Par exemple, vous pouvez déterminer si une nouvelle offre ou l’ajout d’un article à un panier augmente les recettes par visiteur. Les mesures de succès peuvent s’avérer utiles pour identifier des problèmes liés à l’inscription, à la commande ou aux tunnels de vente, mais aussi avec l’engagement des visiteurs ou des clients.

Pour atteindre l’objectif de simplification de la création de tests de [!DNL Target Standard], l’application se charge de certaines configurations qui étaient définies manuellement dans [!DNL Target Classic]. Par exemple, les mesures de succès sont préconfigurées avec les options optimales.

Par défaut, les événements de conversion sont définis sur « compter une fois et laisser le participant dans l’activité » dans [!DNL Target Standard]. Les conversions sont comptabilisées une seule fois, aucune conversion répétée n’est comptabilisée et le visiteur voit toujours le contenu du test.

Les mesures Recettes définies sur « Incrémenter le décompte et laisser l’utilisateur dans l’activité » enregistrent les détails des commandes seulement pour la première commande effectuée par le même visiteur. Toutes les commandes ultérieures augmentent le nombre de conversions, mais n’apportent pas de recettes aux recettes par visite (RPV)/à la valeur de commande moyenne (AOV)/aux ventes et ne sont pas incluses dans le rapport Détails de la commande.

Les mesures de succès suivantes sont disponibles :

| Mesure de succès | Approche de mesure | Définition |
|--- |--- |--- |
| Conversion | Basée sur les conversions | Une conversion se produit lorsqu’un visiteur effectue une action que vous avez définie sur votre site (a cliqué sur un bouton, a affiché une page, a répondu à une enquête ou a effectué un achat). Une conversion peut être comptabilisée une fois par visiteur ou chaque fois qu’un visiteur effectue une conversion. |
| Recettes | Basée sur les conversions | Recettes générées par la visite. Vous pouvez effectuer un choix parmi les mesures de recettes suivantes :<ul><li>Recettes par visiteur (RPV)</li><li>Valeur de commande moyenne (AOV)</li><li>Total ventes</li></ul> |
| Pages vues | Basée sur les engagements | Chaque visite unique est comptabilisée comme une conversion |
| Temps passé sur le site | Basée sur les engagements | Durée de la visite (en secondes), entre le moment où le visiteur voit la première mbox d’affichage de l’activité et celui où la page finale de la session est chargée avec une mbox. |
| Scores personnalisés | Basée sur les engagements | Note globale calculée d’après la valeur attribuée aux pages visitées sur le site, dès l’instant où le visiteur voit la première mbox d’affichage de l’activité pour la première fois. |

Pour les mesures basées sur les engagements (à l’exception des mesures basées sur les conversions et basées sur les recettes), les visiteurs doivent se requalifier pour l’activité à chaque visite afin d’incrémenter le nombre de cette session. La mesure associée commence l’incrémentation après la requalification et s’arrête à la fin de la session de chaque visiteur. Une session s’arrête au bout de 30 minutes d’inactivité. Par conséquent, vous ne verrez pas les résultats immédiatement pendant le test, mais tous les résultats de cette session seront disponibles dans les minutes suivant la fin de la session.

Vous pouvez également créer des mesures de succès personnalisées.

Une fois la mesure de succès sélectionnée, sélectionnez l’action effectuée par un visiteur pour atteindre l’objectif. Choisissez par exemple une mesure de conversion, définissez-la pour qu’elle soit comptabilisée une fois par visiteur, puis indiquez si le succès est atteint lorsqu’un visiteur affiche une page spécifique (ou un ensemble de pages), voit une mbox en particulier ou clique sur un lien spécifique.

S’il est activé, le champ Valeur estimée de la conversion (indisponible pour les mesures Note de page) fournit une valeur pour votre objectif (mais pas pour les autres mesures). Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes (Recettes par visiteur, Valeur de commande moyenne, Total ventes et Commandes), l’estimation utilise la mesure Recettes par visiteur. Les données sont de type devise. Voir [Estimation de l’effet élévateur dans les recettes](../../administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE) pour plus d’informations.

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

>[!VIDEO](https://video.tv.adobe.com/v/17380?captions=fre_fr)