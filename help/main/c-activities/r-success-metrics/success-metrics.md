---
keywords: Ciblage;succès;mesure de conversion;mesure de score de page;mesure pages vues;mesures de chiffre d’affaires;mesure du temps passé sur le site;valeur estimée;paramètres avancés;mesures de succès;paramètres avancés;dépendance;dépendant;Incrémenter le décompte et maintenir l’utilisateur dans l’activité;Incrémenter le décompte, Libérer l’utilisateur et Autoriser la reprise;incrémenter le décompte, Libérer l’utilisateur et Interdire la reprise
description: Découvrez les mesures de succès qui vous aident à déterminer le succès d’une activité. Les mesures de succès comprennent la conversion, le chiffre d’affaires, les pages vues, la notation personnalisée et le temps passé sur le site.
title: Que Sont Les Mesures De Succès ?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: a34d40bef584bfa941731df718cb402c658f5d28
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 22%

---

# [!UICONTROL Success metrics]

Les mesures de succès dans [!DNL Adobe Target] sont des indicateurs clés qui permettent de mesurer les performances de vos activités. Ces mesures capturent des résultats commerciaux importants, tels que les conversions, le chiffre d’affaires par visiteur et l’engagement client, ce qui vous permet d’évaluer l’impact d’expériences ou d’offres spécifiques.

Vous pouvez, par exemple, déterminer si une nouvelle promotion augmente les recettes par visiteur ou entraîne l’ajout d’articles supplémentaires au panier. Les mesures de succès permettent également d’identifier les problèmes dans les flux d’utilisateurs comme les processus d’enregistrement, de passage en caisse ou d’achat, tout en fournissant des informations sur le comportement global des visiteurs.

## Aperçu

Dans [!DNL Target], les mesures de succès sont préconfigurées avec les paramètres recommandés pour garantir un reporting précis et un suivi efficace.

Par défaut, les événements de conversion utilisent le paramètre **[!UICONTROL Increment count & keep user in activity].** Ce paramètre signifie que chaque visiteur n’est comptabilisé comme une conversion qu’une seule fois. Aucune conversion répétée n’est comptabilisée. Ces visiteurs et visiteuses continuent à voir le contenu de l’activité tout au long de leur session.

Pour les mesures de recettes qui utilisent le même paramètre, seule la première commande d’un visiteur consigne les détails de la commande. Bien que les commandes suivantes augmentent le nombre de conversions, elles ne contribuent pas aux mesures basées sur le chiffre d’affaires telles que [!UICONTROL Revenue per Visitor (RPV)], [!UICONTROL Average Order Value (AOV)] ou [!DNL Total Sales]. Ces commandes supplémentaires sont également exclues du rapport [!UICONTROL Order Details].

>[!NOTE]
>
>Pour les activités utilisant [Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), la mesure d’objectif utilise toujours les paramètres « [!UICONTROL Increment Count & Keep User in Activity] » et « [!UICONTROL On Every Impression] ». Ces paramètres ne sont *pas configurables*

Les mesures de succès suivantes peuvent être configurées dans la section [!UICONTROL Reporting Settings] de la [!UICONTROL Activity Settings page], sous l’étape [!UICONTROL Goals & Settings] :

