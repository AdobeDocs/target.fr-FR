---
keywords: multi-valeur;attributs;recommendations;multi-valeur;multi-valeur;multi-valeur
description: Découvrez comment utiliser un champ à plusieurs valeurs dans Adobe [!DNL Target] Recommendations à l’aide d’opérateurs spéciaux à plusieurs valeurs, par exemple pour recommander des films avec plusieurs acteurs.
title: Puis-je utiliser des attributs à plusieurs valeurs dans Recommendations ?
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 9%

---

# Utilisation des attributs à plusieurs valeurs

Il peut arriver que vous souhaitiez utiliser un champ à plusieurs valeurs. Prenons les exemples suivants :

* Vous proposez des films aux utilisateurs. Chaque film compte plusieurs acteurs.
* Vous vendez des billets pour des concerts. Chaque utilisateur a plusieurs groupes préférés.
* Vous vendez des vêtements. Une chemise est disponible en plusieurs tailles.

Pour gérer les recommandations dans ces scénarios, vous pouvez transmettre des données à plusieurs valeurs à [!DNL Target Recommendations] et utiliser des opérateurs spéciaux à plusieurs valeurs.

Pour [!DNL Recommendations] permettre d’identifier des données à plusieurs valeurs, elles doivent être envoyées sous la forme d’un tableau JSON, comme dans les exemples de code ci-dessous.

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

Lorsqu’un attribut d’entité, un attribut de profil ou un paramètre mbox est fourni comme paramètre à plusieurs valeurs selon le format ci-dessus, [!DNL Recommendations] en déduit automatiquement que le champ est à plusieurs valeurs.

Les opérateurs suivants peuvent être utilisés avec les attributs d’entité à plusieurs valeurs, de profil et de mbox :

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## Utilisation d’attributs à plusieurs valeurs dans les règles d’inclusion

>[!NOTE]
>
>Actuellement, la prise en charge de la correspondance dynamique avec des attributs à plusieurs valeurs n’est disponible que dans les critères lors de l’utilisation d’une règle de correspondance d’attributs de profil ou de paramètre (mbox) lors de la comparaison d’une valeur unique côté gauche avec une valeur multiple côté droit. Les attributs à plusieurs valeurs ne sont actuellement pas pris en charge dans les promotions, la correspondance d’attributs d’entité ou pour les listes sur le côté gauche des règles d’inclusion.

### Exemple : exclure les éléments récemment surveillés

Supposons que vous souhaitiez empêcher que les dix derniers films visionnés par l’utilisateur ne soient recommandés. Tout d’abord, écrivez un script de profil appelé `user.lastWatchedMovies` pour effectuer le suivi des dix derniers films consultés sous la forme d’un tableau JSON. Vous pouvez ensuite exclure les éléments à l’aide de la règle d’inclusion suivante :

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

Représentation de la règle d’inclusion par l’API JSON :

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

### Exemple : recommander des éléments à partir des favoris de l’utilisateur

Supposons que vous souhaitiez recommander des billets uniquement pour des concerts si le groupe qui joue est l&#39;un des groupes préférés de l&#39;utilisateur. Tout d’abord, assurez-vous d’avoir une variable de profil appelée `profile.favoriteBands` qui contient les groupes préférés de l’utilisateur. Ensuite, assurez-vous que votre catalogue comprend un `entity.artistPerforming` d’attributs qui inclut l’artiste intervenant dans le concert. Vous pouvez ensuite utiliser la règle d’inclusion suivante :

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

Représentation de la règle d’inclusion par l’API JSON :

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

### Exemple : création par l’API de critères recommandant des éléments des favoris d’un utilisateur

Les critères utilisant des règles de filtrage à plusieurs valeurs, comme tous les critères, peuvent être créés à l’aide d’API Adobe I/O. Un exemple d’appel API permettant de créer un critère dans lequel l’attribut d’entité `id` est contenu dans la liste des paramètres de mbox `favorites` est fourni ici :

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

Celle-ci est alors associée à JavaScript sur la page pour transmettre les contenus favoris :

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
