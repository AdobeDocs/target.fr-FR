---
keywords: faq;questions fréquentes;analytics pour target;a4T;rapport;rapports;afficher des rapports;création de rapports;méthodologie de calcul;impressions;visiteurs;visites;mesure par défaut;conversions des activités;non spécifié
description: Trouver des réponses aux questions fréquentes sur l’affichage de rapports lors de l’utilisation d’Analytics pour [!DNL Target] (A4T). A4T vous permet d’utiliser les rapports Analytics pour [!DNL Target] activités.
title: Trouvez des réponses aux questions sur l’affichage des rapports avec A4T ?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 66c662e367b64ca51c5d9246cb097a12755d9aff
workflow-type: tm+mt
source-wordcount: '2551'
ht-degree: 33%

---

# FAQ sur l’affichage des rapports - A4T

Cette rubrique contient des réponses aux questions fréquentes sur l’affichage de rapports lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Puis-je afficher mon [!DNL Target] données d’activité dans Analysis Workspace ? {#workspace}

Vous pouvez utiliser [!DNL Analysis Workspace] pour analyser votre [!DNL Target] activités et expériences. Le [Panneau Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=fr) vous permet d’afficher l’effet élévateur et le degré de confiance pour trois mesures de succès au maximum. Vous pouvez également approfondir l’analyse à l’aide de tableaux et de visualisations.

Pour obtenir des informations détaillées et des exemples, ouvrez le [Analytics et Target : Tutoriel sur les bonnes pratiques relatives à l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par Adobe Experience League.

## Où les segments peuvent-ils être appliqués dans Analysis Workspace ? {#segmentation}

Les segments sont le plus souvent utilisés en haut d’un panneau dans la zone de dépôt des segments. Le segment est appliqué à tous les tableaux et visualisations du panneau. Cette technique est particulièrement utile pour voir comment le test affecte un sous-ensemble de personnes (par exemple, comment ce test a-t-il été effectué pour les personnes au Royaume-Uni) ?

Un segment peut également être superposé directement dans le tableau à structure libre, mais vous devez le superposer sur l’ensemble du tableau pour conserver les calculs de l’effet élévateur et du degré de confiance dans le panneau A4T. Les segments au niveau des colonnes ne sont actuellement pas pris en charge dans le panneau.

## Lorsque j’applique un segment d’accès pour une [!DNL Target] activité, pourquoi des expériences sans rapport sont-elles renvoyées ? {#activity-segmentation}

La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. (Remarque : cette période d’expiration peut être ajustée par l’assistance clientèle si nécessaire). Lorsque les visiteurs naviguent sur le site tout au long de cette fenêtre d’expiration, ils font partie de nombreux [!DNL Target] les activités, qui sont toutes regroupées dans la dimension .

Lorsque vous segmentez pour qu’une activité soit présente dans un accès, vous obtenez toutes les expériences qui font partie de cette activité. *plus* toutes les autres expériences qui persistent sur cet accès.

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux paramètres avancés ?

Pour les activités utilisant [!DNL Analytics] en tant que source des rapports (A4T), la mesure d’objectif utilise le paramètre &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité]&quot; et &quot;[!UICONTROL À chaque impression]&quot;. Ces paramètres sont les suivants : *not* configurable.

Pour plus d’informations, voir &quot;Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ?&quot; in [FAQ sur les définitions de mesures - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Dois-je utiliser les visiteurs, les visites ou les impressions d’activité comme mesure de normalisation (c.-à-d. méthodologie de comptage) ? {#metrics}

Il existe plusieurs options de normalisation des mesures dans les rapports A4T. Cette mesure, également appelée méthodologie de calcul, devient le dénominateur du calcul de l’effet élévateur. Elle affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance.

* ***Visiteurs uniques*** : augmente une fois qu’un utilisateur est admissible pour une activité pour la première fois.
* ***Visites*** : augmente à chaque session une fois qu’un utilisateur (visiteur unique) entre dans une activité, même s’il ne la consulte pas lors de ses visites ultérieures.
* ***Impressions d’activité*** : augmente à chaque fois que le contenu de l’activité est présenté. (Mesuré par [!DNL Target]).

Lorsqu’un visiteur visualise une page contenant une activité, une variable contenant le nom de cette activité est définie pour ce visiteur. Consultez les scénarios détaillés ci-après pour une comparaison entre les différentes méthodologies de calcul.

Tenez compte des points suivants :

* Les mesures ci-dessus se déclenchent lorsqu’un utilisateur est admissible pour une activité et que le contenu est renvoyé à partir de [!DNL Target]. Cela ne signifie pas pour autant que l’utilisateur a forcément vu l’offre. Si l’activité de l’expérience se trouve en bas de page et que l’utilisateur ne fait pas entièrement défiler celle-ci, l’offre est bien diffusée par [!DNL Target], mais l’utilisateur ne la voit pas.
* Le nombre d’[!UICONTROL impressions d’activité] (mesurées par [!DNL Target]) et d’[!UICONTROL instances] (mesurées par [!DNL Analytics]) est égal, sauf dans le cas de plusieurs appels de mbox sur une même page, dans une même activité. Cela entraîne le comptage de plusieurs [!UICONTROL impressions d’activité], mais d’une seule [!UICONTROL instance].

Pour plus d’informations, voir [Configuration des rapports A4T dans Analysis Workspace pour les activités de ciblage automatique](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Tutorials Adobe Target*.

## Pourquoi les &quot;impressions d’activité&quot; et les &quot;conversions d’activité&quot; sont-elles plus élevées dans Analysis Workspace que dans Reports &amp; Analytics ? {#sametouch}

[!DNL Reports & Analytics] applique un modèle d’attribution de même touche aux &quot;impressions de l’activité&quot; et aux &quot;conversions de l’activité&quot;, tandis que [!DNL Analysis Workspace] affiche les mesures brutes, qui peuvent sembler exagérées en raison de la persistance de la variable [!DNL Target] dimension.

Pour évaluer la précision [!UICONTROL Impressions d’activité] et [!UICONTROL Conversions des activités] mesures dans [!DNL Analysis Workspace], assurez-vous que les deux mesures ont [!UICONTROL Même touche] modèles d’attribution appliqués. Pour appliquer des modèles, cliquez sur l’engrenage des paramètres de colonne, activez [!UICONTROL Modèle d’attribution autre que celui par défaut], puis sélectionnez [!UICONTROL Même touche. ] En savoir plus sur l’attribution dans [Présentation d’Attributs IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) dans le *Guide sur les outils Analytics*.

## Que signifie « conversions de l’activité » si le marketeur choisit une mesure Analytics lors de la configuration de l’activité ? {#section_F3EBACF85AF846E9B366A549AAB64356}

Les &quot;conversions de l’activité&quot; sont vides si une [!DNL Analytics] a été sélectionnée comme mesure de conversion pour l’activité.

## Pourquoi la mention « non spécifié » s’affiche-t-elle dans les rapports Analytics ? Qu’est-ce que cela signifie ? {#unspecified}

Dans d’autres rapports, la mention « non spécifié » indique que les données ne respectent pas une règle de classification, mais cela ne devrait jamais se produire dans A4T. Si la mention « non spécifié » s’affiche, cela signifie que le service de classification ne s’est pas encore exécuté. Les données des activités prennent généralement de 24 à 72 heures pour apparaître dans les rapports. Même si les activités n’apparaissent pas dans ce rapport avant ce moment, toutes les données de visiteur liées à ces activités sont capturées et apparaissent une fois la classification terminée.

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Si une classification a été effectuée pour cette activité et que vous voyez toujours une ligne &quot;Non spécifié&quot; dans le rapport, assurez-vous que le rapport n’utilise pas une variable[!DNL Target] pour afficher les données. À moins que le rapport n’utilise une [!DNL Target]Mesure spécifique, cette ligne &quot;Non spécifié&quot; contient des événements pour les appels qui ne sont pas associés à [!DNL Target]. Cette ligne ne contient aucune [!DNL Target]-informations associées (par exemple, visiteurs/visites/impressions).

## Pourquoi [!DNL Target] mesures envoyées à Analytics même après la désactivation de l’activité ? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

La variable [!DNL Target] envoyée à [!DNL Analytics] dispose d’une période d’expiration de 90 jours par défaut. Si nécessaire, cette période d’expiration peut être ajustée par l’assistance clientèle. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

Vous pouvez voir [!DNL Target] variables envoyées à [!DNL Analytics] après la période d’expiration, car l’expiration est de 90 jours, mais seulement si cet utilisateur ne voit jamais d’autre A4T activé [!DNL Target] activité. Si un utilisateur revient sur le site au 45 e jour et voit une autre activité, le compteur de la valeur entière de l’eVar A4T est réinitialisé à 90 jours. En d’autres termes, la première campagne à partir du jour 1 pourrait persister pendant 45 + 90 = 135 jours au maximum. Si l’utilisateur continue de revenir, vous pouvez atteindre le point où les mesures sont envoyées à [!DNL Analytics] dans vos rapports à partir d’activités beaucoup plus anciennes. Lorsque les utilisateurs suppriment les cookies et ne reviennent pas sur le site, les chiffres de cette activité diminuent, mais vous pouvez toujours les voir.

Cela signifie que les activités continuent d’obtenir des pages vues, des visites, etc., pendant 90 jours jusqu’à la fin de l’activité pour les visiteurs qui sont devenus membres de l’activité lorsqu’elle était principale. Toutefois, si vous examinez la mesure [!UICONTROL Impressions d’activité], vous ne devriez voir aucune impression après la fin de l’activité.

Il s’agit d’un comportement normal et attendu. La variable A4T fonctionne comme n’importe quelle autre eVar - la valeur est associée à l’utilisateur jusqu’à ce qu’elle expire (90 jours). Par conséquent, si une activité est principale pendant seulement deux semaines, la valeur est toujours associée à l’utilisateur pendant au moins les 90 jours suivants.

Il est recommandé d’afficher les rapports pour cette activité seulement pendant la période pendant laquelle l’activité était active. Les dates doivent être correctement définies par défaut lorsque vous affichez l’activité dans [!DNL Analytics], donc, sauf si vous avez manuellement prolongé la date, cela ne devrait pas poser de problème du point de vue de la création de rapports.

Par exemple, supposons que la variable A4T expire après 90 jours et que le test est principal du 1er au 15 janvier.

Le 1er janvier, l’utilisateur consulte le site et voit l’activité XYZ une fois, puis cinq pages ensuite. Au cours des deux semaines suivantes, l’utilisateur ne revient pas sur le site. Pour cet utilisateur, les données ressembleraient à ceci :

| Nom de l’activité | Instances (Impressions) | Pages vues | Visites | Visiteurs uniques |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

L’utilisateur revient le 1er février, consulte cinq autres pages et ne rencontre plus d’activités Target ; l’activité d’origine n’est plus principale. Même si l’activité n’est plus active, l’utilisateur continue à être suivi par le biais de la persistance des eVars. Les données ressemblent maintenant à ce qui suit :

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

Comme les deux expériences étaient visibles avant la conversion, elles reçoivent toutes deux le &quot;crédit&quot; de la commande. Toutefois, une seule commande a eu lieu dans le système, ce qui se reflète dans le total. Pour [!DNL Target] création de rapports, car vous ne placez pas de [!DNL Target] activité par rapport à une autre activité pour voir laquelle est la plus réussie, peu importe que toutes les activités que l’utilisateur a vues reçoivent du crédit. Vous comparez les résultats de deux éléments dans une seule activité. Il n’est pas possible pour un utilisateur de voir des expériences différentes dans la même activité, de sorte que vous n’ayez pas à vous soucier de la contamination croisée du crédit de commande.

Pour plus d’informations, voir [Variables de conversion (eVar)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) dans la variable *Guide d’administration Analytics*.

## Pourquoi est-ce que je continue à voir des impressions après la désactivation de mon activité ? {#deactivated}

Une source d’impressions pour le rapport d’une activité A4T après la désactivation peut être le trafic en mode AQ. Target ne consigne normalement pas les événements pour une activité désactivée, mais Analytics ne dispose pas d’un moyen de savoir que les impressions proviennent du mode AQ. Lorsque le rapport d’activité Target est récupéré à partir d’Analytics, il affiche ces impressions. Cela fonctionne comme prévu car les clients ont besoin d’un moyen de vérifier les rapports A4T même si l’activité n’est pas principale à l’aide du mode AQ.

## Pourquoi le calcul de la mesure Visiteurs uniques est-il différent dans Analytics et Analytics pour Adobe Target (A4T) ? {#section_0C3B648AB54041F9A2AA839D51791883}

Lorsque vous exécutez un test A/B, qui utilise la variable [Le test en t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (la mesure de confiance) pour choisir un gagnant d’un test. L’une des hypothèses est qu’il existe un horizon temporel fixe. Le test n’est pas statistiquement valide, sauf si vous observez cette taille d’échantillon fixe.

Le [!UICONTROL Visiteurs uniques] est différente dans [!DNL Analytics] et [!DNL Target] uniquement lorsque vous observez une période plus courte que le test réel. Si vous n’avez pas atteint votre taille d’échantillon, le test n’est pas aussi fiable. Pour en savoir plus, voir la rubrique [Comment ne pas exécuter un test A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) (en anglais) sur le [site web d’Evan Miller](https://www.evanmiller.org/index.html).

Le [!UICONTROL Visiteurs uniques] mesure affiche le nombre de personnes qui ont été exposées au test et qui ont visité le site au cours d’une période donnée. Ces personnes font partie du test et doivent être comptabilisées. Pour afficher uniquement le nombre de personnes qui ont été exposées au cours d’une seule semaine, vous pouvez créer un segment de visiteurs qui ont exécuté une impression de l’activité et l’ont appliquée au rapport.

Vous pouvez raccourcir la durée de la variable [!DNL Target] persiste jusqu’à une session ; toutefois, cela pose problème pour les tests où l’événement de conversion n’est pas aussi susceptible de se produire au cours de la même session.

## Pourquoi le même visiteur est-il parfois comptabilisé dans plusieurs expériences dans Analytics ? {#section_1397E972D31C4207A142E4D2D6D794A2}

La liste suivante explique les raisons pour lesquelles le même visiteur peut être comptabilisé dans plusieurs expériences dans [!DNL Analytics]:

* Le [!DNL Target] le profil a expiré, mais [!DNL Analytics] le cookie est toujours là. Dans ce cas, [!DNL Target] réévalue l’utilisateur, mais [!DNL Analytics] considère le visiteur comme la même personne.
* Si le visiteur utilise la variable `mbox3rdPartyId`, lorsque le visiteur anonyme est fusionné avec le profil d’identifiant tiers, [!DNL Target] peut mettre le visiteur dans une autre expérience pour établir une correspondance avec l’ID tiers. Pour plus d’informations, voir [Synchronisation de profil en temps réel pour mbox3 à identifiant tiers](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] peut suivre différents appareils comme le même visiteur d’une manière différente que [!DNL Target] effectue le suivi de ces périphériques : Configuration des identifiants tiers dans [!DNL Target] est différent de dans Analytics.

## A4T prend-il en charge les suites de rapports virtuelles ? {#virtual}

Bien que les suites de rapports virtuelles ne soient pas incluses dans la variable [!UICONTROL Suite de rapports] liste, toutes les données A4T partagées avec une suite de rapports liée à une suite de rapports virtuelle dans [!DNL Analytics] a accès à ces données. Notez que toute audience créée à partir d’une suite de rapports virtuelle ne peut pas être repartagée avec [!DNL Target].

## Puis-je modifier le pourcentage de l’affectation du trafic dans une activité qui utilise A4T après l’activation de l’activité ?

La modification du pourcentage d’affectation du trafic dans une activité après l’activation peut entraîner des rapports incohérents dans [!DNL Analytics] car la modification n’affecte que les nouveaux visiteurs. Les visiteurs récurrents ne sont pas affectés.

En règle générale, il est conseillé d’arrêter l’activité existante, puis de créer une nouvelle activité plutôt que de modifier le pourcentage après son activation. La création de rapports pour la nouvelle activité commence par les nouveaux visiteurs et les données des visiteurs récurrents ne provoquent pas de rapports incohérents.

## Comment les visites sont-elles comptabilisées dans Analytics et le crédit de conversion attribué dans une activité de ciblage automatique qui utilise A4T ?

Lorsqu’un visiteur est admissible pour, consulte le contenu ou effectue une conversion dans une activité A4T, [!DNL Target] envoie des données d’événement à [!DNL Analytics]. Ces données d’événement permettent [!DNL Analytics] pour attribuer les événements de conversion et d’autres événements de parcours de navigation se produisant sur la page aux événements appropriés. [!DNL Target] activités et expériences.

Voici quelques points à garder à l’esprit lors de l’affichage [!DNL Analytics] rapports :

* En règle générale, la fenêtre de création de rapports doit commencer à partir de la date de début de l’activité.
* Si une conversion se produit en dehors de la fenêtre du rapport, elle n’est pas visible dans [!DNL Analytics].
* Dans la partie &quot;ciblée&quot; du trafic pour [!UICONTROL Ciblage automatique] activités, les visiteurs peuvent voir différentes expériences d’une session à l’autre. Par exemple, si leur profil ou leur contexte a changé et [!DNL Target]Les algorithmes d’apprentissage automatique de décident qu’ils sont plus susceptibles de se convertir sur une nouvelle expérience. À mesure que les visiteurs passent d’une expérience à l’autre, le nombre de visites est incrémenté pour chaque expérience vue. Contrairement aux activités de test A/B standard où les expériences sont persistantes pour un visiteur entre plusieurs visites.
* Si un visiteur voit plusieurs expériences au cours de plusieurs visites, toute conversion est toujours attribuée à la dernière expérience vue par le visiteur. Comme mentionné, le nombre de visites est incrémenté pour chaque expérience vue par le visiteur. Cela peut diminuer artificiellement les taux de conversion par expérience lors de l’affichage d’expériences sous le[!UICONTROL Ciblés]&quot; dans [!DNL Adobe Analytics] rapports.
