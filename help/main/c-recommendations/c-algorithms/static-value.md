---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;statique;filtre statique
description: Découvrez comment saisir manuellement une ou plusieurs valeurs statiques pour filtrer à l’aide des règles d’inclusion dans les recommandations [!DNL Target] d’Adobe.
title: Filtre statique
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: 'https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 2%
---
# Filtre statique {#static-filter}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment filtrer les recommandations en saisissant manuellement une ou plusieurs valeurs statiques dans les règles d’inclusion dans [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

**[!UICONTROL Le filtre statique]** limite les éléments d’une recommandation aux éléments qui correspondent à des valeurs statiques saisies manuellement. Vous pouvez créer un nombre illimité de règles d’inclusion. Les règles d’inclusion sont jointes à un opérateur AND. Par conséquent, toutes les règles doivent être respectées pour qu’un élément soit inclus dans une recommandation. Pour obtenir des informations générales sur les règles d’inclusion, voir [Utiliser des règles d’inclusion dynamiques et statiques](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Contenu recommandé classé G ou PG

Pour ne recommander que du contenu avec une classification de l&#39;association des films (MPA) « G » ou « PG » (exclure le contenu « R » et « NC17 »), créez une règle de filtrage avec l&#39;opérateur « movie-rating equals any of » et saisissez les valeurs « g-rating » et « pg-rating ».
