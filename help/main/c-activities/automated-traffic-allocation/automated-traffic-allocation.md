---
keywords: affectation automatisée du trafic;ciblage;Incrémenter le décompte et maintenir l’utilisateur dans l’activité;affectation du trafic;affectation automatique;affectation automatique
description: Découvrez comment utiliser une activité de [!UICONTROL Auto-Allocate] dans  [!DNL Adobe Target]  qui identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement davantage de trafic au gagnant.
title: Qu’est-ce qu’une activité [!UICONTROL Auto-Allocate] ?
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 1b1b2271738d12f8da4e695900b70e280f50d8cf
workflow-type: tm+mt
source-wordcount: '3502'
ht-degree: 35%

---

# Vue d’ensemble des [!UICONTROL Auto-Allocate]

Une activité [!UICONTROL Auto-Allocate] dans [!DNL Adobe Target] identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement davantage de trafic au gagnant afin d’augmenter les conversions pendant que le test continue à s’exécuter et à apprendre.

Lors de la [création d’une activité A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) à l’aide du workflow guidé en trois étapes, choisissez l’option **[!UICONTROL Auto-Allocate to best experience]** sur la page **[!UICONTROL Targeting]** (étape 2).

## Le défi {#section_85D5A03637204BACA75E19646162ACFF}

Les tests A/B standard ont un coût. Vous devez générer du trafic pour mesurer les performances de chaque expérience et déterminer l’expérience gagnante grâce à une analyse. L’affectation du trafic reste fixe même après que vous avez admis que certaines expériences sont plus performantes que d’autres. En outre, il est difficile de déterminer la taille de l’échantillon. L’activité doit également s’exécuter en entier avant que vous ne puissiez agir sur un gagnant. Et il y a encore une chance que le gagnant identifié ne soit pas un vrai gagnant.

## La solution : [!UICONTROL Auto-Allocate] {#section_98388996F0584E15BF3A99C57EEB7629}

Une activité [!UICONTROL Auto-Allocate] réduit ce coût et la surcharge liée à la définition d’une expérience gagnante. [!UICONTROL Auto-Allocate] surveille les performances de la mesure d’objectif de toutes les expériences et envoie proportionnellement plus de nouveaux entrants vers les expériences hautement performantes. Suffisamment de trafic est réservé à l’exploration des autres expériences. Vous pouvez constater les avantages du test sur vos résultats, même si l’activité est toujours en cours d’exécution : l’optimisation se produit en parallèle de l’apprentissage.

[!UICONTROL Auto-Allocate] oriente progressivement les visiteurs vers des expériences gagnantes au lieu d’attendre la fin d’une activité pour déterminer une expérience gagnante. Vous bénéficiez de l’effet élévateur plus rapidement, car les participants à l’activité qui auraient été envoyés vers des expériences moins performantes sont dirigés vers des expériences potentiellement gagnantes.

Un test A/B normal en [!DNL Target] montre seulement des comparaisons par paires de challengers avec le contrôle. Par exemple, si une activité possède des expériences : A, B, C et D où A est le contrôle, un test A/B [!DNL Target] normal comparera A par rapport à B, A par rapport à C et A par rapport à D.

Dans de tels tests, la plupart des produits, y compris les [!DNL Target], utilisent un [test t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} pour produire un degré de confiance basé sur la valeur de p. Cette valeur de confiance sert ensuite à déterminer si l’expérience concurrente est suffisamment différente de l’expérience de contrôle. Cependant, [!DNL Target] n’effectue pas automatiquement les comparaisons implicites (B par rapport à C, B par rapport à D et C par rapport à D) qui sont requises pour trouver la « meilleure » expérience. Le marketeur doit dès lors analyser les résultats manuellement pour déterminer la « meilleure » expérience.

[!UICONTROL Auto-Allocate] effectue toutes les comparaisons implicites entre les expériences et produit un gagnant « vrai ». La notion d’expérience de « contrôle » disparaît donc totalement du test.

