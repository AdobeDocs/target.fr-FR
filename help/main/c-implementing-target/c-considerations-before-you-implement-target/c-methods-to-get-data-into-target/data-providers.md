---
keywords: implémenter;implémentation;configuration;configurer;fournisseurs de données
description: Obtenir des données dans [!DNL Target] à l’aide des fournisseurs de données.
title: Comment obtenir des données dans [!DNL Target] Utilisation des fournisseurs de données ?
feature: Implementation
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 55%

---

# Fournisseurs de données

Les fournisseurs de données sont une fonctionnalité qui vous permet de transmettre facilement des données provenant de tiers à [!DNL Adobe Target].

Remarque : Les fournisseurs de données requièrent at.js 1.3 ou version ultérieure.

## Format

Le paramètre `window.targetGlobalSettings.dataProviders` est un tableau de fournisseurs de données.

Pour plus d’informations sur la structure de chaque fournisseur de données, voir [Fournisseurs de données](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}.

## Exemples de cas d’utilisation

Collectez des données auprès d’un tiers (par exemple, un service météorologique, une plateforme de gestion des données, ou même votre propre service Web). Vous pouvez ensuite utiliser ces données pour créer des audiences, cibler du contenu et enrichir le profil du visiteur.

## Avantages de la méthode

Ce paramètre permet aux clients de collecter des données auprès de fournisseurs de données tiers tels que Demandbase, BlueKai ou des services personnalisés, et de les transmettre à Target sous forme de paramètres mbox dans la requête globale mbox.

Cette fonction prend en charge la collecte des données en provenance de fournisseurs multiples via des requêtes synchrones et asynchrones.

Cette approche permet de gérer aisément le scintillement du contenu de la page par défaut, tout en incluant des délais d’attente indépendants pour chaque fournisseur afin de limiter l’impact sur les performances de la page

## Avertissements

Si les fournisseurs de données ont ajouté à `window.targetGlobalSettings.dataProviders` sont asynchrones, elles sont exécutées en parallèle. La requête d’API visiteur est exécutée en parallèle avec des fonctions ajoutées à `window.targetGlobalSettings.dataProviders` pour autoriser un temps d’attente minimal.

at.js ne tente pas de mettre en cache les données. Si le fournisseur de données extrait les données en une seule fois, il doit s’assurer que les données sont mises en cache et que, lorsque la fonction du fournisseur est appelée, les données du cache sont envoyées pour le second appel.

## Exemples de code

Vous trouverez plusieurs exemples dans la section [Fournisseurs de données](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}.

## Liens vers les informations pertinentes

Documentation : [Fournisseurs de données](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)

## Vidéos de formation :

* [Utilisation des fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implémenter les fournisseurs de données dans Adobe Target](https://helpx.adobe.com/fr/target/kt/using/dataProviders-atjs-technical-video-implement.html)
