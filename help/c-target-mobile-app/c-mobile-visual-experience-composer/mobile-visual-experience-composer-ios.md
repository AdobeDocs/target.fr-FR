---
description: Le compositeur d'expérience visuelle d'Adobe Target Mobile permet aux développeurs de procéder à une configuration unique sur leurs applications mobiles ios et de permettre aux marketeurs d'utiliser les fonctionnalités du compositeur d'expérience visuelle pour mobiles.
keywords: Compositeur d'expérience visuelle pour mobile ; compositeur d'expérience visuelle mobile ; options du compositeur d'expérience mobile ; setting - up ; ios ; apple
seo-description: Le compositeur d'expérience visuelle d'Adobe Target Mobile permet aux développeurs de procéder à une configuration unique sur leurs applications mobiles ios et de permettre aux marketeurs d'utiliser les fonctionnalités du compositeur d'expérience visuelle pour mobiles.
seo-title: iOS - Configuration de l’application mobile
solution: Target
title: iOS - Configuration de l’application mobile
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
translation-type: tm+mt
source-git-commit: 29e82d6bcb42b0f05b0b175be7df017184358c38

---


# iOS - Configuration de l’application mobile{#ios-set-up-the-mobile-app}

Le compositeur d&#39;expérience visuelle d&#39;Adobe Target Mobile permet aux développeurs d&#39;effectuer une configuration unique sur leurs applications mobiles ios et de permettre aux spécialistes du marketing d&#39;utiliser les fonctionnalités du compositeur d&#39;expérience visuelle.

Pour plus d&#39;informations sur l&#39;activation de l&#39;extension d&#39;Adobe Target VEC, voir [Adobe Target - Compositeur d&#39;expérience visuelle](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) dans *les SDK Adobe Experience Platform Mobile*.

## Inclusion du SDK mobile et de la bibliothèque Target {#sdk-library}

