---
keywords: mobile app;mobile app location;target mobile app;mobile target locations;mobile app success metrics
description: Pour utiliser Target dans votre application mobile, vous devez créer un emplacement et une mesure de succès.
title: iOS - Création d’un emplacement cible et d’une mesure de succès
feature: mobile implementation
topic: Target
uuid: dc39260c-8222-42b3-9f6b-f83be30e3210
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 92%

---


# iOS - Création d’un emplacement cible et d’une mesure de succès{#ios-create-a-target-location-and-success-metric}

Pour utiliser Target dans votre application mobile, vous devez créer un emplacement et une mesure de succès.

Cette section comprend un exemple de code pouvant être utilisé comme modèle pour votre application. Les exemples de cette section contiennent un code pour iOS. Les mêmes modèles s’appliquent à Android. La syntaxe spécifique à Android est disponible dans le guide [](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/target-main.html)Android SDK 4.x pour les solutions Experience Cloud.

>[!NOTE]
>
>See the [Mobile documentation](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-target-methods.html) for a list of all the available Target methods.

Il existe deux méthodes principales pour créer un emplacement Target dans votre application et faire une requête :

* `targetCreateRequestWithName`
* `targetLoadRequest`

1. Création d’un emplacement Target.

   Voici un exemple d’appel permettant de créer une requête :

   ```
   // make your request 
   ADBTargetLocationRequest *myRequest = [ADBMobile targetCreateRequestWithName:@"heroBanner" 
                                                    defaultContent:@"default.png" 
                                                    parameters:nil];
   ```

   | Paramètre | Description |
   |---|---|
   | `ADBTargetLocationRequest *myRequest` | Remplacez `myRequest` par le nom de votre `targetLocation` dans l’application. |
   | `targetCreateRequestWithName:@"heroBanner"` | Remplacez `heroBanner` par le nom de votre `targetLocation` dans Target. Il s’agit du même nom que celui de la mbox. Cette bannière à forte identification apparaît dans l’interface de Target. |
   | `defaultContent:@"default.png"` | Remplacez `default.png` par la valeur utilisée par l’application lorsque Target ne répond pas. |
   | `parameters:nil` | Précisez le profil ou les paramètres mbox. Obtenez des informations complémentaires dans la section « Diffusion de données personnalisées ». |

   Voici un exemple d’appel permettant de charger la requête :

   ```
   // load your request 
   [ADBMobile targetLoadRequest:myRequest callback:^(NSString *content) { 
                                        // do something with content 
                                        heroImage.image = [UIImage imageNamed:content]; 
   }];
   ```

   | Paramètre | Description |
   |---|---|
   | `targetLoadRequest:myRequest` | Remplacez `myRequest` par le nom de votre `targetLocation` dans l’application. |
   | `NSString *content` | Remplacez le contenu par le contenu actuel provenant d’Adobe. La chaîne peut être au format XML, JSON ou brut. Utilisez cette section du code pour définir les variables, configurer les chemins des images, afficher les commandes de flux, les points de transaction ou toute autre action de votre choix. Target rendra le contenu saisi au niveau de l’interface utilisateur exactement au même format. |
   | `heroImage.image = [UIImage imageNamed:content];` | Par exemple : définissez le contenu et configurez le chemin d’une image à forte identification. |

1. Création d’une mesure de succès.

   La méthode `targetCreateOrderConfirmRequestWithName` peut être utilisée pour suivre une mesure de conversion/succès dans votre application.

   ```
   ADBTargetLocationRequest *req = [ADBMobile targetCreateOrderConfirmRequestWithName: "orderConfirm" 
                                              orderId: orderId 
                                              orderTotal: @"39.95" 
                                              productPurchasedId: _galleryItem.title 
                                              parameters: nil]; 
   [ADBMobile targetLoadRequest: req callback: nil];
   ```

   | Paramètre | Description |
   |---|---|
   | `orderId` | Remplacez cette valeur par une variable dynamique qui représente un ID de commande unique. |
   | `@"39.95"` | Remplacez cette valeur par une variable dynamique qui représente un total de commande unique. |
   | `_galleryItem.title` | Remplacez cette valeur par une variable dynamique qui représente une liste de produits achetés, délimités par des virgules. |
   | `parameters: nil` | Dictionnaire facultatif des paramètres supplémentaires. |

1. Création de l’application.

   Une fois votre emplacement cible créé et le balisage d’une mesure de succès effectué, créez un test A/B. L’activité peut être créée en utilisant le compositeur d’expérience d’après les formulaires.
