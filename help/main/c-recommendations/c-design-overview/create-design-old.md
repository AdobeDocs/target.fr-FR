---
keywords: conception de recommandations, créer une conception, copier une conception
description: Découvrez comment créer une conception Recommendations Adobe [!DNL Target] en utilisant une conception par défaut ou en créant une conception personnalisée pour s’adapter au mieux à la disposition de votre page.
title: Comment créer une conception dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 21%

---

# Création d’une conception

Une conception définit la manière dont les recommandations s’affichent sur une page.

Vous pouvez créer une conception [!UICONTROL Recommendations] à l’aide d’une conception par défaut ou d’une conception personnalisée. L’écran **[!UICONTROL Recommendations > Designs]** affiche à la fois les cartes de conception par défaut et les conceptions qui ont été créées dans votre compte.

Tenez compte des informations suivantes lorsque vous utilisez des conceptions :

* Vous pouvez créer une conception Recommendations à l’aide d’une conception par défaut ou d’une conception personnalisée.
* Vous ne pouvez pas modifier ni supprimer une conception par défaut.
* Vous pouvez modifier, copier ou supprimer une conception personnalisée.
* Pour créer une conception basée sur une conception par défaut, vous devez d’abord copier la conception, puis la modifier.

Cette illustration présente la conception 1 x 4 par défaut :

![1 x 4 conception par défaut](/help/main/c-recommendations/c-design-overview/assets/default-design.png)

Cette illustration présente une conception personnalisée :

![Conception personnalisée](/help/main/c-recommendations/c-design-overview/assets/custom-design.png)

Vous pouvez créer une conception pendant le processus de création d’activité à partir du Compositeur d’expérience visuelle (VEC) ou de la bibliothèque de conception en dehors de la création d’activité. Les sections suivantes supposent que vous créez des conceptions à partir de la bibliothèque, mais les étapes sont similaires.

## Création de conceptions

Vous pouvez créer une conception basée sur une conception par défaut ou sur une conception personnalisée.

### Créer une conception basée sur une conception par défaut

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Designs]** pour afficher la bibliothèque de [!UICONTROL Designs].

   ![ Bibliothèque de conceptions ](/help/main/c-recommendations/c-design-overview/assets/design-library.png)

1. Placez le pointeur de la souris sur la carte de la conception que vous souhaitez créer, puis cliquez sur l’icône **[!UICONTROL Copy]**.

   ![Image Card_CopyDesign](assets/Card_CopyDesign.png)

   La boîte de dialogue [!UICONTROL Create Design] s’affiche.

   ![image createDesign](assets/createDesign.png)

1. Dans le panneau **[!UICONTROL Information]**, ajoutez un **[!UICONTROL Content Name]** et une image d’aperçu facultative à afficher sur la carte de conception.

   Lorsque vous utilisez une conception par défaut, le nom de la conception et « Copier » s’affichent dans le champ **[!UICONTROL Content Name]**. Ce nom est modifiable. Vous pouvez également sélectionner une image à afficher sur la carte de conception.

1. (Conditionnel) Modifiez le **[!UICONTROL Code]** de conception selon vos besoins.

   Les conceptions de recommandations utilisent le langage de conception open-source [!DNL Velocity]. Vous trouverez des informations sur [!DNL Velocity] à l’adresse [https://velocity.apache.org](https://velocity.apache.org) et dans [Personnaliser une conception à l’aide de [!DNL Velocity]](/help/main/c-recommendations/c-design-overview/customizing-a-template.md).

   Une conception peut être au format HTML ou non HTML. Par défaut, les conceptions d’HTML sont enveloppées avec une balise `<div>` pour permettre le suivi des clics dans un environnement web. Les conceptions non HTMLS sont destinées aux environnements non web pour lesquels le suivi des clics n’est pas possible. Faites glisser le bouton [!UICONTROL HTML Design] vers la position « désactivé » pour utiliser du code non HTML.

   >[!NOTE]
   >
   >Le nombre maximal d’entités pouvant être référencées dans une conception, que ce soit en dur ou au moyen de boucles, est de 99.

1. Cliquez sur **[!UICONTROL Save]**.

### Créer une conception personnalisée

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Designs]** pour afficher la bibliothèque de [!UICONTROL Designs].

1. Cliquez sur **[!UICONTROL Create Design]**.

   Si vous souhaitez baser votre nouvelle conception personnalisée sur une conception existante, placez le pointeur de la souris sur la conception souhaitée, puis cliquez sur l’icône [!UICONTROL Copy]. Vous pouvez ensuite modifier la copie pour créer une conception personnalisée.

1. Ajoutez un **[!UICONTROL Content Name]** et une image d’aperçu facultative.

1. (Conditionnel) Modifiez le **[!UICONTROL Code]** de conception selon vos besoins.

   Pour plus d’informations, reportez-vous aux informations de l’étape 4 ci-dessus.

1. Cliquez sur **[!UICONTROL Save]**.

