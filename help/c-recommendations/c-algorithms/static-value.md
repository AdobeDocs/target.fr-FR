---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Saisissez manuellement une ou plusieurs valeurs statiques à filtrer à l’aide de règles d’inclusion dans Adobe Target.
title: Filtrer par valeurs statiques dans les règles d’inclusion dans Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 73%

---


# ![Filtre statique PREMIUM](/help/assets/premium.png)

Saisissez manuellement une ou plusieurs valeurs statiques à filtrer à l’aide de règles d’inclusion dans [!DNL Adobe Target][!DNL Recommendations].

Par exemple, recommandez uniquement le contenu avec une note MPAA de « G » ou « PG ».

>[!NOTE]
>
>Si vous connaissiez la manière dont les règles d’inclusion étaient configurées avant la version 17.6.1 de Target (juin 2017), vous remarquerez que certains opérateurs et options ont changé. Seuls les opérateurs applicables à l’option sélectionnée s’affichent et certains opérateurs ont été renommés (« correspond à » est devenu « est égal à ») pour être plus cohérents et intuitifs. Toutes les règles d’exclusion existantes créées avant cette version ont été automatiquement migrées vers la nouvelle structure. Aucune restructuration n’est nécessaire de votre part.

Vous pouvez créer autant de règles d’inclusion que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.