---
keywords: ciblage d’expérience;xt;mesures;définir des mesures;mesure d’objectif;paramètres d’activité;mesure de succès;conversion;recettes;engagement
description: Découvrez comment spécifier des mesures dans une [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] pour déterminer le moment où une visite est réussie, par exemple [!UICONTROL Conversion], [!UICONTROL Recettes], ou [!UICONTROL Engagement].
title: Comment définir des mesures d’objectif dans une [!UICONTROL Ciblage d’expérience] Activité ?
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 62%

---

# Définition de mesures dans [!UICONTROL Ciblage d’expérience] Activités (XT)

Utilisation de mesures dans une [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] (XT) pour déterminer quand une visite est réussie.

Pour plus d’informations sur les mesures de succès, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Indiquez l’objectif de l’activité.
1. Sélectionnez une [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Sélectionner la mesure de succès](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   La variable [!UICONTROL Sélectionner des mesures] répertorie les mesures de succès que vous pouvez choisir pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * [!UICONTROL Conversion]
   * [!UICONTROL Recettes]
   * [!UICONTROL Engagement]

   Vous pouvez utiliser l’une des mesures de succès prédéfinies ou créer une mesure de succès personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.
1. Indiquez les paramètres de vos mesures.

   Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

   Si cette option est activée, la variable [!UICONTROL Valeur estimée de la conversion] (non disponible pour [!UICONTROL Score de page] (mesures) fournit une valeur pour votre objectif. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

   La configuration adéquate des mesures de succès est essentielle pour obtenir les données attendues.

   Pour en savoir plus, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Facultatif) Ajoutez des mesures supplémentaires.
1. Cliquez sur **[!UICONTROL Continuer]** lorsque vous avez terminé de définir vos mesures. 


Lorsque vous nommez ou renommez une mesure, les caractères suivants ne sont pas autorisés :

| Caractère | Description |
|--- |--- |
| `/` | Barre oblique |
| `?` | Point d’interrogation |
| `#` | Croisillon |
| `:` | Deux-points |
| `=` | Égal |
| `+` | Plus |
| `-` | Moins |
| `@` | Arobase |

## Vidéo de formation : Mesures d’activité (7:43) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur l’utilisation des mesures de succès.

* Comprendre les mesures d’« objectif »
* Découverte et génération des mesures [!UICONTROL Conversion], [!UICONTROL Chiffre d’affaires] et [!UICONTROL Engagement]
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