| Mesure de succès | Approche de mesure | Définition |
|--- |--- |--- |
| [!UICONTROL Conversion] | Basée sur les conversions | La conversion survient lorsqu’un visiteur effectue sur votre site une action que vous avez définie, telle que <ul><li>A affiché une page</li><li>A affiché une mbox</li><li>A cliqué sur un élément</li></ul>Une conversion peut être comptabilisée une fois par visiteur ou chaque fois qu’un visiteur effectue une conversion. |
| [!UICONTROL Revenue] | Basée sur les conversions | Recettes générées par la visite. Vous ne pouvez choisir qu’une seule mesure de chiffre d’affaires :<ul><li>A affiché une mbox</li></ul>Pour plus d’informations sur les modifications de l’interface utilisateur [!DNL Target] mise à jour en ce qui concerne les mesures de succès des recettes, voir [Modifications de l’interface utilisateur  [!DNL Target]  mises à jour](#changes) ci-dessous. |
| [!UICONTROL Engagement] | Basée sur les engagements | Engagement généré par la visite. Vous pouvez choisir parmi les mesures d’engagement suivantes :<UL><li>Pages vues : chaque visite unique est comptabilisée comme une conversion.</li><li>[!UICONTROL Custom Scoring] : score agrégé basé sur la valeur affectée aux pages visitées sur le site, à partir du moment où le visiteur voit pour la première fois la demande de [!DNL Target] d’affichage de l’activité.</li>[!DNL Time on Site] : durée de la visite (en secondes) entre le moment où le visiteur voit la première demande d’affichage de l’activité [!DNL Target] le chargement de la page finale avec une demande dans la session.</UL> |

Pour les mesures basées sur l’engagement (contrairement aux mesures basées sur la conversion et sur les recettes), les visiteurs doivent se requalifier pour l’activité à chaque visite afin d’incrémenter le nombre pour cette session. La mesure associée commence l’incrémentation après la requalification et s’arrête à la fin de la session de chaque visiteur. Une session s’arrête au bout de 30 minutes d’inactivité. Par conséquent, vous ne voyez pas les résultats immédiatement pendant le test. Cependant, tous les résultats de cette session sont disponibles quelques minutes après la fin de la session.

## Mesures de succès personnalisées

Vous pouvez également créer des mesures de succès personnalisées.

Une fois la mesure de succès sélectionnée, sélectionnez l’action effectuée par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure de [!UICONTROL Conversion], définissez-la pour qu’elle soit comptabilisée une fois par visiteur, puis définissez si le succès est atteint lorsqu’un visiteur ou une visiteuse consulte une certaine page (ou un ensemble de pages), consulte une demande de [!DNL Target] spécifique ou clique sur un lien spécifique.

Si cette option est activée, le champ [!UICONTROL Estimated Value of one conversion] (non disponible pour les mesures [!UICONTROL Page Score]) fournit une valeur pour votre objectif, mais pas pour d’autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de chiffre d’affaires ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] et [!UICONTROL Orders]), l’estimation utilise [!UICONTROL Revenue per Visitor]. Les données sont de type devise. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

Les mesures de succès que vous choisissez pour votre activité sont disponibles dans les paramètres de rapport lorsque vous affichez un rapport pour l’activité.

Certaines mesures, telles que [!UICONTROL Custom Scoring] et [!UICONTROL Revenue Per Visitor], nécessitent une implémentation personnalisée qui transmet des informations, telles que les totaux des commandes et les ID de commande.

## Paramètres avancés  {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Utilisez les paramètres avancés pour gérer la façon dont vous mesurez le succès. Les options incluent l’ajout de dépendances, le choix de conserver l’utilisateur dans l’activité ou de le supprimer, et le comptage de la mesure une fois par participant ou à chaque impression.

Pour accéder aux options de [!UICONTROL Advanced Settings], cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmallListVert.svg) ), puis sur **[!UICONTROL Advanced Settings]**.

