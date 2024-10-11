---
keywords: affectation automatisée du trafic;ciblage;gagnant;garantie statistique;confiance;déterminer gagnant;effet élévateur;confiance;défaut;expérience par défaut;affectation automatique;affectation automatique
description: Découvrez comment interpréter les résultats des activités A/B [!UICONTROL Auto-Allocate], en se concentrant sur des indicateurs clés tels que l’effet élévateur et le degré de confiance.
title: Comment interpréter les rapports [!UICONTROL Auto-Allocate] ?
feature: Auto-Allocate
hide: true
hidefromtoc: true
source-git-commit: 5fc18c6d3b493ea0a58048cc20ce3a6c2ffb7d14
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 20%

---

# Interprétation des rapports [!UICONTROL Auto-Allocate]

Interprétez les résultats d’une activité A/B [!UICONTROL Auto-Allocate] dans [!UICONTROL Adobe Target] en examinant des indicateurs importants, notamment l’effet élévateur et le degré de confiance.

La plupart des marketeurs ont tendance à déclarer de manière prématurée une expérience gagnante avant les résultats finaux. [!DNL Target] facilite la détermination du gagnant.

Pour obtenir des informations générales sur la déclaration d’un gagnant, voir [Dix écueils courants des tests A/B et comment les éviter](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identification de l’expérience gagnante {#section_24007470CF5B4D30A06610CE8DD23CE3}

Lors de l’utilisation de la fonction [!UICONTROL Auto-Allocate], [!DNL Target] affiche en haut de la page de l’activité un badge indiquant &quot;Pas encore de gagnant&quot; jusqu’à ce que l’activité atteigne le nombre minimal de conversions avec un degré de confiance suffisant.

![Badge Pas de gagnant](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

Lorsqu’un gagnant définitif est déclaré, [!DNL Target] affiche le badge &quot;Gagnant : expérience *X*&quot;.

![Badge du gagnant](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

>[!NOTE]
>
>Les activités [!UICONTROL Auto-Allocate] sont conçues pour trouver la meilleure expérience parmi toutes les options et pas uniquement pour effectuer des comparaisons par paires avec une expérience de contrôle.

## Garanties statistiques de [!UICONTROL Auto-Allocate] {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

À la fin d’une activité A/B, [!UICONTROL Auto-Allocate] garantit que le gagnant déterminé a un taux de faux positifs effectif de 5 %. Cela signifie que dans seulement 5 % des cas, le gagnant déterminé ne représente pas réellement la meilleure expérience parmi toutes les expériences de l’activité. Pour un [test A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (avec des expériences identiques), [!DNL Target] termine un test moins de 5 % du temps. Dans la mesure où un test A/A (avec des expériences identiques) est censé être exécuté indéfiniment, le badge Gagnant ne devrait jamais apparaître.

[!DNL Target] n’utilise pas de confiance basée sur la valeur p pour [!UICONTROL Auto-Allocate].

La colonne [!UICONTROL Confidence] d’une activité [!UICONTROL Auto-Allocate] affiche la probabilité qu’une expérience soit gagnante dans une marge d’erreur de 1 %. L’algorithme utilise un effet détectable minimal de 1 % entre les taux de conversion les plus élevés et les taux de conversion les moins élevés. L’algorithme utilise [Inégalité de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) pour calculer cette probabilité.

Les tests A/B standard calculent le degré de confiance selon les valeurs-p, [!UICONTROL Auto-Allocate] n’utilise pas de valeurs-p. Les valeurs-p calculent « grossièrement » la probabilité qu’une expérience donnée diffère de l’expérience de contrôle. Elles peuvent seulement servir à déterminer si une expérience diffère de l’expérience de contrôle. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

>[!IMPORTANT]
>
>[!DNL Target] montre un gagnant après un nombre minimal prédéfini de conversions. Toutefois, la décision finale de choisir le gagnant doit toujours être prise sur les résultats du calculateur de taille d’échantillon [!DNL Adobe Target]. [!DNL Target] ne prend pas en compte les taux de conversion de base d’un site et d’autres aspects importants qui sont alimentés dans le calculateur pour déterminer la durée de l’activité. Par conséquent, [!DNL Target] peut afficher un gagnant antérieur au montant justifié en fonction d’un nombre minimum de conversions. Pour plus d’informations, voir [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Présentation des rapports Effet élévateur et Degré de confiance dans les activités [!UICONTROL Auto-Allocate] {#lift-confidence}

Dans les activités [!UICONTROL Auto-Allocate], la première expérience (par défaut nommée Expérience A) est toujours définie comme une expérience &quot;de contrôle&quot; sur l’onglet [!UICONTROL Reports]. Cette expérience n’est pas traitée comme un véritable contrôle statistique dans la modélisation utilisée pour déterminer les performances des expériences, mais elle est traitée comme une référence ou une référence pour certains chiffres du rapport.

La valeur numérique &quot;Effet élévateur&quot; et les limites de 95 % pour chaque expérience sont toujours calculées en référence à l’expérience &quot;Contrôle&quot; définie. L’expérience &quot;de contrôle&quot; définie ne peut pas avoir d’effet élévateur par rapport à elle-même. Par conséquent, une valeur &quot;—&quot; vide est signalée pour cette expérience. Contrairement aux tests A/B, dans les tests [!UICONTROL Auto-Allocate], si une expérience est plus performante que le contrôle défini, une valeur d’effet élévateur négative n’est pas signalée ; à la place, &quot;—&quot; s’affiche.

Les [!UICONTROL Confidence Interval] barres affichées représentent l’intervalle de confiance de 95 % autour de l’estimation moyenne du taux de conversion d’une expérience. Ces barres sont également codées par couleur en fonction de l’expérience de contrôle définie. La barre de l’expérience &quot;Contrôle&quot; est toujours en gris. Les portions d’intervalles de confiance sous l’intervalle de confiance de l’expérience de &quot;contrôle&quot; sont de couleur rouge et les portions d’intervalles de confiance au-dessus de l’expérience de &quot;contrôle&quot; sont de couleur verte.

Un gagnant est trouvé lorsque les 95 % [!UICONTROL Confidence Interval] de l’expérience principale ne chevauchent aucune autre expérience. L’expérience gagnante est désignée avec un badge d’étoile vert à gauche du nom de l’expérience et dans la bannière &quot;Gagnant&quot;. Lorsqu’aucune étoile n’est visible, la bannière indique &quot;Pas encore de gagnant&quot; et un gagnant n’a pas encore été trouvé.

Un nombre &quot;Degré de confiance&quot; est également reporté en regard de l’expérience gagnante ou de l’expérience gagnante actuelle. Ce chiffre est reporté uniquement jusqu’à ce que l’ [!UICONTROL Confidence] de l’expérience principale atteigne au moins 60 %. Si deux expériences sont présentes dans l’activité [!UICONTROL Auto-Allocate], ce nombre représente le degré de confiance selon lequel l’expérience est plus performante que l’autre expérience. Si plus de deux expériences sont présentes dans l’activité [!UICONTROL Auto-Allocate], ce nombre représente le degré de confiance selon lequel l’expérience est plus performante que l’expérience &quot;de contrôle&quot; définie. Si l’expérience &quot;Contrôle&quot; est gagnante, aucun chiffre &quot;Confiance&quot; n’est signalé.

## Questions fréquentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Tenez compte des réponses suivantes aux questions fréquentes :

### L’activité a commencé il y a quelques jours. Pourquoi toutes les valeurs de confiance affichent-elles toujours 0 % ?

L’une des raisons suivantes explique pourquoi 0 % s’affiche dans la colonne [!UICONTROL Confidence] du rapport pour toutes les activités :

* Les tests A/B manuels et [!UICONTROL Auto-Allocate] utilisent des statistiques différentes pour afficher les valeurs [!UICONTROL Confidence].

  Les tests A/B manuels utilisent des valeurs-p basées sur le [test-t Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Une valeur-p est la probabilité de trouver la différence observée (ou une plus extrême) entre une expérience et le contrôle, étant donné qu’en réalité, il n’y a pas de différence de ce type. Ces valeurs-p ne peuvent être utilisées que pour déterminer si les données observées sont cohérentes avec une expérience donnée et si le contrôle est le même. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

  [!UICONTROL Auto-Allocate] indique la probabilité qu’une expérience donnée soit un véritable gagnant pour toutes les expériences de l’activité. Seule une expérience gagnante (qui est la plus susceptible d’être la gagnante) a une valeur de confiance non nulle. Tous les autres sont plus susceptibles d’être des perdants et d’afficher 0 %.

* [!UICONTROL Auto-Allocate] commence à afficher le degré de confiance uniquement une fois que l’expérience gagnante a réuni un degré de confiance de 60 %. Ces niveaux de confiance apparaissent généralement environ la moitié du temps nécessaire à l’exécution d’un test A/B normal (bien que cette période ne soit pas garantie). Pour déterminer la durée d’exécution d’un test A/B, utilisez le [!DNL Adobe Target] [calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) : entrez le taux de conversion du contrôle dans &quot;Taux de conversion de ligne de base&quot;, &quot;5 %&quot; pour &quot;Effet élévateur&quot; et 95 % pour &quot;Degré de confiance&quot;. En règle générale, le degré de confiance apparaît quand chaque expérience a accumulé au moins 50 % des échantillons requis par expérience. Cela vous donne une idée du moment où le degré de confiance commence à apparaître.

* Si le rapport présente globalement un taux de 0 %, cela signifie probablement que l’activité n’a pas encore suffisamment progressé.

### Les badges &quot;Aucun gagnant&quot;, &quot;Gagnant&quot; et &quot;étoile&quot; sont-ils disponibles pour les activités [!UICONTROL Auto-Allocate] qui utilisent [!UICONTROL Analytics as the reporting source] (A4T) ?

Les badges &quot;Pas encore de gagnant&quot; et &quot;Gagnant&quot; ne sont actuellement pas disponibles dans le panneau [!UICONTROL A4T] de [!DNL Analysis Workspace]. Ces badges ne sont pas non plus disponibles si le même rapport est affiché dans [!DNL Target]. Un badge &quot;étoile&quot; gagnant affiché dans un rapport [!DNL Target] pour une activité [!UICONTROL Auto-Allocate] utilisant A4T doit être ignoré.

Pour plus d’informations à ce sujet et sur d’autres limitations et notes, voir [Affectation automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) dans la *Prise en charge d’A4T pour [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] activités*.