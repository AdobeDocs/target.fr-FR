---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Saisissez manuellement une ou plusieurs valeurs statiques à filtrer à l’aide de règles d’inclusion dans Adobe Target.
title: Filtrer par valeurs statiques dans les règles d’inclusion dans Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 75%

---


# ![Filtre statique PREMIUM](/help/assets/premium.png)

Saisissez manuellement une ou plusieurs valeurs statiques à filtrer à l’aide de règles d’inclusion dans Adobe Target.

Par exemple, recommandez uniquement le contenu avec une note MPAA de « G » ou « PG ».

Opérateurs disponibles :

* est égal à
* n’est pas égal à
* contient
* ne contient pas
* commence par
* se termine par
* la valeur est présente
* la valeur est absente
* est supérieur ou égal à
* est inférieur ou égal à

>[!NOTE]
>
>Si vous connaissiez la manière dont les règles d’inclusion étaient configurées avant la version 17.6.1 de Target (juin 2017), vous remarquerez que certains opérateurs et options ont changé. Seuls les opérateurs applicables à l’option sélectionnée s’affichent et certains opérateurs ont été renommés (« correspond à » est devenu « est égal à ») pour être plus cohérents et intuitifs. Toutes les règles d’exclusion existantes créées avant cette version ont été automatiquement migrées vers la nouvelle structure. Aucune restructuration n’est nécessaire de votre part.

Vous pouvez créer autant de règles d’inclusion que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.