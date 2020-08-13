---
keywords: remote offer;create remote offer
description: Création d’offres JSON dans la bibliothèque d’offres pour une utilisation dans le compositeur d’expérience d’après les formulaires.
title: Création d’offres JSON
feature: offers
topic: Standard
uuid: 4ae3ca34-7661-4c1d-a132-fc446e653b90
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 100%

---


# Création d’offres JSON{#create-json-offers}

Création d’offres JSON dans la bibliothèque d’offres pour une utilisation dans le compositeur d’expérience d’après les formulaires.

Les offres JSON peuvent être utilisées dans les activités basées sur des formulaires, permettant ainsi les cas d’utilisation où le système de prise de décision de Target doit envoyer une offre au format JSON qui sera consommée dans des intégrations d’infrastructure d’application d’une seule page ou des intégrations côté serveur.

Tenez compte des informations suivantes lorsque vous utilisez les offres JSON :

* Les offres JSON sont actuellement uniquement disponibles pour les activités AB et XT.
* Les offres JSON peuvent être utilisées uniquement dans les activités basées sur des formulaires.
* L’offre JSON peut être extraite directement via l’API côté serveur, le kit SDK mobile ou le kit SDK NodeJS.
* Dans le navigateur, les offres JSON peuvent désormais être extraites UNIQUEMENT via at.js 1.2.3 (ou version supérieure) et [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) en filtrant les actions via l’action `setJson`.
* Les offres JSON sont diffusées sous forme d’objets JSON natifs plutôt que de chaînes. Les consommateurs de ces objets ne doivent plus traiter ces objets en tant que chaînes et les convertir en objets JSON.
* Contrairement aux autres offres (par exemple, les offres HTML), les offres JSON ne sont pas appliquées automatiquement parce qu’il s’agit d’offres non visuelles. Les développeurs doivent écrire du code pour obtenir explicitement l’offre au moyen de la fonction [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md).
* Les offres JSON ne sont pas prises en charge si vous utilisez mbox.js.

## Création d’une offre JSON {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Cliquez sur **[!UICONTROL Offres]**, puis sélectionnez l’onglet **[!UICONTROL Offres (code)]**.
1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre JSON]**.

   ![](assets/offer-json.png)

1. Saisissez le nom de l’offre.
1. Saisissez ou copiez votre code JSON dans la zone **[!UICONTROL Code]**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Exemple {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

Les offres JSON sont uniquement prises en charge dans les activités créées dans le compositeur d’expérience d’après les formulaires. À l’heure actuelle, les offres JSON peuvent uniquement être utilisées par le biais d’appels d’API directs.

Voici un exemple :

```
adobe.target.getOffer({ 
  mbox: "some-mbox", 
  success: function(actions) { 
    console.log('Success', actions); 
  }, 
  error: function(status, error) { 
    console.log('Error', status, error); 
  } 
});
```

Les actions transmises au rappel de succès constituent un tableau d’objets. En supposant que nous ayons une seule offre JSON, ce tableau contient les éléments suivants :

```
{ 
  "demo": {"a": 1, "b": 2} 
}
```

Le tableau des actions aura la structure suivante :

```
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

Pour extraire l’offre JSON, vous devez effectuer une itération sur les actions pour localiser celle avec l’action `setJson`, puis effectuer une itération sur le tableau de contenu.

## Cas d’utilisation {#section_85B07907B51A43239C8E3498EF58B1E5}

Supposons que l’offre JSON suivante soit diffusée sur votre page web :

```
{ 
    "_id": "5a65d24d8fafc966921e9169", 
    "index": 0, 
    "guid": "7c006504-c6f7-468d-a46f-f72531ea454c", 
    "isActive": true, 
    "balance": "$2,075.06", 
    "picture": "https://placehold.it/32x32", 
    "tags": [ 
      "esse", 
      "commodo", 
      "excepteur", 
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      }, 
    ], 
    "greeting": "Hello, Stephenson Fernandez! You have 4 unread messages.", 
    "favoriteFruit": "strawberry" 
} 
  
```

Le code suivant indique comment accéder à l’attribut « greeting » :

```
adobe.target.getOffer({   
  "mbox": "name_of_mbox", 
  "params": {}, 
  "success": function(offer) {           
        console.log(offer[0].content[0].greeting); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

## Filtrage des offres par type d’offre JSON {#section_52533555BCE6420C8A95EB4EB8907BDE}

Vous pouvez filtrer la bibliothèque d’offres par type d’offre JSON en cliquant sur la liste déroulante **[!UICONTROL Type]**, puis en activant la case à cocher Offres **[!UICONTROL JSON]**.

![](assets/offer-json-filter.png)

