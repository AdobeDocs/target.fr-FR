---
keywords: affectation automatisée du trafic;ciblage;gagnant;garantie statistique;confiance;déterminer gagnant;effet élévateur;confiance;défaut;expérience par défaut;affectation automatique;affectation automatique
description: Découvrez comment interpréter les résultats d’une [!UICONTROL Affectation automatique] Activité A/B dans Adobe [!DNL Target] en examinant des indicateurs importants, notamment l’effet élévateur et la confiance.
title: Comment interpréter [!UICONTROL Affectation automatique] Rapports ?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 29%

---

# Interprétation des rapports d’affectation automatique

Interprétation des résultats d’une [!UICONTROL Affectation automatique] Activité A/B dans [!UICONTROL Adobe Target] en examinant des indicateurs importants, notamment l’effet élévateur et la confiance.

La plupart des marketeurs ont tendance à déclarer de manière prématurée une expérience gagnante avant les résultats finaux. [!DNL Target] facilite la détermination du gagnant.

Pour obtenir des informations générales sur la déclaration d’un gagnant, voir [Dix écueils courants des tests A/B et comment les éviter](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identification de l’expérience gagnante {#section_24007470CF5B4D30A06610CE8DD23CE3}

Lors de l’utilisation de la fonctionnalité [!UICONTROL Affectation automatique], [!DNL Target] affiche en haut de la page de l’activité un badge indiquant « Pas encore de gagnant » jusqu’à ce que l’activité atteigne le nombre de conversions minimal avec un degré de confiance suffisant.

![Badge Pas de gagnant](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

Lorsqu’un gagnant définitif est déclaré, [!DNL Target] affiche &quot;Gagnant : expérience *X*.&quot;

![image gagnante](assets/winner.png)

>[!NOTE]
>
>Les activités d’affectation automatique sont conçues pour identifier la meilleure expérience parmi toutes les options possibles, et pas uniquement pour effectuer des comparaisons par paires avec une expérience de contrôle.

## Garanties statistiques de l’affectation automatique {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

À la fin d’une activité A/B, [!UICONTROL Affectation automatique] garantit que le gagnant déterminé a un taux de faux positifs effectif de 5 %. Cela signifie que dans seulement 5 % des cas, le gagnant déterminé ne représente pas réellement la meilleure expérience parmi toutes les expériences de l’activité. Pour un [Test A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (avec des expériences identiques), [!DNL Target] termine un test moins de 5 % du temps. Dans la mesure où un test A/A (avec des expériences identiques) est censé être exécuté indéfiniment, le badge Gagnant ne devrait jamais apparaître.

[!DNL Target] n’utilise pas de confiance basée sur la valeur p pour [!UICONTROL Affectation automatique].

La variable [!UICONTROL Confiance] dans une colonne [!UICONTROL Affectation automatique] activité (illustrée ci-dessous) affiche la probabilité qu’une expérience soit gagnante dans une marge d’erreur de 1 %. L’algorithme utilise un effet détectable minimal de 1 % entre les taux de conversion les plus élevés et les taux de conversion les moins élevés. L’algorithme utilise [L&#39;inégalité de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) pour calculer cette probabilité.

Les tests A/B standard calculent le degré de confiance selon les valeurs-p, [!UICONTROL ce que ne fait pas l’affectation automatique. ] Les valeurs-p calculent « grossièrement » la probabilité qu’une expérience donnée diffère de l’expérience de contrôle. Elles peuvent seulement servir à déterminer si une expérience diffère de l’expérience de contrôle. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

>[!IMPORTANT]
>
>[!DNL Target] affiche un gagnant après un nombre minimal prédéfini de conversions ; toutefois, la décision finale de choisir le gagnant doit toujours être prise sur les résultats de la [!DNL Adobe Target] Calculateur de taille d’échantillon. [!DNL Target] ne tient pas compte des taux de conversion de base d’un site et d’autres aspects importants qui sont pris en charge dans le calculateur pour déterminer la durée de l’activité. Par conséquent, [!DNL Target] peut afficher un gagnant antérieur à ce qui est justifié en fonction d’un nombre minimum de conversions. Pour plus d’informations, voir [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Présentation des rapports Effet élévateur et degré de confiance dans [!UICONTROL Affectation automatique] activités {#lift-confidence}

Dans [!UICONTROL Affectation automatique] , la première expérience (par défaut appelée Expérience A) est toujours définie comme une expérience &quot;de contrôle&quot; sur la variable [!UICONTROL Rapports] . Cette expérience n’est pas traitée comme un véritable contrôle statistique dans la modélisation utilisée pour déterminer les performances des expériences, mais elle est traitée comme une référence ou une référence pour certains chiffres du rapport.

La valeur numérique &quot;Effet élévateur&quot; et les limites de 95 % pour chaque expérience sont toujours calculées en référence à l’expérience &quot;Contrôle&quot; définie. L’expérience &quot;de contrôle&quot; définie ne peut pas avoir d’effet élévateur par rapport à elle-même. Par conséquent, une valeur &quot;—&quot; vide est signalée pour cette expérience. Contrairement aux tests A/B, dans [!UICONTROL Affectation automatique] Si une expérience est moins performante que le contrôle défini, une valeur d’effet élévateur négative n’est pas signalée ; &quot;—&quot; s’affiche à la place.

L’affichage [!UICONTROL Intervalle de confiance] Les barres représentent l’intervalle de confiance de 95 % autour de l’estimation moyenne du taux de conversion d’une expérience. Ces barres sont également codées par couleur en fonction de l’expérience de contrôle définie. La barre de l’expérience &quot;Contrôle&quot; est toujours en gris. Les portions d’intervalles de confiance sous l’intervalle de confiance de l’expérience de &quot;contrôle&quot; sont de couleur rouge et les portions d’intervalles de confiance au-dessus de l’expérience de &quot;contrôle&quot; sont de couleur verte.

Un gagnant est trouvé lorsque la valeur de 95 % de l’expérience principale [!UICONTROL Intervalle de confiance] ne chevauche aucune autre expérience. L’expérience gagnante est désignée avec un badge d’étoile vert à gauche du nom de l’expérience et dans la bannière &quot;Gagnant&quot;. Lorsqu’aucune étoile n’est visible, la bannière indique &quot;Pas encore de gagnant&quot; et un gagnant n’a pas encore été trouvé.

Un nombre &quot;Degré de confiance&quot; est également reporté en regard de l’expérience gagnante ou de l’expérience gagnante actuelle. Ce chiffre n’est reporté que jusqu’à ce que la variable [!UICONTROL Confiance] atteint au moins 60 %. Si deux expériences sont présentes dans la variable [!UICONTROL Affectation automatique] , ce nombre représente le degré de confiance selon lequel l’expérience est plus performante que l’autre expérience. Si plus de deux expériences sont présentes dans la variable [!UICONTROL Affectation automatique] , ce nombre représente le degré de confiance que l’expérience est plus performante que l’expérience &quot;de contrôle&quot; définie. Si l’expérience &quot;Contrôle&quot; est gagnante, aucun chiffre &quot;Confiance&quot; n’est signalé.

## Questions fréquentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Tenez compte des réponses suivantes aux questions fréquentes :

### L’activité a commencé depuis quelques jours. Pourquoi le degré de confiance reste-t-il à 0 % ?

La colonne [!UICONTROL Confiance] peut rester à 0 % pour toutes les activités pour l’une des raisons suivantes :

* Tests AB manuels et [!UICONTROL Affectation automatique] utiliser différentes statistiques pour afficher [!UICONTROL Confiance] valeurs.

  Les tests A/B manuels utilisent des valeurs-p basées sur [Le test en t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Une valeur-p est la probabilité de trouver la différence observée (ou une plus extrême) entre une expérience et le contrôle, étant donné qu’en réalité, il n’y a pas de différence de ce type. Ces valeurs-p ne peuvent être utilisées que pour déterminer si les données observées sont cohérentes avec une expérience donnée et si le contrôle est le même. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

  [!UICONTROL Affectation automatique] affiche la probabilité qu’une expérience donnée soit un véritable gagnant pour toutes les expériences de l’activité. Seule une expérience gagnante (qui est la plus susceptible d’être la gagnante) a une valeur de confiance non nulle. Tous les autres sont plus susceptibles d’être des perdants et d’afficher 0 %.

* [!UICONTROL L’affectation automatique commence à présenter un taux de confiance seulement quand l’expérience gagnante parvient à un taux de confiance de 60 %. ] Ces niveaux de confiance apparaissent généralement environ la moitié du temps nécessaire à l’exécution d’un test A/B normal (bien que cette période ne soit pas garantie). Pour déterminer la durée d’exécution d’un test A/B, utilisez la variable [!DNL Adobe Target] [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): entrez le taux de conversion du contrôle dans &quot;Taux de conversion de ligne de base&quot;, &quot;5 %&quot; pour &quot;Effet élévateur&quot; et 95 % pour &quot;Degré de confiance&quot;. En règle générale, le degré de confiance apparaît quand chaque expérience a accumulé au moins 50 % des échantillons requis par expérience. Cela vous donne une idée du moment où le degré de confiance commence à apparaître.

* Si le rapport présente globalement un taux de 0 %, cela signifie probablement que l’activité n’a pas encore suffisamment progressé.

### Les badges « Aucun gagnant », « Gagnant » et « étoile » sont-ils disponibles pour les activités dʼ[!UICONTROL Affectation automatique] qui utilisent [!UICONTROL Analytics comme source de création de rapports] (A4T) ?

Les badges &quot;Pas encore de gagnant&quot; et &quot;Gagnant&quot; ne sont actuellement pas disponibles dans la variable [!UICONTROL A4T] dans [!DNL Analysis Workspace]. Ces badges ne sont pas non plus disponibles si le même rapport est affiché dans [!DNL Target]. Badge &quot;étoile&quot; gagnante affiché dans une [!DNL Target] rapport pour un [!UICONTROL Affectation automatique] L’activité utilisant A4T doit être ignorée.

Pour plus d’informations à ce sujet et sur d’autres limitations et notes, voir [Affectation automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) in *Prise en charge d’A4T pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités*.


