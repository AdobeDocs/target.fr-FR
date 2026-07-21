---
title: Règles d’audience complexes
description: Découvrez comment utiliser des ensembles de règles d’audience volumineux ou complexes dans les indicateurs, y compris les limites de valeurs en bloc et comment fractionner les règles sur plusieurs conditions.
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 2%

---

# Règles d’audience complexes {#complex-rules}

## Utilisation d’une logique imbriquée pour les règles complexes {#nested-logic}

La logique imbriquée vous permet de combiner plusieurs conditions d’audience avec un contrôle ET/OU précis. Pour l’activer :

1. Ajoutez les conditions d’audience dont vous avez besoin.
2. Activez **Logique imbriquée** dans la section Règles d’audience .
3. Un numéro est attribué à chaque condition. Saisissez une expression logique qui fait référence à ces nombres, par exemple :
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

## Voir également {#see-also}

* [Audience dans les indicateurs de fonctionnalité et les groupes de fonctionnalités](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
