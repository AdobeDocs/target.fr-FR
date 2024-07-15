---
keywords: plusieurs valeurs;attributs;recommandations;plusieurs valeurs;plusieurs valeurs;plusieurs valeurs
description: Découvrez comment utiliser un champ à plusieurs valeurs dans  [!DNL Target Recommendations] à l’aide d’opérateurs spéciaux à plusieurs valeurs.
title: Puis-je utiliser des attributs à plusieurs valeurs dans Recommendations ?
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 6d2a313b0e54aa5f6717eee850c79e4092309e7d
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 9%

---

# Utilisation des attributs à plusieurs valeurs

Il peut arriver que vous souhaitiez travailler avec un champ à plusieurs valeurs. Prenons les exemples suivants :

* Vous proposez des films aux utilisateurs. Chaque film compte plusieurs acteurs.
* Vous vendez des billets pour des concerts. Chaque utilisateur a plusieurs groupes préférés.
* Vous vendez des vêtements. Une chemise est disponible en plusieurs tailles.

Pour gérer les recommandations dans ces scénarios, vous pouvez transmettre des données à plusieurs valeurs à [!DNL Target Recommendations] et utiliser des opérateurs spéciaux à plusieurs valeurs.

Pour permettre à [!DNL Recommendations] d’identifier des données à plusieurs valeurs, elles doivent être envoyées sous la forme d’un tableau JSON, comme dans les exemples de code ci-dessous.

## Transmettre un paramètre à plusieurs valeurs dans JavaScript

```
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

Pour plus d’informations, voir [Implémentation d’attributs à plusieurs valeurs](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) dans *Attributs d’entité personnalisés*.

## Transmettre un attribut d’entité à plusieurs valeurs dans un fichier CSV

```
## RECSRecommendations Upload File,,,,,,,,,,,,,,,,,,,
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines.,,,,,,,,,,,,,,,,,,,
## RECS,,,,,,,,,,,,,,,,,,,
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left.,,,,,,,,,,,,,,,,,,,
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'.,,,,,,,,,,,,,,,,,,,
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations.,,,,,,,,,,,,,,,,,,,
## RECSentity.id ,entity.name,entity. categoryId ,entity. message ,entity.thumbnailUrl ,entity.value ,entity.pageUrl ,entity.inventory ,entity.margin ,entity.custom1 ,entity.custom2 ,entity.custom3 ,entity.custom4,entity.custom5,entity.custom6,entity.custom7,entity.custom8,entity.custom9,entity.custom10,
1,Sample Product 1,category1,Save 10%,http://sample.store/products/images/product1_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=1,1000,48,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
2,Sample Product 2,category1,Save 10%,http://sample.store/products/images/product2_th.jpg,369,http://sample.store/products/product_detail.jsp?productId=2,1000,52,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
3,Sample Product 3,category1,Save 10%,http://sample.store/products/images/product3_th.jpg,479,http://sample.store/products/product_detail.jsp?productId=3,1000,78,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
4,Sample Product 4,category1,Save 10%,http://sample.store/products/images/product4_th.jpg,409,http://sample.store/products/product_detail.jsp?productId=4,1000,66,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
5,Sample Product 5,category1,Save 10%,http://sample.store/products/images/product5_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=5,1000,45,a,"[ ""v1"", ""v2"" ]",,,,,,,,, 
```

Lorsqu’un attribut d’entité, un attribut de profil ou un paramètre de mbox est fourni sous la forme de plusieurs valeurs selon le format ci-dessus, [!DNL Recommendations] déduit automatiquement que le champ est de plusieurs valeurs.

Les opérateurs suivants peuvent être utilisés avec des attributs d’entité, de profil et de mbox à plusieurs valeurs :

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## Utilisation d’attributs à plusieurs valeurs dans les règles d’inclusion

>[!NOTE]
>
>La prise en charge de la correspondance dynamique avec des attributs à plusieurs valeurs n’est actuellement disponible que dans les critères lors de l’utilisation d’une règle de correspondance d’attributs de profil ou de paramètre (mbox) lors de la comparaison d’une seule valeur du côté gauche à un côté droit à plusieurs valeurs. Les attributs à plusieurs valeurs ne sont actuellement pas pris en charge dans les promotions, la correspondance des attributs d’entité ou pour les listes sur le côté gauche des règles d’inclusion.

### Exemple : exclure les éléments récemment visionnés

Supposons que vous souhaitiez empêcher la recommandation de films figurant dans les dix derniers films visionnés par l’utilisateur. Commencez par écrire un script de profil appelé `user.lastWatchedMovies` pour effectuer le suivi des dix derniers films consultés en tant que tableau JSON. Vous pouvez ensuite exclure les éléments à l’aide de la règle d’inclusion suivante :

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

Représentation de l’API JSON de la règle d’inclusion :

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": "user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### Exemple : recommandations d’éléments parmi les favoris de l’utilisateur

Supposons que vous ne vouliez recommander des tickets que pour les concerts si le groupe jouant est l’un des groupes favoris de l’utilisateur. Tout d’abord, assurez-vous que vous disposez d’une variable de profil appelée `profile.favoriteBands` qui contient les bandes préférées de l’utilisateur. Ensuite, assurez-vous que votre catalogue comprend un attribut `entity.artistPerforming` qui inclut l’artiste qui joue dans le concert. Vous pouvez ensuite utiliser la règle d’inclusion suivante :

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

Représentation de l’API JSON de la règle d’inclusion :

```
{
    "attribute": "artistPerforming",
    "operation": "isContainedInList",
    "source": {
        "name": "profile.favoriteBands",
        "type": "PROFILE"
    }
}
```

### Exemple : création d’API de critères recommandant des éléments à partir des favoris d’un utilisateur

Les critères utilisant des règles de filtrage à plusieurs valeurs, comme tous les critères, peuvent être créés via des API [!DNL Adobe Target]. Un exemple d’appel API pour créer un critère où l’attribut d’entité `id` est contenu dans la liste de paramètres de mbox `favorites` est fourni ici :

```
curl -X POST \
  https://<serverhost>/api/recs/<client>/criteria/item \
  -H 'Accept: application/vnd.adobe.target.v1+json' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: <from API client>' \
  -H 'X-Target-user-email: <email address>' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "viewed criteria",
    "criteriaTitle": "test title",
    "type": "VIEWED_CF",
    "key": "CURRENT",
    "daysCount": "TWO_WEEKS",
    "aggregation": "NONE",
    "backupDisabled": false,
    "partialDesignAllowed": true,
    "configuration": {
        "inclusionRules": [
            {
                "attribute": "id",
                "operation": "isContainedInList",
                "source": {
                    "name": "mbox.favorites",
                    "type": "MBOX"
                }
            }
        ]
    }
}'
```

Cela serait associé à JavaScript sur la page pour transmettre les contenus favoris :

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
