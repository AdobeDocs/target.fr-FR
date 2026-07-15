---
title: Guide de démarrage
description: 'Pour intégrer votre application à des indicateurs, procédez comme suit : de la demande d’accès à la création de votre premier indicateur de fonctionnalité.'
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '436'
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
| **Clients côté serveur** | En cas d’intégration à un SDK côté serveur, vous avez besoin d’un identifiant client d’administration disposant des autorisations appropriées. |
| **Clients de bureau** | Un code de produit et une version de produit peuvent être utilisés à la place d’un identifiant client. |

## Étape 3 : obtenir vos informations d’identification {#step-3-credentials}

Les informations d’identification dont vous avez besoin dépendent de votre chemin d’intégration :

* **Web et mobile (basé sur les balises) :** utilisez le **identifiant de fichier d’environnement** de la propriété de balise publiée. Voir Étape 4a pour savoir comment obtenir ceci.
* **SDK côté serveur :** demandez un **identifiant client de jeton de service** et demandez à la prise en charge des indicateurs de le placer sur la liste autorisée avant de pouvoir effectuer des appels API à partir de SDK.
* **Ordinateur de bureau :** un code de produit et une version de produit peuvent être utilisés à la place d’un identifiant client.

## Étape 4 : Intégration à l’aide d’un SDK {#step-4-integrate}

Suivez les [étapes d’intégration](integration-steps.md) pour votre type d’application. Choisissez le chemin d’accès qui correspond à votre pile :

* **Services web** → Java SDK ou Node.js SDK
* **Applications web et mobiles** → AEP Mobile SDK — consultez les guides [Android](../sdk-releases/android/android-extension-integration-guide.md) et [iOS](../sdk-releases/ios/ios-extension-integration-guide.md)
* **Applications de bureau** → SDK (bientôt disponible)

## Étape 4a : Configurer la collecte de données et publier votre configuration {#step-4a-data-collection}

Si vous intégrez par le biais d’une approche basée sur les balises (web ou mobile), configurez votre propriété de balise avant d’initialiser le SDK :

1. Dans [Collecte de données &#x200B;](https://experience.adobe.com/#/data-collection), ouvrez votre propriété mobile ou web.
1. Installez l’extension **&#x200B;**, puis l’extension **Déploiement d’Experience** (dans cet ordre).
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
* [Étapes d’intégration](integration-steps.md)
* [SDK](sdks.md)

<!-- -->
