---
keywords: implémentation ; implémentation ; configuration ; configuration ; fournisseurs de données
description: Récupérez des données dans la Cible à l’aide de fournisseurs de données.
title: Comment puis-je obtenir des données dans la Cible à l’aide des fournisseurs de données ?
feature: Mise en œuvre
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 66%

---

# Fournisseurs de données

Les fournisseurs de données sont une fonctionnalité qui vous permet de transmettre facilement des données de tiers à [!DNL Adobe Target].

Remarque : Les fournisseurs de données nécessitent at.js 1.3 ou version ultérieure.

## Format

Le paramètre `window.targetGlobalSettings.dataProviders` est un tableau de fournisseurs de données.

Pour plus d’informations sur la structure de chaque fournisseur de données, voir [Fournisseurs de données](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Exemples d’utilisation

Collectez des données auprès d’un tiers (par exemple, un service météorologique, une plateforme de gestion des données, ou même votre propre service Web). Vous pouvez ensuite utiliser ces données pour créer des audiences, cibler du contenu et enrichir le profil du visiteur.

## Avantages de la méthode

Ce paramètre permet aux clients de collecter des données auprès de fournisseurs de données tiers tels que Demandbase, BlueKai ou des services personnalisés, et de les transmettre à Target sous forme de paramètres mbox dans la requête globale mbox.

Cette fonction prend en charge la collecte des données en provenance de fournisseurs multiples via des requêtes synchrones et asynchrones.

Cette approche permet de gérer aisément le scintillement du contenu de la page par défaut, tout en incluant des délais d’attente indépendants pour chaque fournisseur afin de limiter l’impact sur les performances de la page

## Avertissements

Si les fournisseurs de données ajoutés à `window.targetGlobalSettings.dataProviders` sont asynchrones, ils sont exécutés en parallèle. La demande d&#39;API du Visiteur est exécutée en parallèle avec les fonctions ajoutées à `window.targetGlobalSettings.dataProviders` pour permettre un temps d&#39;attente minimum.

at.js n’essaie pas de mettre en cache les données. Si le fournisseur de données extrait les données en une seule fois, il doit s’assurer que les données sont mises en cache et que, lorsque la fonction du fournisseur est appelée, les données du cache sont envoyées pour le second appel.

## Exemples de code

Vous trouverez plusieurs exemples dans la section [Fournisseurs de données](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Liens vers les informations pertinentes

Documentation : [Fournisseurs de données](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

## Vidéos de formation :

* [Utilisation des fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implémenter les fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-technical-video-implement.html)