![Menu Paramètres avancés](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

Pour plus d’informations sur les options de [!UICONTROL Advanced Settings] (« [!UICONTROL What will happen after a user encounters this goal] » et « [!UICONTROL How will the count be incremented] »), voir [Que se passe-t-il lorsqu’un utilisateur ou une utilisatrice rencontre cette mesure d’objectif &#x200B;](#what-happens) ?

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

Les mesures de succès dépendantes ne sont pas converties dans les cas suivants :

* Si vous créez une dépendance circulaire dans laquelle mesure1 dépend de mesure2 et mesure2 dépend de mesure1, aucune mesure ne peut être convertie.
* Les activités [!UICONTROL Automated Personalization] libèrent des utilisateurs et redémarrent l’activité lorsque les mesures de conversion sont atteintes, de sorte qu’aucune mesure dépendant de la mesure de conversion ne soit convertie.

### Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ? {#what-happens}

Utilisez les paramètres avancés pour déterminer ce qu’il se produit une fois qu’un utilisateur atteint la mesure d’objectif. Le tableau suivant présente les options disponibles :

| Une fois que l’utilisateur a rencontré cette mesure d’objectif | Options |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Indiquez comment le décompte est incrémenté :<ul><li>Une fois par participant (par défaut)</li><li>À chaque impression (actualisations de page exclues)</li><li>À chaque impression</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Sélectionnez l’expérience que voit le visiteur s’il entre à nouveau dans l’activité :<ul><li>Même expérience (par défaut)</li><li>Expérience aléatoire</li><li>Expérience non vue</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Déterminez ce que l’utilisateur voit à la place du contenu de l’activité :<ul><li>Même expérience, sans suivi (par défaut)</li><li>Par défaut/autre contenu d’activité</li></ul> |

>[!NOTE]
>
>Si vous configurez une mesure pour l’une des options de [!UICONTROL Increment Count] (mentionnées ci-dessus), le nombre de mesures est correctement incrémenté d’une seule fois par participant au niveau du visiteur uniquement. Le nombre de mesures est incrémenté une fois par visite pour chaque nouvelle session au niveau des visites.

### Comment le nombre est-il incrémenté :

Choisissez le comportement souhaité :

* Une fois par participant
* À chaque impression (à l’exclusion des actualisations de page)
* À chaque impression

## Problèmes connus

* Les mesures de succès avec l’option avancée « Comment sera incrémenté le décompte ? » définie sur « À chaque impression » ou « À chaque impression (actualisations de page exclues) » ne peuvent pas être utilisées en tant que mesure de succès dont dépend une autre mesure.

  Lorsqu’une mesure de succès est définie pour incrémenter à chaque impression, [!DNL Target] comptabilise à nouveau le visiteur à chaque fois qu’il visite cette mesure de succès. [!DNL Target] réinitialise ensuite la mesure de succès « appartenance » sur 0 afin qu’elle puisse être comptabilisée à nouveau à la prochaine impression. Ainsi, si une autre mesure nécessite que cette mesure ait été vue au préalable, [!DNL Target] ne reconnaît jamais que l’utilisateur a vu la première mesure.

## Mise à jour des modifications apportées à l’interface utilisateur de [!DNL Target] {#changes}

La version [[!DNL Target Standard/Premium] 25.2.1](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2), lancée le 17 février 2015, a introduit des interfaces utilisateur [!DNL Target] et [!UICONTROL Visual Experience Composer] (VEC) mises à jour. Cette section décrit les principales différences entre l’interface utilisateur héritée et mise à jour, en particulier en ce qui concerne la configuration et la gestion des mesures de succès.

### Modifications de l’interface utilisateur liées aux mesures de succès [!UICONTROL Revenue]

Dans l’interface [!DNL Target] mise à jour, la liste déroulante [!UICONTROL Default View for Reporting] a été supprimée. Ce champ était redondant, car il enregistrait auparavant la vue de création de rapports par défaut sous [!DNL Overview] > [!UICONTROL Reports] dans l’interface utilisateur héritée.

Avec l’interface utilisateur mise à jour, la mesure de création de rapports par défaut est désormais toujours définie sur [!UICONTROL Revenue per Visitor (RPV)]. Vous pouvez toujours personnaliser la vue de la section [!UICONTROL Reports] pour afficher les mesures les plus pertinentes pour votre analyse.

Cette modification n’affecte pas les mesures de diffusion. Cette modification affecte uniquement le filtre par défaut affiché dans la vue de création de rapports. Comme la RPV est la mesure la plus couramment utilisée par les clients, cette valeur par défaut a été sélectionnée pour rationaliser les workflows de création de rapports. Vous pouvez passer à d’autres mesures à tout moment dans la section [!UICONTROL Reports] .