---
keywords: affectation automatisée du trafic ; ciblage ; gagnant ; garantie statistique ; confiance ; déterminer gagnant ; effet élévateur ; confiance ; valeur par défaut ; expérience par défaut ; affectation automatique ; affectation automatique
description: Découvrez comment interpréter les résultats d’une activité A/B d’affectation automatique dans l’Adobe [!DNL Target] en examinant des indicateurs importants, notamment l’effet élévateur et la confiance.
title: Comment interpréter les rapports d’affectation automatique ?
feature: Affectation automatique
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 47%

---

# Interprétation des rapports d’affectation automatique

Interprétez les résultats d&#39;une activité [!UICONTROL Affectation automatique] A/B dans [!UICONTROL Adobe Target] en examinant des indicateurs importants, notamment l&#39;effet élévateur et la confiance.

La plupart des marketeurs ont tendance à déclarer de manière prématurée une expérience gagnante avant les résultats finaux. Désormais, il est plus facile de déterminer le gagnant.

>[!NOTE]
>
>Pour des informations générales sur la déclaration d’un gagnant, voir [Dix pièges de test A/B courants et comment les éviter](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identifier l’expérience gagnante {#section_24007470CF5B4D30A06610CE8DD23CE3}

Lors de l’utilisation de la fonctionnalité [!UICONTROL Affectation automatique], [!DNL Target] affiche en haut de la page de l’activité un badge indiquant « Pas encore de gagnant » jusqu’à ce que l’activité atteigne le nombre de conversions minimal avec un degré de confiance suffisant.

![Badge Pas de gagnant](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

Lors de la déclaration d’un gagnant définitif, [!DNL Target] affiche la mention « Gagnant : expérience X. »

![](assets/winner.png)

>[!NOTE]
>
>Les activités d’affectation automatique sont conçues pour identifier la meilleure expérience parmi toutes les options possibles, et pas uniquement pour effectuer des comparaisons par paires avec une expérience de contrôle.

## Garanties statistiques de l&#39;affectation automatique {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

À la fin d’une activité A/B, l’affectation automatique garantit que le gagnant déterminé a un taux de faux positifs effectif de 5 %. Cela signifie que dans seulement 5 % des cas, le gagnant déterminé ne représente pas réellement la meilleure expérience parmi toutes les expériences de l’activité. En ce qui concerne les tests A/A (avec des expériences identiques), nous ne concluons le test que dans moins de 5 % des cas. Dans la mesure où un test A/A (avec des expériences identiques) est censé être exécuté indéfiniment, le badge Gagnant ne devrait jamais apparaître.

Nous n’utilisons pas un degré de confiance basé sur la valeur p pour l’affectation automatique.

La colonne Confiance dans une activité d’affectation automatique (illustrée ci-dessous) présente la probabilité qu’une expérience soit la gagnante avec une marge d’erreur de 1 % (l’algorithme utilise un effet détectable minimum de 1 % entre le meilleur et le deuxième meilleur taux de conversion). Pour calculer cette probabilité, l’algorithme applique l’[inégalité de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)).

Les tests A/B standard calculent le degré de confiance selon les valeurs-p, ce que ne fait pas l’affectation automatique. Les valeurs-p calculent « grossièrement » la probabilité qu’une expérience donnée diffère de l’expérience de contrôle. Elles peuvent seulement servir à déterminer si une expérience diffère de l’expérience de contrôle. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

>[!IMPORTANT]
>
>Cible montre un gagnant après un nombre minimal prédéfini de conversions ; toutefois, la décision finale de choisir le gagnant doit toujours être prise sur les résultats du calculateur de taille d’échantillon [Adobe Target ](https://docs.adobe.com/content/target-microsite/testcalculator.html). La cible ne tient pas compte des taux de conversion de base d&#39;un site et d&#39;autres aspects importants qui sont insérés dans le calculateur pour déterminer la durée de l&#39;activité. En conséquence, la Cible peut afficher un gagnant plus tôt que garanti sur la base d’un nombre minimum de conversions. Pour plus d’informations, voir [Calculateur de taille d’échantillon](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Comprendre l’effet élévateur et le rapports de confiance dans les activités d’affectation automatique {#lift-confidence}

Dans les activités d’affectation automatique, la première expérience (par défaut nommée Expérience A) est toujours définie comme une expérience de contrôle dans l’onglet Rapports. Cette expérience n’est pas traitée comme un véritable contrôle statistique dans la modélisation utilisée pour déterminer les performances des expériences, mais elle est traitée comme une référence ou une référence pour certaines figures du rapport.

La valeur numérique &quot;Effet élévateur&quot; et les limites de 95 % pour chaque expérience sont toujours calculées en fonction de l’expérience de contrôle définie. L’expérience de contrôle définie ne peut pas avoir d’effet élévateur par rapport à elle-même. Par conséquent, une valeur &quot;—&quot; vide est reportée pour cette expérience. Contrairement aux tests A/B, dans les tests d’affectation automatique, si une expérience enregistre des performances pires que le contrôle défini, aucune valeur d’effet élévateur négative n’est signalée ; à la place, &quot;—&quot; s’affiche.

Les barres Intervalle de fiabilité affichées représentent l’intervalle de confiance de 95 % autour de l’estimation moyenne du taux de conversion d’une expérience. Elles sont également codées par couleur en fonction de l’expérience de contrôle définie. La barre de l’expérience &quot;Contrôle&quot; est toujours grise en couleur. Les portions d’intervalles de confiance au-dessous de l’intervalle de confiance de l’expérience de contrôle sont en rouge et les portions d’intervalles de confiance au-dessus de l’expérience de contrôle sont en vert.

Un gagnant est trouvé lorsque l’intervalle de confiance de 95 % de l’expérience principale ne chevauche aucune autre expérience. L’expérience gagnante est désignée avec un badge d’étoile verte à gauche du nom de l’expérience et dans la bannière &quot;Gagnant&quot;. Lorsqu’aucune étoile n’est visible, la bannière indique &quot;Pas encore de gagnant&quot; et un gagnant n’a pas encore été trouvé.

Un nombre de fiabilité est également signalé en regard de l’expérience gagnante ou de l’expérience de pointe. Ce chiffre n’est rapporté que jusqu’à ce que la fiabilité de l’expérience principale atteigne au moins 60 %. Si l’expérience d’affectation automatique comporte exactement deux expériences, ce nombre représente le niveau de confiance selon lequel l’expérience se comporte mieux que l’autre expérience. Si plus de deux expériences sont présentes dans l’expérience d’affectation automatique, ce nombre représente le niveau de confiance que l’expérience enregistre de meilleures performances que l’expérience de contrôle définie. Si l’expérience de contrôle est gagnante, aucun chiffre de confiance n’est signalé.

## Questions fréquentes {#section_C8E068512A93458D8C006760B1C0B6A2}

**L’activité a commencé depuis quelques jours. Pourquoi le degré de confiance reste-t-il à 0 % ?**

La colonne [!UICONTROL Confiance] peut rester à 0 % pour toutes les activités pour l’une des raisons suivantes :

* Les tests A/B manuels et l’affectation automatique utilisent différentes statistiques pour afficher les valeurs de confiance.

   Les tests A/B manuels utilisent des valeurs-p en fonction du [test en t de Student](https://en.wikipedia.org/wiki/Student%27s_t-test). Une valeur-p est la probabilité de trouver la différence observée (ou une plus extrême) entre une expérience et le contrôle, étant donné qu’en réalité, il n’y a pas de différence de ce type. Ces valeurs-p ne peuvent être utilisées que pour déterminer si les données observées sont cohérentes avec une expérience donnée et si le contrôle est le même. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

   L’affectation automatique présente la probabilité qu’une expérience donnée soit l’expérience gagnante par rapport à toutes les expériences de l’activité. Cela signifie que seule une expérience gagnante (dont la probabilité qu’il s’agisse de l’expérience gagnante est la plus élevée) aura une valeur de confiance non nulle. Toutes les autres expériences sont probablement des expériences perdantes, avec un taux de 0 %.

* L’affectation automatique commence à présenter un taux de confiance seulement quand l’expérience gagnante parvient à un taux de confiance de 60 %. Ces niveaux de confiance apparaissent généralement dans environ la moitié du temps nécessaire à l’exécution d’un test A/B normal (bien que cela ne soit pas garanti). Pour déterminer la durée d’exécution d’un test A/B normal, utilisez un [calculateur de taille d’échantillon](https://docs.adobe.com/content/target-microsite/testcalculator.html) : plug-control&#39;s conversion-rate in &quot;Baseline taux de conversion&quot;, &quot;5 %&quot; for &quot;Lift&quot; et 95 % for &quot;Confidence&quot;. En règle générale, le degré de confiance apparaît quand chaque expérience a accumulé au moins 50 % des échantillons requis par expérience. Ainsi, vous savez à peu près quand le degré de confiance commencera à apparaître.
* Si le rapport présente globalement un taux de 0 %, cela signifie probablement que l’activité n’a pas encore suffisamment progressé.
