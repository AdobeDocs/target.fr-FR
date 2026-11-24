---
keywords: conception de recommandations, créer une conception, copier une conception
description: Découvrez comment créer une conception [!DNL Target Recommendations] à l’aide d’une conception par défaut ou en créant une conception personnalisée pour s’adapter au mieux à la disposition d’une page.
title: Création d’une conception
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
TQID: 'https://experienceleague.adobe.com/GLWcKaQGl6TmL9i7LYUiYepg6SkAjBtL-78-zlaWCTk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 11%
---
# Création d’une conception {#create-design}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer, modifier, copier et supprimer des conceptions dans [!DNL Adobe Target Recommendations] et comment renvoyer des recommandations au format JSON.

>[!ENDSHADEBOX]

Une conception définit la manière dont les recommandations s’affichent sur une page. Une conception peut être basée sur une conception par défaut ou créée en tant que conception personnalisée. L’écran **[!UICONTROL Recommendations]** > **[!UICONTROL Conceptions]** affiche les cartes de conception par défaut et les conceptions créées dans le compte.

* Une conception par défaut ne peut pas être modifiée ni supprimée.
* Une conception personnalisée peut être modifiée, copiée ou supprimée.
* Pour créer une conception basée sur une conception par défaut, copiez d&#39;abord la conception, puis modifiez la copie.

Une conception peut être créée pendant le processus de création d’activité à partir du **[!UICONTROL Compositeur d’expérience visuelle]** (VEC) ou de la bibliothèque de conception en dehors de la création d’activité. Les étapes suivantes supposent que la conception est créée à partir de la bibliothèque, mais les étapes sont similaires.

## Création d’une conception à partir de la bibliothèque {#steps}

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Conceptions]** pour afficher la bibliothèque **[!UICONTROL Conceptions]**.

