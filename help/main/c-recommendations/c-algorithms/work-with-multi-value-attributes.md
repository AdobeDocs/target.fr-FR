---
keywords: multi-valeur;attributs;recommendations;multi-valeur;multi-valeur;multi-valeur
description: Découvrez comment utiliser un champ à plusieurs valeurs dans [!DNL Target Recommendations] à l’aide d’opérateurs spéciaux à plusieurs valeurs.
title: Utilisation des attributs à plusieurs valeurs
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
TQID: 'https://experienceleague.adobe.com/FrjVxvYfGh2o-qomXRbVh6WS6f65Mja41gBMhejEPlE'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 2%
---
# Utilisation des attributs à plusieurs valeurs {#multi-value-attributes}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment envoyer des données à plusieurs valeurs à [!DNL Adobe Target Recommendations] et comment les utiliser dans des règles d’inclusion avec les opérateurs à plusieurs valeurs.

>[!ENDSHADEBOX]

Un champ à plusieurs valeurs contient plusieurs valeurs pour le même élément ou visiteur. Par exemple :

* Films proposés aux utilisateurs : un film donné compte plusieurs acteurs.
* Billets vendus pour des concerts : un utilisateur donné a plusieurs groupes préférés.
* Vêtements vendus : une chemise est disponible en plusieurs tailles.

Pour gérer les recommandations dans ces scénarios, les données à plusieurs valeurs peuvent être transmises à [!DNL Target Recommendations] et utilisées avec des opérateurs spéciaux à plusieurs valeurs.

## Envoi de données à plusieurs valeurs {#send}

Pour permettre à [!DNL Recommendations] d&#39;identifier des données à plusieurs valeurs, elles doivent être envoyées sous la forme d&#39;un tableau JSON.

Pour un paramètre à plusieurs valeurs dans JavaScript (`targetPageParams`), consultez [Implémentation d’attributs à plusieurs valeurs](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) dans *Attributs d’entité personnalisés*.

Dans un fichier CSV, un attribut d’entité à plusieurs valeurs est envoyé sous la forme d’un tableau JSON dans la cellule de l’attribut, comme dans l’exemple suivant.

+++ Exemple de fichier CSV avec un attribut à plusieurs valeurs

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

+++

Lorsqu&#39;un attribut d&#39;entité, un attribut de profil ou un paramètre de mbox est fourni en tant que paramètre à plusieurs valeurs dans ce format, [!DNL Recommendations] en déduit automatiquement que le champ est à plusieurs valeurs.

## Utilisation d’attributs à plusieurs valeurs dans les règles d’inclusion {#multi-value-inclusion-rules}

Les opérateurs suivants peuvent être utilisés avec les attributs d’entité à plusieurs valeurs, de profil et de mbox :

* **[!UICONTROL est contenu dans la liste]**
* **[!UICONTROL n&#39;est pas contenu dans la liste]**

>[!NOTE]
>
>La prise en charge de la correspondance dynamique avec les attributs à plusieurs valeurs n’est actuellement disponible que dans les critères qui utilisent une règle de correspondance d’attributs de profil ou de paramètre (mbox) qui compare une seule valeur sur le côté gauche à une valeur à plusieurs valeurs sur le côté droit. Les attributs à plusieurs valeurs ne sont actuellement pas pris en charge dans les promotions, la correspondance d’attributs d’entité ou pour les listes sur le côté gauche des règles d’inclusion.

### Exemple : exclure les éléments récemment surveillés

Pour éviter que les dix derniers films visionnés par l’utilisateur ne soient recommandés, commencez par écrire un script de profil appelé `user.lastWatchedMovies` qui suit les dix derniers films visionnés sous la forme d’un tableau JSON. Les éléments peuvent ensuite être exclus avec la règle d’inclusion suivante :

```
Profile Attribute Matching
id - is not contained in list - user.lastWatchedMovies
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

Pour recommander des billets de concert uniquement lorsque le groupe joué est l’un des groupes préférés de l’utilisateur, deux éléments sont requis : une variable de profil appelée `profile.favoriteBands` qui contient les groupes préférés de l’utilisateur, et un attribut `entity.artistPerforming` dans le catalogue qui contient l’artiste jouant dans le concert. La règle d’inclusion suivante peut ensuite être utilisée :

```
Profile Attribute Matching
artistPerforming - is contained in list - profile.favoriteBands
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

Les critères qui utilisent des règles de filtrage à plusieurs valeurs peuvent être créés via les API [!DNL Adobe Target], comme tous les critères. L’exemple d’appel API suivant crée un critère dans lequel l’attribut d’entité `id` est contenu dans la liste des paramètres de mbox `favorites` :

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

Cet appel est associé à JavaScript sur la page qui transmet le contenu des favoris :

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