1. Ajoutez la bibliothèque à votre projet via votre [!DNL Podfile] Cocoapods en ajoutant le pod &#39;`ACPTargetVEC`&#39;.
1. Ouvrez votre projet d’application Objective-C dans XCode.
1. Accédez aux paramètres de génération de votre projet et définissez Toujours les bibliothèques standard « Embed » sur Oui si elles n&#39;ont pas déjà été définies.
1. Dans les paramètres de génération de projet, recherchez « Other linker flags » et ajoutez `$(inherited)` s’il n’est pas déjà présent.
1. Pour le projet objective-C uniquement : créez un fichier Swift pour créer l’en-tête de liaison. Elle configure votre environnement d’application pour Swift.
1. Ajoutez le gestionnaire deeplink :

   1. Dans les paramètres de projet de votre application, cliquez sur **[!UICONTROL Infos]**.
   1. Sous **[!UICONTROL Types d&#39;URL]**, cliquez sur le triangle pour l&#39;ouvrir, puis cliquez sur le signe plus pour ajouter un nouveau champ.
   1. Ajoutez les informations suivantes :

      * Identificateur: `com.adobe.sdktest`
      * Modèles d&#39;URL : `vectester`
      * Rôle : Éditeur
   1. Cliquez en dehors des paramètres de projet de l’application &gt; **[!UICONTROL Général]**.
   1. Cliquez à nouveau sur les paramètres de projet de votre application &gt; **[!UICONTROL Infos]** pour vérifier que vos paramètres ont été enregistrés.

      Avec l’exemple de type d’URL, le modèle d’URL de votre application sera :

      ```
      vectester://com.adobe.sdktest
      ```


1. Dans XCode, ouvrez votre fichier [!DNL AppDelegate].
1. En haut du fichier, ajoutez la ligne suivante à la fin de vos importations :

   `#import "ACPTargetVEC.h"`

   Si vous utilisez Swift, ajoutez la ligne suivante :

   `import ACPTargetVEC`

1. Dans le fichier [!DNL AppDelegate], ajoutez la ligne suivante à `AppDelegate::application:didFinishLaunchingWithOptions:`. Si la fonction de délégation n’est pas définie, créez-la et ajoutez la ligne suivante pour l’application Objective-C ou Swift, respectivement :

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY (Skip any framework which is not applicable for you): 
   [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
   [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
   [ACPLifecycle registerExtension]; 
   [ACPIdentity registerExtension]; 
   [ACPUserProfile registerExtension]; 
   [ACPTarget registerExtension];
   
   [ACPTargetVEC registerExtension];
   [ACPCore start:^{
        [ACPCore lifecycleStart:nil];
   }];
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
   ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
   ACPLifecycle.registerExtension() 
   ACPIdentity.registerExtension() 
   ACPUserProfile.registerExtension() 
   ACPTarget.registerExtension() 
   
   ACPTargetVEC.registerExtension() 
   
   ACPCore.start {
     ACPCore.lifecycleStart(nil)
   }
   ```

   Par exemple, la méthode devrait ressembler à l’exemple suivant :

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
        // Override point for customization after application launch. 
       [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
       [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
       [ACPLifecycle registerExtension]; 
       [ACPIdentity registerExtension]; 
       [ACPUserProfile registerExtension]; 
       [ACPTarget registerExtension]; 
   
       [ACPTargetVEC registerExtension]; 
   
       [ACPCore start:nil]; 
       [ACPCore lifecycleStart:nil]; 
   
      return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) 
   { 
       ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
       ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
       ACPLifecycle.registerExtension() 
       ACPIdentity.registerExtension() 
       ACPUserProfile.registerExtension() 
       ACPTarget.registerExtension() 
   
       ACPTargetVEC.registerExtension() 
   
       ACPCore.start(nil) 
       ACPCore.lifecycleStart(nil)
   
       return true 
   
   }
   ```

1. Ajoutez la ligne suivante au début de `AppDelegate:application:openURL`. Si la fonction de délégation n’est pas définie, créez-la et ajoutez la ligne suivante.

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   [ACPTargetVEC handleDeepLink:url];
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   ACPTargetVEC.handleDeepLink(url)
   ```

   Par exemple, la méthode devrait ressembler à l’exemple suivant :

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY:
   -  (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
    [ACPTargetVEC handleDeepLink:url];
    return YES;
   }
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY:
   func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
      ACPTargetVEC.handleDeepLink(url)
      return true;
   }
   ```

1. Générez et exécutez votre application et utilisez-la pour tester les fonctionnalités d&#39;un compositeur d&#39;applications mobiles.

## Configuration des vues Target sur votre application mobile {#views}

Le SDK Adobe Mobile présente une nouvelle méthode que les développeurs peuvent appliquer chaque fois qu’une nouvelle vue apparaît. Veuillez consulter les instructions générales sur la manière d&#39;insérer correctement les appels d&#39;API de vue Target pour une application ios. Dans iOS, toutes les vues cibles sont définies par rapport au `UIViewController` dans lequel elles apparaissent. Ainsi, contrairement à Android, l’insertion de `TargetViews` est limitée aux appels suivants.

L&#39;extension VEC d&#39;application mobile Adobe Mobile génère automatiquement des noms pour que vous `UIViewControllers` interactiviez dans la structure d&#39;un compositeur d&#39;applications mobiles, en fonction du nom de classe du sous-classé `UIViewController`. Si vous souhaitez remplacer ces noms, vous pouvez appeler la méthode suivante dans `viewWillAppear``ViewController`.

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

Le SDK d’Adobe Mobile propose également une autre méthode permettant aux développeurs de cibler des vues personnalisées au cours de l’exécution. En tant que développeur, vous devez vous assurer que les vues sont nommées de façon unique. Appelez la méthode suivante avant d&#39;ajouter la vue `superview`:

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## Définition - configuration des paramètres de profil et d&#39;autres paramètres globaux {#parameters}

Nous prenons maintenant en charge la définition de paramètres globaux transmis dans chaque appel d&#39;API, ainsi que la transmission des paramètres mbox/view aux vues correspondantes.

Paramètres inclus :

* paramètres mbox ou d’affichage
* paramètres de profil
* paramètres de produit
* paramètres de commande

**Prise en charge des paramètres globaux :**

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setGlobalRequest(targetParams)
```

**Transfert de paramètres vers la vue déclenchée suivante :**

Nous avons fourni des vues automatiques créées par défaut, telles que « `AUTO_<viewControllerName>`pour chaque contrôleur de vue présent dans votre application ». Si vous souhaitez transférer ces paramètres, vous pouvez appeler l’API suivante :

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setRequest(targetParams)
```

**Transfert de paramètres vers une vue spécifique :**

Nous avons constaté que l&#39;API déclenchait les vues via `TargetVEC.targetView("view_name")`. Vous pouvez aussi transférer des paramètres spécifiques à cette vue, comme illustré ci-dessous :

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## Appel explicite de l&#39;API de prérécupération {#section_373DB4527FC649C58FBA3DF0C18C9836}

Dans certains cas, vous pouvez souhaiter rappeler l’API de prérécupération, afin d’actualiser les offres en cache. Les API suivantes sont exposées et décrites ainsi :

**Prérécupérer les offres :**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI. 
 */ 
+ (void) prefetchOffers;
```

**Prérécupérer les offres en arrière-plan :**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI. 
 */ 
+ (void) prefetchOffersBackground;
```

## Didacticiels : Mise en œuvre d&#39;Experience Cloud dans Mobile ios Objective-C et les applications Swift {#tutorial}

* [Mise en œuvre de Experience Cloud dans les applications Objective-C d&#39;ios Mobile](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-objective-c-apps-with-launch/index.html)
* [Mise en œuvre de Experience Cloud dans les applications rapides ios Mobile](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-swift-apps-with-launch/index.html)

Une fois ces didacticiels terminés, vous pouvez :

* Création d&#39;une propriété Launch mobile
* Installation d&#39;une propriété Launch dans une application Objective-C ou Swift
* Implémentez les solutions Adobe Experience Cloud suivantes :
   * Service Experience Cloud ID
   * Adobe Target
   * Adobe Analytics
   * Adobe Audience Manager

* Publier les modifications au lancement par le biais des environnements de développement, d&#39;évaluation et de production