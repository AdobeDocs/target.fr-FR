---
keywords: application mobile;envoi de données d’application mobile;application mobile target;données utilisateur personnalisées mobiles;données personnalisées d’application mobile
description: Découvrez comment envoyer des informations supplémentaires sur l’emplacement ou l’utilisateur à Adobe [!DNL Target] comme paires nom-valeur pour vous aider à créer des audiences personnalisées.
title: Comment envoyer des données utilisateur personnalisées dans une application iOS ?
feature: Implement Mobile
role: Developer
exl-id: c64219ec-8d60-4d05-b2b8-103e8ffcaefc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 90%

---

# iOS - Envoi de données utilisateur personnalisées

Vous pouvez envoyer des informations supplémentaires sur l’emplacement ou l’utilisateur à Target sous forme de paires nom-valeur.

Ces informations peuvent être utilisées pour créer des audiences personnalisées (par exemple, utilisateurs disposant de plus de 25 000 miles) et créer des rapports.

Il existe deux types de paramètres pouvant être envoyés via un appel Target :

* Paramètres mbox

   Les paramètres de mbox ne persistent pas d’une session à l’autre.
* Paramètres de profil

   Les paramètres de profil ne sont pas stockés dans le magasin des profils de visiteur et persistent d’une session à l’autre. Les paramètres mbox ne sont pas persistants. Tandis que certaines clés sont réservées, les paramètres de profil et mbox peuvent être des paires personnalisées de type clé-valeur.

Bien que certaines clés soient réservées, les paramètres de profil et mbox peuvent contenir des paires clé-valeur personnalisées.

1. Création d’un dictionnaire.

   Commencez par créer un dictionnaire contenant les valeurs que vous avez envoyées pour être transférées à Target. Pour des questions pratiques, ajoutez ces éléments à la méthode `welcomeMessageCampaign` de manière à ne pas devoir vous soucier de la portée.

   Vous trouverez ci-dessous un exemple de dictionnaire. Vous pouvez le copier et le coller dans la méthode `(void)welcomeMessageCampaign`. Les valeurs des clés telles que `userLevel` et `userMiles` sont codées en dur pour cet exemple. En règle générale, vous transférez les variables correspondantes.

   ```
   NSDictionary *targetParams = [[NSDictionary alloc] initWithObjectsAndKeys: 
                                 @"platinum",@"userLevel", 
                                 @26500,@"userMiles", 
                                 @"1067007",@"entity.id", 
                                 @"dealsapp.qa", @"host", 
                                 @"fashion",@"entity.categoryId", 
                                 @"millenial", @"profile.persona", 
                                 @"cohort_5", @"profile.cohort", 
                                 nil];
   ```

   * Les clés contenant un préfixe de profil (par exemple : `profile.persona`) sont stockées au niveau du profil d’utilisateur.

      Ces attributs de profil peuvent être utilisés pour différentes activités et différents canaux.

   * Les clés ne contenant aucun préfixe (par exemple : `userMiles`) sont des paramètres mbox.

      Ces paramètres sont disponibles uniquement lors de la session.

   * Les clés contenant un préfixe d’entité (par exemple : `entity.category.id`) sont utilisées pour des recommandations de produits.

1. Vérification des données.
   1. Dans l’application `didFinishLaunchingWithOptions`, décommentez ou ajoutez `[ADBMobile setDebugLogging:YES];`.

      Cette action imprime les journaux de débogage détaillés.
   1. Création de l’application.
   1. Vérifiez que les paramètres ont été transférés vers l’appel cible.

      Recherchez le nom de votre emplacement cible dans la console de débogage. Vous remarquerez un appel vers `YOUR-CLIENT-CODE.tt.omtrdc.net` contenant l’ensemble des paramètres que vous venez de transférer.

      ![](assets/mobile-debug.png)
   Vous pouvez créer des audiences et restreindre ou cibler l’affichage de certains contenus en utilisant ces paramètres dans Target Standard.
