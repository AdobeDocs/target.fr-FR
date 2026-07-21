---
title: Guide de démarrage
description: 'Pour intégrer votre application à des indicateurs, procédez comme suit : de la demande d’accès à la création de votre premier indicateur de fonctionnalité.'
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 9a4e16418c93fa163d821409a0eecb251f2a9929
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 1%

---

# Guide de démarrage {#startup-guide}

Pour intégrer des indicateurs à votre application, procédez comme suit.

## Étape 1 : Demander l&#39;accès {#step-1-access}

Demandez l’accès à la console Indicateurs et rejoignez votre équipe. Consultez [Demande d’accès](../console/request-access.md) pour obtenir des instructions détaillées.

## Étape 2 : intégration de votre application {#step-2-onboard}

Après avoir obtenu l’accès, connectez-vous à la console Indicateurs et vérifiez que votre application est répertoriée sous votre équipe. Si ce n’est pas le cas, demandez à l’administrateur de votre équipe de l’ajouter. Voir [Intégration de votre application](../applications/onboard-your-application.md).

Avant l’intégration, préparez les éléments suivants :

| Exigence | Détails |
|---|---|
| **ID de l’application** | Identifiant client unique utilisé lors de l’appel des API Flags. Utilisez l’identifiant client existant de votre application, le cas échéant. |

## Étape 3 : obtenir votre identifiant de fichier d’environnement {#step-3-credentials}

L’identifiant de fichier d’environnement dont vous avez besoin dépend de votre chemin d’intégration :

* **Web et mobile (basé sur les balises) :** utilisez le **identifiant de fichier d’environnement** de la propriété de balise publiée. Voir Étape 4a pour savoir comment obtenir ceci.

## Étape 4 : Intégration à l’aide d’un SDK {#step-4-integrate}

Suivez le guide d’intégration correspondant à votre type d’application. Choisissez le chemin d’accès qui correspond à votre pile :

* **Applications web et mobiles** — consultez les guides [Android](../sdk-releases/android/android-extension-integration-guide.md), [iOS](../sdk-releases/ios/ios-extension-integration-guide.md) et [Web](../sdk-releases/web/web-extension-integration-guide.md) dans la section du guide d’intégration

## Étape 4a : Configurer la collecte de données et publier votre configuration {#step-4a-data-collection}

Si vous intégrez par le biais d’une approche basée sur les balises (web ou mobile), configurez votre propriété de balise avant d’initialiser le SDK :

1. Dans [Collecte de données &#x200B;](https://experience.adobe.com/#/data-collection), ouvrez votre propriété mobile ou web.
1. Installez l’extension **&#x200B;**, puis l’extension **Flags** (dans cet ordre).
1. Sélectionnez votre **flux de données** (doit inclure le jeu de données Customer Journey Analytics) et votre domaine Edge.
1. Publiez la configuration via **Développement → Évaluation → Production**.
1. Copiez le **ID du fichier d’environnement** de l’onglet **Environnements** — vous l’utiliserez pour initialiser le SDK.

>[!IMPORTANT]
>
>Dans l’environnement **staging**, faites précéder l’ID du fichier d’environnement de `staging/`, c’est-à-dire utilisez `staging/<environmentId>`. En **production**, utilisez directement l’identifiant du fichier d’environnement.

## Étape 5 : créer et tester votre premier indicateur de fonctionnalité {#step-5-feature-flag}

Une fois l’intégration terminée, créez votre premier indicateur de fonctionnalité dans la console et testez-le :

* [Créer votre premier indicateur de fonctionnalité](../feature-flags/create-your-first-feature-flag.md)

## Voir également {#see-also}

* [Intégration d’indicateurs dans l’application](integrating-in-your-app.md)
* [SDK](sdks.md)

<!-- -->
