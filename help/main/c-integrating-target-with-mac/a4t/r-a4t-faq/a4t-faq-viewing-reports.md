---
keywords: faq;questions fréquentes;analytics pour target;a4T;rapport;rapports;afficher des rapports;création de rapports;méthodologie de calcul;impressions;visiteurs;visites;mesure par défaut;conversions des activités;non spécifié
description: Trouvez des réponses aux questions fréquentes sur l’affichage des rapports lors de l’utilisation d’Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser les rapports Analytics pour les activités  [!DNL Target] .
title: Trouvez des réponses aux questions sur l’affichage des rapports avec A4T ?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: c747a8a0ed480130f254818e21b98addca16ca41
workflow-type: tm+mt
source-wordcount: '2539'
ht-degree: 24%

---

# FAQ sur l’affichage des rapports - A4T

Cette rubrique contient des réponses aux questions fréquentes sur l’affichage des rapports lors de l’utilisation de [!DNL Adobe Analytics] comme source des rapports pour [!DNL Adobe Target] (A4T).

## Puis-je afficher mes données d’activité [!DNL Target] dans [!DNL Analysis Workspace] ? {#workspace}

+++Réponse
Vous pouvez utiliser [!DNL Analysis Workspace] pour analyser vos activités et expériences [!DNL Target]. Le [panneau Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=fr) vous permet d’afficher l’effet élévateur et le degré de confiance pour trois mesures de succès au maximum. Vous pouvez également approfondir l’analyse à l’aide de tableaux et de visualisations.

