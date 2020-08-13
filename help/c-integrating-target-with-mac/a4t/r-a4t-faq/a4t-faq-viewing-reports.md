---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: Cette rubrique contient des réponses aux questions fréquentes sur l’affichage des rapports lors de l’utilisation d’Analytics comme source de création de rapports pour Target (A4T).
title: FAQ sur l’affichage des rapports - A4T
feature: a4t troubleshooting
topic: Standard
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1992'
ht-degree: 63%

---


# FAQ sur l’affichage des rapports - A4T{#view-reports-a-t-faq}

This topic contains answers to questions that are frequently asked about viewing reports when using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## Can I view my Target activity data in Analysis Workspace? {#workspace}

Vous pouvez l’utiliser [!DNL Analysis Workspace] pour analyser vos [!DNL Target] activités et expériences. Le panneau [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics pour la Cible vous permet d’afficher l’effet élévateur et la fiabilité de trois mesures de réussite au maximum. Vous pouvez également approfondir vos recherches à l’aide de tableaux et de visualisations.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## Où les segments peuvent-ils être appliqués en Analysis Workspace ? {#segmentation}

Les segments sont généralement appliqués en haut d’un panneau dans la zone de dépôt de segments. Le segment est appliqué à tous les tableaux et visualisations du panneau. Cette technique est particulièrement utile pour déterminer comment le test affecte un sous-ensemble de personnes (par exemple, comment ce test a-t-il fonctionné pour les personnes au Royaume-Uni) ?

## Lorsque j’applique un segment d’accès pour une activité de Cible spécifique, pourquoi vois-je des expériences sans rapport renvoyées ? {#activity-segmentation}

La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. (Remarque : cette période d’expiration peut être ajustée par le service à la clientèle si nécessaire). Lorsque les visiteurs naviguent sur le site tout au long de cette fenêtre d’expiration, ils font partie de nombreuses [!DNL Target] activités, qui sont toutes collectées dans la dimension.

Par conséquent, lorsque vous segmentez une activité pour qu’elle soit présente dans un accès, vous obtenez toutes les expériences qui font partie de cette activité *ainsi* que toutes les autres expériences qui persistent dans cet accès.

## Dois-je utiliser des visiteurs, des visites ou des impressions d’activité comme mesure de normalisation (c.-à-d. méthodologie de comptage) ? {#metrics}

Il existe plusieurs options de normalisation des mesures dans le rapports A4T. Cette mesure, également appelée méthodologie de comptabilisation, devient le dénominateur du calcul de l’effet élévateur. Elle affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance.

* ***Visiteurs uniques*** : augmente une fois qu’un utilisateur est admissible pour une activité pour la première fois.
* ***Visites*** : augmente à chaque session une fois qu’un utilisateur (visiteur unique) entre dans une activité, même s’il ne la consulte pas lors de ses visites ultérieures.
* ***Impressions d’activité*** : augmente à chaque fois que le contenu de l’activité est présenté. (Mesuré par [!DNL Target]).

Lorsqu’un visiteur visualise une page contenant une activité, une variable contenant le nom de cette activité est définie pour ce visiteur. Consultez les scénarios détaillés ci-après pour une comparaison entre les différentes méthodologies de calcul.

Tenez compte des points suivants :

* All of the above metrics trigger when a user qualifies for an activity and content is returned from [!DNL [!DNL Target]]. Cela ne signifie pas pour autant que l’utilisateur a forcément vu l’offre. Si l’activité de l’expérience se trouve en bas de page et que l’utilisateur ne fait pas entièrement défiler celle-ci, l’offre est bien diffusée par [!DNL Target], mais l’utilisateur ne la voit pas.
* Le nombre d’[!UICONTROL impressions d’activité] (mesurées par [!DNL Target]) et d’[!UICONTROL instances] (mesurées par [!DNL Analytics]) est égal, sauf dans le cas de plusieurs appels de mbox sur une même page, dans une même activité. Cela entraîne le comptage de plusieurs [!UICONTROL impressions d’activité], mais d’une seule [!UICONTROL instance].

## Pourquoi les &quot;impressions d’activité&quot; et les &quot;conversions d’activité&quot; sont-elles plus élevées dans Analysis Workspace que les rapports et analyses ? {#sametouch}

[!DNL Reports & Analytics] applique un modèle d’attribution d’une même touche aux &quot;impressions d’activité&quot; et aux &quot;conversions d’activité&quot;, tandis que [!DNL Analysis Workspace] affiche les mesures brutes, qui peuvent sembler exagérées en raison de la persistance de la [!DNL Target] dimension.

To evaluate accurate [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. Pour appliquer des modèles, cliquez sur l’engrenage des paramètres de colonne, activez [!UICONTROL Modèle d’attribution autre que celui par défaut], puis sélectionnez [!UICONTROL Même touche. ] Pour en savoir plus sur l’attribution dans l’aperçu [du QI des](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) attributs, consultez le Guide *des outils* Analytics.

## Que signifie « conversions de l’activité » si le marketeur choisit une mesure Analytics lors de la configuration de l’activité ?{#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Activity conversions&quot; will be empty if an [!DNL Analytics] metric was selected as the conversion metric for the activity.

## Pourquoi la mention « non spécifié » s’affiche-t-elle dans les rapports Analytics ? Qu’est-ce que cela signifie ? {#unspecified}

Dans d’autres rapports, la mention « non spécifié » indique que les données ne respectent pas une règle de classification, mais cela ne devrait jamais se produire dans A4T. Si la mention « non spécifié » s’affiche, cela signifie que le service de classification ne s’est pas encore exécuté. Les données des activités prennent généralement de 24 à 72 heures pour apparaître dans les rapports. Même si les activités n’apparaissent pas dans le rapport avant ce délai, les données des visiteurs associés à ces activités sont capturées et apparaîtront une fois la classification terminée.

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

## Pourquoi des mesures Target sont-elles envoyées à Analytics même quand l’activité a été désactivée ?{#section_38AA8380A4D54A18972F1EF3E73E22EF}

La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. Cette période d’expiration peut être ajustée par le service à la clientèle si nécessaire. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

You might see [!DNL Target] variables sent to [!DNL Analytics] after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled [!DNL Target] activity. Si un utilisateur revient sur le site au 45 e jour et voit une autre activité, le compteur de la valeur entière de l’eVar A4T est réinitialisé à 90 jours. En d’autres termes, la première campagne à partir du jour 1 pourrait persister pendant 45 + 90 = 135 jours au maximum. If the user keeps coming back, you might get to the point where you see metrics sent to [!DNL Analytics] in your reporting from much older activities. Si l’utilisateur supprime les cookies et ne revient pas sur le site, les chiffres dans cette activité baisseront, mais resteront visibles.

Cela signifie que ces activités continuent de bénéficier de vues, de visites, etc., jusqu’à 90 jours après la fin de l’activité pour les visiteurs devenus membres de l’activité lorsque celle-ci était active. Toutefois, si vous examinez la mesure [!UICONTROL Impressions d’activité], vous ne devriez voir aucune impression après la fin de l’activité.

Il s’agit d’un comportement normal et attendu. La variable A4T fonctionne comme n’importe quelle autre eVar - la valeur est associée à l’utilisateur jusqu’à ce qu’elle expire (90 jours). Si, par conséquent, une activité est active pendant deux semaines seulement, la valeur reste associée à l’utilisateur pendant les 90 jours suivants, au moins.

Il est recommandé d’afficher les rapports pour cette activité seulement pendant la période pendant laquelle l’activité était active. The dates should be set correctly by default when you view the activity in [!DNL Analytics], so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

Par exemple, supposons que la variable A4T expire après 90 jours et que notre test est actif du 1er au 15 janvier.

Le 1er janvier, l’utilisateur consulte le site et voit l’activité XYZ une fois, puis cinq pages ensuite. Au cours des deux semaines suivantes, l’utilisateur ne revient pas sur le site. Pour cet utilisateur, les données ressembleraient à ceci :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

L’utilisateur revient le 1er février, consulte cinq autres pages, mais ne consulte aucune autre activité Target et l’activité d’origine n’est plus active. Même si l’activité n’est plus active, l’utilisateur continue à être suivi par le biais de la persistance des eVars. Les données ressemblent maintenant à ce qui suit :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

L’utilisateur revient sur le site le 1er mars et voit une nouvelle activité, l’activité ABC. Il voit également cinq pages. Puisque l’activité XYZ continue à suivre l’utilisateur en raison de l’eVar persistante et que l’activité ABC est définie pour cet utilisateur, deux lignes s’affichent dans les rapports :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

L’utilisateur revient alors le 1er avril, consulte cinq autres pages et effectue un achat. L’expiration à 90 jours de cette première valeur d’eVar est réinitialisée le 1er avril, ce qui se répercutera dans les rapports. La conversion est répercutée à toutes les activités Target que l’utilisateur voit, mais le nombre total de conversions est dédupliqué :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques | Commandes |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Les deux expériences ayant été vues avant la conversion, elles sont toutes deux « créditées » de la commande. Toutefois, une seule commande a eu lieu dans le système, ce qui se reflète dans le total. For [!DNL Target] reporting, because you aren’t putting a [!DNL Target] activity against another activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. Vous comparez les résultats de deux éléments au cours d’une seule et même activité. Il n’est pas possible de présenter à l’utilisateur des contenus différents dans la même activité, de sorte que l’inter-contamination du crédit de la commande ne présente pas de problème.

For more information, see [Conversion Variables (eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## Pourquoi le calcul de la mesure Visiteurs uniques est-il différent dans Analytics et dans Analytics for Target (A4T) ?{#section_0C3B648AB54041F9A2AA839D51791883}

Lorsque vous exécutez un test A/B qui utilise le test en t de Student (la mesure du degré de confiance) pour choisir le gagnant d’un test, on suppose entre autres qu’une date de fin est définie. Le test n’est pas statistiquement valide si vous n’examinez pas cet échantillon de taille fixe.

The [!UICONTROL Unique Visitors] metric is different in [!DNL Analytics] and [!DNL Target] only when you are looking at a period of time that is shorter than the actual test. Le test n’est pas fiable si la taille de l’échantillon n’est pas atteinte. Pour en savoir plus, voir la rubrique [Comment ne pas exécuter un test A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) (en anglais) sur le [site web d’Evan Miller](https://www.evanmiller.org/index.html).

The [!UICONTROL Unique Visitors] metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. Ces personnes font toujours partie du test et doivent être comptabilisées. Pour afficher uniquement le nombre de personnes qui ont été exposées au cours d’une seule semaine, vous pouvez créer un segment de visiteurs qui ont exécuté une impression de l’activité et l’ont appliquée au rapport.

You can shorten the amount of time the [!DNL Target] variable persists down to a session; however, that is usually problematic for tests where the conversion event isn’t as likely to happen within the same session.

## Pourquoi le même visiteur est-il parfois comptabilisé dans plusieurs expériences dans Analytics ? {#section_1397E972D31C4207A142E4D2D6D794A2}

La liste suivante explique les raisons pour lesquelles le même visiteur peut être comptabilisé dans plusieurs expériences dans [!DNL Analytics]:

* The [!DNL Target] profile expired but the [!DNL Analytics] cookie is still there. In this situation, [!DNL Target] re-evaluates the user but [!DNL Analytics] considers the visitor to be the same person.
* Si le visiteur utilise `mbox3rdPartyId`, lorsque le visiteur anonyme est fusionné avec son profil d’ID tiers,  peut le mettre dans une expérience différente pour établir une correspondance avec l’ID tiers. [!DNL Target] Pour plus d’informations, voir [Synchronisation de profil en temps réel pour mbox3 à identifiant tiers](../../../c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] peut suivre différents périphériques comme le même visiteur d&#39;une manière différente que [!DNL Target] le suivi de ces périphériques : la configuration des identifiants tiers dans [!DNL Target] est différente de celle d’Analytics.

## A4T prend-il en charge les suites de rapports virtuelles ?

Les suites de rapports virtuelles *ne sont pas* incluses dans la liste des suites de rapports et les audiences des suites de rapports virtuelles ne sont pas prises en charge dans les rapports A4T.

## Puis-je modifier le pourcentage de l’affectation du trafic dans une activité qui utilise A4T après l’activation de l’activité ?

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in [!DNL Analytics] because the change impacts only new visitors. Les visiteurs récurrents ne sont pas affectés.

En règle générale, il est conseillé d’arrêter l’activité existante, puis de créer une nouvelle activité plutôt que de modifier le pourcentage après son activation. La création de rapports pour la nouvelle activité commence par les nouveaux visiteurs et les données des visiteurs de retour ne provoqueront pas de rapports incohérents.
