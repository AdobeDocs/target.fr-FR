---
keywords: ciblage d’expérience;xt;mesures;définir des mesures;mesure d’objectif;paramètres d’activité;mesure de succès;conversion;recettes;engagement
description: Découvrez comment spécifier des mesures dans un Adobe [!DNL Target] activité de ciblage d’expérience afin de déterminer le moment où une visite est réussie, comme Conversion, Recettes et Engagement.
title: Comment définir des mesures d’objectif dans une activité de ciblage d’expérience ?
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 83%

---

# Définition de mesures dans les activités de ciblage d’expérience (XT)

Utilisation de mesures dans une [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] (XT) pour déterminer quand une visite est réussie.

Pour plus d’informations sur les mesures de succès, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Indiquez l’objectif de l’activité.
1. Sélectionnez une [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Sélectionner la mesure de succès](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   La page [!UICONTROL Mesures de succès] répertorie les mesures de succès que vous pouvez sélectionner pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * Conversion
   * Recettes
   * Engagement

   Vous pouvez utiliser n’importe quelle mesure de succès préconfigurée ou en créer une personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.
1. Indiquez les paramètres de vos mesures.

   Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

   S’il est activé, le champ [!UICONTROL Valeur estimée de la conversion] (indisponible pour les mesures Note de page) fournit une valeur pour votre objectif. Cette valeur permet à Target de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

   La configuration adéquate des mesures de succès est essentielle pour obtenir les données attendues.

   Pour en savoir plus, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).
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

## Vidéo de formation : Mesures d’activité (7:43) ![Badge de tutoriel](/help/main/assets/tutorial.png)


Cette vidéo comporte des informations sur l’utilisation des mesures de succès.

* Comprendre les mesures d’« objectif »
* Découverte et génération des mesures Conversion, Chiffre d’affaires et Engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
