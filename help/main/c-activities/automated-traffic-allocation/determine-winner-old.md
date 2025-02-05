---
keywords: affectation automatisée du trafic;ciblage;gagnant;garantie statistique;confiance;déterminer le gagnant;effet élévateur;confiance;par défaut;expérience par défaut;affectation automatique;affectation automatique
description: Découvrez comment interpréter les résultats d’une activité A/B [!UICONTROL Auto-Allocate] dans l’Adobe  [!DNL Target] en examinant des indicateurs importants, notamment l’effet élévateur et le degré de confiance.
title: Comment Interpréter [!UICONTROL Auto-Allocate] Rapports ?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 21%

---

# Interprétation des rapports d’affectation automatique

Interpréter les résultats d’une activité A/B [!UICONTROL Auto-Allocate] dans [!UICONTROL Adobe Target] en examinant des indicateurs importants, y compris l’effet élévateur et le degré de confiance.

La plupart des marketeurs ont tendance à déclarer de manière prématurée une expérience gagnante avant les résultats finaux. [!DNL Target] vous permet de déterminer plus facilement le gagnant.

Pour obtenir des informations générales sur la manière de désigner un gagnant, consultez [ Dix pièges courants des tests A/B et comment les éviter ](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identifier l’expérience gagnante {#section_24007470CF5B4D30A06610CE8DD23CE3}

Lors de l’utilisation de la fonctionnalité [!UICONTROL Auto-Allocate], [!DNL Target] affiche un badge en haut de la page de l’activité indiquant « Aucun gagnant pour le moment » jusqu’à ce que l’activité atteigne le nombre minimum de conversions avec un degré de confiance suffisant.

![Badge Pas de gagnant](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

Lorsqu’un gagnant définitif est déclaré, [!DNL Target] affiche « Gagnant : expérience *X* ».

![image gagnante](assets/winner.png)

>[!NOTE]
>
>Les activités d’affectation automatique sont conçues pour identifier la meilleure expérience parmi toutes les options possibles, et pas uniquement pour effectuer des comparaisons par paires avec une expérience de contrôle.

## Garanties statistiques de l’affectation automatique {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

À la fin d&#39;une activité A/B, [!UICONTROL Auto-Allocate] garantit que le gagnant déterminé a un taux effectif de faux positifs de 5%. Cela signifie que dans seulement 5 % des cas, le gagnant déterminé ne représente pas réellement la meilleure expérience parmi toutes les expériences de l’activité. Pour un test [A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (avec des expériences identiques), [!DNL Target] termine un test moins de 5 % du temps. Dans la mesure où un test A/A (avec des expériences identiques) est censé être exécuté indéfiniment, le badge Gagnant ne devrait jamais apparaître.

[!DNL Target] n’utilise pas le degré de confiance basé sur la valeur de p pour les [!UICONTROL Auto-Allocate].

La colonne [!UICONTROL Confidence] d’une activité de [!UICONTROL Auto-Allocate] (illustrée ci-dessous) affiche la probabilité qu’une expérience soit gagnante avec une marge d’erreur de 1 %. L&#39;algorithme utilise un effet détectable minimum de 1% entre les meilleurs et les meilleurs taux de conversion secondaires. L’algorithme utilise [Inégalité de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) pour calculer cette probabilité.

Les tests A/B standard calculent le degré de confiance selon les valeurs-p, [!UICONTROL Auto-Allocate] n’utilise pas les p-values. Les valeurs-p calculent « grossièrement » la probabilité qu’une expérience donnée diffère de l’expérience de contrôle. Elles peuvent seulement servir à déterminer si une expérience diffère de l’expérience de contrôle. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

>[!IMPORTANT]
>
>[!DNL Target] indique un gagnant après un nombre minimum prédéfini de conversions ; cependant, la décision finale de choisir le gagnant doit toujours se baser sur les résultats du [!DNL Adobe Target] Calculateur de taille d’échantillon. [!DNL Target] ne prend pas en compte les taux de conversion de base d’un site ni d’autres aspects importants intégrés au calculateur pour déterminer la durée de l’activité. Par conséquent, [!DNL Target] pouvez afficher un gagnant plus tôt que prévu en fonction d’un nombre minimum de conversions. Pour plus d’informations, voir [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Comprendre les rapports d’effet élévateur et de confiance dans les activités [!UICONTROL Auto-Allocate] {#lift-confidence}

Dans les activités [!UICONTROL Auto-Allocate], la première expérience (par défaut appelée Expérience A) est toujours définie comme une expérience « Contrôle » sur l’onglet [!UICONTROL Reports] . Cette expérience n’est pas traitée comme un véritable contrôle statistique dans la modélisation utilisée pour déterminer la performance des expériences, mais elle est traitée comme une référence ou une référence pour certains chiffres du rapport.

La valeur numérique « Lift » et les limites de 95 % de chaque expérience sont toujours calculées par référence à l’expérience « Contrôle » définie. L’expérience « Contrôle » définie ne peut pas avoir d’effet élévateur par rapport à elle-même. Une valeur « — » vide est donc signalée pour cette expérience. Contrairement aux tests A/B, dans les tests [!UICONTROL Auto-Allocate], si une expérience s’avère moins performante que le contrôle défini, aucune valeur négative de Lift n’est signalée ; à la place, « — » s’affiche.

Les barres de [!UICONTROL Confidence Interval] affichées représentent l’intervalle de confiance de 95 % autour de l’estimation moyenne du taux de conversion d’une expérience. Ces barres sont également codées par couleur par rapport à l’expérience « Contrôle » définie. La barre de l’expérience « Contrôle » est toujours grise. Les parties des intervalles de confiance sous l’intervalle de confiance de l’expérience « de contrôle » sont en rouge et les parties des intervalles de confiance au-dessus de l’expérience « de contrôle » sont en vert.

Un gagnant est trouvé lorsque la [!UICONTROL Confidence Interval] à 95 % de l’expérience principale ne chevauche aucune autre expérience. L’expérience gagnante est désignée par un badge étoile vert à gauche du nom de l’expérience et dans la bannière « Gagnant ». Lorsqu’aucune étoile n’est visible, la bannière indique « Aucun gagnant encore » et aucun gagnant n’a encore été trouvé.

Un nombre « Confiance » est également signalé en regard de l’expérience actuellement en tête ou gagnante. Ce chiffre est signalé uniquement jusqu’à ce que la [!UICONTROL Confidence] de l’expérience principale atteigne au moins 60 %. Si deux expériences sont présentes dans l’activité [!UICONTROL Auto-Allocate], ce nombre représente le niveau de confiance selon lequel l’expérience est plus performante que l’autre expérience. Si plus de deux expériences sont présentes dans l’activité [!UICONTROL Auto-Allocate], ce nombre représente le niveau de confiance selon lequel l’expérience est plus performante que l’expérience « de contrôle » définie. Si l’expérience « Contrôle » gagne, aucun chiffre « Confiance » n’est signalé.

## Questions fréquentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Tenez compte des réponses suivantes aux questions fréquentes :

### L&#39;activité a débuté il y a quelques jours. Pourquoi toutes les valeurs de confiance affichent-elles toujours 0 % ?

L’une des raisons suivantes explique pourquoi 0 % s’affiche dans la colonne [!UICONTROL Confidence] du rapport pour toutes les activités :

* Les tests A/B manuels et les [!UICONTROL Auto-Allocate] utilisent différentes statistiques pour afficher les valeurs [!UICONTROL Confidence].

  Les tests A/B manuels utilisent des valeurs de p basées sur le test en t de [Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Une valeur-p est la probabilité de trouver la différence observée (ou une plus extrême) entre une expérience et le contrôle, étant donné qu’en réalité, il n’y a pas de différence de ce type. Ces valeurs-p ne peuvent être utilisées que pour déterminer si les données observées sont cohérentes avec une expérience donnée et si le contrôle est le même. Elles ne peuvent pas servir à déterminer si une expérience diffère d’une autre expérience (que l’expérience de contrôle).

  [!UICONTROL Auto-Allocate] indique la probabilité qu’une expérience donnée soit un véritable gagnant pour toutes les expériences de l’activité. Seule une expérience gagnante (qui est le plus susceptible d’être gagnante) a une valeur de confiance non nulle. Tous les autres sont plus susceptibles d&#39;être perdants et affichent 0%.

* [!UICONTROL Auto-Allocate] ne commence à afficher un niveau de confiance qu’une fois que l’expérience gagnante a obtenu 60 % de confiance. Ces niveaux de confiance apparaissent généralement environ la moitié du temps nécessaire à un test A/B normal (bien que cette période ne soit pas garantie). Pour déterminer la durée d’exécution d’un test A/B normal, utilisez le [!DNL Adobe Target] [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) : taux de conversion de la commande de bouchon dans « Taux de conversion de base », « 5 % » pour « Effet élévateur » et 95 % pour « Degré de confiance ». En règle générale, le degré de confiance apparaît quand chaque expérience a accumulé au moins 50 % des échantillons requis par expérience. Cela vous donne une idée du moment où la confiance commence à apparaître.

* Si le rapport présente globalement un taux de 0 %, cela signifie probablement que l’activité n’a pas encore suffisamment progressé.

### Les badges « Pas de gagnant », « Gagnant » et « étoile » sont-ils disponibles pour les activités [!UICONTROL Auto-Allocate] qui utilisent [!UICONTROL Analytics as the reporting source] (A4T) ?

Les badges « Pas encore de gagnant » et « Gagnant » ne sont actuellement pas disponibles dans le panneau [!UICONTROL A4T] dans [!DNL Analysis Workspace]. Ces badges ne sont pas disponibles non plus si le même rapport est affiché dans [!DNL Target]. Le badge « étoile » gagnant affiché dans un rapport [!DNL Target] pour une activité [!UICONTROL Auto-Allocate] à l’aide d’A4T doit être ignoré.

Pour plus d’informations à ce sujet et sur d’autres limites et notes, consultez [Affectation automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) dans *Prise en charge d’A4T pour les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]*.


