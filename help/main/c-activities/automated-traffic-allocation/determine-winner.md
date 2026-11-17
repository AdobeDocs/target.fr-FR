---
keywords: affectation automatisée du trafic;ciblage;gagnant;garantie statistique;confiance;déterminer le gagnant;effet élévateur;confiance;par défaut;expérience par défaut;affectation automatique;affectation automatique
description: Découvrez comment interpréter les résultats de l’activité A/B [!UICONTROL Affectation automatique], en vous concentrant sur les indicateurs clés tels que l’effet élévateur et le degré de confiance.
title: Comment Interpréter Les Rapports D’[!UICONTROL Affectation Automatique] ?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
TQID: 'https://experienceleague.adobe.com/o4mFGMk-M5QUvJ57kYnfjMPvVZL8l6YegJQSJyHjAxc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 174d4631b6f4a481c039bd7fff52a8e70161e19e
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 3%
---
# Interprétation des rapports d’[!UICONTROL affectation automatique] {#interpret-auto-allocate-reports}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment identifier l’expérience gagnante d’une activité d’**[!UICONTROL affectation automatique]**, qui offre des garanties statistiques d’**[!UICONTROL affectation automatique]**, et comment lire les chiffres de l’effet élévateur et du degré de confiance dans le rapport.

>[!ENDSHADEBOX]

Le rapport d’une activité A/B **[!UICONTROL Affectation automatique]** dans [!DNL Adobe Target] indique si l’activité a trouvé un gagnant et dans quelle mesure [!DNL Target] est sûr de ce résultat. Des indicateurs tels que le badge du gagnant, l’effet élévateur et le degré de confiance vous aident à interpréter les résultats.

