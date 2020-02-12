---
keywords: multivariate;mvt;metrics;set metrics;goal metric;activity settings;success metric;conversion;revenue;engagement
description: Pour déterminer quand une visite est réussie, utilisez les mesures dans un test multivarié.
title: Définition de mesures
solution: Target,standard
uuid: 0fb297ba-f1c3-4139-ac37-7fa0bf2ac308
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Définition de mesures{#set-metrics}

Pour déterminer quand une visite est réussie, utilisez les mesures dans un test multivarié.

Pour plus d’informations sur les mesures de succès, voir [Mesures de succès](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Indiquez l’objectif de l’activité.
1. Sélectionnez une [mesure de succès](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Définition de la liste des mesures](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   La page [!UICONTROL Mesures de succès] répertorie les mesures de succès que vous pouvez sélectionner pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * Conversion
   * Recettes
   * Engagement
   Vous pouvez utiliser n’importe quelle mesure de succès préconfigurée ou en créer une personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.
1. Indiquez les paramètres de vos mesures.

   Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

   S’il est activé, le champ [!UICONTROL Valeur estimée de la conversion] (indisponible pour les mesures Note de page) fournit une valeur pour votre objectif. Cette valeur permet à Target de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif. Voir [Estimation de l’effet élévateur dans les recettes](../../../administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE) pour plus d’informations.

   La configuration adéquate des mesures de succès est essentielle pour obtenir les données attendues.

   Pour en savoir plus, voir [Mesures de succès](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)
1. (Facultatif) Ajoutez des mesures supplémentaires.
1. Cliquez sur **[!UICONTROL Continuer]** lorsque vous avez terminé de définir vos mesures. 
Notez que les caractères suivants sont interdits lorsque vous nommez ou renommez une mesure :

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

## Vidéo de formation : Mesures d’activité (7:43) Badge de ![didacticiel](/help/assets/tutorial.png)

Cette vidéo comporte des informations sur l’utilisation des mesures de succès.

* Comprendre les mesures d’« objectif »
* Comprendre et créer des mesures de conversion, de recettes et d’engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
