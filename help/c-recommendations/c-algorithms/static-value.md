---
keywords: règles d’inclusion ; critères d’inclusion ; recommandations ; promotion ; promotions ; filtrage dynamique ; statique ; filtre statique
description: Découvrez comment saisir manuellement une ou plusieurs valeurs statiques à filtrer à l’aide de règles d’inclusion dans Adobe Target.
title: Comment Filtrer Par Valeurs Statiques Dans Les Activités Recommendations ?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 45%

---


# ![Filtre ](/help/assets/premium.png) PREMIUMStatic

Saisissez manuellement une ou plusieurs valeurs statiques à filtrer à l’aide de règles d’inclusion dans [!DNL Adobe Target] [!DNL Recommendations].

Par exemple, ne recommander que le contenu dont l’évaluation est &quot;G&quot; ou &quot;PG&quot; pour Motion Picture Association (MPA).

Vous pouvez créer autant de règles d’inclusion que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

>[!NOTE]
>
>Si vous connaissiez la manière dont les règles d’inclusion étaient configurées avant la version 17.6.1 de Target (juin 2017), vous remarquerez que certains opérateurs et options ont changé. Seuls les opérateurs applicables à l’option sélectionnée s’affichent et certains opérateurs ont été renommés (« correspond à » est devenu « est égal à ») pour être plus cohérents et intuitifs. Toutes les règles d’exclusion existantes créées avant cette version ont été automatiquement migrées vers la nouvelle structure. Aucune restructuration n’est nécessaire de votre part.

## Contenu recommandé classé G ou PG

Pour créer une règle d’inclusion avec des valeurs statiques afin de recommander le contenu avec une note MPA de &quot;G&quot; ou &quot;PG&quot; uniquement (excluez &quot;R&quot; et &quot;NC17&quot;), vous pouvez créer les règles de filtrage suivantes : &quot;la notation cinéma est égale à g&quot; et &quot;la notation cinéma est égale à pg&quot;, comme illustré ci-dessous.

![exemple de notation de film](/help/c-recommendations/c-algorithms/assets/movies.png)

