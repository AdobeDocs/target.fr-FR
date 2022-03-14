---
keywords: application mobile;emplacement d’application mobile;application mobile target;emplacements des applications mobiles target;mesures de succès des applications mobiles
description: Consultez un exemple de code pour découvrir comment créer des emplacements et des mesures de succès dans les applications iOS afin d’utiliser Adobe [!DNL Target] pour personnaliser et optimiser votre application.
title: Comment créer [!DNL Target] Emplacements et mesures de succès dans une application iOS ?
feature: Implement Mobile
role: Developer
exl-id: c2f05478-b019-47a7-b1a5-3783929e6732
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 82%

---

# iOS : créez une [!DNL Target] mesure d’emplacement et de succès

Pour utiliser Target dans votre application mobile, vous devez créer un emplacement et une mesure de succès.

Cette section comprend un exemple de code pouvant être utilisé comme modèle pour votre application. Les exemples de cette section contiennent un code pour iOS. Les mêmes modèles s’appliquent à Android. La syntaxe spécifique à Android est disponible dans le guide [](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/target-main.html)Android SDK 4.x pour les solutions Experience Cloud.

>[!NOTE]
>
>Voir [Documentation mobile](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-target-methods.html) pour obtenir la liste de toutes les méthodes Target disponibles.

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