1. Commencez la conception de l’une des manières suivantes :

   * Pour baser la conception sur une conception par défaut ou sur une conception existante, cliquez sur l’icône Autres actions ( ![icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) de cette conception, puis cliquez sur **[!UICONTROL Copier]**. La boîte de dialogue **[!UICONTROL Créer une conception]** s’affiche. La copie modifiée devient une nouvelle conception personnalisée.
   * Pour créer entièrement une conception personnalisée, cliquez sur **[!UICONTROL Créer une conception]**.

     ![Bibliothèque de conceptions avec le bouton Créer une conception en surbrillance](../assets/design_1.png)

1. Saisissez un **[!UICONTROL Nom]** et sélectionnez une image d’aperçu facultative à afficher sur la carte de conception.

   Lorsqu’une conception par défaut est utilisée, le nom de la conception suivi de « Copier » apparaît dans le champ **[!UICONTROL Nom du contenu]**. Le nom peut être modifié.

1. (Conditionnel) Modifiez la conception **[!UICONTROL Code]**, selon vos besoins.

   Les conceptions de recommandations utilisent le langage de conception libre Velocity. Pour plus d’informations sur Velocity, voir [https://velocity.apache.org](https://velocity.apache.org) et [Personnaliser une conception à l’aide de Velocity](/help/main/c-recommendations/c-design-overview/customizing-a-template.md).

   Une conception peut être au format HTML ou non HTML. Par défaut, les conceptions HTML sont encapsulées avec une balise `<div>` pour permettre le suivi des clics dans un environnement web. Les conceptions non HTML sont réservées aux environnements non web dans lesquels le suivi des clics n’est pas possible. Faites glisser le bouton bascule **[!UICONTROL Conception HTML]** en position « désactivé » pour utiliser du code non HTML.

   >[!NOTE]
   >
   >Le nombre maximal d&#39;entités pouvant être référencées dans une conception, que ce soit par des boucles codées en dur ou traversantes, est de 99.

1. Cliquez sur **[!UICONTROL Créer]**.

1. Cliquez sur l’icône Plus d’actions (![Icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) de la conception à modifier, copier ou supprimer, puis cliquez sur l’option appropriée : **[!UICONTROL Modifier]**, **[!UICONTROL Copier]** ou **[!UICONTROL Supprimer]**.

   ![Bibliothèque de conceptions avec le menu Autres actions ouvert, affichant Modifier, Copier et Supprimer](../assets/design_2.png)

Les conceptions sont disponibles sur l’ensemble du compte. L’utilisation sur plusieurs comptes doit être prise en compte avant la suppression d’une conception. Les conceptions supprimées ne peuvent pas être récupérées.

## Exemple JSON {#json-example}

L’exemple suivant montre comment les réponses JSON peuvent être renvoyées lorsqu’une activité est configurée avec l’[éditeur basé sur les formulaires](/help/main/c-experiences/form-experience-composer.md).

1. Créez une conception à partir de la **[!UICONTROL bibliothèque de conception]** ou dans le workflow basé sur les formulaires. Une conception créée dans le workflow du **[!UICONTROL compositeur d’expérience visuelle]** (VEC) ne peut être qu’une conception HTML, encapsulée dans un `<div>` à des fins de suivi des clics.

1. Assurez-vous que l’option **[!UICONTROL Conception HTML]** est désactivée :

   ![Bouton bascule de conception HTML en position désactivée](/help/main/c-recommendations/c-design-overview/assets/html_design_toggle.png)

1. Collez du code tel que l’exemple suivant dans la conception :

   +++ Exemple de code de conception qui renvoie une liste d’ID d’entité

   ```javascript
       #* 
       * "Return a simple list of recommended entity ids"   
       *#
   
       {   
         "notes":{   
         "purpose": "Return a simple list of recommended entity ids",   
         "use-case": "Use this approach if you prefer to do a real-time lookup of entity attribute details (such as inventory, price, rating) from another system (such as a CMS, PIM or ecommerce platform)",   
         "version": "01"   
         },   
         "recommendedItems": {   
           "key": "$key.id",   
           "slot-01": "$entity1.id",   
           "slot-02": "$entity2.id",   
           "slot-03": "$entity3.id",   
           "slot-04": "$entity4.id",   
           "slot-05": "$entity5.id",   
           "slot-06": "$entity6.id",   
           "slot-07": "$entity7.id",   
           "slot-08": "$entity8.id",   
           "slot-09": "$entity9.id",   
           "slot-10": "$entity10.id"   
         }   
       }  
   ```

   +++

1. Configurez une activité [!DNL Recommendations] basée sur les formulaires qui utilise cette conception.

   +++ Découvrez comment configurer une activité [!DNL Recommendations] basée sur des formulaires 

   1. Accédez à la page **[!UICONTROL Activités]**.
   1. Cliquez Sur **[!UICONTROL Créer Une Activité]** > **[!UICONTROL Recommandations]**.
   1. Sous **[!UICONTROL Choisir le compositeur d’expérience]**, sélectionnez **[!UICONTROL Formulaire]**, puis cliquez sur **[!UICONTROL Suivant]**.
   1. Sous Location (Emplacement), saisissez le texte « Sample_Recs_Response ».
   1. Sous **[!UICONTROL Contenu par défaut]**, cliquez sur la flèche vers le bas, puis sur **[!UICONTROL Ajouter une recommandation]**.
   1. Choisissez un type de page. Celui-ci détermine le filtrage initial de l’écran suivant.
   1. Sélectionnez une carte de critères, puis cliquez sur **[!UICONTROL Suivant]**.
   1. Sélectionnez la conception créée à l&#39;étape précédente, puis cliquez sur **[!UICONTROL Suivant]**.
   1. Terminez le processus de configuration.
   1. Cliquez sur la flèche droite en regard de **[!UICONTROL Inactif]**, puis sélectionnez **[!UICONTROL Activer]**.

   +++

1. Une fois l’activité configurée et activée, un exemple de requête peut être configuré pour récupérer la réponse JSON nettoyée.

   À partir du moment où l’activité est enregistrée, [!DNL Target] doit créer un modèle pour prendre en charge la configuration des critères sélectionnés. Selon un certain nombre de facteurs, ce processus peut prendre un certain temps. Les résultats apparaissent une fois le modèle créé.

   Par exemple :

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   où

   | Paramètre | Valeur |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | Le code client [!DNL Target] (disponible sur /help/target/products.html#recsSettings > Jeton API Recommendations > Code client). |
   | `[YOUR_MBOX_NAME]` | Nom qui a été sélectionné dans la section « Emplacements » de l’activité Recommendations basée sur les formulaires, dans ce cas Sample_Recs_Response. |
   | `[ENTITY_ID]` | `entity.id` d’un élément du catalogue. |
   | `[AT_PROPERTY_TOKEN]` | (Facultatif) Ajouté lorsqu’une propriété (faisant partie des autorisations d’Enterprise) a été sélectionnée lors de la configuration de l’activité. |

Une fois l’algorithme exécuté et les résultats disponibles, la réponse ressemble à ce qui suit :

![Réponse JSON avec les éléments recommandés](/help/main/c-recommendations/c-design-overview/assets/json_recommendation.png){width="575px"}

## Autres conseils sur les objets JSON {#json-tips}

Une simple liste d’éléments délimitée par des virgules peut également être renvoyée en configurant une conception avec la syntaxe suivante :

```
$entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Des informations supplémentaires peuvent également être envoyées dans la réponse. Le code suivant est un exemple plus complexe qui renvoie beaucoup plus que les identifiants d’entité avec leurs emplacements associés (ordre). Cet exemple de conception renvoie également les détails de l’activité, les détails du **[!UICONTROL profil cible]** (le cas échéant) et les autres `entity.attributes` associés aux éléments renvoyés.

+++ Exemple de code de conception qui renvoie des détails d’activité, de profil et d’entité

```javascript
  {   
   "adobeRecommendations": {   
    "notes": {   
     "purpose": "Return a list of entity ids with their associated entity.attributes",   
     "use-case": "Use this approach to avoid looking up attribute details after receiving a response from Target",   
     "version": "01"   
    },   
    "recommendedItems": {   
     "slot-01": "$entity1.id",   
     "slot-02": "$entity2.id",   
     "slot-03": "$entity3.id",   
     "slot-04": "$entity4.id",   
     "slot-05": "$entity5.id",   
     "slot-06": "$entity6.id",   
     "slot-07": "$entity7.id",   
     "slot-08": "$entity8.id",   
     "slot-09": "$entity9.id",   
     "slot-10": "$entity10.id"   
    },   
    "activityDetails": {   
     "mbox.name": "email-mbox",   
     "campaign.name": "\${campaign.name}",   
     "campaign.id": "\${campaign.id}",   
     "campaign.recipe.name": "\${campaign.recipe.name}",   
     "campaign.recipe.id": "\${campaign.recipe.id}",   
     "offer.name": "\${offer.name}",   
     "offer.id": "\${offer.id}",   
     "criteria.title": "$criteria.title",   
     "algorithm.name": "$algorithm.name",   
     "algorithm.dayCount": "$algorithm.dayCount"   
    },   
    "visitorProfile": {   
     "profile.favorite-category": "\${profile.favorite-category}",   
     "profile.test": "\${profile.test}",   
     "user.endpoint.lastPurchasedEntity": "\${user.endpoint.lastPurchasedEntity}",   
     "user.endpoint.lastViewedEntity": "\${user.endpoint.lastViewedEntity}",   
     "user.endpoint.mostViewedEntity": "\${user.endpoint.mostViewedEntity}",   
     "user.endpoint.categoryAffinity": "\${user.endpoint.categoryAffinity}",   
     "profile.geolocation.city": "\${profile.geolocation.city}",   
     "profile.geolocation.dma": "\${profile.geolocation.dma}",   
     "profile.geolocation.state": "\${profile.geolocation.state}",   
     "profile.geolocation.country": "\${profile.geolocation.country}",   
     "profile.sessionCount": "\${profile.sessionCount}",   
     "profile.averageDaysBetweenVisits": "\${profile.averageDaysBetweenVisits}",   
     "profile.browserTime": "\${profile.browserTime}",   
     "user.activeActivities": "\${user.activeActivities}",   
     "user.pcId": "\${user.pcId}",   
     "user.isFirstSession": "\${user.isFirstSession}",   
     "user.isNewSession": "\${user.isNewSession}",   
     "user.header": "\${user.header}",   
     "user.parameter": "\${user.parameter}"   
    },   
    "recKey": {   
     "recKeyDetails": {   
      "id": "$key.id",   
      "name": "$key.name",   
      "category": "$key.category",   
      "pageUrl": "$key.pageUrl",   
      "thumbnailUrl": "$key.thumbnailUrl"   
     }   
    },   
    "recDetailedResults": {   
     "recEntity1Details": {   
      "id": "$entity1.id",   
      "name": "$entity1.name",   
      "category": "$entity1.category",   
      "pageUrl": "$entity1.pageUrl",   
      "thumbnailUrl": "$entity1.thumbnailUrl"   
     },   
     "recEntity2Details": {   
      "id": "$entity2.id",   
      "name": "$entity2.name",   
      "category": "$entity2.category",   
      "pageUrl": "$entity2.pageUrl",   
      "thumbnailUrl": "$entity2.thumbnailUrl"   
     },   
     "recEntity3Details": {   
      "id": "$entity3.id",   
      "name": "$entity3.name",   
      "category": "$entity3.category",   
      "pageUrl": "$entity3.pageUrl",   
      "thumbnailUrl": "$entity3.thumbnailUrl"   
     },   
     "recEntity4Details": {   
      "id": "$entity4.id",   
      "name": "$entity4.name",   
      "category": "$entity4.category",   
      "pageUrl": "$entity4.pageUrl",   
      "thumbnailUrl": "$entity4.thumbnailUrl"   
     },   
     "recEntity5Details": {   
      "id": "$entity5.id",   
      "name": "$entity5.name",   
      "category": "$entity5.category",   
      "pageUrl": "$entity5.pageUrl",   
      "thumbnailUrl": "$entity5.thumbnailUrl"   
     },   
     "recEntity6Details": {   
      "id": "$entity6.id",   
      "name": "$entity6.name",   
      "category": "$entity6.category",   
      "pageUrl": "$entity6.pageUrl",   
      "thumbnailUrl": "$entity6.thumbnailUrl"   
     },   
     "recEntity7Details": {   
      "id": "$entity7.id",   
      "name": "$entity7.name",   
      "category": "$entity7.category",   
      "pageUrl": "$entity7.pageUrl",   
      "thumbnailUrl": "$entity7.thumbnailUrl"   
     },   
     "recEntity8Details": {   
      "id": "$entity8.id",   
      "name": "$entity8.name",   
      "category": "$entity8.category",   
      "pageUrl": "$entity8.pageUrl",   
      "thumbnailUrl": "$entity8.thumbnailUrl"   
     },   
     "recEntity9Details": {   
      "id": "$entity9.id",   
      "name": "$entity9.name",   
      "category": "$entity9.category",   
      "pageUrl": "$entity9.pageUrl",   
      "thumbnailUrl": "$entity9.thumbnailUrl"   
     },   
     "recEntity10Details": {   
      "id": "$entity10.id",   
      "name": "$entity10.name",   
      "category": "$entity10.category",   
      "pageUrl": "$entity10.pageUrl",   
      "thumbnailUrl": "$entity10.thumbnailUrl"   
     }   
    }   
   }   
  }  
```

+++

