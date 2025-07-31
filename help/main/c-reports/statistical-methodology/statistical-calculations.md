---
keywords: rapports;méthodologie statistique;calculs statistiques;statistiques;moyenne;taux de conversion;chiffre d’affaires par visiteur;rpv;intervalle de confiance;effet élévateur;test de richesse;calculs hors ligne
description: Découvrez les calculs statistiques utilisés dans les activités de [!UICONTROL A/B Test] manuelle dans  [!DNL Adobe Target].
title: Comment puis-je en savoir plus sur les calculs statistiques utilisés dans les activités [!UICONTROL A/B Test] ?
feature: Reports
exl-id: 5f7377b9-0567-4b6f-8968-4696b2088d0a
source-git-commit: 18f8ccd3edfda635c3f47bd67ff0b7a516748fa8
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 2%

---

# Calculs statistiques dans les tests A/B

Cet article documente les calculs statistiques détaillés utilisés dans les tests A/B manuels dans [!DNL Adobe Target]. Des définitions sont fournies pour [!UICONTROL Conversion Rate], [!UICONTROL Confidence Interval of Conversion Rate], [!UICONTROL Lift], [!UICONTROL Confidence Interval for Lift] et [!UICONTROL Confidence].

>[!NOTE]
>
>Les informations de cet article remplacent le fichier PDF *Calculs Adobe Target pour les tests A/B* auparavant disponible en téléchargement sur ce site.

![Rapport cible présentant le [!UICONTROL Conversion Rate], la [!UICONTROL Average Lift and Confidence Interval] et la [!UICONTROL Confidence] d’une activité de test A/B.](/help/main/c-reports/statistical-methodology/img/target_report.png)

## Performances moyennes

La section suivante explique les calculs utilisés dans l’illustration précédente.

### Taux de conversion et recettes par visiteur (RPV)

L’illustration suivante présente les [!UICONTROL Conversion Rate], les [!UICONTROL Confidence Interval of Conversion Rate] et le nombre de [!UICONTROL Conversions] dans un rapport [!DNL Target]. Par exemple, la première ligne indique que pour l’expérience A : la [!UICONTROL Conversion Rate] est de 25,81 % avec une [!UICONTROL Confidence Interval] de ± 7,7 % et 32 conversions ont été enregistrées. Étant donné que 124 visiteurs ont vu l’expérience, cela équivaut à 32/124 = 25,81 %.

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

Le taux de conversion ou **moyenne**, *μ<sub>ν</sub>*, pour chaque expérience *ν* dans une expérience est défini(e) comme le rapport de la somme de la mesure par rapport au nombre d’unités affectées à cette mesure, *N<sub>ν</sub>* :

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

Ici,

* *Y<sub>iv</sub>* est la valeur de la mesure pour chaque unité *i* qui a été affectée à une expérience donnée *ν*.

* La somme des unités *i* dépend du choix de la méthode de comptage.

   * Si *[!UICONTROL Visitors]* est utilisé comme méthode de comptage, chaque unité est un visiteur unique défini comme un participant unique à l’activité pendant toute la durée de celle-ci.
   * Si *[!UICONTROL Visits]* est utilisé comme méthode de comptage, chaque unité est une visite unique définie comme un participant unique à une expérience au cours d’une session de [!DNL Target] (avec un `sessionId` unique). Lorsque l’`sessionId` change ou que le visiteur atteint l’étape de conversion, une nouvelle visite est comptabilisée.
   * Si *[!UICONTROL Activity Impressions]* est utilisé comme méthode de comptage, chaque unité est une impression unique définie comme chaque fois qu’un visiteur charge une page de l’activité.

## [!UICONTROL Confidence Interval of Mean]/[!UICONTROL Conversion Rate]

L’intervalle de confiance du taux de conversion est intuitivement défini comme une plage de taux de conversion possibles cohérente avec les données sous-jacentes.

Lors de l’exécution d’expériences, le taux de conversion d’une expérience donnée est une *estimation* du taux de conversion « réel ». Pour quantifier l’incertitude de cette estimation, [!DNL Target] utilise un intervalle de confiance. [!DNL Target] signale toujours un intervalle de confiance de 95 %, ce qui signifie qu’à la fin, 95 % des intervalles de confiance calculés incluent le taux de conversion réel de l’expérience.

Un nombre « Confiance » est également signalé en regard de l’expérience actuellement en tête ou gagnante. Ce chiffre est signalé uniquement jusqu’à ce que la [!UICONTROL Confidence] de l’expérience principale atteigne au moins 60 %. Si deux expériences sont présentes dans l’activité, ce nombre représente le niveau de confiance selon lequel l’expérience fonctionne mieux que l’autre expérience. Si l’activité comporte plus de deux expériences, ce nombre représente le niveau de confiance selon lequel l’expérience est plus performante que l’expérience « de contrôle » définie. Si l’expérience « Contrôle » gagne, aucun chiffre « Confiance » n’est signalé.

Un intervalle de confiance à 95 % du taux de conversion *μ<sub>ν</sub>* est défini comme la plage de valeurs :

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

Où l’erreur standard pour la moyenne est définie comme

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

Lorsqu’une estimation non biaisée de l’écart type échantillon est utilisée :

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

