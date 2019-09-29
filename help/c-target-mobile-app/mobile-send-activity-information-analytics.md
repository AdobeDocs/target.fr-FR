---
description: Cette section décrit comment envoyer des informations sur l’activité de l’application mobile Target à Adobe Analytics pour la segmentation postAdHoc.
seo-description: Cette section décrit comment envoyer des informations sur l’activité de l’application mobile Target à Adobe Analytics pour la segmentation postAdHoc.
seo-title: Envoi des informations d’activité à Adobe Analytics
title: Envoi des informations d’activité à Adobe Analytics
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Envoi des informations d’activité à Adobe Analytics{#send-activity-information-to-adobe-analytics}

Cette section décrit comment envoyer des informations sur l’activité de l’application mobile Target à Adobe Analytics pour la segmentation postAdHoc.

**Conditions préalables**

* Cette intégration nécessite qu’Analytics et Target soient implémentés à l’aide du SDK mobile.
* Vérifiez que votre suite de rapports peut recevoir les informations d’activité de Target.

   Pour cela, le code client Target doit généralement être ajouté à la suite de rapports Analytics. Cette fonctionnalité est peut-être déjà activée si vous utilisez l’intégration SiteCatalyst-Test&amp;Target pour les activités web. Contactez le service client Adobe pour toute question concernant cette étape.

1. Récupérez les informations sur l’activité.

   Si vous incluez une chaîne comme celle présentée ci-dessous dans votre contenu d’expérience, Target renvoie les informations de campagne que vous pouvez envoyer à Analytics :

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Remplacez le texte de votre code json d’expérience par un élément comme dans l’exemple suivant :

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   Dans cet exemple, un nœud avec la variable « `tntVal` » est ajouté pour obtenir les informations sur l’activité. Ajoutez un code similaire pour les autres expériences, avec un titre et un message appropriés.

   Cette chaîne fournit un numéro (par exemple 115110:0:0) dans la réponse de Target. Cela indique l’ID d’activité, l’ID d’expérience et le type de trafic. Voici une réponse simple de Target :

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Analysez l’objet JSON.

   Analysez la réponse renvoyée par Target dans le rappel. Vous pouvez utiliser NSJSONSerialization pour analyser cette réponse et la stocker dans un dict ou un tableau.

   Pour plus d’informations, consultez la documentation [sur la](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) sérialisation NSJSONSerialization.
1. Envoyez les données à Analytics.

   Ajoutez les informations d’activité analysées (telles que `tntVal` dans la réponse ci-dessus) à votre objet de données contextuelles dans un appel Analytics. Cet appel Analytics contenant les données contextuelles peut être déclenché immédiatement. Il peut aussi attendre que l’appel Analytics suivant soit déclenché.

   Par exemple, cet appel peut être déclenché lors du rappel de l’appel `targetLoadRequest` :

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` est une clé d’événement réservée dans le SDK mobile. La post-classification de la variable `tntVal` dans Analytics fonctionne de la même manière dans le SDK mobile que sur le web (JavaScript). Une fois les informations traitées dans Analytics, les noms d’activité et d’expérience doivent apparaître dans l’interface Analytics.

