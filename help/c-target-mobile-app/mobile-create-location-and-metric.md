---
keywords: application mobile;emplacement d’application mobile;application mobile target;emplacements des applications mobiles target;mesures de succès des applications mobiles
description: Vue d’exemples de code pour vous aider à apprendre à créer des emplacements et des mesures de réussite dans les applications iOS afin que vous puissiez utiliser l’Adobe [!DNL Target] pour personnaliser et optimiser votre application.
title: Comment créer des  [!DNL Target] emplacements et des mesures de réussite dans une application iOS ?
feature: Mise en oeuvre de Mobile
role: Developer
exl-id: c2f05478-b019-47a7-b1a5-3783929e6732
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 81%

---

# iOS : créez un emplacement [!DNL Target] et une mesure de réussite.

Pour utiliser Target dans votre application mobile, vous devez créer un emplacement et une mesure de succès.

Cette section comprend un exemple de code pouvant être utilisé comme modèle pour votre application. Les exemples de cette section contiennent un code pour iOS. Les mêmes modèles s’appliquent à Android. La syntaxe spécifique à Android est disponible dans le guide [](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/target-main.html)Android SDK 4.x pour les solutions Experience Cloud.

>[!NOTE]
>
>Pour obtenir la liste de toutes les méthodes de Cible disponibles, consultez la [documentation mobile](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-target-methods.html).

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