[!UICONTROL Auto-Allocate] affecte intelligemment de nouveaux visiteurs aux expériences jusqu’à ce que l’intervalle de confiance de la meilleure expérience ne chevauche celui d’aucune autre expérience. Normalement, ce processus peut produire des faux positifs, mais [!UICONTROL Auto-Allocate] utilise des intervalles de confiance basés sur l’[inégalité de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank} qui compense les évaluations répétées. À ce stade, il y a un véritable gagnant. Lorsque [!UICONTROL Auto-Allocate] s’arrête, à condition qu’il n’y ait aucune dépendance temporelle substantielle aux visiteurs qui arrivent sur la page, il y a au moins 95 % de chances que [!UICONTROL Auto-Allocate] renvoie une expérience dont la réponse réelle n’est pas inférieure de moins de 1 % (relatif) à la réponse réelle de l’expérience gagnante.

## Quand utiliser [!UICONTROL Auto-Allocate] par rapport aux activités [!UICONTROL A/B Test] ou [!UICONTROL Automated Personalization] {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Utilisez **[!UICONTROL Auto-Allocate]** lorsque vous souhaitez optimiser votre activité depuis le début et identifier les expériences gagnantes le plus rapidement possible. En diffusant plus souvent des expériences hautement performantes, les performances globales de l’activité augmentent.
* Utilisez un test A/B standard **[A/B Test](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** lorsque vous souhaitez caractériser les performances de toutes les expériences avant d’optimiser votre site. Un test A/B vous aide à classer toutes vos expériences, tandis que [!UICONTROL Auto-Allocate] trouve les meilleures performances, mais ne garantit pas la différenciation entre les moins performantes.
* Utilisez [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) lorsque vous souhaitez des algorithmes d’optimisation de la plus haute complexité, tels que des modèles de machine learning qui créent des prédictions en fonction d’attributs de profil individuels. [!UICONTROL Auto-Allocate] examine le comportement agrégé des expériences (tout comme les tests A/B standard) et ne fait pas de distinction entre les visiteurs.

## Principaux avantages de la [!UICONTROL Auto-Allocate] {#section_0913BF06F73C4794862561388BBDDFF0}

* Préserve la rigueur d’un test A/B
* Identifie un gagnant statistiquement significatif plus rapidement qu’un test A/B manuel
* Fournit un effet élévateur de campagne moyen plus élevé qu’un test A/B manuel

## Terminologie  {#section_670F8785BA894745B43B6D4BFF953188}

Les termes suivants sont utiles pour aborder le [!UICONTROL Auto-Allocate] :

**Bandit à plusieurs bras :** une approche du type [bandit à plusieurs bras](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage.

## Fonctionnement de l’algorithme {#section_ADB69A1C7352462D98849F2918D4FF7B}

La logique globale derrière [!UICONTROL Auto-Allocate] intègre à la fois les performances mesurées (comme le taux de conversion) et les intervalles de confiance des données cumulées. Contrairement à un test A/B standard où le trafic est réparti équitablement entre les expériences, [!UICONTROL Auto-Allocate] modifie l’affectation du trafic entre les expériences.

* 80 % des visiteurs sont affectés à l’aide de la logique intelligente décrite ci-dessous.
* 20 % des visiteurs sont affectés de manière aléatoire à toutes les expériences afin de s’adapter aux changements de comportement des visiteurs.

L’approche du bandit à plusieurs bras permet à certaines expériences d’être explorées tandis que les expériences performantes sont exploitées. Davantage de nouveaux visiteurs sont dirigés vers des expériences aux meilleures performances tout en préservant la possibilité de réagir aux conditions changeantes. Ces modèles sont mis à jour au moins une fois par heure pour garantir que le modèle réagit aux dernières données.

Alors que davantage de visiteurs participent à l’activité, certaines expériences commencent à augmenter leurs performances et plus de trafic est envoyé vers les expériences performantes. 20 % du trafic reste réparti de manière aléatoire pour explorer toutes les expériences. Si l’une des expériences moins performantes commence à augmenter ses performances, plus de trafic est affecté à cette expérience. Si une activité hautement performante diminue ses performances, moins de trafic est affecté à cette expérience. Par exemple, si un événement pousse les visiteurs à rechercher d’autres informations sur votre site multimédia ou des ventes de week-end sur votre site de vente au détail, vous obtiendrez des résultats différents.

L’illustration suivante représente les performances possibles de l’algorithme au cours d’un test avec quatre expériences (cliquez pour développer l’illustration) :

![affectation automatique d’image](assets/auto-allocate.png){width="600" zoomable="yes"}

L’illustration montre l’évolution du trafic affecté à chaque expérience sur plusieurs tours pendant la durée de vie de l’activité, jusqu’à ce que l’expérience gagnante puisse être déterminée.

| Arrondi | Description |
|--- |--- |
| ![Tour de chauffe](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **Tour de chauffe (0)** : au cours du tour de chauffe, chaque expérience reçoit une affectation égale du trafic jusqu’à ce que chaque expérience de l’activité atteigne un minimum de 1 000 visiteurs et 50 conversions.<ul><li>Expérience A = 25 %</li><li>Expérience B = 25 %</li><li>Expérience C = 25 %</li><li>Expérience D = 25 %</li></ul>Une fois que chaque expérience reçoit 1 000 visiteurs et 50 conversions, [!DNL Target] démarre l’affectation automatisée du trafic. Toutes les affectations se produisent par tour ; deux expériences sont sélectionnées pour chaque tour.<br>Seules deux expériences passent à l’étape suivante : D et C.<br>En allant de l’avant, les deux expériences se voient attribuer 80 % du trafic de manière égale. Les deux autres expériences continuent à participer, mais ne sont diffusées que dans le cadre de l’affectation aléatoire de 20 % du trafic au fur et à mesure que de nouveaux visiteurs entrent dans l’activité.<br>Toutes les affectations sont mises à jour toutes les heures (indiqué par les tours sur l’axe X ci-dessus). Après chaque tour, les données cumulées sont comparées. |
| ![1er tour](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **1er tour** : durant ce tour, 80 % du trafic est affecté aux expériences C et D (40 % chacune). 20 % du trafic est affecté de manière aléatoire aux expériences A, B, C et D (5 % à chaque expérience). Au cours de ce tour, l’expérience A enregistre de bonnes performances.<ul><li>L’algorithme sélectionne l’expérience D pour passer à la ronde suivante, car elle présente le taux de conversion le plus élevé (comme indiqué par l’échelle verticale de chaque activité).</li><li>L’algorithme sélectionne également l’expérience A pour progresser, puisqu’elle présente la limite supérieure la plus élevée de l’intervalle de confiance de 95 % de Bernstein pour les expériences restantes.</li></ul>Les expériences D et A passent au tour suivant. |
| ![2e tour](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **2e tour** : durant ce tour, 80 % du trafic est affecté aux expériences A et D (40 % chacune). 20 % du trafic est affecté de manière aléatoire, ce qui signifie que les expériences A, B, C et D récupèrent chacune 5 % du trafic. Au cours de ce tour, l’expérience B enregistre de bonnes performances.<ul><li>L’algorithme sélectionne l’expérience D pour passer à la ronde suivante, car elle présente le taux de conversion le plus élevé (comme indiqué par l’échelle verticale de chaque activité).</li><li>L’algorithme sélectionne également l’expérience B pour progresser, puisqu’elle présente la limite supérieure la plus élevée de l’intervalle de confiance de 95 % de Bernstein pour les expériences restantes.</li></ul>Les expériences D et B passent au tour suivant. |
| ![3e tour](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **3e tour** : durant ce tour, 80 % du trafic est affecté aux expériences B et D (40 % chacune). 20 % du trafic est affecté de manière aléatoire, ce qui signifie que les expériences A, B, C et D récupèrent chacune 5 % du trafic. Au cours de ce tour, l’expérience D continue d’enregistrer de bonnes performances, de même que l’expérience C.<ul><li>L’algorithme sélectionne l’expérience D pour passer à la ronde suivante, car elle présente le taux de conversion le plus élevé (comme indiqué par l’échelle verticale de chaque activité).</li><li>L’algorithme sélectionne également l’expérience C pour progresser, puisqu’elle présente la limite supérieure la plus élevée de l’intervalle de confiance de 95 % de Bernstein pour les expériences restantes.</li></ul>Les expériences D et C passent au tour suivant. |
| ![4e tour](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **4e tour** : durant ce tour, 80 % du trafic est affecté aux expériences C et D (40 % chacune). 20 % du trafic est affecté de manière aléatoire, ce qui signifie que les expériences A, B, C et D récupèrent chacune 5 % du trafic. Au cours de ce tour, l’expérience C enregistre de bonnes performances.<ul><li>L’algorithme sélectionne l’expérience C pour passer à la ronde suivante, car elle présente le taux de conversion le plus élevé (comme indiqué par l’échelle verticale de chaque activité).</li><li>L’algorithme sélectionne également l’expérience D pour progresser, puisqu’elle présente la limite supérieure la plus élevée de l’intervalle de confiance de 95 % de Bernstein pour les expériences restantes.</li></ul>Les expériences C et D passent au tour suivant. |
| ![Tour n](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **Round *n*** : Au fur et à mesure que l’activité progresse, une expérience hautement performante commence à émerger et le processus se poursuit jusqu’à ce qu’il y ait une expérience gagnante. Lorsque l’intervalle de confiance de l’expérience présentant le taux de conversion le plus élevé ne chevauche celui d’aucune autre expérience, il est considéré comme le gagnant. Un [badge) s&#39;affiche sur la page de l&#39;activité gagnante](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) ainsi que dans la liste des [!UICONTROL Activity].<ul><li>L’algorithme désigne l’expérience C comme gagnante définitive.</li></ul>À ce stade, l’algorithme distribue 80 % du trafic à l’expérience C, tandis que 20 % du trafic continue à être distribué de manière aléatoire à toutes les expériences (A, B, C et D). Au total, l’expérience C récupère 85 % du trafic. Dans le cas improbable où l’intervalle de confiance du gagnant recommence à chevaucher un autre intervalle, l’algorithme restaure le comportement du tour 4 ci-dessus.<P>**Important** : si vous avez choisi manuellement un gagnant plus tôt dans le processus, il aurait été facile de choisir la mauvaise expérience. C’est pourquoi il est recommandé d’attendre que l’algorithme détermine l’expérience gagnante. |

>[!NOTE]
>
>Si une activité ne comporte que deux expériences, les deux expériences obtiennent un trafic égal jusqu’à ce que [!DNL Target] trouve une expérience gagnante avec un degré de confiance de 75 %. À ce stade, les deux tiers du trafic sont attribués au gagnant et un tiers au perdant. Ensuite, lorsqu’une expérience atteint un degré de confiance de 95 %, 90 % du trafic est alloué au gagnant et 10 % au perdant. [!DNL Target] envoie toujours du trafic vers l’expérience « perdue » pour éviter les faux positifs à la fin (c’est-à-dire conserver une partie de l’exploration).

Une fois qu’une activité [!UICONTROL Auto-Allocate] est activée, les opérations suivantes ne sont pas autorisées à partir de l’interface utilisateur Tar[!DNL]get :

* Basculer le mode d’« Affectation du trafic » en « Manuel »
* Modifier le type de mesure d’objectif
* Modification des options dans le panneau « [!UICONTROL Advanced Settings] »

## Voir comment fonctionne l’affectation automatique

Pour plus d’informations, voir [ L’affectation automatique peut vous donner des résultats de test plus rapides et un chiffre d’affaires plus élevé qu’un test manuel](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md).

## Avertissements {#section_5C83F89F85C14FD181930AA420435E1D}

Tenez compte des informations suivantes lorsque vous utilisez [!UICONTROL Auto-Allocate] :

### La fonctionnalité [!UICONTROL Auto-Allocate] fonctionne avec un seul paramètre de mesure avancé : [!UICONTROL Increment Count and Keep User in Activity]

Les paramètres de mesure avancés suivants ne sont pas pris en charge : [!UICONTROL Increment Count], [!UICONTROL Release User], [!UICONTROL Allow Reentry and Increment Count] et [!UICONTROL Release User and Bar from Reentry].

### Les visiteurs réguliers peuvent gonfler les taux de conversion de l’expérience.

Si un visiteur qui visualise l’expérience A revient fréquemment et effectue plusieurs conversions, le taux de conversion de l’expérience A augmente artificiellement. Comparez ce résultat à l’expérience B, où les visiteurs effectuent une conversion, mais ne reviennent pas souvent. Par conséquent, le CR de l’expérience A semble meilleur que le CR de l’expérience B, de sorte que les nouveaux visiteurs sont plus susceptibles d’être affectés à A qu’à B. Si vous choisissez de compter une fois par participant, les CR de A et CR de B peuvent être identiques.

Si les visiteurs récurrents sont distribués de manière aléatoire, leur effet sur les taux de conversion sera a priori nivelé. Pour atténuer cet effet, vous pouvez changer la méthode de comptabilisation de la mesure d’objectif pour ne compter qu’une fois par participant.

### Différencie les utilisateurs hautement performants des utilisateurs peu performants.

[!UICONTROL Auto-Allocate] est capable de différencier les expériences hautement performantes (et de trouver un gagnant). Il peut arriver que la différenciation des expériences les moins performantes soit insuffisante.

Si vous souhaitez produire une différenciation statistiquement significative entre toutes les expériences, vous pouvez envisager d’utiliser le mode d’affectation manuelle du trafic.

### Les taux de conversion corrélés au temps (ou variables selon le contexte) peuvent fausser les montants alloués.

Certains facteurs qui peuvent être ignorés lors d’un test A/B standard, car ils affectent toutes les expériences de la même manière, ne peuvent pas être ignorés dans une activité [!UICONTROL Auto-Allocate]. L&#39;algorithme est sensible aux taux de conversion observés.

Vous trouverez ci-dessous des exemples de facteurs qui peuvent affecter les performances des expériences de manière inégale :

* Expériences présentant une pertinence contextuelle variable (heure, lieu, sexe, etc.).

  Par exemple :

   * « Dieu merci, c&#39;est vendredi » entraîne des conversions plus élevées le vendredi.
   * « Démarrez votre lundi » a une conversion plus élevée le lundi.
   * « Préparez-vous pour un hiver sur la côte Est » offre une conversion plus élevée dans les endroits de la côte Est ou touchés par l&#39;hiver.

  L’utilisation d’expériences avec une pertinence contextuelle variable peut fausser les résultats d’un test [!UICONTROL Auto-Allocate] plus que d’un test A/B, car le test A/B analyse les résultats sur une plus longue période.

* Expériences avec des délais variables de conversion (probablement à cause de l’urgence du message).

  Par exemple, « Derniers jours des soldes à -30 % » signale au visiteur d’effectuer une conversion aujourd’hui, tandis que « 50 % sur votre premier achat » n’engendre pas le même sentiment d’urgence.

## Questions fréquentes  {#section_0E72C1D72DE74F589F965D4B1763E5C3}

Consultez les FAQ et les réponses suivantes lorsque vous effectuez des activités [!UICONTROL Auto-Allocate] :

### [!UICONTROL Analytics for Target] (A4T) prend-il en charge les activités [!UICONTROL Auto-Allocate] ?

Oui. Pour plus d’informations, consultez Prise en charge d’[ A4T pour les activités d’affectation automatique et de ciblage automatique ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

### Les visiteurs récurrents sont-ils automatiquement réaffectés à des expériences hautement performantes ?

Non. Seuls les nouveaux visiteurs sont affectés automatiquement. Les visiteurs récurrents continuent de voir leur expérience originale pour protéger la validité du test A/B.

### Comment l’algorithme traite-t-il les faux positifs ?

L’algorithme garantit un degré de confiance de 95 % ou un taux de faux positifs de 5 % si vous patientez jusqu’à l’apparition du badge Gagnant.

### Quand commence [!UICONTROL Auto-Allocate] allouer le trafic ?

L’algorithme commence à fonctionner quand toutes les expériences de l’activité atteignent un minimum de 1 000 visiteurs et 50 conversions.

### Comment l’algorithme exploite-t-il de manière agressive ?

80 % du trafic est diffusé à l’aide de [!UICONTROL Auto-Allocate] et 20 % du trafic est diffusé de manière aléatoire. Lorsqu’un gagnant a été identifié, 80 % du trafic y est envoyé, tandis que toutes les expériences continuent à recevoir du trafic dans le cadre des 20 %, y compris l’expérience gagnante.

### Les expériences perdues s’affichent-elles ?

Oui. Le bandit à plusieurs bras s’assure qu’au moins 20 % du trafic est réservé à l’exploration des taux de conversion ou des modèles changeants sur l’ensemble des expériences.

### Qu’advient-il des activités qui présentent de longs délais de conversion ?

Tant que toutes les expériences en cours d’optimisation font face à des délais similaires, le comportement est identique à celui d’une activité avec un cycle de conversion plus rapide. Cependant, il faut plus de temps pour atteindre le seuil de conversion de 50 avant que le processus d’affectation du trafic ne commence.

### En quoi est-[!UICONTROL Auto-Allocate] différent de [!UICONTROL Automated Personalization] ?

[!UICONTROL Automated Personalization] utilise les attributs de profil de chaque visiteur pour déterminer la meilleure expérience. Ce faisant, l’activité est optimisée, mais également personnalisée en fonction de cet utilisateur.

[!UICONTROL Auto-Allocate], en revanche, est un test A/B qui produit un gagnant agrégé (l’expérience la plus populaire, mais pas nécessairement l’expérience la plus efficace pour chaque visiteur).

### Les visiteurs récurrents gonflent-ils le taux de conversion de ma mesure de succès ?

Actuellement, la logique favorise les visiteurs qui convertissent rapidement leur expérience ou la visitent plus souvent, car ces visiteurs gonflent temporairement le taux de conversion global de l’expérience à laquelle ils appartiennent. L’algorithme s’ajuste fréquemment, de sorte que l’augmentation du taux de conversion est amplifiée à chaque instantané. Si le site reçoit de nombreux visiteurs et visiteuses récurrents, leurs conversions peuvent potentiellement gonfler le taux de conversion global de l’expérience à laquelle ils appartiennent. Il y a de bonnes chances que les visiteurs récurrents soient distribués de manière aléatoire, auquel cas l’effet global (effet élévateur augmenté) est équilibré. Pour atténuer cet effet, vous pouvez changer la méthode de comptabilisation de la mesure de succès pour ne compter qu’une fois par participant.

### Puis-je utiliser le calculateur de taille d’échantillon lorsque j’utilise [!UICONTROL Auto-Allocate] pour estimer la durée nécessaire à l’activité pour identifier le gagnant ?

Vous pouvez utiliser le [!DNL Adobe Target] existant [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) pour obtenir une estimation de la durée d’exécution du test. (Comme pour les tests A/B traditionnels, appliquez la correction Bonferroni si vous testez plus de deux offres ou plus d’une mesure de conversion/hypothèse.) Ce calculateur est conçu pour les tests A/B traditionnels à horizon fixe et fournit une estimation uniquement. L’utilisation du calculateur pour une activité [!UICONTROL Auto-Allocate] est facultative, car [!UICONTROL Auto-Allocate] déclare une activité gagnante pour vous. Il n’est pas nécessaire de choisir un moment précis pour consulter les résultats du test. Les valeurs fournies sont toujours statistiquement valides.

Les expériences de [!DNL Adobe] interne ont permis de trouver les éléments suivants :

* Lorsque vous testez exactement deux expériences, [!UICONTROL Auto-Allocate] trouve un gagnant plus rapidement que les tests à horizon fixe (c’est-à-dire la période suggérée par le calculateur de taille d’échantillon) lorsque la différence de performance entre les expériences est importante. Cependant, [!UICONTROL Auto-Allocate] pouvez avoir besoin de temps supplémentaire pour identifier un gagnant lorsque la différence de performance entre les expériences est faible. Dans ces cas, les tests à horizon fixe se seraient généralement terminés sans résultat statistiquement significatif.
* Lorsque vous testez plus de deux expériences, [!UICONTROL Auto-Allocate] trouve une expérience gagnante plus rapidement que les tests à horizon fixe (c’est-à-dire la période suggérée par le calculateur de taille d’échantillon) lorsqu’une seule expérience dépasse considérablement toutes les autres expériences. Lorsque plusieurs expériences « gagnent » toutes les deux par rapport à d’autres, mais qu’elles sont étroitement liées, [!UICONTROL Auto-Allocate] peut nécessiter un délai supplémentaire pour déterminer laquelle est supérieure. Dans ces cas, les tests à horizon fixe se seraient généralement terminés par la conclusion que les expériences « gagnantes » étaient meilleures que les expériences moins performantes, mais n’auraient pas permis d’identifier laquelle était supérieure.

### Dois-je supprimer une expérience sous-performante d’une activité [!UICONTROL Auto-Allocate] pour accélérer le processus de détermination d’un gagnant ?

Il n’y a aucune raison de supprimer une expérience peu performante. [!UICONTROL Auto-Allocate] diffuse automatiquement plus souvent des expériences hautement performantes et moins souvent des expériences sous-performantes. Le fait de laisser une expérience sous-performante dans l’activité n’a pas d’incidence significative sur la vitesse à laquelle déterminer un gagnant.

20 % des visiteurs sont affectés de manière aléatoire à toutes les expériences. Le volume de trafic diffusé vers une expérience peu performante est minimal (20 % divisé par le nombre d’expériences).

### Puis-je modifier la mesure d’objectif au cours d’une activité [!UICONTROL Auto-Allocate] ? {#change-metric}

[!DNL Adobe] ne recommande pas de modifier la mesure d’objectif au cours d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. [!DNL Adobe] ne garantit pas ce qui se produit si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

### Puis-je modifier la source de création de rapports au cours d’une activité [!UICONTROL Auto-Allocate] ? {#change-reporting}

[!DNL Adobe] ne recommande pas de modifier la source de création de rapports au cours d’une activité. Bien qu’il soit possible de modifier la source de création de rapports (de [!DNL Target] à A4T ou inversement) au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. [!DNL Adobe] ne garantit pas ce qui se produit si vous modifiez la source de création de rapports dans une activité après son exécution.

Cette recommandation s’applique aux activités [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

### Puis-je utiliser l’option [!UICONTROL Reset Report Data] lors de l’exécution d’une activité [!UICONTROL Auto-Allocate] ?

Il n’est pas recommandé d’utiliser l’option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Auto-Allocate]. Bien qu’elle supprime les données de rapports visibles, cette option ne supprime pas tous les enregistrements d’identification du modèle de [!UICONTROL Auto-Allocate]. Au lieu d’utiliser l’option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Auto-Allocate], créez une activité et désactivez l’activité d’origine. (Ces conseils s’appliquent également aux activités de [!UICONTROL Auto-Target] et de [!UICONTROL Automated Personalization].)

### Comment crée-[!UICONTROL Auto-Allocate] des modèles en ce qui concerne les environnements ?

[!UICONTROL Auto-Allocate] crée des modèles en fonction du trafic et du comportement de conversion enregistrés dans l’environnement par défaut uniquement. Par défaut, [!UICONTROL Production] est l’environnement par défaut, mais cet environnement peut être modifié dans [!DNL Target] ([Administration > Environnements](/help/main/administrating-target/environments.md)).

Si un accès se produit dans un autre environnement (autre que l’environnement par défaut), le trafic est distribué en fonction du comportement de conversion observé dans l’environnement par défaut. Le résultat de cet accès (conversion ou non-conversion) est enregistré à des fins de création de rapports, mais n’est pas pris en compte dans le modèle de [!UICONTROL Auto-Allocate].

Lors de la sélection d’un autre environnement, le rapport affiche le trafic et les conversions pour cet environnement. L’environnement sélectionné par défaut pour un rapport est l’environnement par défaut sélectionné à l’échelle du compte. L’environnement par défaut ne peut pas être défini sur une base par activité.

### Une activité [!UICONTROL Auto-Allocate] peut-elle ajuster l’intervalle de recherche en amont au cours d’un test pour prendre en compte les modifications de tendances au fil du temps ?

Par exemple, l’activité peut-elle prendre en compte le mois de décembre pour décider comment allouer le trafic, plutôt que d’examiner les données des visiteurs de septembre (lorsque le test a commencé) ?

Non, [!UICONTROL Auto-Allocate] prend en compte les performances de l’ensemble de l’activité.

### Une expérience gagnante est-[!UICONTROL Auto-Allocate] présentée à un visiteur récurrent si l’expérience gagnante est différente de ce que le visiteur a vu lors de la qualification pour l’activité ?

[!UICONTROL Auto-Allocate] utilise sticky decisioning pour les mêmes raisons que les activités [!UICONTROL A/B Test]. L’affectation du trafic fonctionne uniquement pour les nouveaux visiteurs.

## Vidéos de formation {#section_893E5B36DC4A415C9B1D287F51FCCB83}

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Workflow d’activité - Ciblage (2:14) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comprend des informations sur la configuration de l’affectation du trafic.

* Affecter une audience à votre activité
* Augmenter ou ralentir le trafic
* Sélectionner votre méthode d’affectation du trafic
* Affecter du trafic entre différentes expériences

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### Création de tests A/B (8:36) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment créer un test A/B à l’aide du processus assisté en trois étapes de Target. [!UICONTROL Auto-Allocate] discussion commence à 4:45.

* Création d’une activité A/B dans [!DNL Adobe Target]
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/17391)
