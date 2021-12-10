---
keywords: promotions;promotions front;promotions;rétropromotions;type de promotions;liste d’éléments;promouvoir par attribut;promouvoir une collection
description: Découvrez comment ajouter des éléments en promotion et contrôler leur emplacement dans votre Adobe [!DNL Target] Conceptions Recommendations. Vous pouvez ajouter des promotions statiques et dynamiques.
title: Comment ajouter des promotions dans les conceptions Recommendations ?
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 0d8d04091968923c7d343692140279c026d579f4
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 49%

---

# ![PREMIUM](/help/assets/premium.png) Ajout de promotions

Ajoutez des éléments en promotion et contrôlez leur placement dans votre [!DNL Adobe Target Recommendations] conceptions. Vous pouvez ajouter des promotions statiques et dynamiques.

>[!IMPORTANT]
>
>Les règles d’exclusion statiques et dynamiques sont des fonctionnalités puissantes qui peuvent vous aider dans vos efforts de marketing. Pour obtenir des informations détaillées, des exemples et des scénarios de cas d’utilisation, voir [Utilisation de règles d’inclusion dynamiques et statiques](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

Lorsque vous créez une activité [!DNL Recommendations], vous avez la possibilité d’inclure des éléments en promotion dans votre conception [!DNL Recommendations]. Les promotions utilisent les emplacements disponibles d’une conception et ont priorité sur les résultats des critères et les recommandations de sauvegarde. Par exemple, si votre conception compte six emplacements et que vous utilisez deux d’entre eux pour des promotions, quatre emplacements sont disponibles pour des éléments recommandés en fonction des critères.

Les promotions sont dédupliquées par rapport aux articles recommandés par les critères de votre activité ; un élément donné n’apparaîtra donc pas deux fois dans un bac de recommandations unique.

Vous pouvez promouvoir des éléments spécifiques, promouvoir des éléments de manière dynamique ou en fonction d’attributs, ou promouvoir des collections.

![[!UICONTROL Promotion avant] et [!UICONTROL Promotion Précédente] options dans [!DNL Target] Interface utilisateur](assets/add_promotion_toggles.png)

>[!NOTE]
>
>L’utilisation de promotions modifie la structure et le résultat du CSV. Ces modifications sont susceptibles d’avoir un impact sur les processus externes qui utilisent le format CSV, tels que la messagerie électronique.

1. Sur la page **[!UICONTROL Options]**, activez **[!UICONTROL Promotion avant]** ou **[!UICONTROL Promotion arrière]**.

   L’illustration suivante présente la bascule [!UICONTROL Promotion avant] sur la position « Activé ».

   ![Options d’ajout de promotion avant](/help/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   Vous pouvez insérer des promotions avant *et* après les résultats des critères.

1. Définissez le nombre d’emplacements de conception à utiliser pour les éléments en promotion.

   Vous pouvez utiliser jusqu’à 20 emplacements en fonction de votre conception de [!DNL Recommendations]. Chaque emplacement utilisé devient indisponible pour les recommandations renvoyées en fonction de vos critères.

1. Définissez des dates de début et de fin pour vos éléments en promotion.

   Si vous ne définissez pas de date de début, la promotion commence immédiatement. Si vous ne définissez pas de date de fin, la promotion s’exécute indéfiniment.

1. Sélectionnez un **[!UICONTROL Type de promotion]**.

   * Sélectionnez **[!UICONTROL Liste des éléments]** et entrez les valeurs `entity.id` des éléments spécifiques que vous souhaitez promouvoir, séparées par des virgules.

   * Sélectionnez **[!UICONTROL Promouvoir par attribut]** et ajoutez des règles pour définir les attributs des éléments que vous souhaitez promouvoir.

      Si vous sélectionnez [!UICONTROL Promouvoir par attribut], vous pouvez créer des correspondances dynamiques. Pour plus d’informations, voir [Utilisation de règles d’inclusion dynamiques et statiques](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Sélectionnez **[!UICONTROL Promouvoir une collection]** et choisissez la collection d’éléments que vous souhaitez promouvoir.

      Vous pouvez créer de nouvelles collections à utiliser pour les promotions. Voir [Création d’une collection](/help/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) pour plus d’informations.
   Si vous choisissez **[!UICONTROL Liste des éléments]** comme la propriété **[!UICONTROL Type de promotion]**, vous pouvez sélectionner la variable **[!UICONTROL Ordre des éléments aléatoire]** si vous le souhaitez.

   L’ordre de tri par défaut pour [!UICONTROL Liste des éléments] est basé sur l’ordre dans lequel vous avez saisi [!DNL Target] Interface utilisateur ou API. Si votre liste contient plus d’éléments que le nombre d’emplacements définis pour les promotions, la variable [!UICONTROL Ordre des éléments aléatoire] Cette option aléatoire les éléments en promotion affichés dans votre conception. Si vous sélectionnez cette option, le résultat est [!DNL Target] sélection aléatoire des éléments activés pour les promotions dans le modèle à partir de l’ensemble de promotions complet sur chaque accès.

   Si vos entités n’ont pas de `entity.value` (par exemple, vous ne vendez pas de produits) vous pouvez transmettre une valeur numérique à la variable `entity.value` , par exemple la date de publication. Dans ce cas, les éléments en promotion peuvent être promus selon la date de publication la plus récente, dans l’ordre décroissant. Le `entity.value` est de type double ; il n’accepte pas les chaînes.

   Si vous avez sélectionné la variable **[!UICONTROL Promouvoir par attribut]** ou **[!UICONTROL Promouvoir une collection]** , l’option permettant d’organiser l’ordre de manière aléatoire n’est pas applicable.

   Lors de la promotion d’éléments spécifiques à l’aide de la variable [!UICONTROL Promouvoir par attribut] ou [!UICONTROL Promouvoir une collection] , l’ordre par défaut dans lequel les éléments sont présentés repose sur les options suivantes : `entity.value` , dans l’ordre numérique décroissant.

   Le tableau suivant illustre les différences entre ces options :

   | Type de promotion | Tri par défaut | Tri de sauvegarde | Option de filtrage dynamique |
   | --- | --- | --- | --- |
   | [!UICONTROL Liste des éléments] | Ordre saisi dans l’interface utilisateur/l’API de Target | Aléatoire (lorsqu’il est sélectionné via l’interface utilisateur/l’API) | Non |
   | [!UICONTROL Promouvoir par attribut] | `entity.value` (ordre décroissant) | Pas d’organisation aléatoire | Oui |
   | [!UICONTROL Promouvoir une collection] | `entity.value` (ordre décroissant) | Pas d’organisation aléatoire | Non |

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Les promotions sont appliquées à toutes les expériences de l’activité.
