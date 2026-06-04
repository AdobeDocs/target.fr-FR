---
keywords: multivarié;mvt;mesures;mesures définies;mesure d’objectif;paramètres d’activité;mesure de succès;conversion;recettes;engagement
description: Découvrez comment spécifier des mesures dans une activité  [!DNL Adobe Target] [!UICONTROL Test multivarié] pour déterminer le moment où une visite est réussie, comme [!UICONTROL Conversion], [!UICONTROL Chiffre d’affaires] et [!UICONTROL Engagement].
title: Comment définir les mesures d’objectif dans une activité de [!UICONTROL test multivarié] (MVT) ?
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
TQID: https://experienceleague.adobe.com/iJntBcXy4QNgEq0SnzLpqMX6S5HQ6kBy4PMoQivlVxw
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 56%

---

# Définition de mesures pour une activité [!UICONTROL test multivarié]

Utilisez les mesures dans un [!DNL Adobe Target] [!UICONTROL test multivarié] pour déterminer le moment où une visite est réussie.

Pour plus d’informations sur les mesures de succès, voir [ Mesures de succès ](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Indiquez l’objectif de l’activité.
1. Sélectionnez une [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Définition de la liste des mesures](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list-new.png)

   La page [!UICONTROL Sélectionner des mesures] répertorie les mesures de succès que vous pouvez choisir pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * [!UICONTROL  Conversion ]
   * [!UICONTROL Recettes]
   * [!UICONTROL Engagement]

   Vous pouvez utiliser n’importe quelle mesure de succès préconfigurée ou en créer une personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.

1. Indiquez les paramètres de vos mesures.

   Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

   Si cette option est activée, le champ [!UICONTROL Valeur estimée de la conversion] (non disponible pour les mesures [!UICONTROL Score de page]) fournit une valeur pour votre objectif. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif. Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations.

   La configuration adéquate des mesures de succès est essentielle pour obtenir les données attendues.

   Pour en savoir plus, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

1. (Facultatif) Ajoutez des mesures supplémentaires.
1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** lorsque vous avez terminé de définir vos mesures.

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
