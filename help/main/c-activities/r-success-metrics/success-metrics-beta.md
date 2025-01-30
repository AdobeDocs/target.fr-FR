---
keywords: Ciblage;succès;mesure de conversion;mesure de score de page;mesure pages vues;mesures de chiffre d’affaires;mesure du temps passé sur le site;valeur estimée;paramètres avancés;mesures de succès;paramètres avancés;dépendance;dépendant;Incrémenter le décompte et maintenir l’utilisateur dans l’activité;Incrémenter le décompte, Libérer l’utilisateur et Autoriser la reprise;incrémenter le décompte, Libérer l’utilisateur et Interdire la reprise
description: Découvrez les mesures de succès d’Adobe [!DNL Target]  qui vous aident à déterminer le succès d’une activité. Les mesures de succès comprennent la conversion, le chiffre d’affaires, les pages vues, la notation personnalisée et le temps passé sur le site.
title: Que Sont Les Mesures De Succès ?
feature: Success Metrics
hide: true
hidefromtoc: true
source-git-commit: 99ea312405e397e97e64e32d2685e8a6966d8928
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 40%

---

# Mesures de succès

Dans [!DNL Adobe Target], les mesures de succès sont des paramètres utilisés pour mesurer le succès d’une activité. Les mesures de succès incluent des mesures commerciales clés qui vous permettent de déterminer le succès d’une expérience ou d’une offre donnée dans une activité [!DNL Target].

Par exemple, vous pouvez déterminer si une nouvelle offre ou l’ajout d’un article à un panier augmente les recettes par visiteur. Les mesures de succès peuvent s’avérer utiles pour identifier des problèmes liés à l’inscription, à la commande ou aux tunnels de vente, mais aussi avec l’engagement des visiteurs ou des clients.

## Aperçu

Dans [!DNL Target], les mesures de succès sont préconfigurées avec les options optimales à des fins de création de rapports et de suivi.

Par défaut, les événements de conversion sont définis sur [!UICONTROL Increment count & keep user in activity]. Les conversions ne sont comptabilisées qu’une seule fois, aucune conversion répétée n’est comptabilisée et le visiteur voit toujours le contenu de l’activité.

Mesures de revenus définies sur « [!UICONTROL Increment count & keep user in activity] » détails de commande de journal uniquement pour la première commande effectuée par le même visiteur. Toutes les commandes suivantes augmentent le nombre de conversions, mais n&#39;ajouteront pas de revenus à RPV/AOV/Sales, et ne seront pas incluses dans l&#39;état [!UICONTROL Order Details].

>[!NOTE]
>
>Pour les activités utilisant [Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), la mesure d’objectif utilisera toujours les paramètres « [!UICONTROL Increment Count & Keep User in Activity] » et « [!UICONTROL On Every Impression] ». Ceci n’est *pas configurable*.

Les mesures de succès suivantes sont disponibles :

| Mesure de succès | Approche de mesure | Définition |
|--- |--- |--- |
| Conversion | Basée sur les conversions | La conversion survient lorsqu’un visiteur effectue sur votre site une action que vous avez définie, telle que <ul><li>A cliqué sur un bouton</li><li>A affiché une page</li><li>A répondu à un questionnaire</li><li>A effectué un achat</li></ul>Une conversion peut être comptabilisée une fois par visiteur ou chaque fois qu’un visiteur effectue une conversion. |
| Recettes | Basée sur les conversions | Recettes générées par la visite. Vous pouvez effectuer un choix parmi les mesures de recettes suivantes :<ul><li>Recettes par visiteur (RPV)</li><li>Valeur de commande moyenne (AOV)</li><li>Total ventes</li><li>Commandes</li></ul> |
| Pages vues | Basée sur les engagements | Chaque visite unique est comptabilisée comme une conversion |
| Scores personnalisés | Basée sur les engagements | Score agrégé basé sur la valeur affectée aux pages visitées sur le site, à partir du moment où le visiteur voit pour la première fois la demande de [!DNL Target] d’affichage de l’activité. |
| Temps passé sur le site | Basée sur les engagements | Durée de la visite (en secondes) entre le moment où le visiteur voit la première demande de [!DNL Target] d’affichage de l’activité et le chargement de la page finale avec une demande dans la session. |

Pour les mesures basées sur les engagements (à l’exception des mesures basées sur les conversions et basées sur les recettes), les visiteurs doivent se requalifier pour l’activité à chaque visite afin d’incrémenter le nombre de cette session. La mesure associée commence l’incrémentation après la requalification et s’arrête à la fin de la session de chaque visiteur. Une session s’arrête au bout de 30 minutes d’inactivité. Par conséquent, vous ne verrez pas les résultats immédiatement pendant le test. Cependant, tous les résultats de cette session sont disponibles quelques minutes après la fin de la session.

## Mesures de succès personnalisées

Vous pouvez également créer des mesures de succès personnalisées.

Une fois la mesure de succès sélectionnée, sélectionnez l’action effectuée par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure de [!UICONTROL Conversion], définissez-la pour qu’elle soit comptabilisée une fois par visiteur, puis définissez si le succès est atteint lorsqu’un visiteur ou une visiteuse consulte une certaine page (ou un ensemble de pages), consulte une demande de [!DNL Target] spécifique ou clique sur un lien spécifique.

