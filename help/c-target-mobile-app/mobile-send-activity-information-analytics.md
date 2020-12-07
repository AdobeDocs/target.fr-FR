---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: Cette section décrit comment envoyer des informations d’activité d’application mobile Adobe Target à Adobe Analytics pour la segmentation postAhoc.
title: Envoyer des informations sur l’activité Adobe Target à Adobe Analytics
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 34%

---


# Envoi des informations d’activité à Adobe Analytics{#send-activity-information-to-adobe-analytics}

This section describes how to send [!DNL Target] mobile app activity information to Adobe [!DNL Analytics] for post hoc segmentation.

**Conditions préalables**

* This integration requires that [!DNL Analytics] and [!DNL Target] are implemented using the mobile SDK.
* Ensure that your report suite is enabled to receive activity information from [!DNL Target].

   This is usually done by adding the [!DNL Target] client code to the [!DNL Analytics] report suite. Cette fonctionnalité est peut-être déjà activée si vous utilisez l’intégration SiteCatalyst-Test&amp;Target pour les activités web. Contactez le service client Adobe pour toute question concernant cette étape.

1. Récupérez les informations sur l’activité.

   If you include a string like the following in your experience content, [!DNL Target] returns the activity information that you can send to [!DNL Analytics]:

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Remplacez le texte de votre code json d’expérience par un élément comme dans l’exemple suivant :

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   In this example, a node with the variable `tntVal` is added to obtain the activity information. Ajoutez un code similaire pour les autres expériences, avec un titre et un message appropriés.

   Cette chaîne fournit un numéro (par exemple 115110:0:0) dans la réponse de [!DNL Target]. Indique l’ID d’activité, l’ID d’expérience et le type de trafic. The following is a sample response from [!DNL Target]:

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Analysez l’objet JSON.

   Parse the response that came back from [!DNL Target] in the callback. You can use `NSJSONSerialization` to parse this response and store it in a dictionary or an array.

   Pour plus d&#39;informations, consultez la documentation [](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) NSJSONSerialization.

1. Envoyez les données à [!DNL Analytics].

   Ajoutez les informations d’activité analysées (telles que `tntVal` dans la réponse ci-dessus) à votre objet de données contextuelles dans un appel [!DNL Analytics] This [!DNL Analytics] call containing the context data can be fired immediately or it can wait until the next [!DNL Analytics] call is fired.

   Par exemple, cet appel peut être déclenché lors du rappel de l’appel `targetLoadRequest` :

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` est une clé d’événement réservée dans le SDK mobile. The post-classification of the `tntVal` variable in [!DNL Analytics] works in the same way in the mobile SDK as it does on the web (JavaScript). After the information is processed in [!DNL Analytics], you should see activity and experience names in the [!DNL Analytics] interface.