Pour obtenir des informations détaillées et des exemples, ouvrez le [tutoriel Analytics et Target : bonnes pratiques pour l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par [!UICONTROL Adobe Experience League].

+++

## Où les segments peuvent-ils être appliqués dans [!DNL Analysis Workspace] ? {#segmentation}

+++Réponse
Les segments sont le plus souvent utilisés en haut d’un panneau dans la zone de dépôt des segments. Le segment est appliqué à tous les tableaux et visualisations du panneau. Cette technique est particulièrement utile pour voir comment le test affecte un sous-ensemble de personnes (par exemple, comment ce test a-t-il été effectué pour les personnes au Royaume-Uni) ?

Un segment peut également être superposé directement dans le tableau à structure libre, mais vous devez le superposer sur l’ensemble du tableau pour conserver les calculs de l’effet élévateur et du degré de confiance dans le panneau A4T. Les segments au niveau des colonnes ne sont actuellement pas pris en charge dans le panneau.

+++

## Quel modèle Attribution IQ est utilisé dans [!DNL Analysis Workspace] ?

+++Réponse
Lors de l’utilisation des impressions et conversions d’activité [!DNL Target] dans [!DNL Analysis Workspace], le modèle Attribution IQ &quot;Même touche&quot; est le modèle par défaut appliqué aux mesures pour garantir un comptage précis. Ce modèle fonctionne bien dans 99 % des cas. Cependant, vous pouvez remplacer cette attribution standard dans Attribution IQ.

+++

## Lorsque j’applique un segment d’accès pour une activité [!DNL Target] spécifique, pourquoi des expériences sans rapport sont-elles renvoyées ? {#activity-segmentation}

+++Réponse
La variable [!DNL Target] envoyée à [!DNL Analytics] a une période d’expiration de 90 jours par défaut. (Remarque : cette période d’expiration peut être ajustée par l’assistance clientèle si nécessaire). Lorsque les visiteurs naviguent sur le site tout au long de cette fenêtre d’expiration, ils font partie de nombreuses activités [!DNL Target], qui sont toutes collectées dans la dimension.

Lorsque vous segmentez pour qu’une activité soit présente dans un accès, vous obtenez toutes les expériences qui font partie de cette activité *plus* toutes les autres expériences qui persistent sur cet accès.

+++

## Lors de la configuration de mon [!UICONTROL Goal Metrics], pourquoi ne puis-je pas accéder à [!UICONTROL Advanced Settings] ?

+++Réponse
Pour les activités utilisant [!DNL Analytics] comme source des rapports (A4T), la mesure d’objectif utilise les paramètres &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; et &quot;[!UICONTROL On Every Impression]&quot;. Ces paramètres sont *non* configurables.

Pour plus d’informations, voir &quot;Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ?&quot; dans [FAQ sur les définitions de mesures - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Dois-je utiliser les visiteurs, les visites ou les impressions d’activité comme mesure de normalisation (c.-à-d. méthodologie de comptage) ? {#metrics}

+++Réponse
Il existe plusieurs options de normalisation des mesures dans les rapports A4T. Cette mesure, également appelée méthodologie de calcul, devient le dénominateur du calcul de l’effet élévateur. Elle affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance.

* ***Visiteurs uniques*** augmente une fois qu’un utilisateur est admissible pour une activité pour la première fois.
* ***Visites*** est incrémenté pour chaque session une fois qu’un utilisateur (visiteur unique) entre dans une activité, même si l’activité n’est pas affichée lors des visites suivantes.
* ***Impressions d’activité*** augmente chaque fois que le contenu de l’activité est diffusé. (Mesure par [!DNL Target]).

Lorsqu’un visiteur visualise une page contenant une activité, une variable contenant le nom de cette activité est définie pour ce visiteur. Consultez les scénarios détaillés ci-après pour une comparaison entre les différentes méthodologies de calcul.

Tenez compte des points suivants :

* Les mesures ci-dessus se déclenchent lorsqu’un utilisateur est admissible pour une activité et que le contenu est renvoyé depuis [!DNL Target]. Cela ne signifie pas pour autant que l’utilisateur a forcément vu l’offre. Si l’activité de l’expérience se trouve en bas de page et que l’utilisateur ne fait pas entièrement défiler celle-ci, l’offre est bien diffusée par [!DNL Target], mais l’utilisateur ne la voit pas.
* [!UICONTROL Activity Impressions] (mesuré par [!DNL Target]) et [!UICONTROL Instances] (mesuré par [!DNL Analytics]) sont égaux, sauf s’il existe plusieurs appels de mbox sur la même page dans la même activité. Cela entraîne la comptabilisation de plusieurs [!UICONTROL Activity Impressions], mais d’un seul [!UICONTROL Instance].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr) dans *Adobe Target Tutorials*.

+++

## Pourquoi les &quot;impressions d’activité&quot; et les &quot;conversions d’activité&quot; sont-elles plus élevées dans [!DNL Analysis Workspace] que [!UICONTROL Reports & Analytics] ? {#sametouch}

+++Réponse
[!DNL Reports & Analytics] applique un modèle d’attribution de même touche aux &quot;impressions de l’activité&quot; et aux &quot;conversions de l’activité&quot;, tandis que [!DNL Analysis Workspace] affiche les mesures brutes, qui peuvent sembler exagérées en raison de la persistance de la dimension [!DNL Target].

Pour évaluer la précision des mesures [!UICONTROL Activity Impressions] et [!UICONTROL Activity Conversions] dans [!DNL Analysis Workspace], assurez-vous que les deux mesures ont des modèles d’attribution [!UICONTROL Same Touch] appliqués. Vous pouvez appliquer des modèles en cliquant sur l’engrenage des paramètres de colonne, en activant [!UICONTROL Non-default attribution models], puis en sélectionnant [!UICONTROL Same Touch]. Pour en savoir plus sur l’attribution dans la [présentation d’Attributs IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html?lang=fr) du *Guide des outils Analytics*.

+++

## Que signifie &quot;conversions de l’activité&quot; si le marketeur choisit une mesure [!DNL Analytics] lors de la configuration de l’activité ? {#section_F3EBACF85AF846E9B366A549AAB64356}

+++Réponse
Les &quot;conversions de l’activité&quot; sont vides si une mesure [!DNL Analytics] a été sélectionnée comme mesure de conversion pour l’activité.

+++

## Pourquoi &quot;non spécifié&quot; s’affiche-t-il dans les rapports [!DNL Analytics] ? Qu’est-ce que cela signifie ? {#unspecified}

+++Réponse
Dans d’autres rapports, &quot;non spécifié&quot; signifie que les données ne respectent pas une règle de classification, mais cela ne devrait jamais se produire dans A4T. Si la mention « non spécifié » s’affiche, cela signifie que le service de classification ne s’est pas encore exécuté. Les données des activités prennent généralement de 24 à 72 heures pour apparaître dans les rapports. Même si les activités n’apparaissent pas dans ce rapport avant ce moment, toutes les données de visiteur liées à ces activités sont capturées et apparaissent une fois la classification terminée.

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Si la classification a été effectuée pour cette activité et que vous voyez toujours une ligne &quot;Non spécifié&quot; dans le rapport, assurez-vous que le rapport n’utilise pas de mesure non-[!DNL Target] pour afficher les données. À moins que le rapport n’utilise une mesure spécifique à [!DNL Target], cette ligne &quot;Non spécifié&quot; contient des événements pour les appels qui ne sont pas associés à [!DNL Target]. Cette ligne ne contiendra aucune information associée à [!DNL Target] (par exemple, visiteurs/visites/impressions).

+++

## Pourquoi [!DNL Target] mesures sont-elles envoyées à [!DNL Analytics] même après la désactivation de l’activité ? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++Réponse
La variable [!DNL Target] envoyée à [!DNL Analytics] a une période d’expiration de 90 jours par défaut. Si nécessaire, cette période d’expiration peut être ajustée par l’assistance clientèle. Ce paramètre est global pour toutes les activités. Toutefois, il ne doit pas être adapté à un seul cas.

Vous pouvez voir [!DNL Target] variables envoyées à [!DNL Analytics] après la période d’expiration, car l’expiration est de 90 jours, mais seulement si cet utilisateur ne voit jamais une autre activité [!DNL Target] compatible A4T. Si un utilisateur revient sur le site au 45 e jour et voit une autre activité, le compteur de la valeur entière de l’eVar A4T est réinitialisé à 90 jours. En d’autres termes, la première campagne à partir du jour 1 pourrait persister pendant 45 + 90 = 135 jours au maximum. Si l’utilisateur continue de revenir, vous pouvez en arriver au point où les mesures envoyées à [!DNL Analytics] dans vos rapports provenant d’activités beaucoup plus anciennes s’affichent. Lorsque les utilisateurs suppriment les cookies et ne reviennent pas sur le site, les chiffres de cette activité diminuent, mais vous pouvez toujours les voir.

Cela signifie que les activités continuent d’obtenir des pages vues, des visites, etc., pendant 90 jours jusqu’à la fin de l’activité pour les visiteurs qui sont devenus membres de l’activité lorsqu’elle était active. Cependant, si vous observez la mesure [!UICONTROL Activity Impressions], vous ne devriez voir aucune impression une fois l’activité terminée.

Il s’agit d’un comportement normal et attendu. La variable A4T fonctionne comme n’importe quelle autre eVar - la valeur est associée à l’utilisateur jusqu’à ce qu’elle expire (90 jours). Par conséquent, si une activité est active pendant seulement deux semaines, la valeur est toujours associée à l’utilisateur pendant au moins les 90 jours suivants.

Il est recommandé d’afficher les rapports pour cette activité seulement pendant la période pendant laquelle l’activité était active. Les dates doivent être correctement définies par défaut lorsque vous affichez l’activité dans [!DNL Analytics]. Par conséquent, sauf si vous avez étendu manuellement la date, cela ne devrait pas poser de problème du point de vue de la création de rapports.

Par exemple, supposons que la variable A4T expire après 90 jours et que le test est actif du 1er au 15 janvier.

Le 1er janvier, l’utilisateur consulte le site et voit l’activité XYZ une fois, puis cinq pages ensuite. Au cours des deux semaines suivantes, l’utilisateur ne revient pas sur le site. Pour cet utilisateur, les données ressembleraient à ceci :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

L’utilisateur revient le 1er février, consulte cinq autres pages et ne rencontre plus d’activités Target et l’activité d’origine n’est plus active. Même si l’activité n’est plus active, l’utilisateur continue à être suivi par le biais de la persistance des eVars. Les données ressemblent maintenant à ce qui suit :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

L’utilisateur revient sur le site le 1er mars et voit une nouvelle activité, l’activité ABC. Il voit également cinq pages. Comme l’activité XYZ suit toujours l’utilisateur par le biais de la persistance, et que l’ABC est ensuite défini pour cet utilisateur, deux éléments de ligne s’affichent dans les rapports :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

L’utilisateur revient alors le 1er avril, consulte cinq autres pages et effectue un achat. L’expiration de 90 jours de cette première valeur d’eVar est réinitialisée le 1er avril, ce qui s’affiche dans les rapports. La conversion est répercutée à toutes les activités Target que l’utilisateur voit, mais le nombre total de conversions est dédupliqué :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques | Commandes |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Comme les deux expériences étaient visibles avant la conversion, elles reçoivent toutes deux le &quot;crédit&quot; de la commande. Toutefois, une seule commande a eu lieu dans le système, ce qui se reflète dans le total. Pour la création de rapports [!DNL Target], puisque vous ne placez pas une activité [!DNL Target] par rapport à une autre activité pour voir laquelle est plus réussie, peu importe que toutes les activités que l’utilisateur a vues reçoivent du crédit. Vous comparez les résultats de deux éléments dans une seule activité. Il n’est pas possible pour un utilisateur de voir des expériences différentes dans la même activité, de sorte que vous n’ayez pas à vous soucier de la contamination croisée du crédit de commande.

Pour plus d’informations, voir [Variables de conversion (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html?lang=fr)) dans le *Guide de l’administrateur Analytics*.

+++

## Pourquoi est-ce que je continue à voir des impressions après la désactivation de mon activité ? {#deactivated}

+++Réponse
Une source d’impressions pour le rapport d’une activité A4T après la désactivation peut être le trafic en mode AQ. Target ne consigne normalement pas les événements pour une activité désactivée, mais Analytics ne dispose pas d’un moyen de savoir que les impressions proviennent du mode AQ. Lorsque le rapport d’activité Target est récupéré depuis Analytics, il affiche ces impressions. Cela fonctionne comme prévu, car les clients doivent pouvoir vérifier les rapports A4T même si l’activité n’est pas active à l’aide du mode AQ.

+++

## Pourquoi [!DNL Analytics] et [!UICONTROL Analytics for Adobe Target] (A4T) calculent-ils les nombres différemment pour la mesure [!UICONTROL Unique Visitors] ? {#section_0C3B648AB54041F9A2AA839D51791883}

+++Réponse
Lorsque vous exécutez un test A/B qui utilise le test en t [Welch&#39;s ](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (la mesure de confiance) pour choisir un gagnant d’un test, l’une des hypothèses est qu’il existe un horizon à temps fixe. Le test n’est pas statistiquement valide, sauf si vous observez cette taille d’échantillon fixe.

La mesure [!UICONTROL Unique Visitors] est différente dans [!DNL Analytics] et [!DNL Target] uniquement lorsque vous observez une période plus courte que le test réel. Si vous n’avez pas atteint votre taille d’échantillon, le test n’est pas aussi fiable. Pour en savoir plus, voir la rubrique [Comment ne pas exécuter un test A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) (en anglais) sur le [site web d’Evan Miller](https://www.evanmiller.org/index.html).

La mesure [!UICONTROL Unique Visitors] affiche le nombre de personnes qui ont été exposées au test et qui ont visité le site au cours d’une période donnée. Ces personnes font partie du test et doivent être comptabilisées. Pour afficher uniquement le nombre de personnes qui ont été exposées au cours d’une seule semaine, vous pouvez créer un segment de visiteurs qui ont exécuté une impression de l’activité et l’ont appliquée au rapport.

Vous pouvez raccourcir le temps pendant lequel la variable [!DNL Target] persiste jusqu’à une session ; toutefois, cela pose problème pour les tests où l’événement de conversion n’est pas aussi susceptible de se produire au cours de la même session.

+++

## Pourquoi un même visiteur est-il parfois comptabilisé dans plusieurs expériences dans [!DNL Analytics] ? {#section_1397E972D31C4207A142E4D2D6D794A2}

+++Réponse
La liste suivante explique les raisons pour lesquelles un même visiteur peut être comptabilisé dans plusieurs expériences dans [!DNL Analytics] :

* Le profil [!DNL Target] a expiré mais le cookie [!DNL Analytics] est toujours présent. Dans ce cas, [!DNL Target] réévalue l’utilisateur, mais [!DNL Analytics] considère le visiteur comme la même personne.
* Si le visiteur utilise le `mbox3rdPartyId`, lorsque le visiteur anonyme est fusionné avec le profil d’ID tiers, [!DNL Target] peut le mettre dans une expérience différente pour correspondre à l’ID tiers. Pour plus d’informations, voir [Synchronisation de profil en temps réel pour mbox3 à identifiant tiers](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] peut effectuer le suivi de différents appareils sur lesquels le même visiteur effectue un suivi différent de [!DNL Target] par rapport à ces appareils : la configuration des identifiants tiers dans [!DNL Target] est différente de celle d’Analytics.

+++

## A4T prend-il en charge les suites de rapports virtuelles ? {#virtual}

+++Réponse
Bien que les suites de rapports virtuelles ne soient pas incluses dans la liste [!UICONTROL Report Suite], toutes les données A4T partagées avec une suite de rapports liée à une suite de rapports virtuelle dans [!DNL Analytics] ont accès à ces données. Notez que toute audience créée à partir d’une suite de rapports virtuelle ne peut pas être partagée à nouveau vers [!DNL Target].

+++

## Puis-je modifier le pourcentage de l’affectation du trafic dans une activité qui utilise A4T après l’activation de l’activité ?

+++Réponse
La modification du pourcentage d’affectation du trafic dans une activité après l’activation peut entraîner des rapports incohérents dans [!DNL Analytics], car la modification n’affecte que les nouveaux visiteurs. Les visiteurs récurrents ne sont pas affectés.

En règle générale, il est conseillé d’arrêter l’activité existante, puis de créer une nouvelle activité plutôt que de modifier le pourcentage après son activation. La création de rapports pour la nouvelle activité commence par les nouveaux visiteurs et les données des visiteurs récurrents ne provoquent pas de rapports incohérents.

+++

## Comment les visites sont-elles comptabilisées dans [!DNL Analytics] et le crédit de conversion attribué dans une activité [!UICONTROL Auto-Target] qui utilise A4T ?

+++Réponse
Lorsqu’un visiteur est admissible pour une activité A4T, visualise du contenu ou convertit du contenu, [!DNL Target] envoie des données d’événement à [!DNL Analytics]. Ces données d’événement permettent à [!DNL Analytics] d’attribuer des événements de conversion et d’autres événements de parcours de navigation se produisant sur la page aux activités et expériences [!DNL Target] appropriées.

Voici quelques points à garder à l’esprit lors de l’affichage des rapports [!DNL Analytics] :

* En règle générale, la fenêtre de création de rapports doit commencer à partir de la date de début de l’activité.
* Si une conversion se produit en dehors de la fenêtre du rapport, la conversion n’est pas visible dans [!DNL Analytics].
* Dans la partie &quot;ciblée&quot; du trafic pour les activités [!UICONTROL Auto-Target], les visiteurs peuvent voir différentes expériences d’une session à l’autre. Par exemple, si leur profil ou leur contexte a changé et que les algorithmes d’apprentissage automatique de [!DNL Target] décident qu’ils sont plus susceptibles de se convertir sur une nouvelle expérience. À mesure que les visiteurs passent d’une expérience à l’autre, le nombre de visites est incrémenté pour chaque expérience vue. Contrairement aux activités de test A/B standard où les expériences sont persistantes pour un visiteur entre plusieurs visites.
* Si un visiteur voit plusieurs expériences au cours de plusieurs visites, toute conversion est toujours attribuée à la dernière expérience vue par le visiteur. Comme mentionné, le nombre de visites est incrémenté pour chaque expérience vue par le visiteur. Cela peut diminuer artificiellement les taux de conversion par expérience lors de l’affichage d’expériences sous la dimension &quot;[!UICONTROL Targeted]&quot; dans les rapports [!DNL Adobe Analytics].

+++

## Comment effectuer le suivi des impressions d’activité dans [!DNL Analysis Workspace] lors de l’utilisation de [!UICONTROL Analytics for Target] (A4T) ? {#activity-impressions}

+++Réponse

Pour afficher les impressions d’activité dans [!DNL Analysis Workspace] :

1. Dans l’interface utilisateur de [!DNL Target], cliquez sur **[!UICONTROL View in Analytics]**.
1. Ajoutez la colonne **[!UICONTROL Activity Impressions]** au rapport [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr){target=_blank}.
1. Dans la colonne **[!UICONTROL Activity Impressions]**, cliquez sur l’icône [!UICONTROL Gear].
1. Cliquez sur **[!UICONTROL Use non-default attribution model]**.
1. Sélectionnez **[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**.

+++
