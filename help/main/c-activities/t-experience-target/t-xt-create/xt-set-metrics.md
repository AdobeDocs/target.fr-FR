---
keywords: ciblage d’expérience;xt;mesures;définir des mesures;mesure d’objectif;paramètres d’activité;mesure de succès;conversion;recettes;engagement
description: Découvrez comment spécifier des mesures dans une activité de  [!DNL Adobe Target] [!UICONTROL ciblage d’expérience] pour déterminer le moment où une visite est réussie, comme [!UICONTROL Conversion], [!UICONTROL Chiffre d’affaires] ou [!UICONTROL Engagement].
title: Comment définir les mesures d’objectif dans une activité de [!UICONTROL ciblage d’expérience] ?
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
TQID: https://experienceleague.adobe.com/DRFhQ7plSdYqXdzodxFe8h22fSz9xZs9ATt5Ri2s6AA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 351
ht-degree: 52%

---

# Définition de mesures dans les activités [!UICONTROL &#x200B; Ciblage d’expérience &#x200B;] (XT)

Utilisez les mesures dans une activité [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] (XT) pour déterminer le moment où une visite est réussie.

Pour plus d’informations sur les mesures de succès, voir [&#x200B; Mesures de succès &#x200B;](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Indiquez l’objectif de l’activité.
1. Sélectionnez une [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Sélectionner la mesure de succès](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   La page [!UICONTROL Sélectionner des mesures] répertorie les mesures de succès que vous pouvez choisir pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * [!UICONTROL &#x200B; Conversion &#x200B;]
   * [!UICONTROL Recettes]
   * [!UICONTROL Engagement]

   Utilisez l’une des mesures de succès préconfigurées ou créez une mesure de succès personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.
1. Indiquez les paramètres de vos mesures.

   Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

   Si cette option est activée, le champ [!UICONTROL Valeur estimée de la conversion] (non disponible pour les mesures [!UICONTROL Score de page]) fournit une valeur pour votre objectif. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

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

## Vidéo de formation : Mesures d’activité (7:43) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur l’utilisation des mesures de succès.

* Comprendre les mesures d’« objectif »
* comprendre et créer des mesures [!UICONTROL Conversion], [!UICONTROL Chiffre d’affaires] et [!UICONTROL Engagement] ;
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
