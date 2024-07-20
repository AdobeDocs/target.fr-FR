---
keywords: Ciblage;succès;mesure de conversion;mesure du score de page;mesure des pages vues;mesures des recettes;mesure du temps passé sur le site;valeur estimée;paramètres avancés;mesures de succès;paramètres avancés;dépendance;dépendante;incrémenter le décompte et laisser l’utilisateur dans l’activité;incrémenter le décompte, libérer l’utilisateur et autoriser le retour;incrémenter le décompte, libérer l’utilisateur et bloquer le retour
description: Découvrez les mesures de succès dans Adobe [!DNL Target] qui vous aident à déterminer le succès d’une activité. Les mesures de succès comprennent la conversion, les recettes, les pages vues, la notation personnalisée et le temps passé sur le site.
title: Que sont les mesures de succès ?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: b0bf54d47ac44afc3597f308ea38fd479c54026d
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 42%

---

# Mesures de succès

Dans [!DNL Adobe Target], les mesures de succès sont des paramètres utilisés pour mesurer le succès d’une activité. Les mesures de succès incluent des mesures commerciales clés qui vous permettent de déterminer le succès d’une expérience ou d’une offre donnée dans une activité [!DNL Target].

Par exemple, vous pouvez déterminer si une nouvelle offre ou l’ajout d’un article à un panier augmente les recettes par visiteur. Les mesures de succès peuvent s’avérer utiles pour identifier des problèmes liés à l’inscription, à la commande ou aux tunnels de vente, mais aussi avec l’engagement des visiteurs ou des clients.

## Aperçu

Dans [!DNL Target], les mesures de succès sont préconfigurées avec les options optimales à des fins de création de rapports et de suivi.

Par défaut, les événements de conversion sont définis sur &quot;[!UICONTROL Increment count & keep user in activity]&quot;. Les conversions ne sont comptabilisées qu’une seule fois, aucune conversion répétée n’est comptabilisée et le visiteur voit toujours le contenu de l’activité.

Les mesures de recettes définies sur &quot;[!UICONTROL Increment count & keep user in activity]&quot; consignent les détails de la commande uniquement pour la première commande effectuée par le même visiteur. Toutes les commandes suivantes augmentent le nombre de conversions, mais n’ajoutent pas de recettes aux recettes par visiteur/valeur de commande moyenne/ventes et ne sont pas incluses dans le rapport [!UICONTROL Order Details].

>[!NOTE]
>
>Pour les activités utilisant [Analytics comme source des rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), la mesure d’objectif utilisera toujours les paramètres &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; et &quot;[!UICONTROL On Every Impression]&quot;. Il est *non* configurable.

Les mesures de succès suivantes sont disponibles :

| Mesure de succès | Approche de mesure | Définition |
|--- |--- |--- |
| Conversion | Basée sur les conversions | La conversion se produit lorsqu’un visiteur effectue sur votre site une action que vous avez définie, telle que <ul><li>Clic sur un bouton</li><li>A affiché une page</li><li>Réalisation d’une enquête</li><li>Effectué un achat</li></ul>Une conversion peut être comptabilisée une fois par visiteur ou chaque fois qu’un visiteur effectue une conversion. |
| Recettes | Basée sur les conversions | Recettes générées par la visite. Vous pouvez effectuer un choix parmi les mesures de recettes suivantes :<ul><li>Recettes par visiteur (RPV)</li><li>Valeur de commande moyenne (AOV)</li><li>Total ventes</li><li>Commandes</li></ul> |
| Pages vues | Basée sur les engagements | Chaque visite unique est comptabilisée comme une conversion |
| Scores personnalisés | Basée sur les engagements | Score agrégé basé sur la valeur attribuée aux pages visitées sur le site, dès l’instant où le visiteur voit la première requête [!DNL Target] d’affichage de l’activité pour la première fois. |
| Temps passé sur le site | Basée sur les engagements | Durée de la visite (en secondes), entre le moment où le visiteur voit la première requête [!DNL Target] d’affichage de l’activité et celui où la page finale est chargée avec une requête dans la session. |

Pour les mesures basées sur les engagements (à l’exception des mesures basées sur les conversions et basées sur les recettes), les visiteurs doivent se requalifier pour l’activité à chaque visite afin d’incrémenter le nombre de cette session. La mesure associée commence l’incrémentation après la requalification et s’arrête à la fin de la session de chaque visiteur. Une session s’arrête au bout de 30 minutes d’inactivité. Par conséquent, vous ne verrez pas les résultats immédiatement pendant le test. Cependant, tous les résultats de cette session sont disponibles dans les minutes qui suivent la fin de la session.

## Mesures de succès personnalisées

Vous pouvez également créer des mesures de succès personnalisées.

Une fois la mesure de succès sélectionnée, sélectionnez l’action effectuée par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure [!UICONTROL Conversion], définissez-la pour qu’elle soit comptabilisée une fois par visiteur, puis définissez si le succès est obtenu lorsqu’un visiteur affiche une certaine page (ou un ensemble de pages), affiche une requête [!DNL Target] spécifique ou clique sur un lien spécifique.