Si cette option est activée, le champ [!UICONTROL Estimated Value of one conversion] (non disponible pour les mesures [!UICONTROL Page Score]) fournit une valeur pour votre objectif, mais pas pour d’autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de chiffre d’affaires ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] et [!UICONTROL Orders]), l’estimation utilise [!UICONTROL Revenue per Visitor]. Les données sont de type devise. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

Les mesures de succès que vous choisissez pour votre activité sont disponibles dans les paramètres des rapports lorsque vous consultez un rapport pour l’activité.

Certaines mesures, telles que [!UICONTROL Custom Scoring] et [!UICONTROL Revenue Per Visitor], nécessitent une implémentation personnalisée qui transmet des informations telles que les totaux des commandes et les ID de commande.

## Paramètres avancés  {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Utilisez les paramètres avancés pour gérer la façon dont vous mesurez le succès. Les options incluent l’ajout de dépendances, le choix de conserver l’utilisateur dans l’activité ou de le supprimer, et le comptage de la mesure une fois par participant ou à chaque impression.

Pour accéder aux options de [!UICONTROL Advanced Settings], cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmallListVert.svg) ), puis sur **[!UICONTROL Advanced Settings]**.

![Menu Paramètres avancés](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option [!UICONTROL Advanced Settings] n’est pas disponible. Pour plus d’informations, consultez [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Ajouter une dépendance

Vous pouvez utiliser les paramètres avancés pour créer des mesures de succès dépendantes, en incrémentant une mesure uniquement si un visiteur atteint une autre mesure en premier.

Par exemple, une conversion de test peut être valide uniquement si un visiteur clique sur l’offre ou atteint une page spécifique avant la conversion.

La fonctionnalité de dépendance n’est *pas* prise en charge pour les éléments suivants :

* activités [!UICONTROL Recommendations]. Cette fonctionnalité est prise en charge pour tous les autres types d’activité.
* Si vous utilisez [Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Le type de mesure « A affiché une page ».
* Le type de mesure « Clic sur un élément » pour les activités du Compositeur d’expérience visuelle (VEC).

Les mesures de succès dépendantes ne seront pas converties dans les cas suivants :

* Si vous créez une dépendance circulaire dans laquelle mesure1 dépend de mesure2 et mesure2 dépend de mesure1, aucune mesure ne peut être convertie.
* Les activités [!UICONTROL Automated Personalization] libèrent des utilisateurs et redémarrent l’activité lorsque les mesures de conversion sont atteintes, de sorte qu’aucune mesure dépendant de la mesure de conversion ne sera convertie.

### Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ?

Utilisez les paramètres avancés pour déterminer ce qu’il se produit une fois qu’un utilisateur atteint la mesure d’objectif. Le tableau suivant présente les options disponibles :

| Une fois que l’utilisateur a rencontré cette mesure d’objectif | Options |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Indiquez comment le décompte est incrémenté :<ul><li>Une fois par participant (par défaut)</li><li>À chaque impression (actualisations de page exclues)</li><li>À chaque impression</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Sélectionnez l’expérience que le visiteur voit s’il retourne à l’activité :<ul><li>Même expérience (par défaut)</li><li>Expérience aléatoire</li><li>Expérience non vue</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Déterminez ce que l’utilisateur voit à la place du contenu de l’activité :<ul><li>Même expérience, sans suivi (par défaut)</li><li>Par défaut/autre contenu d’activité</li></ul> |

>[!NOTE]
>
>Si vous configurez une mesure pour l’une des options de [!UICONTROL Increment Count] (mentionnées ci-dessus), le nombre de mesures est correctement incrémenté d’une seule fois par participant au niveau du visiteur uniquement. Le nombre de mesures est incrémenté une fois par visite pour chaque nouvelle session au niveau des visites.

### Comment le décompte sera-t-il incrémenté :

Choisissez le comportement souhaité :

* Une fois par participant
* À chaque impression (à l’exclusion des actualisations de page)
* À chaque impression

## Problèmes connus

* Les mesures de succès avec l’option avancée « Comment sera incrémenté le décompte ? » définie sur « À chaque impression » ou « À chaque impression (actualisations de page exclues) » ne peuvent pas être utilisées en tant que mesure de succès dont dépend une autre mesure.

Lorsqu’une mesure de succès est définie pour incrémenter à chaque impression, [!DNL Target] comptabilise à nouveau le visiteur à chaque fois qu’il visite cette mesure de succès. [!DNL Target] réinitialise ensuite la mesure de succès « appartenance » sur 0 afin qu’elle puisse être comptabilisée à nouveau à la prochaine impression. Ainsi, si une autre mesure nécessite que cette mesure ait été vue au préalable, [!DNL Target] ne reconnaît jamais que l’utilisateur a vu la première mesure.

## Vidéo de formation : Mesures d’activité

Cette vidéo indique comment utiliser les mesures d’activité.

* Comprendre les mesures d’« objectif »
* Comprendre et créer des mesures de conversion, de recettes et d’engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
