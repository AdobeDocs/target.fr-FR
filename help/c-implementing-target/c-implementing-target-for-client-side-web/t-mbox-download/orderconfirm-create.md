---
keywords: order confirmation;orderConfirmPage
description: La mbox de confirmation de commande enregistre des détails sur les commandes passées sur votre site, puis rend possible la création de rapports en fonction des recettes et des commandes. Elle contribue également aux algorithmes de recommandation, tels que « Les personnes qui ont acheté le produit x ont également acheté le produit y ».
title: Création d’une mbox de confirmation de commande – mbox.js
feature: null
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 69%

---


# Création d’une mbox de confirmation de commande – mbox.js

La mbox de confirmation de commande enregistre des détails sur les commandes passées sur votre site, puis rend possible la création de rapports en fonction des recettes et des commandes. Elle contribue également aux algorithmes de recommandation, tels que « Les personnes qui ont acheté le produit x ont également acheté le produit y ».

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>* Remarque : Si les utilisateurs effectuent des achats sur votre site web, il est recommandé de mettre en œuvre une mbox de confirmation de commande, même si vous utilisez Analytics for Target (A4T) pour créer vos rapports.
   >
   >
* Vous pouvez également créer une mbox de confirmation de commande pour at.js 1.*l&#39;* utilisation de la même méthode ; toutefois, la  [!DNL at.js] méthode est préférée. Pour plus d’informations, voir [Suivi des conversions](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
   >
   >
* Si vous utilisez at.js 2.*x*,  `mboxCreate` n’est plus pris en charge. Pour la confirmation de commande à l’aide d’at.js 2.*x*, utilisez les API suivantes liées au suivi :  [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) et  [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).


1. Sur votre page des détails de la commande, insérez un script de mbox en respectant le modèle ci-dessous.
1. Remplacez les MOTS EN LETTRES MAJUSCULES par des valeurs dynamiques ou statiques issues de votre catalogue.

   >[!NOTE]
   >
   >Remarque : Utilisez des virgules de séparation pour séparer plusieurs ID de produit.

   **Conseil :** Vous pouvez également transmettre des informations de commande dans une mbox quelconque (qui n’a pas à être nommée `orderConfirmPage`). Vous pouvez également transmettre les informations de la commande dans plusieurs mbox au sein de la même campagne.

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

La mbox de confirmation de commande utilise les paramètres suivants :

| Paramètre | Description |
|--- |--- |
| `orderId` | Valeur unique identifiant une commande pour la comptabilisation de la conversion.<br>L’`orderId` doit être unique. Les commandes en double ne sont pas prises en compte dans les rapports. |
| `orderTotal` | Valeur monétaire de l’achat.<br>Ne transmettez pas le symbole monétaire. Utilisez un point décimal (pas une virgule) pour indiquer les valeurs décimales. |
| `productPurchasedId` (Facultatif) | Liste des ID de produit achetés dans la commande séparés par des virgules.<br>Ces ID de produit s’affichent dans le rapport d’audit pour prendre en charge l’analyse de rapports supplémentaire. |