---
keywords: faq;questions fréquentes;analytics pour target;a4T;rapport;rapports;afficher des rapports;création de rapports;méthodologie de calcul;impressions;visiteurs;visites;mesure par défaut;conversions des activités;non spécifié
description: Trouvez des réponses aux questions fréquentes sur l’affichage des rapports lors de l’utilisation d’Analytics pour la Cible (A4T). A4T vous permet d’utiliser le rapports Analytics pour les activités de Cible.
title: Trouver des réponses aux questions sur l’affichage des rapports avec A4T ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 2773b934fc27e102c34afc29e5b22fc8725878bd
workflow-type: tm+mt
source-wordcount: '2526'
ht-degree: 38%

---


# FAQ sur l’affichage des rapports - A4T

Cette rubrique contient des réponses aux questions fréquemment posées sur l’affichage des rapports lors de l’utilisation de [!DNL Adobe Analytics] comme source de rapports pour [!DNL Adobe Target] (A4T).

## Puis-je vue mes données d&#39;activité Cible à Analysis Workspace ? {#workspace}

Vous pouvez utiliser [!DNL Analysis Workspace] pour analyser vos [!DNL Target] activités et expériences. Le [panneau Analyses pour la Cible](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) vous permet d’afficher l’effet élévateur et la fiabilité de trois mesures de réussite au maximum. Vous pouvez également approfondir vos recherches à l’aide de tableaux et de visualisations.

Pour obtenir des informations détaillées et des exemples, ouvrez la section [Analyses et Cible : Didacticiel sur les meilleures pratiques en matière d’Analyse ](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par Adobe Experience League.

## Où les segments peuvent-ils être appliqués en Analysis Workspace ? {#segmentation}

Les segments sont le plus souvent utilisés en haut d’un panneau dans la zone de dépôt des segments. Le segment est appliqué à tous les tableaux et visualisations du panneau. Cette technique est particulièrement utile pour déterminer comment le test affecte un sous-ensemble de personnes (par exemple, comment ce test a-t-il fonctionné pour les personnes au Royaume-Uni) ?

Un segment peut également être superposé directement dans le tableau à structure libre, mais notez que vous devez le superposer sur l’ensemble du tableau pour conserver les calculs d’effet élévateur et de fiabilité dans le panneau A4T. Les segments au niveau de la colonne ne sont actuellement pas pris en charge dans le panneau.

## Lorsque j’applique un segment d’accès pour une activité de Cible spécifique, pourquoi les expériences sans rapport sont-elles renvoyées ? {#activity-segmentation}

La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. (Remarque : cette période d’expiration peut être ajustée par le service à la clientèle si nécessaire). Lorsque les visiteurs naviguent sur le site tout au long de cette fenêtre d&#39;expiration, ils font partie de nombreuses activités [!DNL Target], qui sont toutes collectées dans la dimension.

Lorsque vous segmentez une activité pour qu’elle soit présente dans un accès, vous obtenez toutes les expériences qui font partie de cette activité *plus* toutes les autres expériences qui persistent sur cet accès.

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux paramètres avancés ?

Pour les activités qui utilisent [!DNL Analytics] comme source de rapports (A4T), la mesure d’objectif utilise les paramètres &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur en Activité]&quot; et &quot;[!UICONTROL Sur chaque impression]&quot;. Ces paramètres sont *non* configurables.