## Modifier, copier ou supprimer une conception

N&#39;oubliez pas que vous ne pouvez pas modifier ni copier une conception par défaut ; vous ne pouvez copier que les conceptions par défaut.

Pointez sur la conception souhaitée dans la bibliothèque [!UICONTROL Design], puis cliquez sur l’icône appropriée : modifier, copier ou supprimer.

![Icônes de survol d’une conception](/help/main/c-recommendations/c-design-overview/assets/hover-icons-design.png)

Vous pouvez copier une conception existante pour créer une conception en double que vous pouvez ensuite modifier. Ce processus permet de créer une conception similaire avec moins d’effort.

Sachez que les conceptions sont disponibles sur l’ensemble du compte. Tenez compte de l’utilisation dans d’autres comptes avant de supprimer une conception. Les conceptions supprimées ne peuvent pas être récupérées.

## Exemple d’objet JSON {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

L’exemple suivant montre comment les réponses JSON peuvent être renvoyées lors de la configuration d’une activité via l’éditeur basé sur les formulaires.

1. Créez une conception à partir de la bibliothèque de conception ou dans le processus basé sur les formulaires. Si vous tentez de créer une conception dans le workflow [!UICONTROL Visual Experience Composer] (VEC), vous ne pouvez rien créer d’autre qu’une conception d’HTML, qui est encapsulée dans un `<div>` à des fins de suivi des clics.

1. Assurez-vous que l’option « Conception HTML » est désactivée :

   ![image html_design_toggle](assets/html_design_toggle.png)

1. Le code suivant est un exemple de ce que vous pouvez coller dans votre conception :

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

1. Configurez une activité de [!DNL Recommendations] basée sur les formulaires qui utilise cette conception.

   1. Accédez à la page **[!UICONTROL Activities]**.
   1. Cliquez sur **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**.
   1. Sous **[!UICONTROL Choose Experience Composer]**, sélectionnez **[!UICONTROL Form]**, puis cliquez sur **[!UICONTROL Next]**.
   1. Sous Emplacement, saisissez le texte : « Sample_Recs_Response ».
   1. Sous **[!UICONTROL Default Content]**, cliquez sur la flèche vers le bas, puis sur **[!UICONTROL Add Recommendation]**.
   1. Choisissez un type de page. Celui-ci détermine le filtrage initial de l’écran suivant.
   1. Sélectionnez une carte Critères, puis cliquez sur **[!UICONTROL Next]**.
   1. Sélectionnez la conception créée à l’étape précédente, puis cliquez sur **[!UICONTROL Next]**.
   1. Terminez le processus de configuration.
   1. Cliquez sur la flèche de droite en regard de **[!UICONTROL Inactive]**, puis sélectionnez **[!UICONTROL Activate]**.

1. Une fois votre activité configurée et activée, vous pouvez configurer un exemple de requête pour récupérer la réponse JSON vierge.

   À partir du moment où vous enregistrez votre activité, [!DNL Target] devez créer un modèle pour prendre en charge la configuration des critères sélectionnés. Selon un certain nombre de facteurs, ce processus peut prendre un certain temps. Les résultats apparaissent une fois le modèle créé.

   Par exemple :

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   où

   | Paramètre | Valeur |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | Code client Target (disponible sur /help/target/products.html#recsSettings > Jeton API Recommendations > Code client). |
   | `[YOUR_MBOX_NAME]` | Nom que vous avez sélectionné dans la section « Emplacements » du Recommendations basé sur les formulaires, dans ce cas Sample_Recs_Response. |
   | `[ENTITY_ID` | L’`entity.id` d’un élément de votre catalogue. |
   | `[AT_PROPERTY_TOKEN]` | (Facultatif) Ajoutez ce paramètre si vous avez sélectionné une propriété (fonctionnalité des autorisations d’Enterprise) pendant la configuration de votre activité. |

Après l’exécution de votre algorithme et l’obtention des résultats, votre réponse doit ressembler à ceci :

![image json_recommendation](assets/json_recommendation.png){width="575px"}

## Autres conseils et astuces concernant les objets JSON {#section_C305673C68944749969DB239E3221DC2}

Vous pouvez également renvoyer une simple liste d’éléments délimitée par des virgules en configurant une conception avec la syntaxe suivante :

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Vous avez aussi la possibilité d’envoyer des informations supplémentaires dans la réponse. Le fichier de code suivant est un exemple plus complexe qui renvoie bien plus que les ID d’entité et leurs emplacements associés (ordre). Cet exemple de conception renvoie également les détails de l’activité, les détails du profil cible (le cas échéant) et d’autres `entity.attributes` associés aux éléments renvoyés.

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

## Vidéo de formation : création de conceptions personnalisées dans Recommendations (3:20) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo traite des sujets suivants :

* Créer une conception personnalisée
* comprendre comment référencer des variables d’affichage dans vos conceptions ;

>[!VIDEO](https://video.tv.adobe.com/v/34832?captions=fre_fr)
