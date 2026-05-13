---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;statique;filtre statique
description: Découvrez comment saisir manuellement une ou plusieurs valeurs statiques pour filtrer à l’aide des règles d’inclusion dans  [!DNL Target] Recommendations.
title: Comment Filtrer Par Valeurs Statiques Dans Les Activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 43%

---

# [!UICONTROL Static Filter]

Saisissez manuellement une ou plusieurs valeurs statiques à filtrer à l’aide des règles d’inclusion dans [!DNL Adobe Target Recommendations].

Par exemple, recommandez uniquement le contenu dont la classification de l’Association des films (MPA) est « G » ou « PG ».

Vous pouvez créer autant de règles d’inclusion que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

>[!NOTE]
>
>Si vous connaissiez la manière dont les règles d’inclusion étaient configurées avant la version 17.6.1 de Target (juin 2017), vous remarquerez que certains opérateurs et options ont changé. Seuls les opérateurs applicables à l’option sélectionnée s’affichent et certains opérateurs ont été renommés (« correspond à » est devenu « est égal à ») pour être plus cohérents et intuitifs. Toutes les règles d’exclusion existantes créées avant cette version ont été automatiquement migrées vers la nouvelle structure. Aucune restructuration n’est nécessaire de votre part.

## Contenu recommandé classé G ou PG

Pour créer une règle d’inclusion avec des valeurs statiques afin de recommander un contenu avec une évaluation MPA de « G » ou « PG » uniquement (exclure le contenu « R » et « NC17 »), vous pouvez créer les règles de filtrage suivantes : « évaluation film est égale à n’importe lequel entre g » et « évaluation film est égale à n’importe lequel entre pg ».
