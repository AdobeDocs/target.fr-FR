---
keywords: rapports;méthodologie statistique;calculs statistiques;statistiques;moyenne;taux de conversion;recettes par visiteur;rpv;intervalle de confiance;effet élévateur;test en t de bienvenue;calculs hors ligne
description: En savoir plus sur les calculs statistiques utilisés dans le mode manuel [!UICONTROL Test A/B] activités dans [!DNL Adobe Target].
title: Comment puis-je en savoir plus sur les calculs statistiques utilisés dans [!UICONTROL Test A/B] Activités ?
feature: Reports
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 5%

---

# Calculs statistiques dans les tests A/B

Cet article documente les calculs statistiques détaillés utilisés dans les tests A/B manuels dans [!DNL Adobe Target]. Les définitions sont fournies pour [!UICONTROL Taux de conversion], [!UICONTROL Intervalle de confiance du taux de conversion], [!UICONTROL Effet élévateur], [!UICONTROL Intervalle de confiance pour l’effet élévateur], et [!UICONTROL Confiance].

>[!NOTE]
>
>Les informations de cet article remplacent le fichier PDF *Calculs Adobe Target pour les tests A/B* auparavant disponible en téléchargement sur ce site.

![Le rapport Target affiche la variable [!UICONTROL Taux de conversion], [!UICONTROL Effet élévateur moyen et intervalle de confiance], et [!UICONTROL Confiance] d’une activité de test A/B.](/help/main/c-reports/statistical-methodology/img/target_report.png)

## Performances moyennes

La section suivante explique les calculs utilisés dans l’illustration précédente.

### Campagnes sur le taux de conversion et les recettes par visiteur (RPV)

L’illustration suivante présente [!UICONTROL Taux de conversion], [!UICONTROL Intervalle de confiance du taux de conversion]et le nombre de [!UICONTROL Conversions] dans [!DNL Target] rapport. Par exemple, la première ligne indique que pour l’expérience A : la valeur [!UICONTROL Taux de conversion] est de 25,81 % avec une [!UICONTROL Intervalle de confiance] de ±7,7 % et 32 conversions ont été enregistrées. Étant donné que 124 visiteurs ont vu l’expérience, cela équivaut à 32/124 = 25,81 %.

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

Le taux de conversion ou **mean**, *μ<sub>ν</sub>*, pour chaque expérience *ν* dans une expérience est défini comme un ratio de la somme de la mesure par rapport au nombre d’unités affectées à cette mesure, *N<sub>ν</sub>*:

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

Ici,

* *Y<sub>iν</sub>* est la valeur de la mesure pour chaque unité *i*, qui a été affecté à une expérience donnée *ν*.

* La somme sur les unités *i* dépend du choix de la méthodologie de comptage.

   * If *[!UICONTROL Visiteurs]* est utilisée comme méthodologie de comptage, chaque unité est un visiteur unique défini comme participant unique à l’activité pour la durée de celle-ci.
   * If *[!UICONTROL Visites]* est utilisée comme méthodologie de comptage, chaque unité est une visite unique définie comme participant unique à une expérience au cours d’une [!DNL Target] session (avec une `sessionId`). Lorsque la variable `sessionId` change ou le visiteur atteint l’étape de conversion, une nouvelle visite est comptabilisée.
   * If *[!UICONTROL Impressions d’activité]* est utilisée comme méthodologie de comptage. Chaque unité est une impression unique définie à chaque chargement d’une page de l’activité par un visiteur.

## [!UICONTROL Intervalle de confiance du moyen]/[!UICONTROL Taux de conversion]

L’intervalle de confiance du taux de conversion est défini intuitivement comme une plage de taux de conversion possibles cohérents avec les données sous-jacentes.

Lors de l’exécution d’expériences, le taux de conversion d’une expérience donnée est une *estimation* du taux de conversion &quot;true&quot;. Pour quantifier l&#39;incertitude de cette estimation, [!DNL Target] utilise un intervalle de confiance. [!DNL Target] indique toujours un intervalle de confiance de 95 %, ce qui signifie qu’à la fin, 95 % des intervalles de confiance calculés incluent le taux de conversion réel de l’expérience.

Intervalle de confiance de 95 % du taux de conversion *μ<sub>ν</sub>* est défini comme la plage de valeurs :

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

Lorsque l’erreur standard pour la moyenne est définie comme

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

Lorsqu’une estimation impartiale de l’écart-type d’échantillon est utilisée :

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

Lorsque la campagne est une campagne de taux de conversion (c’est-à-dire que la mesure de conversion est binaire), l’erreur standard se réduit à :

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## Effet élévateur

