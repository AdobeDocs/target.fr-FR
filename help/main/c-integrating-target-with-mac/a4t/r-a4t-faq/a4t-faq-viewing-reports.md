---
keywords: faq;questions fréquentes;analytics pour target;a4T;rapport;rapports;afficher des rapports;création de rapports;méthodologie de calcul;impressions;visiteurs;visites;mesure par défaut;conversions des activités;non spécifié
description: Trouvez des réponses aux questions fréquentes sur l’affichage des rapports lors de l’utilisation d’Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser la création de rapports Analytics pour les activités  [!DNL Target] .
title: Trouvez des réponses aux questions sur l’affichage de rapports avec A4T ?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: c747a8a0ed480130f254818e21b98addca16ca41
workflow-type: tm+mt
source-wordcount: '2539'
ht-degree: 26%

---

# FAQ sur l’affichage des rapports - A4T

Cette rubrique contient les réponses aux questions fréquentes sur l’affichage des rapports lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Puis-je afficher mes données d’activité [!DNL Target] dans [!DNL Analysis Workspace] ? {#workspace}

+++Réponse
Vous pouvez utiliser [!DNL Analysis Workspace] pour analyser vos activités et expériences [!DNL Target]. Le [panneau Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=fr) vous permet d’afficher l’effet élévateur et le degré de confiance pour trois mesures de succès au maximum. Vous pouvez également approfondir vos connaissances à l’aide de tableaux et de visualisations.

Pour obtenir des informations détaillées et des exemples, ouvrez le tutoriel [Analytics et Target : bonnes pratiques relatives à l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) fourni par [!UICONTROL Adobe Experience League].

+++

## Où les segments peuvent-ils être appliqués dans [!DNL Analysis Workspace] ? {#segmentation}

+++Réponse
Les segments sont le plus souvent utilisés en haut d’un panneau dans la zone de dépôt de segments. Le segment est appliqué à tous les tableaux et visualisations du panneau. Cette technique est particulièrement utile pour déterminer l’impact du test sur un sous-ensemble de personnes (par exemple, comment ce test a-t-il été réalisé pour les personnes au Royaume-Uni) ?

Un segment peut également être superposé directement dans le tableau à structure libre. Notez toutefois que vous devez le superposer sur l’ensemble du tableau pour conserver les calculs d’effet élévateur et de confiance dans le panneau A4T. Les segments au niveau des colonnes ne sont actuellement pas pris en charge dans le panneau.

+++

## Quel modèle Attribution IQ est utilisé dans [!DNL Analysis Workspace] ?

+++Réponse
Lors de l’utilisation d’impressions et de conversions d’activité [!DNL Target] dans [!DNL Analysis Workspace], le modèle Attribution IQ « Touche identique » est le modèle par défaut appliqué aux mesures afin d’assurer un comptage précis. Ce modèle fonctionne bien dans 99 % des cas. Cependant, vous pouvez remplacer cette attribution standard dans Attribution IQ.

+++

## Lorsque j’applique un segment d’accès à une activité de [!DNL Target] spécifique, pourquoi des expériences non liées sont-elles renvoyées ? {#activity-segmentation}

+++Réponse
La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. (Remarque : cette période d’expiration peut être ajustée par l’assistance clientèle si nécessaire). Lorsque les visiteurs et visiteuses parcourent le site tout au long de cette fenêtre d’expiration, ils ou elles font partie de nombreuses activités [!DNL Target], qui se rassemblent toutes dans la dimension .

Lorsque vous segmentez pour qu’une activité soit présente dans un accès, vous obtenez toutes les expériences qui font partie de cette activité *plus* toutes les autres expériences qui persistent sur cet accès.

+++

## Lors de la configuration de mon [!UICONTROL Goal Metrics], pourquoi ne puis-je pas accéder à [!UICONTROL Advanced Settings] ?

+++Réponse
Pour les activités utilisant [!DNL Analytics] comme source de création de rapports (A4T), la mesure d’objectif utilise les paramètres « [!UICONTROL Increment Count & Keep User in Activity] » et « [!UICONTROL On Every Impression] ». Ces paramètres ne sont *pas configurables*

Pour plus d’informations, reportez-vous à la rubrique « Lorsque je configure mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ? » dans la [FAQ sur les définitions de mesures - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Dois-je utiliser les visiteurs, les visites ou les impressions d’activité comme mesure de normalisation (c’est-à-dire la méthodologie de comptage) ? {#metrics}

+++Réponse
Il existe plusieurs options pour normaliser les mesures dans les rapports A4T. Cette mesure, également appelée méthode de comptage, devient le dénominateur du calcul de l’effet élévateur. Elle affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance.

* ***Visiteurs uniques*** incrémentez une fois lorsqu’un utilisateur se qualifie pour la première fois pour une activité.
* ***Visites*** incrémentez pour chaque session une fois qu’un utilisateur (visiteur unique) entre dans une activité, même si l’activité n’est pas consultée lors des visites ultérieures.
* ***Impressions d’activité*** incrémentez chaque fois que le contenu de l’activité est diffusé. (Mesuré par [!DNL Target]).

Lorsqu’un visiteur visualise une page contenant une activité, une variable contenant le nom de cette activité est définie pour ce visiteur. Consultez les scénarios détaillés ci-après pour une comparaison entre les différentes méthodologies de calcul.

Tenez compte des points suivants :

* Les mesures ci-dessus se déclenchent lorsqu’un utilisateur est qualifié pour une activité et que le contenu est renvoyé par [!DNL Target]. Cela ne signifie pas pour autant que l’utilisateur a forcément vu l’offre. Si l’activité de l’expérience se trouve en bas de page et que l’utilisateur ne fait pas entièrement défiler celle-ci, l’offre est bien diffusée par [!DNL Target], mais l’utilisateur ne la voit pas.
* [!UICONTROL Activity Impressions] (mesurée par [!DNL Target]) et [!UICONTROL Instances] (mesurée par [!DNL Analytics]) sont égales, sauf s’il existe plusieurs appels de mbox sur la même page dans la même activité. Cela entraîne le comptage de plusieurs [!UICONTROL Activity Impressions], mais d’une seule [!UICONTROL Instance].

Pour plus d’informations, consultez [Comment configurer des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr) dans *Tutoriels Adobe Target*.

+++

## Pourquoi les « impressions d’activité » et les « conversions d’activité » sont-elles plus élevées en [!DNL Analysis Workspace] qu’en [!UICONTROL Reports & Analytics] ? {#sametouch}

+++Réponse
[!DNL Reports & Analytics] applique un modèle d’attribution de même touche aux « impressions d’activité » et aux « conversions d’activité », tandis qu’[!DNL Analysis Workspace] affiche les mesures brutes, qui peuvent sembler exagérées en raison de la persistance de la dimension [!DNL Target].

Pour évaluer des mesures d’[!UICONTROL Activity Impressions] et de [!UICONTROL Activity Conversions] précises dans [!DNL Analysis Workspace], assurez-vous que les deux mesures sont dotées de modèles d’attribution [!UICONTROL Same Touch] appliqués. Les modèles peuvent être appliqués en cliquant sur l’engrenage des paramètres de colonne, en activant [!UICONTROL Non-default attribution models], puis en sélectionnant [!UICONTROL Same Touch]. Pour en savoir plus sur l’attribution, consultez [Présentation d’Attributes IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html?lang=fr) dans le *Guide des outils Analytics*.

+++

## Que signifie le terme « conversions d’activité » si le spécialiste marketing sélectionne une mesure [!DNL Analytics] lors de la configuration de l’activité ? {#section_F3EBACF85AF846E9B366A549AAB64356}

+++Réponse
Les « conversions d’activité » sont vides si une mesure de [!DNL Analytics] a été sélectionnée en tant que mesure de conversion de l’activité.

+++

## Pourquoi est-ce que je vois « non spécifié » dans les rapports [!DNL Analytics] ? Qu’est-ce que cela signifie ? {#unspecified}

+++Réponse
Dans d’autres rapports, la mention « non spécifié » indique que les données ne respectent pas une règle de classification, mais cela ne devrait jamais se produire dans A4T. Si la mention « non spécifié » s’affiche, cela signifie que le service de classification ne s’est pas encore exécuté. Les données des activités prennent généralement de 24 à 72 heures pour apparaître dans les rapports. Bien que les activités n’apparaissent pas dans ce rapport avant ce moment, toutes les données du visiteur liées à ces activités sont capturées et apparaissent lorsque la classification est terminée.

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Si une classification a été effectuée pour cette activité et que vous voyez toujours une ligne « Non spécifié » dans le rapport, assurez-vous que le rapport n’utilise pas une mesure non [!DNL Target] pour afficher les données. Sauf si le rapport utilise une mesure spécifique à [!DNL Target], cette ligne « Non spécifié » contient des événements pour les appels qui ne sont pas associés à [!DNL Target]. Cette ligne ne contient aucune information relative au [!DNL Target] (par exemple, visiteurs/visites/impressions).

+++

## Pourquoi des mesures [!DNL Target] sont-elles envoyées à [!DNL Analytics] même après la désactivation de l’activité ? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++Réponse
La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. Cette période d’expiration peut être ajustée par l’assistance clientèle si nécessaire. Ce paramètre est global pour toutes les activités. Cependant, il ne doit pas être ajusté dans un cas.

Il se peut que [!DNL Target] variables soient envoyées à [!DNL Analytics] après la période d’expiration, car celle-ci est de 90 jours, mais uniquement si cet utilisateur ne voit jamais une autre activité [!DNL Target] compatible avec A4T. Si un utilisateur revient sur le site au 45 e jour et voit une autre activité, le compteur de la valeur entière de l’eVar A4T est réinitialisé à 90 jours. En d’autres termes, la première campagne à partir du jour 1 pourrait persister pendant 45 + 90 = 135 jours au maximum. Si l’utilisateur ou l’utilisatrice ne cesse de revenir, vous pourriez en arriver au point où vous voyez les mesures envoyées à [!DNL Analytics] dans vos rapports à partir d’activités beaucoup plus anciennes. Lorsque les utilisateurs suppriment des cookies et ne reviennent pas sur le site, les nombres dans cette activité chutent, mais vous pouvez toujours les voir.

Cela signifie que les activités continuent d’obtenir des pages vues, des visites, etc., jusqu’à 90 jours après la fin de l’activité pour les visiteurs qui ont intégré l’activité pendant qu’elle était active. Cependant, si vous examinez la mesure [!UICONTROL Activity Impressions] , vous ne devriez pas voir d’impressions après la fin de l’activité.

Il s’agit d’un comportement normal et attendu. La variable A4T fonctionne comme n’importe quelle autre eVar - la valeur est associée à l’utilisateur jusqu’à ce qu’elle expire (90 jours). Par conséquent, si une activité n’est active que pendant deux semaines, la valeur reste associée à l’utilisateur pendant au moins les 90 jours suivants.

Il est recommandé d’afficher les rapports pour cette activité seulement pendant la période pendant laquelle l’activité était active. Les dates doivent être correctement définies par défaut lorsque vous affichez l’activité dans [!DNL Analytics]. Par conséquent, à moins que vous n’ayez étendu manuellement la date, cela ne devrait pas poser de problème du point de vue du compte rendu des performances.

Par exemple, supposons que la variable A4T expire après 90 jours et que le test soit actif du 1er au 15 janvier.

Le 1er janvier, l’utilisateur consulte le site et voit l’activité XYZ une fois, puis cinq pages ensuite. Au cours des deux semaines suivantes, l’utilisateur ne revient pas sur le site. Pour cet utilisateur, les données ressembleraient à ceci :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

L’utilisateur ou l’utilisatrice revient le 1er février, consulte cinq pages supplémentaires, ne rencontre plus d’activités Target et l’activité d’origine n’est plus active. Même si l’activité n’est plus active, l’utilisateur continue à être suivi par le biais de la persistance des eVars. Les données ressemblent maintenant à ce qui suit :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

L’utilisateur revient sur le site le 1er mars et voit une nouvelle activité, l’activité ABC. Il voit également cinq pages. Comme l’activité XYZ suit toujours l’utilisateur par le biais de la persistance, et que l’activité ABC est ensuite définie pour cet utilisateur, deux éléments de ligne s’affichent dans les rapports :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

L’utilisateur revient alors le 1er avril, consulte cinq autres pages et effectue un achat. L’expiration de 90 jours de cette première valeur eVar est réinitialisée le 1er avril. Vous pouvez donc le constater dans les rapports. La conversion est répercutée à toutes les activités Target que l’utilisateur voit, mais le nombre total de conversions est dédupliqué :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques | Commandes |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Comme les deux expériences ont été vues avant la conversion, elles sont toutes deux « créditées » pour la commande. Toutefois, une seule commande a eu lieu dans le système, ce qui se reflète dans le total. Pour les rapports [!DNL Target], comme vous ne placez pas une activité [!DNL Target] par rapport à une autre activité pour déterminer laquelle est la plus réussie, le fait que toutes les activités vues par l’utilisateur aient obtenu du crédit n’a pas d’importance. Vous comparez les résultats de deux éléments au sein d’une seule activité. Il n’est pas possible pour un utilisateur de voir différentes expériences dans la même activité, vous n’avez donc pas à vous soucier de la contamination croisée du crédit de commande.

Pour plus d’informations, voir [Variables de conversion (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html?lang=fr)) dans le *Guide d’administration d’Analytics*.

+++

## Pourquoi est-ce que je continue à voir des impressions après la désactivation de mon activité ? {#deactivated}

+++Réponse
Une source d’impressions dans un rapport d’activité A4T après la désactivation peut être le trafic en mode QA. Normalement, Target ne consigne pas les événements pour une activité désactivée, mais Analytics ne peut pas savoir que les impressions proviennent du mode assurance qualité. Lorsque le rapport d’activité de Target est récupéré à partir d’Analytics, il affiche ces impressions. Cela fonctionne comme prévu, car les clients et clientes ont besoin d’un moyen de vérifier les rapports A4T, même si l’activité n’est pas active à l’aide du mode QA.

+++

## Pourquoi [!DNL Analytics] et [!UICONTROL Analytics for Adobe Target] (A4T) calculent-ils les nombres de la mesure [!UICONTROL Unique Visitors] différemment ? {#section_0C3B648AB54041F9A2AA839D51791883}

+++Réponse
Lorsque vous exécutez un test A/B, qui utilise le test en t de [Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (la mesure de confiance) pour choisir le vainqueur d’un test, l’une des hypothèses est qu’il existe un horizon temporel fixe. Le test n&#39;est pas statistiquement valide à moins que vous ne regardiez cette taille d&#39;échantillon fixe.

La mesure [!UICONTROL Unique Visitors] est différente dans [!DNL Analytics] et [!DNL Target] uniquement lorsque vous étudiez une période plus courte que le test réel. Si vous n’avez pas atteint la taille de votre échantillon, le test n’est pas aussi fiable. Pour en savoir plus, voir la rubrique [Comment ne pas exécuter un test A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) (en anglais) sur le [site web d’Evan Miller](https://www.evanmiller.org/index.html).

La mesure [!UICONTROL Unique Visitors] affiche le nombre de personnes qui ont été exposées au test et qui ont visité le site au cours de la période spécifiée. Ces personnes font partie du test et devraient être comptées. Pour afficher uniquement le nombre de personnes qui ont été exposées au cours d’une seule semaine, vous pouvez créer un segment de visiteurs qui ont exécuté une impression de l’activité et l’ont appliquée au rapport.

Vous pouvez réduire la durée pendant laquelle la variable [!DNL Target] persiste jusqu’à une session. Toutefois, cela pose problème pour les tests où l’événement de conversion est moins susceptible de se produire au cours de la même session.

+++

## Pourquoi un même visiteur est-il parfois comptabilisé dans plusieurs expériences dans [!DNL Analytics] ? {#section_1397E972D31C4207A142E4D2D6D794A2}

+++Réponse
La liste suivante explique pourquoi le même visiteur peut être comptabilisé dans plusieurs expériences dans [!DNL Analytics] :

* Le profil [!DNL Target] a expiré, mais le cookie [!DNL Analytics] est toujours présent. Dans ce cas, [!DNL Target] réévalue l’utilisateur, mais [!DNL Analytics] considère que le visiteur est la même personne.
* Si le visiteur utilise le `mbox3rdPartyId`, lorsque le visiteur anonyme est fusionné avec le profil d’ID tiers, [!DNL Target] pouvez placer le visiteur dans une expérience différente pour qu’elle corresponde à l’ID tiers. Pour plus d’informations, voir [Synchronisation de profil en temps réel pour mbox3 à identifiant tiers](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] peut effectuer le suivi de différents appareils avec le même visiteur d’une manière différente que [!DNL Target] ne suit ces appareils : la configuration de l’identifiant tiers dans [!DNL Target] est différente de celle dans Analytics.

+++

## A4T prend-il en charge les suites de rapports virtuelles ? {#virtual}

+++Réponse
Bien que les suites de rapports virtuelles ne soient pas incluses dans la liste [!UICONTROL Report Suite], toutes les données A4T partagées avec une suite de rapports liée à une suite de rapports virtuelle dans [!DNL Analytics] ont accès à ces données. Notez que toute audience créée à partir d’une suite de rapports virtuelle ne peut pas être repartagée sur [!DNL Target].

+++

## Puis-je modifier le pourcentage de l’affectation du trafic dans une activité qui utilise A4T après l’activation de l’activité ?

+++Réponse
La modification du pourcentage d’affectation du trafic dans une activité après l’activation peut entraîner des rapports incohérents dans [!DNL Analytics], car la modification n’affecte que les nouveaux visiteurs. Les visiteurs récurrents ne sont pas affectés.

En règle générale, il est conseillé d’arrêter l’activité existante, puis de créer une nouvelle activité plutôt que de modifier le pourcentage après son activation. Les rapports relatifs à la nouvelle activité commencent par les nouveaux visiteurs. Les données des visiteurs récurrents n’entraînent pas de création de rapports incohérents.

+++

## Comment les visites sont-elles comptabilisées dans les [!DNL Analytics] et comment le crédit de conversion est-il alloué dans une activité [!UICONTROL Auto-Target] qui utilise A4T ?

+++Réponse
Lorsqu’un visiteur remplit les conditions pour participer à une activité A4T, affiche du contenu ou effectue une conversion, [!DNL Target] envoie des données d’événement à [!DNL Analytics]. Ces données d’événement [!DNL Analytics] permettent d’attribuer les événements de conversion et d’autres événements de parcours de navigation se produisant sur la page aux activités et expériences [!DNL Target] pertinentes.

Voici quelques points à garder à l’esprit lors de l’affichage de rapports [!DNL Analytics] :

* En règle générale, il est recommandé que votre créneau de rapport commence à la date de début de l’activité.
* Si une conversion se produit en dehors de la fenêtre du rapport, elle n’est pas visible dans [!DNL Analytics].
* Dans la partie « ciblée » du trafic pour les activités [!UICONTROL Auto-Target], les visiteurs peuvent voir différentes expériences d’une session à l’autre. Par exemple, si leur profil ou contexte a changé et que les algorithmes de machine learning de [!DNL Target] décident qu’ils sont plus susceptibles de convertir une nouvelle expérience. À mesure que les visiteurs passent d’une expérience à l’autre, le nombre de visites augmente pour chaque expérience vue. Cela diffère des activités de test A/B normales où les expériences sont visibles pour un visiteur à travers les visites.
* Si un visiteur voit plusieurs expériences au cours des visites, toute conversion est toujours attribuée à la dernière expérience qu’il a vue. Comme mentionné, le nombre de visites incrémente pour chaque expérience que le visiteur a vue. Cela peut réduire artificiellement les taux de conversion par expérience lors de l’affichage d’expériences sous la dimension « [!UICONTROL Targeted] » dans les rapports [!DNL Adobe Analytics].

+++

## Comment effectuer le suivi des impressions d’activité dans [!DNL Analysis Workspace] lors de l’utilisation de [!UICONTROL Analytics for Target] (A4T) ? {#activity-impressions}

+++Réponse

Pour afficher les impressions d’activité dans [!DNL Analysis Workspace] :

1. Dans l’interface utilisateur de [!DNL Target], cliquez sur **[!UICONTROL View in Analytics]**.
1. Ajoutez la colonne **[!UICONTROL Activity Impressions]** au rapport [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr){target=_blank}.
1. Dans la colonne **[!UICONTROL Activity Impressions]**, cliquez sur l’icône [!UICONTROL Gear] .
1. Cliquez sur **[!UICONTROL Use non-default attribution model]**.
1. Sélectionnez **[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**.

+++
