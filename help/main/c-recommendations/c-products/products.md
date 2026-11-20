---
keywords: produit, collections
description: En savoir plus sur les entités dans Adobe [!DNL Target] Recommendations. Les entités font référence aux éléments que vous souhaitez recommander à l'aide de [!DNL Target], tels que les articles, les films ou les produits.
title: Comment utiliser les entités ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: ffe23eea-b914-4c86-ad54-c63c1cc1c0d7
TQID: 'https://experienceleague.adobe.com/zfISb59XJ5qrD1-FA0syglPPswIL8cA0N0pBpY4tgIE'
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
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%
---
# Prise en main des entités {#get-started-entities}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez les entités dans [!DNL Adobe Target Recommendations] et où les gérer.

>[!ENDSHADEBOX]

Les entités sont les éléments que [!DNL Recommendations] peut recommander. Une entité peut être un produit, un élément de contenu (tel qu’un article, un diaporama, une image, un film ou une émission de télévision), une offre d’emploi, un restaurant, etc.

[!DNL Recommendations] affiche les éléments de vos collections en fonction des critères que vous avez configurés.

## Comment les entités atteignent Recommendations

Les informations sur vos entités peuvent être transmises à [!DNL Recommendations] de plusieurs manières, notamment :

* Avec les [attributs d’entité](/help/main/c-recommendations/c-products/entity-attributes.md) envoyés à partir de vos pages, à l’aide d’une mbox ou de `targetPageParams`.
* Avec [flux](/help/main/c-recommendations/c-products/feeds.md), qui peuvent utiliser des fichiers CSV, le format de flux [!DNL Google Product Search] ou les classifications de produits [!DNL Adobe Analytics].
* Avec l’API de diffusion.

Si [!DNL Target] collecte des données pour un élément à partir d’un flux et d’une mbox, les données les plus récentes sont utilisées.

Les entités chargées et les valeurs d’attribut d’entité expirent après 61 jours. Envoyez à nouveau chaque élément au moins une fois tous les 60 jours. Dans le cas contraire, [!DNL Target] considère que l&#39;élément n&#39;est plus pertinent et le supprime du catalogue.

## Gestion des entités

Utilisez les pages suivantes pour travailler avec vos entités :

* [Attributs d’entité](/help/main/c-recommendations/c-products/entity-attributes.md) et [Attributs d’entité personnalisés](/help/main/c-recommendations/c-products/custom-entity-attributes.md) : définissez les informations de produit ou de contenu que vous transmettez à [!DNL Recommendations].
* [Flux](/help/main/c-recommendations/c-products/feeds.md) : intégrez des informations d’entité ou de contenu à vos recommandations.
* [Recherche catalogue](/help/main/c-recommendations/c-products/catalog-search.md) : recherchez des articles dans votre catalogue.
* [Collections](/help/main/c-recommendations/c-products/collections.md) : configurez vos collections. Une collection est sélectionnée pour chaque expérience lorsque vous créez une activité [!DNL Recommendations].
* [Exclusions](/help/main/c-recommendations/c-products/exclusions.md) : empêcher l’affichage de certains éléments dans vos recommandations. Les exclusions s’appliquent à toutes les activités du compte.