De nombreux professionnels du marketing commettent l’erreur de déclarer prématurément une expérience gagnante avant que les résultats n’indiquent clairement un gagnant. [!DNL Target] vous permet de déterminer plus facilement le gagnant. Pour obtenir des informations générales sur la manière de désigner un gagnant, consultez [Dix pièges courants des tests A/B et comment les éviter](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identifier l’expérience gagnante {#identify-winner}

Lorsque vous utilisez la fonction **[!UICONTROL Affectation automatique]**, [!DNL Target] affiche un badge en haut de la page de l’activité. Le badge indique « Aucun gagnant pour le moment » jusqu’à ce que l’activité atteigne le nombre minimum de conversions avec un degré de confiance suffisant.

![Badge Pas de gagnant](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

Lorsqu&#39;un gagnant définitif est déclaré, [!DNL Target] affiche le badge « Gagnant : expérience *X* ».

![Badge gagnant](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

Le badge gagnant s’affiche également dans le pop-up d’informations d’une activité de la liste **[!UICONTROL Activités]**. Vous pouvez donc voir le statut d’une activité **[!UICONTROL Affectation automatique]** sans l’ouvrir.

>[!NOTE]
>
>Les activités d’**[!UICONTROL affectation automatique]** sont conçues pour trouver la meilleure expérience parmi toutes les options, et pas seulement pour effectuer des comparaisons par paires avec le contrôle.

## Garanties statistiques de l’[!UICONTROL affectation automatique] {#statistical-guarantees}

À la fin d’une activité A/B, l’**[!UICONTROL affectation automatique]** garantit que le gagnant déterminé a un taux effectif de faux positifs de 5 %. Cela signifie que dans seulement 5 % des cas, le gagnant déterminé ne représente pas réellement la meilleure expérience parmi toutes les expériences de l’activité.

Pour un test [A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (avec des expériences identiques), [!DNL Target] conclut un test moins de 5 % du temps. Le comportement attendu d’un test A/A est d’exécuter indéfiniment. Le badge gagnant ne doit donc jamais s’afficher.

### Confiance et p-values {#confidence-p-values}

[!DNL Target] n’utilise pas le degré de confiance basé sur la valeur-p pour l’**[!UICONTROL affectation automatique]**. La colonne **[!UICONTROL Confiance]** dans une activité **[!UICONTROL Affectation automatique]** affiche la probabilité qu’une expérience soit gagnante dans une marge d’erreur de 1 %. L&#39;algorithme utilise un effet détectable minimum de 1 % entre les meilleurs et les meilleurs taux de conversion secondaires, et il utilise l&#39;[inégalité de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) pour calculer cette probabilité.

Les tests A/B normaux calculent le degré de confiance en fonction de valeurs p, qui calculent de manière « approximative » la probabilité qu’une expérience donnée soit différente du contrôle. Elles peuvent seulement servir à déterminer si une expérience diffère de l’expérience de contrôle. Ils ne peuvent pas être utilisés pour déterminer si une expérience est différente d’une autre expérience (pas du contrôle).

>[!IMPORTANT]
>
>[!DNL Target] affiche un gagnant après un nombre minimum prédéfini de conversions. Cependant, la décision finale de choisir le gagnant doit toujours être basée sur les résultats du Calculateur de taille d&#39;échantillon [!DNL Adobe Target]. [!DNL Target] ne prend pas en compte les taux de conversion de base d&#39;un site et d&#39;autres aspects importants qui sont intégrés au calculateur pour déterminer la durée de l&#39;activité. Par conséquent, [!DNL Target] peut afficher un gagnant plus tôt que prévu en fonction d’un nombre minimum de conversions. Pour plus d&#39;informations, voir [Calculateur de taille d&#39;échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Présentation des rapports d’effet élévateur et de confiance {#lift-confidence}

L’onglet **[!UICONTROL Rapports]** d’une activité **[!UICONTROL Affectation automatique]** affiche les chiffres suivants :

| Image | Description |
|---|---|
| **Expérience de contrôle** | La première expérience (nommée Expérience A par défaut) est toujours définie comme expérience « Contrôle » sur l’onglet **[!UICONTROL Rapports]**. Cette expérience n’est pas traitée comme un véritable contrôle statistique dans la modélisation utilisée pour déterminer la performance des expériences, mais elle est traitée comme une référence ou une référence pour certains chiffres du rapport. |
| **Croissance** | La valeur « Lift » et les limites de 95 % de chaque expérience sont toujours calculées par référence à l’expérience « Control » définie. L’expérience « Contrôle » ne peut pas avoir d’effet élévateur par rapport à elle-même. Par conséquent, le rapport affiche une valeur « — » vide pour cette expérience.<br>Contrairement aux tests A/B, dans les tests d’**[!UICONTROL affectation automatique]**, si une expérience est moins performante que le contrôle défini, aucune valeur d’effet élévateur négatif n’est signalée. À la place, « - » s’affiche. |
| **Intervalles de confiance** | Les **[!UICONTROL barres d’intervalle de confiance]** affichées représentent l’intervalle de confiance de 95 % autour de l’estimation moyenne du taux de conversion d’une expérience. Les barres sont codées par couleur en fonction de l’expérience « Contrôle » définie :<ul><li>La barre de l’expérience « Contrôle » est toujours grise.</li><li>Les parties des intervalles de confiance inférieurs à l’intervalle de confiance de l’expérience « Contrôle » sont rouges.</li><li>Les portions des intervalles de confiance supérieures à l’intervalle de confiance de l’expérience « Contrôle » sont en vert.</li></ul> |
| **Gagnant** | Un gagnant est trouvé lorsque l’**[!UICONTROL intervalle de confiance à 95 %]** de l’expérience principale ne chevauche aucune autre expérience. L’expérience gagnante est désignée par un badge étoile vert à gauche du nom de l’expérience et dans la bannière « Gagnant ». Lorsqu’aucune étoile n’est visible, la bannière indique « Aucun gagnant encore » et aucun gagnant n’a encore été trouvé. |
| **Numéro de confiance** | Un nombre « Confiance » est également signalé en regard de l’expérience actuellement en tête ou gagnante. Ce chiffre est signalé uniquement jusqu’à ce que le **[!UICONTROL degré de confiance]** de l’expérience principale atteigne au moins 60 %.<ul><li>Si deux expériences sont présentes dans l’activité **[!UICONTROL Affectation automatique]**, le nombre représente le niveau de confiance selon lequel l’expérience est plus performante que l’autre expérience.</li><li>Si plus de deux expériences sont présentes, le nombre représente le niveau de confiance selon lequel l’expérience fonctionne mieux que l’expérience « de contrôle » définie.</li><li>Si l’expérience « Contrôle » gagne, aucun chiffre « Confiance » n’est signalé.</li></ul> |

## Questions fréquentes {#faq}

Tenez compte des réponses suivantes aux questions fréquentes.

+++ L&#39;activité a débuté il y a quelques jours. Pourquoi toutes les valeurs de confiance affichent-elles toujours 0 % ?

L’une des raisons suivantes explique pourquoi 0 % s’affiche dans la colonne **[!UICONTROL Confiance]** du rapport pour toutes les expériences :

* Les tests A/B manuels et l’**[!UICONTROL affectation automatique]** utilisent différentes statistiques pour afficher les valeurs de **[!UICONTROL degré de confiance]**.

  Les tests A/B manuels utilisent des valeurs p basées sur le test t de [Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Une valeur de p est la probabilité de trouver la différence observée (ou une différence plus extrême) entre une expérience et le contrôle, étant donné qu’en réalité il n’existe aucune différence de ce type. Ces p-values ne peuvent être utilisées que pour déterminer si les données observées sont cohérentes avec une expérience donnée et le contrôle étant le même. Ils ne peuvent pas être utilisés pour déterminer si une expérience est différente d’une autre expérience (pas du contrôle).

  L’**[!UICONTROL Affectation automatique]** indique la probabilité qu’une expérience donnée soit véritablement gagnante pour toutes les expériences de l’activité. Seule une expérience gagnante (qui est le plus susceptible d’être gagnante) a une valeur de confiance non nulle. Tous les autres sont plus susceptibles d&#39;être perdants et affichent 0%.

* L’**[!UICONTROL affectation automatique]** ne commence à afficher un degré de confiance qu’une fois l’expérience gagnante obtenue avec un degré de confiance de 60 %. Ces niveaux de confiance apparaissent généralement environ la moitié du temps nécessaire à un test A/B normal (bien que cette période ne soit pas garantie). Pour déterminer la durée d’exécution d’un test A/B normal, utilisez le [!DNL Adobe Target] [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) : saisissez le taux de conversion du contrôle dans « Taux de conversion de base », « 5 % » pour « Effet élévateur » et 95 % pour « Degré de confiance ». En règle générale, le degré de confiance commence à s’afficher une fois que chaque expérience a rassemblé au moins 50 % des échantillons requis par expérience. Cela vous donne une idée du moment où la confiance commence à apparaître.

* Si le rapport indique 0 % de manière générale, il est probable qu’il soit trop tôt dans l’activité.

+++

+++ Les badges « Aucun gagnant », « Gagnant » et « étoile » sont-ils disponibles pour les activités d’[!UICONTROL affectation automatique] qui utilisent [!UICONTROL Analytics] comme source de création de rapports (A4T) ?

Les badges « Pas encore de gagnant » et « Gagnant » apparaissent dans le pop-up d’informations sur l’activité de la liste **[!UICONTROL Activités]**. Ils n’apparaissent pas dans le panneau **[!UICONTROL A4T]** dans [!DNL Analysis Workspace] ou lorsque vous affichez le même rapport dans [!DNL Target]. Si un rapport [!DNL Target] pour une activité A4T **[!UICONTROL Affectation automatique]** affiche un badge « étoile » gagnant, ignorez-le.

Pour plus d’informations à ce sujet et sur d’autres limites et notes, consultez [Affectation automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) dans la prise en charge de *A4T pour les activités d’[!UICONTROL Affectation automatique] et de [!UICONTROL Ciblage automatique]*.

+++
