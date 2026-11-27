---
keywords: promotions;promotions frontales;promotions dorsales;type de promotions;liste d’éléments;promouvoir par attribut;promouvoir une collection
description: Découvrez comment ajouter des éléments en promotion et contrôler leur emplacement dans vos conceptions Adobe [!DNL Target] Recommendations. Vous pouvez ajouter des promotions statiques et dynamiques.
title: Comment ajouter des promotions dans les conceptions Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
TQID: 'https://experienceleague.adobe.com/tAfKOzwjnUJgypDh-4LdVukNlTVwMS4UkvcNmCaCV0E'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%
---
# Ajout de promotions {#add-promotions}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment ajouter des éléments promus à une conception [!DNL Recommendations] et comment leur ordre de tri est déterminé.

>[!ENDSHADEBOX]

Les promotions placent des éléments spécifiques dans une conception [!DNL Recommendations], en plus des éléments recommandés par les critères. Ils utilisent les emplacements disponibles dans la conception et sont prioritaires sur les résultats des critères et les recommandations de sauvegarde. Par exemple, si une conception comporte six emplacements et que deux d’entre eux sont utilisés pour des promotions, il reste quatre emplacements pour les éléments recommandés en fonction de critères.

Les promotions sont dédupliquées par rapport aux éléments recommandés par les critères de l’activité, de sorte qu’un élément donné n’apparaît pas deux fois dans une seule barre d’état de recommandations.

![Boîte de dialogue Modifier la promotion avec les boutons Promotion avant et Promotion arrière désactivés](assets/add_promotion_toggles.png)

>[!NOTE]
>
>L’utilisation de promotions modifie la structure et la sortie du fichier CSV. Ces modifications peuvent affecter tout processus externe qui implique un fichier CSV, tel qu’un e-mail.

## Ajouter une promotion {#add-promotion}

Une promotion définit les éléments qui font l&#39;objet d&#39;une promotion, le nombre d&#39;emplacements de conception utilisés et la période d&#39;affichage.

1. Sur la page **[!UICONTROL Options]**, cliquez sur le bouton (bascule) **[!UICONTROL Promotion avant]** ou **[!UICONTROL Promotion arrière]**.

   L’illustration suivante présente le bouton bascule **[!UICONTROL Promotion front]** en position « activé ». Les promotions peuvent être insérées avant et après les résultats des critères.

   ![Modifiez la boîte de dialogue de promotion en activant le bouton Promotion avant et en affichant les options Nombre d&#39;emplacements de conception, Planification et Type de promotion](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

1. Définissez le **[!UICONTROL nombre d&#39;emplacements de conception]** à utiliser pour les éléments en promotion.

   Jusqu&#39;à 20 emplacements peuvent être utilisés, selon la conception [!DNL Recommendations]. Chaque emplacement utilisé devient indisponible pour les recommandations renvoyées en fonction des critères.

1. Définissez une date de **Début** et une date de **Fin** pour les éléments promus.

   Si aucune date de début n’est définie, la promotion commence immédiatement. Si aucune date de fin n’est définie, la promotion s’exécute indéfiniment.

1. Sélectionnez un **[!UICONTROL type de promotion]** :

   * **[!UICONTROL Liste d’éléments]** : saisissez les valeurs `entity.id` des éléments à convertir, séparées par des virgules.
   * **[!UICONTROL Promouvoir par attribut]** : ajoutez des règles pour définir les attributs des éléments à promouvoir. Cette option permet des correspondances dynamiques par le biais de règles d’inclusion statiques et dynamiques. Pour obtenir des informations détaillées, des exemples et des scénarios d’utilisation, consultez [Utilisation de règles d’inclusion dynamiques et statiques](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules).
   * **[!UICONTROL Convertir une collection]** : sélectionnez la collection d’éléments à convertir. De nouvelles collections peuvent être créées pour les promotions. Voir [Créer une collection](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08).

   Le type de promotion détermine également l’ordre de tri des éléments promus. Voir [Types de promotion et ordre de tri](#promotion-sort-order).

   ![Boîte de dialogue Modifier la promotion avec les options Type de promotion mises en surbrillance : Liste des éléments, Promouvoir par attribut et Promouvoir une collection](/help/main/c-recommendations/t-create-recs-activity/assets/promotion_type.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Les promotions sont appliquées à toutes les expériences de l’activité.

## Types de promotion et ordre de tri {#promotion-sort-order}

L&#39;ordre de tri des éléments promus dépend du type de promotion, comme le montre le tableau suivant.

| Type de promotion | Tri par défaut | Tri de sauvegarde | Option de filtrage dynamique |
| --- | --- | --- | --- |
| **[!UICONTROL Liste d&#39;éléments]** | Commande saisie dans l’interface utilisateur ou l’API [!DNL Target] | Aléatoire (si sélectionné via l’interface utilisateur ou l’API) | Non |
| **[!UICONTROL Promouvoir par attribut]** | `entity.value` (ordre décroissant) | Aucune randomisation | Oui |
| **[!UICONTROL Promouvoir une collection]** | `entity.value` (ordre décroissant) | Aucune randomisation | Non |

* **[!UICONTROL Liste d’éléments]** : l’ordre de tri par défaut est l’ordre saisi dans l’interface utilisateur ou l’API [!DNL Target]. La case à cocher **[!UICONTROL Randomiser l&#39;ordre des éléments]** est disponible pour ce type. Lorsque la liste inclut plus d’éléments que le nombre d’emplacements définis pour les promotions, cette option rend aléatoire les éléments promus affichés dans la conception. À chaque accès, [!DNL Target] sélectionne de manière aléatoire les éléments activés pour les promotions dans le modèle à partir de l’ensemble des promotions.
* **[!UICONTROL Promouvoir par attribut]** et **[!UICONTROL Promouvoir une collection]** : l’ordre par défaut est basé sur l’attribut `entity.value`, dans l’ordre numérique décroissant. La randomisation de l’ordre n’est pas applicable.

Si les entités ne disposent pas d’un attribut `entity.value` (par exemple, l’entreprise ne vend pas de produits), une valeur numérique telle que la date de publication peut être transmise à l’attribut `entity.value`. Les éléments promus sont ensuite triés par date de publication la plus récente, dans l’ordre décroissant. L&#39;attribut `entity.value` est de type double et n&#39;accepte pas les chaînes.