S’il est activé, le champ [!UICONTROL Estimated Value of one conversion] (indisponible pour les mesures [!UICONTROL Page Score]) fournit une valeur pour votre objectif, mais pas pour les autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] et [!UICONTROL Orders]), l’estimation utilise [!UICONTROL Revenue per Visitor]. Les données sont de type devise. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

Les mesures de succès que vous choisissez pour votre activité sont disponibles dans les paramètres des rapports lorsque vous consultez un rapport pour l’activité.

Certaines mesures, telles que [!UICONTROL Custom Scoring] et [!UICONTROL Revenue Per Visitor], nécessitent une mise en oeuvre personnalisée qui transmet des informations telles que les totaux des commandes et les identifiants de commande.

## Paramètres avancés  {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Utilisez les paramètres avancés pour gérer la façon dont vous mesurez le succès. Les options incluent l’ajout de dépendances, le choix de garder l’utilisateur dans l’activité ou de le supprimer, ainsi que la comptabilisation de la mesure une fois par participant ou à chaque impression.

Pour accéder aux options [!UICONTROL Advanced Settings], cliquez sur **[!UICONTROL vertical ellipses]** > **[!UICONTROL Advanced Settings]**.

![Menu Paramètres avancés](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option [!UICONTROL Advanced Settings] ne sera pas disponible. Pour plus d’informations, voir [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Ajouter une dépendance

Vous pouvez utiliser les paramètres avancés pour créer des mesures de succès dépendantes, en incrémentant une mesure uniquement si un visiteur atteint d’abord une autre mesure.

![Ajouter une dépendance](/help/main/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Par exemple, une conversion de test peut être valide uniquement si un visiteur clique sur l’offre ou atteint une page spécifique avant la conversion.

La fonctionnalité de dépendance n’est *pas* prise en charge pour les éléments suivants :

* [!UICONTROL Recommendations] activités. Cette fonctionnalité est prise en charge pour tous les autres types d’activité.
* Si vous utilisez [Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Type de mesure &quot;A affiché une page&quot;.
* Type de mesure &quot;A cliqué sur un élément&quot; pour les activités du compositeur d’expérience visuelle (VEC).

Les mesures de succès dépendantes ne seront pas converties dans les cas suivants :

* Si vous créez une dépendance circulaire dans laquelle mesure1 dépend de mesure2 et mesure2 dépend de mesure1, aucune mesure ne peut être convertie.
* Les activités d’Automated Personalization libèrent les utilisateurs et redémarrent l’activité une fois les mesures de conversion atteintes. Par conséquent, les mesures qui dépendent de la mesure de conversion ne pourront pas être converties.

### Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ?

Utilisez les paramètres avancés pour déterminer ce qu’il se produit une fois qu’un utilisateur atteint la mesure d’objectif. Le tableau suivant répertorie les options disponibles :

| Une fois que l’utilisateur a rencontré cette mesure d’objectif | Options |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Indiquez comment le décompte est incrémenté :<ul><li>Une fois par participant (par défaut)</li><li>À chaque impression (actualisations de page exclues)</li><li>À chaque impression</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Sélectionnez l’expérience que le visiteur voit s’il retourne à l’activité :<ul><li>Même expérience (par défaut)</li><li>Expérience aléatoire</li><li>Expérience non vue</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Déterminez ce que l’utilisateur voit à la place du contenu de l’activité :<ul><li>Même expérience, sans suivi (par défaut)</li><li>Par défaut/autre contenu d’activité</li></ul> |

>[!NOTE]
>
>Si vous configurez une mesure sur l’une des options [!UICONTROL Increment Count] (mentionnée ci-dessus), le nombre de mesures est incrémenté correctement une fois par participant au niveau du visiteur uniquement. Le nombre de mesures est incrémenté une fois par visite pour chaque nouvelle session au niveau de la visite.

### Comment le décompte sera-t-il incrémenté ?

Choisissez le comportement souhaité :

* Une fois par participant
* À chaque impression (actualisations de page exclues)
* À chaque impression

## Problèmes connus

* Les mesures de succès avec l’option avancée « Comment sera incrémenté le décompte ? » définie sur « À chaque impression » ou « À chaque impression (actualisations de page exclues) » ne peuvent pas être utilisées en tant que mesure de succès dont dépend une autre mesure.

Lorsqu’une mesure de succès est définie pour être incrémentée à chaque impression, [!DNL Target] comptabilise à nouveau le visiteur chaque fois qu’il visite cette mesure de succès. [!DNL Target] réinitialise ensuite la mesure de succès &quot;appartenance&quot; à 0 afin qu’elle puisse à nouveau compter sur l’impression suivante. Par conséquent, si une autre mesure nécessite que cette mesure ait été vue en premier, [!DNL Target] ne reconnaît jamais que l’utilisateur a vu la première mesure.

## Vidéo de formation : Mesures d’activité

Cette vidéo indique comment utiliser les mesures d’activité.

* Comprendre les mesures d’« objectif »
* Comprendre et créer des mesures de conversion, de recettes et d’engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
