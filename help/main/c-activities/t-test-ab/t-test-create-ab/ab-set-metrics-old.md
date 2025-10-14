---
keywords: A/B;mesures d’activité;mesures;définir des mesures;mesure d’objectif;paramètres d’activité;mesure de succès;conversion;recettes;engagement
description: Découvrez comment spécifier des mesures dans une activité A [!DNL Adobe Target] B pour déterminer le moment où une visite est réussie, telles que [!UICONTROL Conversion], [!UICONTROL Revenue] et [!UICONTROL Engagement].
title: Comment définir les mesures d’objectif dans une activité A/B ?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 59%

---

# Définition de mesures

Utilisez les mesures d’une activité A/B [!DNL Adobe Target] pour déterminer le moment où une visite est réussie.

Pour plus d’informations sur les mesures de succès, voir [&#x200B; Mesures de succès &#x200B;](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Dans la section **[!UICONTROL Reporting Settings]** de la page **[!UICONTROL Goals & Settings]** , sélectionnez une [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Sélectionner la mesure de succès](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   L’option [!UICONTROL Select Metrics] répertorie les mesures de succès que vous pouvez choisir pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Vous pouvez utiliser n’importe quelle mesure de succès préconfigurée ou en créer une personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.

1. Indiquez les paramètres de vos mesures.

   Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

   Si cette option est activée, le champ [!UICONTROL Estimated Value of the Conversion] (non disponible pour les mesures [!UICONTROL Page Score]) fournit une valeur pour votre objectif. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

   La configuration correcte des mesures de succès est essentielle pour vous assurer d’obtenir les données attendues.

   Pour en savoir plus, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Facultatif) Ajoutez des mesures supplémentaires.

Lorsque vous nommez ou renommez une mesure, les caractères suivants ne sont pas autorisés :

| Caractère | Description |
|--- |--- |
| / | Barre oblique |
| ? | Point d’interrogation |
| # | Croisillon |
| : | Deux-points |
| = | Égal |
| + | Plus |
| - | Moins |
| @ | Arobase |

## Vidéo de formation : Mesures d’activité (7:43) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur l’utilisation des mesures de succès.

* Comprendre les mesures d’« objectif »
* Comprendre et créer des mesures de conversion, de recettes et d’engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
