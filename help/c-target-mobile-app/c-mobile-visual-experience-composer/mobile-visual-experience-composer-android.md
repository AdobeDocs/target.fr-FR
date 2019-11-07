---
keywords: vec mobile;compositeur d’expérience visuelle mobile;options du compositeur d’expérience mobile;configuration;android
description: La nouvelle bibliothèque de SDK d’Adobe Target permet aux développeurs de procéder à une configuration unique sur leurs applications mobiles Android et permet aux marketeurs d’utiliser les fonctionnalités du compositeur d’expérience visuelle (VEC) mobile.
title: Android - Configuration de l’application mobile pour Adobe Target
topic: Standard
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Android - Configuration de l’application mobile{#android-set-up-the-mobile-app}

Le compositeur d’expérience visuelle (VEC) d’Adobe Target Mobile permet aux développeurs d’effectuer une configuration unique sur leurs applications mobiles Android et de permettre aux spécialistes du marketing d’utiliser les fonctionnalités de l’application Mobile VEC.

Pour plus d’informations sur l’activation de l’extension d’Adobe Target VEC, voir [Adobe Target - Visual Experience Composer](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) dans les *SDK Adobe Experience Platform Mobile*.

## Inclure le SDK Mobile et la bibliothèque Target {#sdk-library}

1. Pour plus d’informations sur l’initialisation de SDK V5, voir [Initialize the SDK and Set Up Tracking](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk) (en anglais).
1. Ajoutez la ligne suivante à la section correspondant aux dépendances :

   ```
   implementation 'com.adobe.marketing.mobile:target:1.+'
   implementation 'com.adobe.marketing.mobile:target-vec:1.+'
   ```

1. L’application Mobile VEC nécessite que les artefacts suivants soient inclus comme dépendance dans `build.gradle`.

   ```
    implementation 'android.arch.lifecycle:extensions:1.1.1'
    implementation 'io.github.sac:SocketclusterClientJava:1.7.5'
    implementation 'com.android.support:support-compat:28.0.0'
    implementation 'com.android.support:support-fragment:28.0.0'
   ```

1. Ajoutez un filtre d’intention dans votre fichier `AndroidManifest.XML`, en choisissant un modèle de lien profond unique pour la création de l’application Mobile VEC (par exemple, `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`) :

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
   
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
   
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. Allez dans votre projet mobile et insérez les lignes suivantes à la fin de `Application::onCreate override` :

   ```
   public class SDKTest extends MultiDexApplication { 
   
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("YOUR_ADOBE_LAUNCH_APP_ID"); 
   
           ... 
           try { 
               TargetVEC.registerExtension(); //Single line code to initialize TargetVEC
               Target.registerExtension();
               Identity.registerExtension();
               Lifecycle.registerExtension();
               Signal.registerExtension();
               MobileCore.start(null);
           } catch (InvalidInitException e) { 
             .. 
           }
       }
   
   /* Rest of Application test goes here ... */
   ```

1. Si votre version ne fonctionne pas, passez en revue les exemples de projets fournis ci-dessous qui devraient être prêts à l’emploi et examinez les changements dans les emplacements suivants :

   1. `Application::OnCreate override`
   1. `AndroidManifest.XML`
   1. `build.gradle` de l’application Android

## Configuration des vues Target sur votre application mobile {#views}

Le SDK Adobe Mobile présente une nouvelle méthode que les développeurs peuvent appliquer chaque fois qu’une nouvelle vue apparaît. En tant que développeur, vous devez vous assurer que les vues sont nommées de façon unique et que l’appel `targetView` se trouve sur le fil d’interface utilisateur principal. Dans cette section, nous allons d’abord expliquer comment insérer correctement ces appels avec deux applications de démonstration différentes et discuter des directives générales sur la façon d’insérer correctement les appels d’API de la vue Target pour n’importe quelle application Android.

>[!NOTE]
>
>Si le paramètre `targetView function` n’est pas déclenché, l’extension VEC tente d’identifier la vue à partir de l’activité Android. Pour les applications qui ne disposent pas de vues dynamiques, cette étape peut être facultative.

Une vue Target peut être déclenchée avec un appel de fonction. Les paramètres de ciblage peuvent éventuellement être fournis avec la vue.

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile App VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

Notre premier exemple de projet est la maquette d’une application d’horaire de bus. Pour configurer cette application pour une utilisation dans l’application Mobile VEC :

1. Dans Android Studio, ouvrez le projet avec le fichier `build.gradle` dans le sous-répertoire `BusBooking` du package.
1. Dans la méthode `DemoApplication::OnCreate`, ajoutez `TargetVEC.registerExtension()` pour enregistrer l’extension Target VEC, ainsi que d’autres extensions.
1. Créez et exécutez l’application.
1. Pour entrer dans le mode de création de l’application Mobile VEC, utilisez [!DNL sdkbetabus://com.adobe.sdkbetabus] comme modèle d’URL et ouvrez le lien profond généré sur l’appareil (voir les instructions ci-dessous).

À partir de cette simple application de réservation de bus, nous utilisons toutes les vues cibles générées automatiquement et associées au cycle de vie de l’activité. De plus, nous démontrons la flexibilité de l’API en appelant l’API de la vue cible sur un élément de vue personnalisé qui est ajouté dynamiquement, en cliquant sur un bouton caché (l’image de l’offre sur l’écran). Cette nouvelle vue cible est implémentée en insérant un appel d’API dans le code figurant dans `OfferDetailsActivity.java:40`. En cliquant sur un bouton caché, un nouvel événement de la vue cible appelé « SURPRISE_VIEW » est déclenché, permettant au marketeur de cibler plus précisément le changement sur l’expérience de l’application.

Insertion de la vue dynamique ciblée :

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause();
        MobileCore.lifecyclePause();
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume();
        MobileCore.lifecycleStart(null);
    } 
}
```

## Configuration des paramètres de profil et autres paramètres globaux {#parameters}

Nous prenons désormais en charge la configuration des paramètres globaux qui seront transmis par chaque appel d’API, ainsi que la transmission des paramètres mbox ou d’affichage aux vues correspondantes.

Paramètres inclus :

* paramètres mbox ou d’affichage
* paramètres de profil
* paramètres de produit
* paramètres de commande

**Prise en charge des paramètres globaux :**

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Transfert de paramètres vers la vue déclenchée suivante :**

Nous fournissons quelques vues automatiques, créées par défaut, comme « `AUTO_<activity|fragment name>` », pour chacune des activités et des fragments figurant dans votre application. Si vous souhaitez transférer ces paramètres, vous pouvez appeler l’API suivante :

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("viewKey1", "viewparam1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilevalueforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Transfert de paramètres vers une vue spécifique :**

Nous avons fait en sorte que l’API déclenche les vues via `TargetVEC.targetView("view_name")`. Vous pouvez aussi transférer des paramètres spécifiques à cette vue, comme illustré ci-dessous :

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## Appel explicite de l’API de prérécupération {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

Dans certains cas, vous pouvez souhaiter rappeler l’API de prérécupération, afin d’actualiser les offres en cache. Les API suivantes sont exposées et décrites ainsi :

* **prefetchOffers**

   ```
   /** 
    * Prefetch Target offers. 
    * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
    * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
    * to call this method inside the containing component's onCreate() lifecycle method 
    */ 
   public static void prefetchOffers();
   ```

* **prefetchOffersBackground**

   ```
   /** 
    * Prefetch Target offers in the background. 
    * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
    * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
    * be applied as Target Views are being triggered. 
    */ 
   public static void prefetchOffersBackground();
   ```

## Didacticiel : Implémentation d’Experience Cloud dans les applications mobiles Android {#tutorial}

* [Implémentation d’Experience Cloud dans les applications mobiles Android (Implement the Experience Cloud in Mobile Android Applications)](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-android-apps-with-launch/index.html)

Après avoir terminé cet didacticiel, vous serez en mesure de :

* Créer une propriété Launch mobile
* Installer une propriété Launch dans une application Android
* Implémenter les solutions Adobe Experience Cloud suivantes :
   * Service Experience Cloud ID
   * Adobe Target
   * Adobe Analytics
   * Adobe Audience Manager

* Publier les modifications dans Launch par le biais d’environnements de développement, d’évaluation et de production