Lorsque la campagne est une campagne de taux de conversion (c’est-à-dire que la mesure de conversion est binaire), l’erreur standard se réduit à :

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## Effet élévateur

L’illustration suivante présente [!UICONTROL Lift] et [!UICONTROL Confidence Interval of Lift] dans un rapport [!DNL Target]. Le nombre représente la moyenne de la plage des limites de l’effet élévateur, et la flèche indique si l’effet élévateur est positif ou négatif. La flèche s’affiche en gris jusqu’à ce que le degré de confiance atteigne 95 %. Une fois que le degré de confiance a dépassé le seuil, la flèche est verte ou rouge en fonction d’une courbe d’élévation positive ou négative.

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

L’effet élévateur entre une expérience *ν* et l’expérience de contrôle *ν<sub>0</sub>* est le « delta » relatif dans les taux de conversion, défini comme

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

Lorsque les taux de conversion individuels sont tels que définis ci-dessus. Plus simplement,

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

Si le taux de conversion de l’expérience de contrôle *ν<sub>0</sub>* est de 0, il n’y a pas d’effet élévateur.

## [!DNL Confidence Interval of Lift]

Le graphique en boîte de la colonne [!UICONTROL Average Lift and Confidence Interval] représente la valeur moyenne et la [!UICONTROL Confidence Interval of Lift] de 95 %. L’indicateur est gris lorsqu’il y a chevauchement de l’intervalle de confiance d’une expérience donnée de non-contrôle avec l’intervalle de confiance de l’expérience de contrôle. Le graphique à boîtes est vert ou rouge lorsque la plage de l’intervalle de confiance de l’expérience donnée est supérieure ou inférieure à l’intervalle de confiance de l’expérience de contrôle.

L’erreur standard de l’effet élévateur entre une expérience *ν* et l’expérience de contrôle *ν<sub>0</sub>* est définie comme suit :

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="métrique-moyen"></p>

Alors l’intervalle de confiance à 95 % de l’effet élévateur est :

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

Ce calcul utilise la méthode « Delta », et est décrit [plus en détail dans ce document](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL Confidence]

La dernière colonne indique le degré de confiance dans un rapport [!DNL Target]. Le degré de confiance d’une expérience est une probabilité (exprimée en pourcentage) d’obtenir un résultat aussi extrême que celui observé, en admettant que l’hypothèse nulle soit vraie. En termes de p-values, le degré de confiance affiché est *1 - p-value*. Intuitivement, un degré de confiance plus élevé signifie qu’il est moins probable que l’expérience de contrôle et de non-contrôle ait des taux de conversion égaux.

En [!DNL Target], un test t bilatéral **test de Welch** est effectué entre l’expérience de test et l’expérience de contrôle afin de tester si les moyens d’expérience de test et de contrôle sont identiques. Étant donné que nous ne savons généralement pas si les tailles d’échantillon et les variances de deux groupes sont identiques avant d’exécuter l’expérience, et [!DNL Target] vous permet également d’envoyer des pourcentages inégaux de trafic à chaque expérience, nous ne supposons pas que la variance pour chaque expérience soit égale. Ainsi, le test t de Welch est choisi au lieu du test t de Student.

Pour effectuer le test t de Welch, nous commençons d&#39;abord par calculer la statistique t et les degrés de liberté, puis nous exécutons un test t à deux queues pour générer la valeur p. Enfin, nous calculons le degré de confiance en fonction de la valeur de p.

La statistique *t* est définie comme étant la différence des moyennes de deux variables aléatoires indépendantes, *ν* et *ν<sub>0</sub>*, divisée par l’erreur standard de la différence :

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

Où *μ<sub>v</sub>* et *μ<sub>v0</sub>* sont les moyennes de *ν* et *ν<sub>0</sub>* respectivement, et l’erreur standard de la différence entre *μ<sub>v</sub>* et *μ<sub>v0</sub>* est donnée par :

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

Où *σ<sup>2</sup><sub>v</sub>* et *σ<sup>2</sup><sub>v<sub>0</sub></sub>* sont les variances de deux expériences *ν* et *ν<sub>0</sub>* respectivement, et *N<sub>v</sub>* et *N<sub>v<sub>0</sub></sub>* sont des tailles d’échantillon pour *ν* et *ν<sub>0</sub>* respectivement.

Pour le test en t de Welch, le degré de liberté est calculé comme suit :

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

Et le degré de liberté pour *ν* et *ν<sub>0</sub>* sont définis comme suit :

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

Ensuite, la valeur p peut être calculée à partir de la zone dans les extrémités de la distribution *t* :

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

Enfin, le degré de confiance signalé dans [!DNL Target] est défini comme suit :

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## Exécution de calculs hors ligne

Le [rapport CSV téléchargé](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) comprend uniquement des données brutes. Il ne tient pas compte des mesures calculées (recettes par visiteur, effet élévateur ou degré de confiance, par exemple) utilisées dans les tests A/B.

Pour calculer ces quantités statistiques, téléchargez le fichier Excel [!DNL Target] [Calculateur de confiance complet](/help/main/assets/complete_confidence_calculator.xlsx) pour saisir la valeur de l’activité.
