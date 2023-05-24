---
keywords: affectation automatisée du trafic;ciblage;gagnant;garantie statistique;confiance;déterminer gagnant;effet élévateur;confiance;défaut;expérience par défaut;affectation automatique;affectation automatique
description: Découvrez comment interpréter les résultats d’une activité A/B d’affectation automatique dans Adobe [!DNL Target] en examinant des indicateurs importants, notamment l’effet élévateur et la confiance.
title: Comment interpréter les rapports d’affectation automatique ?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 4564e0b95bbd19f20c75e5e83d452d12a5403083
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 44%

---

# Interprétation des rapports d’affectation automatique

Interprétation des résultats d’une [!UICONTROL Affectation automatique] Activité A/B dans [!UICONTROL Adobe Target] en examinant des indicateurs importants, notamment l’effet élévateur et la confiance.

La plupart des marketeurs ont tendance à déclarer de manière prématurée une expérience gagnante avant les résultats finaux. Désormais, il est plus facile de déterminer le gagnant.

>[!NOTE]
>
>Pour obtenir des informations générales sur la déclaration d’un gagnant, voir [Dix écueils courants des tests A/B et comment les éviter](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identification de l’expérience gagnante {#section_24007470CF5B4D30A06610CE8DD23CE3}

Lors de l’utilisation de la fonctionnalité [!UICONTROL Affectation automatique], [!DNL Target] affiche en haut de la page de l’activité un badge indiquant « Pas encore de gagnant » jusqu’à ce que l’activité atteigne le nombre de conversions minimal avec un degré de confiance suffisant.

![Badge Pas de gagnant](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

Lors de la déclaration d’un gagnant définitif, [!DNL Target] affiche la mention « Gagnant : expérience X. »

![image gagnante](assets/winner.png)

>[!NOTE]
>
>Les activités d’affectation automatique sont conçues pour identifier la meilleure expérience parmi toutes les options possibles, et pas uniquement pour effectuer des comparaisons par paires avec une expérience de contrôle.

## Garanties statistiques de l’affectation automatique {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

À la fin d’une activité A/B, l’affectation automatique garantit que le gagnant déterminé a un taux de faux positifs effectif de 5 %. Cela signifie que dans seulement 5 % des cas, le gagnant déterminé ne représente pas réellement la meilleure expérience parmi toutes les expériences de l’activité. En ce qui concerne les tests A/A (avec des expériences identiques), nous ne concluons le test que dans moins de 5 % des cas. Dans la mesure où un test A/A (avec des expériences identiques) est censé être exécuté indéfiniment, le badge Gagnant ne devrait jamais apparaître.

Nous n’utilisons pas un degré de confiance basé sur la valeur p pour l’affectation automatique.

La colonne Confiance dans une activité d’affectation automatique (illustrée ci-dessous) présente la probabilité qu’une expérience soit la gagnante avec une marge d’erreur de 1 % (l’algorithme utilise un effet détectable minimum de 1 % entre le meilleur et le deuxième meilleur taux de conversion). Pour calculer cette probabilité, l’algorithme applique l’[inégalité de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29).

Les tests A/B standard calculent le degré de confiance selon les valeurs-p, ce que ne fait pas l’affectation automatique. Les valeurs-p calculent « grossièrement » la probabilité qu’une expérience donnée diffère de l’expérience de contrôle. Elles peuvent seulement servir à déterminer si une expérience diffère de l’expérience de contrôle. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

>[!IMPORTANT]
>
>Target affiche un gagnant après un nombre minimum prédéfini de conversions ; cependant, la décision finale de choisir le gagnant doit toujours être prise sur les résultats de la [!DNL Adobe Target] Calculateur de taille d’échantillon. [!DNL Target] ne tient pas compte des taux de conversion de base d’un site et d’autres aspects importants qui sont pris en charge dans le calculateur pour déterminer la durée de l’activité. Par conséquent, Target peut afficher un gagnant plus tôt que garanti sur la base d’un nombre minimum de conversions. Pour plus d’informations, voir [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Présentation des rapports Effet élévateur et degré de confiance dans les activités d’affectation automatique {#lift-confidence}

Dans les activités d’affectation automatique, la première expérience (par défaut appelée Expérience A) est toujours définie comme une expérience de &quot;contrôle&quot; dans l’onglet Rapports . Cette expérience n’est pas traitée comme un véritable contrôle statistique dans la modélisation utilisée pour déterminer les performances des expériences, mais elle est traitée comme une référence ou une référence pour certains chiffres du rapport.

La valeur numérique &quot;Effet élévateur&quot; et les limites de 95 % pour chaque expérience sont toujours calculées en référence à l’expérience &quot;Contrôle&quot; définie. L’expérience &quot;de contrôle&quot; définie ne peut pas avoir d’effet élévateur par rapport à elle-même. Par conséquent, une valeur &quot;—&quot; vide est signalée pour cette expérience. Contrairement aux tests A/B, dans les tests d’affectation automatique, si les performances d’une expérience sont pires que celles du contrôle défini, aucune valeur d’effet élévateur négative n’est signalée ; &quot;—&quot; s’affiche à la place.

Les barres Intervalle de confiance affichées représentent l’intervalle de confiance de 95 % autour de l’estimation moyenne du taux de conversion d’une expérience. Elles sont également codées par couleur par rapport à l’expérience &quot;de contrôle&quot; définie. La barre de l’expérience &quot;Contrôle&quot; est toujours en gris. Les portions d’intervalles de confiance sous l’intervalle de confiance de l’expérience de &quot;contrôle&quot; sont de couleur rouge et les portions d’intervalles de confiance au-dessus de l’expérience de &quot;contrôle&quot; sont de couleur verte.

Un gagnant est trouvé lorsque l’intervalle de confiance de 95 % de l’expérience principale ne chevauche aucune autre expérience. L’expérience gagnante est désignée avec un badge d’étoile vert à gauche du nom de l’expérience et dans la bannière &quot;Gagnant&quot;. Lorsqu’aucune étoile n’est visible, la bannière indique &quot;Pas encore de gagnant&quot; et un gagnant n’a pas encore été trouvé.

Un nombre &quot;Degré de confiance&quot; est également reporté en regard de l’expérience gagnante ou de l’expérience gagnante actuelle. Ce chiffre est reporté uniquement jusqu’à ce que le degré de confiance de l’expérience principale atteigne au moins 60 %. Si exactement deux expériences sont présentes dans l’expérience d’affectation automatique, ce nombre représente le degré de confiance selon lequel l’expérience est plus performante que l’autre expérience. Si plus de deux expériences sont présentes dans l’expérience d’affectation automatique, ce nombre représente le degré de confiance selon lequel l’expérience est plus performante que l’expérience de &quot;contrôle&quot; définie. Si l’expérience &quot;Contrôle&quot; est gagnante, aucun chiffre &quot;Confiance&quot; n’est signalé.

## Questions fréquentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Tenez compte des réponses suivantes aux questions fréquentes :

### L’activité a commencé depuis quelques jours. Pourquoi le degré de confiance reste-t-il à 0 % ?

La colonne [!UICONTROL Confiance] peut rester à 0 % pour toutes les activités pour l’une des raisons suivantes :

* Les tests A/B manuels et l’affectation automatique utilisent différentes statistiques pour afficher les valeurs de confiance.

   Les tests A/B manuels utilisent des valeurs-p basées sur [Le test en t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Une valeur-p est la probabilité de trouver la différence observée (ou une plus extrême) entre une expérience et le contrôle, étant donné qu’en réalité, il n’y a pas de différence de ce type. Ces valeurs-p ne peuvent être utilisées que pour déterminer si les données observées sont cohérentes avec une expérience donnée et si le contrôle est le même. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

   L’affectation automatique présente la probabilité qu’une expérience donnée soit l’expérience gagnante par rapport à toutes les expériences de l’activité. Cela signifie que seule une expérience gagnante (dont la probabilité qu’il s’agisse de l’expérience gagnante est la plus élevée) aura une valeur de confiance non nulle. Toutes les autres expériences sont probablement des expériences perdantes, avec un taux de 0 %.

* L’affectation automatique commence à présenter un taux de confiance seulement quand l’expérience gagnante parvient à un taux de confiance de 60 %. Ces niveaux de confiance apparaissent généralement environ la moitié du temps nécessaire à l’exécution d’un test A/B normal (bien que cela ne soit pas garanti). Pour déterminer la durée d’exécution d’un test A/B, utilisez la variable [!DNL Adobe Target] [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): le taux de conversion du contrôle de la prise en charge dans &quot;Taux de conversion de ligne de base&quot;, &quot;5 %&quot; pour &quot;Effet élévateur&quot; et 95 % pour &quot;Degré de confiance&quot;. En règle générale, le degré de confiance apparaît quand chaque expérience a accumulé au moins 50 % des échantillons requis par expérience. Ainsi, vous savez à peu près quand le degré de confiance commencera à apparaître.

* Si le rapport présente globalement un taux de 0 %, cela signifie probablement que l’activité n’a pas encore suffisamment progressé.

### Les badges « Aucun gagnant », « Gagnant » et « étoile » sont-ils disponibles pour les activités dʼ[!UICONTROL Affectation automatique] qui utilisent [!UICONTROL Analytics comme source de création de rapports] (A4T) ?

Les badges &quot;Pas encore de gagnant&quot; et &quot;Gagnant&quot; ne sont actuellement pas disponibles dans la variable [!UICONTROL A4T] dans [!DNL Analysis Workspace]. Ces badges ne sont pas non plus disponibles si le même rapport est affiché dans [!DNL Target]. Badge &quot;étoile&quot; gagnante affiché dans une [!DNL Target] rapport pour un [!UICONTROL Affectation automatique] L’activité utilisant A4T doit être ignorée.

Pour plus d’informations à ce sujet et sur d’autres limitations et notes, voir [Affectation automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) in *Prise en charge d’A4T pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités*.


