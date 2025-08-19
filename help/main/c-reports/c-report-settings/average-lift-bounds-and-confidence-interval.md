---
keywords: Target;rapports;paramètres de rapport;environnement;effet élévateur;limite de l’effet élévateur;variance;confiance;contrôle
description: Découvrez comment interpréter les rapports Adobe [!DNL Target] qui incluent des points de données et des représentations de visualisation pour vous aider à comprendre les limites de l’effet élévateur et le niveau de confiance de vos activités.
title: Comment puis-je afficher l’effet élévateur moyen, les limites de l’effet élévateur et l’intervalle de confiance ?
feature: Reports
exl-id: 0453aec1-cca5-462c-8eed-0d40bb4cf323
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 60%

---

# Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance

Les rapports comprennent plusieurs points de données et représentations de visualisation qui vous aident à comprendre les limites de l’effet élévateur et le niveau de confiance associé à votre activité [!DNL Adobe Target] afin de vous aider à déterminer plus précisément un gagnant.

>[!NOTE]
>
>Cette fonctionnalité est disponible uniquement lors de l’affichage de rapports en mode [!UICONTROL Table]. Cette fonctionnalité n’est pas disponible pour les activités utilisant [Analytics comme source de rapports (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Interprétation des données {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

L’illustration suivante présente [!UICONTROL Lift Bounds and Confidence Level] informations :

![Rapport élévateur moyen et degré de confiance](/help/main/c-reports/c-report-settings/assets/lift-screenshot-new.png)

Les informations d’effet élévateur et de confiance dans l’interface utilisateur de création de rapports [!DNL Target] incluent :

### Effet élévateur

Le grand nombre et la flèche reflètent la valeur de l’effet élévateur attendue. Ce nombre correspond au milieu de la gamme des limites de l’effet élévateur. La flèche de l’effet élévateur attendu s’affiche en gris jusqu’à ce que le degré de confiance dépasse 95 %. Au-delà de ce seuil, la flèche s’affiche en rouge ou en vert selon que l’effet élévateur est respectivement négatif ou positif.

### Limites de l’effet élévateur

Ceci correspond à l’intervalle de confiance de 95 % de l’effet élévateur. La valeur s’affiche sous forme de plage au-dessous de l’effet élévateur moyen. Voir [Exemple de calcul](#example) ci-dessous pour un exemple de la manière dont ces limites d’effet élévateur sont calculées.

### Graphique à boîtes

Le graphique à boîtes de l’interface [!DNL Target] représente la valeur attendue et l’intervalle de confiance à 95 % de la mesure de succès en question. Cette fonction peut être considérée comme un moyen graphique d’afficher l’effet élévateur et les informations relatives à ses limites.

Il existe plusieurs méthodes clés [!DNL Target] vous aider à interpréter les informations de confiance, l’une d’elles étant la couleur. Le graphique affiche les chevauchements éventuellement présents dans l’intervalle de confiance d’une expérience spécifique en indiquant l’intervalle de confiance de contrôle indiqué en gris, et n’importe quelle gamme d’intervalles de confiance d’une expérience spécifique qui est supérieure ou inférieure à celle de l’intervalle de confiance de contrôle en vert ou en rouge, respectivement.

La longueur du diagramme en boîte représente la taille de l’intervalle de confiance d’une manière facile à comprendre. À mesure que vous collectez davantage de données durant votre activité, la barre se déplace et se modifie. L’intervalle de confiance est dérivé de la variance et de la taille de l’échantillon (nombre de visiteurs). Plus la variance est réduite et la taille de l’échantillon conséquente, plus l’intervalle de confiance est étroit.

### Confiance

Le degré de confiance d’une expérience ou d’une offre affichée est une probabilité (exprimée en pourcentage) d’obtenir un résultat _moins extrême_ que celui réellement observé, _si l’hypothèse nulle est vraie_, c’est-à-dire s’il n’y a aucune différence de taux de conversion entre cette expérience ou offre, et l’expérience/offre de contrôle. En termes de p-values, ce degré de confiance affiché est `1 - p-value`. En d’autres termes, un degré de confiance plus élevé indique que les données sont moins cohérentes avec l’hypothèse que l’offre/expérience de contrôle et de non-contrôle ont des taux de conversion égaux.

## Comprendre comment l’intervalle de confiance de l’effet élévateur est déterminé {#pdf}

Téléchargez le fichier PDF [ Intervalle de confiance pour l’effet élévateur ](/help/main/assets/confidence_interval_lift.pdf) pour plus d’informations.

## Comment les limites de l’effet élévateur sont-elles calculées ? {#section_1D360781D972483693680BE0F07AEAD1}

Les limites de l’effet élévateur représentent les intervalles de confiance de 95 % de l’effet élévateur que l’expérience ou l’offre spécifique présente par rapport à l’expérience ou à l’offre de contrôle. Globalement parlant, cela signifie que l’effet élévateur effectif a environ 95 % de chances de se situer entre ces limites.

Les limites de l’effet élévateur sont calculées à l’aide de la formule suivante :

![image lift_diagram](assets/lift_diagram.png)

Quelques calculs supplémentaires sont nécessaires pour arriver à l’entrée de nos limites de l’effet élévateur :

* **t-value :** la statistique critique pour notre niveau de confiance à 95 % est 1,96. Pour en savoir plus sur les valeurs [t, cliquez ici](https://en.wikipedia.org/wiki/T-statistic).
* **Variance de l’effet élévateur :** l’écart-type sur la valeur de succès de l’expérience N et l’écart-type sur la valeur de succès de l’expérience de contrôle sont nécessaires pour déterminer la variance de l’effet élévateur, qui est calculée à l’aide de la formule suivante (illustrée dans le cas où la mesure de succès est une conversion).

  ![image lift_variance](assets/lift_variance.png)

* **Écart-type sur le taux de conversion ou la mesure de succès :** l’écart-type est calculé de la même manière que l’expérience N et le contrôle, en appliquant la formule suivante (illustrée dans le cas où la mesure de succès est une conversion). Pour plus d’informations sur l’écart-type, [cliquez ici](https://en.wikipedia.org/wiki/Standard_error).

  ![image standard_error](assets/standard_error.png)

  >[!NOTE]
  >
  >L’écart-type des activités de mesure de succès en termes de chiffre d’affaires repose sur la variance du chiffre d’affaires au sein de l’échantillon.

## Exemple de calcul {#example}

Prenons un exemple d’activité comportant les deux expériences et les résultats suivants :

| Expérience | Visiteurs | Conversions | Taux de conversion |
|--- |--- |--- |--- |
| Expérience A (contrôle) | 219 328 | 2 466 | 1,12 % |
| Expérience B | 218 362 | 3 040 | 1,39% |

D’après nos formules, nous pouvons calculer les entrées dont nous avons besoin pour les limites de l’effet élévateur.

**Écart-type pour l’expérience A (contrôle)**

![image_standard_error_A](assets/standard_error_A.png)

**Écart-type pour l’expérience B**

![image standard_error_B](assets/standard_error_B.png)

**Variance de l’effet élévateur pour l’expérience B**

![image lift_variance_B](assets/lift_variance_B.png)

**Limites de l’effet élévateur pour l’expérience B**

Effet élévateur escompté pour l’expérience B :

![image lift_bounds_B](assets/lift_bounds_B.png)

Les limites de l’effet élévateur pour l’expérience B seraient alors :

![image lift_bounds_B2](assets/lift_bounds_B2.png)

>[!NOTE]
>
>Il peut y avoir un léger écart entre les calculs manuels effectués avec les formules ci-dessus et les chiffres présentés dans le rapport. Cet écart peut être dû au fait que les nombres de pages vues utilisés dans les calculs manuels ont été arrondis. L’effet élévateur affiché dans le rapport [!DNL Target] est basé sur les nombres exacts obtenus à partir de l’engagement total et du nombre d’engagements. Les chiffres se rapportant aux engagements sont disponibles via l’API rapport de synthèse.

## Quand les limites de l’effet élévateur ne sont-elles pas affichées ? {#section_C5622E1E94684DAD937249B51A9E42CC}

Dans certains cas, [!DNL Target] n’affiche pas les limites de l’effet élévateur :

* Quelle que soit l’activité, lorsque le nombre total de visites ou de visiteurs est inférieur à 30.
* Pour les activités [!UICONTROL Auto-Allocate], aucune limite d’effet élévateur ne s’affiche tant qu’une expérience n’a pas atteint un degré de confiance de 60 %.
