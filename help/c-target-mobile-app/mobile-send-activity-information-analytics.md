---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: Cette section décrit comment envoyer des informations d’activité d’application mobile Adobe Target à Adobe Analytics pour la segmentation postAhoc.
title: Envoyer des informations sur l'Activité à Adobe Analytics
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 33%

---


# Envoi des informations d’activité à Adobe Analytics{#send-activity-information-to-adobe-analytics}

Cette section décrit comment envoyer [!DNL Target] des informations sur l&#39;activité d&#39;application mobile à l&#39;Adobe [!DNL Analytics] pour la segmentation post hoc.

**Conditions préalables**

* Cette intégration requiert que [!DNL Analytics] et [!DNL Target] soient implémentés à l’aide du SDK mobile.
* Assurez-vous que votre suite de rapports est activée pour recevoir les informations d’activité de [!DNL Target].

   Pour ce faire, il vous suffit généralement d’ajouter le code client [!DNL Target] à la suite de rapports [!DNL Analytics]. Cette fonctionnalité est peut-être déjà activée si vous utilisez l’intégration SiteCatalyst-Test&amp;Target pour les activités web. Contactez le service client Adobe pour toute question concernant cette étape.

1. Récupérez les informations sur l’activité.

   Si vous incluez une chaîne du type suivant dans votre contenu d’expérience, [!DNL Target] renvoie les informations d’activité que vous pouvez envoyer à [!DNL Analytics] :

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

   Dans cet exemple, un noeud avec la variable `tntVal` est ajouté pour obtenir les informations d’activité. Ajoutez un code similaire pour les autres expériences, avec un titre et un message appropriés.

   Cette chaîne fournit un numéro (par exemple 115110:0:0) dans la réponse de [!DNL Target]. Indique l’ID d’activité, l’ID d’expérience et le type de trafic. Voici un exemple de réponse de [!DNL Target] :

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Analysez l’objet JSON.

   Analysez la réponse qui est revenue de [!DNL Target] dans le rappel. Vous pouvez utiliser `NSJSONSerialization` pour analyser cette réponse et la stocker dans un dictionnaire ou un tableau.

   Pour plus d&#39;informations, consultez la [documentation NSJSONSerialization](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error).

1. Envoyez les données à [!DNL Analytics].

   Ajoutez les informations d’activité analysées (telles que `tntVal` dans la réponse ci-dessus) à votre objet de données contextuelles dans un appel [!DNL Analytics] Cet appel [!DNL Analytics] contenant les données contextuelles peut être déclenché immédiatement ou attendre le déclenchement de l&#39;appel suivant [!DNL Analytics].

   Par exemple, cet appel peut être déclenché lors du rappel de l’appel `targetLoadRequest` :

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` est une clé d’événement réservée dans le SDK mobile. La post-classification de la variable `tntVal` dans [!DNL Analytics] fonctionne de la même manière dans le SDK mobile que sur le Web (JavaScript). Une fois les informations traitées dans [!DNL Analytics], les noms des activités et des expériences doivent s&#39;afficher dans l&#39;interface [!DNL Analytics].

