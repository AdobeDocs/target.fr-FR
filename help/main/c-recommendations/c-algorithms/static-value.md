---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;statique;filtre statique
description: Découvrez comment saisir manuellement une ou plusieurs valeurs statiques à filtrer à l’aide de règles d’inclusion dans Adobe [!DNL Target] Recommendations.
title: Comment Filtrer Par Valeurs Statiques Dans Les Activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 45%

---

# Filtre statique

Saisissez manuellement une ou plusieurs valeurs statiques à filtrer à l’aide des règles d’inclusion dans [!DNL Adobe Target] [!DNL Recommendations].

Par exemple, recommandez uniquement du contenu avec une note MPA (Motion Picture Association) de &quot;G&quot; ou &quot;PG&quot;.

Vous pouvez créer autant de règles d’inclusion que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

>[!NOTE]
>
>Si vous connaissiez la manière dont les règles d’inclusion étaient configurées avant la version 17.6.1 de Target (juin 2017), vous remarquerez que certains opérateurs et options ont changé. Seuls les opérateurs applicables à l’option sélectionnée s’affichent et certains opérateurs ont été renommés (« correspond à » est devenu « est égal à ») pour être plus cohérents et intuitifs. Toutes les règles d’exclusion existantes créées avant cette version ont été automatiquement migrées vers la nouvelle structure. Aucune restructuration n’est nécessaire de votre part.

## Contenu recommandé noté G ou PG

Pour créer une règle d’inclusion avec des valeurs statiques afin de recommander du contenu avec une note MPA de &quot;G&quot; ou &quot;PG&quot; uniquement (exclure le contenu &quot;R&quot; et &quot;NC17&quot;), vous pouvez créer les règles de filtrage suivantes &quot;la notation cinéma est égale à g&quot; et &quot;la notation cinéma égale à pg&quot;, comme illustré ci-dessous.

![Exemple de notation de film](/help/main/c-recommendations/c-algorithms/assets/movies.png)