Pour plus d’informations, voir &quot;Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ?&quot; dans [Définition des mesures - FAQ sur A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Dois-je utiliser des visiteurs, des visites ou des impressions d’activité comme mesure de normalisation (c.-à-d. méthodologie de comptage) ? {#metrics}

Il existe plusieurs options de normalisation des mesures dans le rapports A4T. Cette mesure, également appelée méthodologie de comptabilisation, devient le dénominateur du calcul de l’effet élévateur. Elle affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance.

* ***Visiteurs uniques*** : augmente une fois qu’un utilisateur est admissible pour une activité pour la première fois.
* ***Visites*** : augmente à chaque session une fois qu’un utilisateur (visiteur unique) entre dans une activité, même s’il ne la consulte pas lors de ses visites ultérieures.
* ***Impressions d’activité*** : augmente à chaque fois que le contenu de l’activité est présenté. (Mesuré par [!DNL Target]).

Lorsqu’un visiteur visualise une page contenant une activité, une variable contenant le nom de cette activité est définie pour ce visiteur. Consultez les scénarios détaillés ci-après pour une comparaison entre les différentes méthodologies de calcul.

Tenez compte des points suivants :

* Les mesures ci-dessus se déclenchent lorsqu’un utilisateur est admissible pour une activité et que le contenu est renvoyé à partir de [!DNL Target]. Cela ne signifie pas pour autant que l’utilisateur a forcément vu l’offre. Si l’activité de l’expérience se trouve en bas de page et que l’utilisateur ne fait pas entièrement défiler celle-ci, l’offre est bien diffusée par [!DNL Target], mais l’utilisateur ne la voit pas.
* Le nombre d’[!UICONTROL impressions d’activité] (mesurées par [!DNL Target]) et d’[!UICONTROL instances] (mesurées par [!DNL Analytics]) est égal, sauf dans le cas de plusieurs appels de mbox sur une même page, dans une même activité. Cela entraîne le comptage de plusieurs [!UICONTROL impressions d’activité], mais d’une seule [!UICONTROL instance].

Pour plus d’informations, voir [Comment configurer des rapports A4T dans Analysis Workspace pour les activités d’Cible automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) dans *Tutorials Adobe Target*.

## Pourquoi les &quot;impressions d’activité&quot; et les &quot;conversions d’activité&quot; sont-elles plus élevées dans Analysis Workspace que les rapports et analyses ? {#sametouch}

[!DNL Reports & Analytics] applique un modèle d’attribution d’une même touche aux &quot;impressions d’activité&quot; et aux &quot;conversions d’activité&quot;, alors qu’ [!DNL Analysis Workspace] affiche les mesures brutes, qui peuvent sembler exagérées en raison de la persistance de la  [!DNL Target] dimension.

Pour évaluer des mesures [!UICONTROL Impressions d’Activité] et [!UICONTROL Conversions d’Activité] précises dans [!DNL Analysis Workspace], veillez à ce que les deux mesures aient des modèles d’attribution [!UICONTROL Même touche] appliqués. Pour appliquer des modèles, cliquez sur l’engrenage des paramètres de colonne, activez [!UICONTROL Modèle d’attribution autre que celui par défaut], puis sélectionnez [!UICONTROL Même touche. ] Pour en savoir plus sur l’attribution, consultez la section [Présentation du QI des attributs](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) du *Guide des outils Analytics*.

## Que signifie « conversions de l’activité » si le marketeur choisit une mesure Analytics lors de la configuration de l’activité ?{#section_F3EBACF85AF846E9B366A549AAB64356}

Les &quot;conversions d’Activité&quot; sont vides si une mesure [!DNL Analytics] a été sélectionnée comme mesure de conversion pour l’activité.

## Pourquoi la mention « non spécifié » s’affiche-t-elle dans les rapports Analytics ? Qu’est-ce que cela signifie ? {#unspecified}

Dans d’autres rapports, la mention « non spécifié » indique que les données ne respectent pas une règle de classification, mais cela ne devrait jamais se produire dans A4T. Si la mention « non spécifié » s’affiche, cela signifie que le service de classification ne s’est pas encore exécuté. Les données des activités prennent généralement de 24 à 72 heures pour apparaître dans les rapports. Bien que les activités n’apparaissent pas dans ce rapport avant cette date, toutes les données visiteurs liées à ces activités sont capturées et apparaissent une fois la classification terminée.

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Si la classification a été effectuée pour cette activité et que vous voyez toujours une ligne Non spécifié dans le rapport, veillez à ce que le rapport n’utilise pas une mesure non-[!DNL Target] pour afficher les données. Sauf si le rapport utilise une mesure spécifique [!DNL Target], cette ligne &quot;Non spécifié&quot; contient des événements pour les appels qui ne sont pas associés à [!DNL Target]. Cette ligne ne contiendra aucune information [!DNL Target] associée (par exemple, visiteurs/visites/impressions).

## Pourquoi des mesures Target sont-elles envoyées à Analytics même quand l’activité a été désactivée ?{#section_38AA8380A4D54A18972F1EF3E73E22EF}

La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. Cette période d’expiration peut être ajustée par le service à la clientèle si nécessaire. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

Vous pouvez voir des variables [!DNL Target] envoyées à [!DNL Analytics] après la période d’expiration, car l’expiration est de 90 jours, mais uniquement si cet utilisateur ne voit jamais une autre activité [!DNL Target] activée pour A4T. Si un utilisateur revient sur le site au 45 e jour et voit une autre activité, le compteur de la valeur entière de l’eVar A4T est réinitialisé à 90 jours. En d’autres termes, la première campagne à partir du jour 1 pourrait persister pendant 45 + 90 = 135 jours au maximum. Si l’utilisateur revient sans cesse, vous pouvez en arriver au point où des mesures envoyées à [!DNL Analytics] dans votre rapports par des activités beaucoup plus anciennes sont affichées. Lorsque les utilisateurs suppriment les cookies et ne reviennent pas sur le site, les chiffres de cette activité diminuent, mais vous pouvez toujours les voir.

Cela signifie que les activités continuent d’obtenir des vues de page, des visites, etc., jusqu’à 90 jours après la fin de l’activité pour les visiteurs qui sont devenus partie intégrante de l’activité alors qu’elle était principale. Toutefois, si vous examinez la mesure [!UICONTROL Impressions d’activité], vous ne devriez voir aucune impression après la fin de l’activité.

Il s’agit d’un comportement normal et attendu. La variable A4T fonctionne comme n’importe quelle autre eVar - la valeur est associée à l’utilisateur jusqu’à ce qu’elle expire (90 jours). Par conséquent, si une activité est principale pendant seulement deux semaines, la valeur est toujours associée à l’utilisateur pendant au moins les 90 jours suivants.

Il est recommandé d’afficher les rapports pour cette activité seulement pendant la période pendant laquelle l’activité était active. Les dates doivent être correctement définies par défaut lorsque vous vue l&#39;activité dans [!DNL Analytics]. Par conséquent, à moins que vous n&#39;ayez manuellement étendu la date, cela ne devrait pas poser problème du point de vue rapports.

Par exemple, supposons que la variable A4T expire après 90 jours et que le test soit principal du 1er au 15 janvier.

Le 1er janvier, l’utilisateur consulte le site et voit l’activité XYZ une fois, puis cinq pages ensuite. Au cours des deux semaines suivantes, l’utilisateur ne revient pas sur le site. Pour cet utilisateur, les données ressembleraient à ceci :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 3 | 1 |

L’utilisateur revient le 1er février, consulte cinq autres pages, mais ne consulte aucune autre activité Target et l’activité d’origine n’est plus active. Même si l’activité n’est plus active, l’utilisateur continue à être suivi par le biais de la persistance des eVars. Les données ressemblent maintenant à ce qui suit :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

L’utilisateur revient sur le site le 1er mars et voit une nouvelle activité, l’activité ABC. Il voit également cinq pages. Comme l’activité XYZ suit toujours l’utilisateur par le biais de la persistance, et que cet utilisateur dispose d’un ensemble ABC, deux éléments de ligne s’affichent dans le rapports :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 3 | 15 | 3 | 1 |
| ABC | 3 | 5 | 3 | 1 |

L’utilisateur revient alors le 1er avril, consulte cinq autres pages et effectue un achat. L&#39;expiration de 90 jours de cette première valeur d&#39;eVar est réinitialisée le 1er avril, vous voyez donc cela dans le rapports. La conversion est répercutée à toutes les activités Target que l’utilisateur voit, mais le nombre total de conversions est dédupliqué :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques | Commandes |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 3 |
| ABC | 1 | 10 | 2 | 1 | 3 |
| Total | 2 | 20 | 3 | 1 | 3 |

Les deux expériences ayant été vues avant la conversion, elles reçoivent toutes deux un &quot;crédit&quot; pour la commande. Toutefois, une seule commande a eu lieu dans le système, ce qui se reflète dans le total. Pour le rapports [!DNL Target], comme vous ne placez pas d’activité [!DNL Target] par rapport à une autre activité pour déterminer laquelle est la plus performante, il n’est pas important que toutes les activités que l’utilisateur a vues obtiennent du crédit. Vous comparez les résultats de deux éléments dans une seule activité. Il n’est pas possible pour un utilisateur d’afficher des expériences différentes dans la même activité, de sorte que vous n’ayez pas à vous inquiéter de la contamination croisée du crédit de commande.

Pour plus d’informations, voir [Variables de conversion (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) dans le *Guide d’administration Analytics*.

## Pourquoi est-ce que je continue à voir plus d’impressions après la désactivation de mon activité ? {#deactivated}

Le trafic en mode AQ peut être une source d’impressions pour un rapport activité A4T après la désactivation. En règle générale, la cible ne consigne pas les événements pour une activité désactivée, mais Analytics ne dispose pas d’un moyen de savoir si les impressions proviennent du mode AQ. Lorsque le rapport d’activité de Cible est récupéré à partir d’Analytics, il affiche ces impressions. Cela fonctionne comme prévu car les clients ont besoin d’un moyen de vérifier les rapports A4T même si l’activité n’est pas principale en utilisant le mode AQ.

## Pourquoi le calcul de la mesure Visiteurs uniques est-il différent dans Analytics et dans Analytics for Target (A4T) ?{#section_0C3B648AB54041F9A2AA839D51791883}

Lorsque vous exécutez un test A/B qui utilise le test en t de Student (la mesure du degré de confiance) pour choisir le gagnant d’un test, on suppose entre autres qu’une date de fin est définie. Le test n’est pas statistiquement valide si vous n’examinez pas cet échantillon de taille fixe.

La mesure [!UICONTROL Visiteurs uniques] est différente dans [!DNL Analytics] et [!DNL Target] uniquement lorsque vous observez une période plus courte que le test réel. Le test n’est pas fiable si la taille de l’échantillon n’est pas atteinte. Pour en savoir plus, voir la rubrique [Comment ne pas exécuter un test A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) (en anglais) sur le [site web d’Evan Miller](https://www.evanmiller.org/index.html).

La mesure [!UICONTROL Visiteurs uniques] affiche le nombre de personnes qui ont été exposées au test et qui ont visité le site pendant la période spécifiée. Ces personnes font partie du test et doivent être comptabilisées. Pour afficher uniquement le nombre de personnes qui ont été exposées au cours d’une seule semaine, vous pouvez créer un segment de visiteurs qui ont exécuté une impression de l’activité et l’ont appliquée au rapport.

Vous pouvez raccourcir la durée pendant laquelle la variable [!DNL Target] persiste jusqu’à une session ; toutefois, cela pose problème pour les tests où le événement de conversion n’est pas aussi susceptible de se produire au cours de la même session.

## Pourquoi le même visiteur est-il parfois comptabilisé dans plusieurs expériences dans Analytics ? {#section_1397E972D31C4207A142E4D2D6D794A2}

La liste suivante explique les raisons pour lesquelles le même visiteur peut être comptabilisé dans plusieurs expériences dans [!DNL Analytics]:

* Le profil [!DNL Target] a expiré mais le cookie [!DNL Analytics] est toujours présent. Dans ce cas, [!DNL Target] réévalue l’utilisateur, mais [!DNL Analytics] considère que le visiteur est la même personne.
* Si le visiteur utilise `mbox3rdPartyId`, lorsque le visiteur anonyme est fusionné avec le profil d’identification tiers, [!DNL Target] peut placer le visiteur dans une autre expérience pour correspondre à l’identifiant tiers. Pour plus d’informations, voir [Synchronisation de profil en temps réel pour mbox3 à identifiant tiers](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] peut suivre différents périphériques comme le même visiteur d&#39;une manière différente de celle qui  [!DNL Target] suit ces périphériques : la configuration des identifiants tiers dans  [!DNL Target] est différente de celle d’Analytics.

## A4T prend-il en charge les suites de rapports virtuelles ?

Les suites de rapports virtuelles *ne sont pas* incluses dans la liste des suites de rapports et les audiences des suites de rapports virtuelles ne sont pas prises en charge dans les rapports A4T.

## Puis-je modifier le pourcentage de l’affectation du trafic dans une activité qui utilise A4T après l’activation de l’activité ?

La modification du pourcentage d’affectation du trafic dans une activité après l’activation peut entraîner un rapports incohérent dans [!DNL Analytics], car cette modification n’a d’incidence que sur les nouveaux visiteurs. Les visiteurs récurrents ne sont pas affectés.

En règle générale, il est conseillé d’arrêter l’activité existante, puis de créer une nouvelle activité plutôt que de modifier le pourcentage après son activation. Le rapports des nouveaux débuts d&#39;activité avec de nouveaux visiteurs et les données des visiteurs de retour ne provoquent pas un rapports incohérent.

## Comment les visites sont-elles comptabilisées dans Analytics et le crédit de conversion alloués dans une activité de Cible automatique qui utilise A4T ?

Lorsqu’un visiteur est admissible, vue du contenu ou effectue une conversion dans une activité A4T, [!DNL Target] envoie des données de événement à [!DNL Analytics]. Ces données de événement permettent à [!DNL Analytics] d’attribuer des événements de conversion et d’autres événements de parcours de navigation se produisant sur la page aux activités et expériences [!DNL Target] pertinentes.

Voici quelques points à garder à l’esprit lors de l’affichage des rapports [!DNL Analytics] :

* En règle générale, il est recommandé que la fenêtre de votre rapports commence à partir de la date du début de l’activité.
* Si une conversion se produit en dehors de la fenêtre du rapport, elle n’est pas visible dans [!DNL Analytics].
* Dans la partie &quot;ciblée&quot; du trafic pour les activités [!UICONTROL Cible automatique], les visiteurs peuvent voir différentes expériences d’une session à l’autre. Par exemple, si leur profil ou leur contexte a changé et que les algorithmes d’apprentissage automatique de [!DNL Target] décident qu’ils sont plus susceptibles de convertir une nouvelle expérience. Lorsque les visiteurs passent d’une expérience à une autre, le nombre de visites augmente pour chaque expérience vue. Contrairement aux activités de test A/B standard où les expériences sont collées à un visiteur d’une visite à l’autre.
* Si un visiteur voit plusieurs expériences entre différentes visites, toute conversion est toujours attribuée à la dernière expérience vue par le visiteur. Comme mentionné, le nombre de visites est incrémenté pour chaque expérience vue par le visiteur. Cela peut diminuer artificiellement les taux de conversion par expérience lors de l’affichage d’expériences sous la dimension &quot;[!UICONTROL Ciblé]&quot; dans les rapports [!DNL Adobe Analytics].
