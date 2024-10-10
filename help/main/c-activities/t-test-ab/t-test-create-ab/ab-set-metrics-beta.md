---
keywords: A/B;mesures d’activité;mesures;définir des mesures;mesure d’objectif;paramètres d’activité;mesure de succès;conversion;recettes;engagement
description: Découvrez comment définir des mesures dans une activité A/B pour déterminer le succès de la visite, y compris [!UICONTROL Conversion], [!UICONTROL Revenue] et [!UICONTROL Engagement].
title: Comment définir des mesures d’objectif dans une activité A/B ?
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 22a12d29fb894e916783efc65dfe8dfd698dff83
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 58%

---

# Définition de mesures

Utilisez des mesures dans une activité A/B [!DNL Adobe Target] pour déterminer quand une visite est réussie.

Pour plus d’informations sur les mesures de succès, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Dans la section **[!UICONTROL Reporting Settings]** de la page **[!UICONTROL Goals & Settings]**, sélectionnez une [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   L’option [!UICONTROL Select Metrics] répertorie les mesures de succès que vous pouvez choisir pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Vous pouvez utiliser n’importe quelle mesure de succès préconfigurée ou en créer une personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.

1. Indiquez les paramètres de vos mesures.

   Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

   S’il est activé, le champ [!UICONTROL Estimated Value of the Conversion] (indisponible pour les mesures [!UICONTROL Page Score]) fournit une valeur pour votre objectif. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

   La configuration correcte des mesures de succès est essentielle pour obtenir les données attendues.

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