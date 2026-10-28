---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;statique;filtre statique
description: Découvrez comment saisir manuellement une ou plusieurs valeurs statiques pour filtrer à l’aide des règles d’inclusion dans les recommandations de [!DNL Target] Adobe.
title: Comment Filtrer Par Valeurs Statiques Dans Les Activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
source-git-commit: 7f111df77c4b368dbe000a699ee19f5ff1ea266f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 30%
---
# Filtre statique

Saisissez manuellement une ou plusieurs valeurs statiques pour filtrer à l’aide des règles d’inclusion dans [!DNL Adobe Target] [!DNL Recommendations].

Par exemple, recommandez uniquement le contenu dont la classification de l’Association des films (MPA) est « G » ou « PG ».

Vous pouvez créer autant de règles d’inclusion que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

>[!NOTE]
>
>Si vous connaissez la configuration des règles d’inclusion avant la version Target 17.6.1 (juin 2017), vous remarquerez que certaines des options et certains des opérateurs ont changé. Seuls les opérateurs applicables à l’option sélectionnée s’affichent et certains opérateurs ont été renommés (« correspond à » est devenu « est égal à ») pour être plus cohérents et intuitifs. Toutes les règles d’exclusion existantes créées avant cette version ont été automatiquement migrées vers la nouvelle structure. Aucune restructuration n’est nécessaire de votre part.

## Contenu recommandé classé G ou PG

Pour créer une règle d&#39;inclusion avec des valeurs statiques afin de recommander un contenu avec une évaluation MPA de « G » ou « PG » uniquement (exclure le contenu « R » et « NC17 »), vous pouvez créer les règles de filtrage suivantes « évaluation film égale à g-rating » et « évaluation film égale à pg-rating », comme illustré ci-dessous.

![exemple d’évaluation des films](/help/main/c-recommendations/c-algorithms/assets/movies.png)