L’illustration suivante présente [!UICONTROL Effet élévateur] et [!UICONTROL Intervalle de confiance de l’effet élévateur] dans [!DNL Target] Rapport. Le nombre représente la moyenne de la plage des limites de l’effet élévateur, tandis que la flèche indique si l’effet élévateur est positif ou négatif. La flèche s’affiche en gris jusqu’à ce que le degré de confiance dépasse 95 %. Une fois le degré de confiance dépassé, la flèche est verte ou rouge en fonction d’un effet élévateur positif ou négatif.

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

Effet élévateur entre une expérience  *ν*, et l’expérience de contrôle *ν<sub>0</sub>* est le &quot;delta&quot; relatif dans les taux de conversion, défini comme

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

Où les taux de conversion individuels sont tels que définis ci-dessus. Plus simplement :

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

Si le taux de conversion de l’expérience de contrôle *ν<sub>0</sub>* est 0, il n’y a pas d’ascenseur.

## [!DNL Confidence Interval of Lift]

Graphique en boîte dans la variable [!UICONTROL Effet élévateur moyen et intervalle de confiance] représente la valeur moyenne et 95 % ; [!UICONTROL Intervalle de confiance de l’effet élévateur]. Le graphique en boîte est gris lorsqu’il existe un chevauchement dans l’intervalle de confiance d’une expérience donnée qui n’est pas témoin avec l’intervalle de confiance de l’expérience de contrôle. Le diagramme en boîte est vert ou rouge lorsque la plage de l’intervalle de confiance de l’expérience donnée est supérieure ou inférieure à l’intervalle de confiance de l’expérience de contrôle.

L’erreur standard de l’effet élévateur entre une expérience  *ν*, et l’expérience de contrôle  *ν<sub>0</sub>* est défini comme suit :

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="mesure-moyenne"></p>

L’intervalle de confiance de 95 % de l’effet élévateur est alors :

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

Ce calcul utilise la méthode &quot;Delta&quot; et est décrit comme suit : [plus de détails dans ce document](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL Degré de confiance]

La dernière colonne indique la confiance dans un [!DNL Target] rapport. La confiance d’une expérience est une probabilité (indiquée sous la forme d’un pourcentage) d’obtenir un résultat moins extrême que celui observé, étant donné que l’hypothèse nulle est vraie. En termes de p-valeurs, le degré de confiance affiché est *1 - p-value*. Intuitivement, une confiance plus élevée signifie qu’il est moins probable que l’expérience de contrôle et l’expérience de non-contrôle aient des taux de conversion égaux.

Dans [!DNL Target], un **Le test en t de Welch** est effectué entre l’expérience de test et l’expérience de contrôle afin de tester si les moyens du test et des expériences de contrôle sont identiques. Parce que nous ne savons généralement pas si les tailles d’échantillon et les variations de deux groupes sont identiques avant de réaliser l’expérience, et [!DNL Target] vous permet également d’envoyer des pourcentages de trafic inégaux à chaque expérience. nous ne supposons pas que la variance de chaque expérience est égale. Ainsi, le test en t de Welch est choisi au lieu du test en t de Student.

Pour effectuer le test en t de Welch, nous commençons par calculer la statistique en t et les degrés de liberté, puis nous exécutons un test en t bidimensionnel pour générer la valeur p. Enfin, nous calculons la confiance en fonction de la valeur p.

Le *t*-statistics est défini comme la différence des moyens de deux variables aléatoires indépendantes, *ν* et *ν<sub>0</sub>*, divisé par l’erreur standard de la différence :

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

Où *μ<sub>v</sub>* et *μ<sub>v0</sub>* sont les moyens *ν*  et *ν<sub>0</sub>* et l’erreur standard de la différence entre *μ<sub>v</sub>* et *μ<sub>v0</sub>* sont donnés par :

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

Où *underline<sup>2</sup><sub>v</sub>* et *underline<sup>2</sup><sub>v<sub>0</sub></sub>* sont les variations de deux expériences ; *ν*  et *ν<sub>0</sub>* respectivement, et *N<sub>v</sub>* et *N<sub>v<sub>0</sub></sub>* sont des tailles d’échantillon pour *ν* et *ν<sub>0</sub>* respectivement.

Pour le test en t de Welch, le degré de liberté est calculé comme suit :

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

Et degré de liberté pour *ν*  et *ν<sub>0</sub>* sont définies comme suit :

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

Ensuite, la valeur p peut être calculée à partir de la zone située dans les queues de la variable *t*-distribution:

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

Enfin, le degré de confiance indiqué dans [!DNL Target] est défini comme suit :

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## Exécution de calculs hors ligne

Le [rapport CSV téléchargé](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) comprend uniquement des données brutes. Il ne tient pas compte des mesures calculées (recettes par visiteur, effet élévateur ou degré de confiance, par exemple) utilisées dans les tests A/B.

Pour calculer ces quantités statistiques, téléchargez le [!DNL Target] [Calculateur de confiance complet](/help/main/assets/complete_confidence_calculator.xlsx) Fichier Excel pour saisir la valeur de l’activité.