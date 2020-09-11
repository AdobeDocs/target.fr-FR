---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Informations sur la création de règles d’inclusion dans Adobe Target pour les critères et les promotions et sur l’ajout de règles de filtrage dynamiques ou statiques supplémentaires pour obtenir de meilleurs résultats.
title: Utiliser des règles d’inclusion dynamiques et statiques dans Adobe Target Recommendations
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '1478'
ht-degree: 56%

---


# ![PREMIUM](/help/assets/premium.png) Utilisation de règles d’inclusion dynamiques et statiques{#use-dynamic-and-static-inclusion-rules}

Informations sur la création de règles d’inclusion pour les critères et les promotions en Adobe Target et l’ajout de règles de filtrage dynamiques ou statiques supplémentaires afin d’obtenir de meilleurs résultats pour vos recommandations.

Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Les critères et les promotions ainsi que l’utilisation des règles d’inclusion sont abordés dans cette rubrique.

## Ajout de règles de filtrage à des critères {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Lorsque vous [créez des critères](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), cliquez sur **[!UICONTROL Ajouter une règle de filtrage]** sous **[!UICONTROL Règles d’inclusion]**.

![](assets/inclusion_options_new.png)

Les options disponibles varient en fonction du secteur industriel vertical et de la clé de recommandation sélectionnés.

## Ajout de règles de filtrage à des promotions {#section_D59AFB62E2EE423086281CF5D18B1076}

Lors de la [création d’une promotion](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), sélectionnez **[!UICONTROL Promouvoir par attribut]**, puis cliquez sur **[!UICONTROL Ajouter une règle de filtrage]**.

![](assets/inclusion_options.png)

## Types de filtre {#section_0125F1ED10A84C0EB45325122460EBCD}

Le tableau suivant répertorie les types d’options de filtrage pour les critères et les promotions :

### Filtrage dynamique

Les options suivantes sont disponibles pour le filtrage dynamique :

#### Correspondance des attributs d’entité

Filtrez dynamiquement en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel les utilisateurs ont interagi.

Par exemple, recommandez uniquement des articles correspondant à la marque de l’article en cours.

Opérateurs disponibles :

* est égal à
* n’est pas égal à
* est compris entre
* contient
* ne contient pas
* commence par
* se termine par
* la valeur est présente
* la valeur est absente
* est supérieur ou égal à
* est inférieur ou égal à

#### Correspondance des attributs de profil

Filtrez dynamiquement en comparant des éléments (entités) à une valeur du profil de l’utilisateur.

Par exemple, recommandez uniquement des articles correspondant à la marque préférée du visiteur.

Opérateurs disponibles :

* est égal à
* n’est pas égal à
* contient
* ne contient pas
* commence par
* se termine par
* est supérieur ou égal à
* est inférieur ou égal à
* est compris entre

#### Correspondance de paramètres

Filtrez dynamiquement en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).

Par exemple, recommandez uniquement du contenu correspondant au paramètre de la page « industrie ».

Important : Si l’activité a été créée avant le 31 octobre 2016, sa diffusion échoue si elle utilise le filtre « Correspondance de paramètres ». Pour contourner ce problème, procédez comme suit :

* Créez une activité et ajoutez-y des critères.
* Utilisez un critère qui ne contient pas le filtre « Correspondance de paramètres ».
* Supprimez le filtre « Correspondance de paramètres » des critères.

Opérateurs disponibles :

* est égal à
* n’est pas égal à
* contient
* ne contient pas
* commence par
* se termine par
* est supérieur ou égal à
* est inférieur ou égal à
* est compris entre

### Filtrer par valeur

L’option suivante est disponible pour le filtrage dynamique :

#### Filtre statique

Saisissez manuellement une ou plusieurs valeurs statiques à filtrer.

Par exemple, recommandez uniquement le contenu avec une note MPAA de « G » ou « PG ».

Opérateurs disponibles :

* est égal à
* n’est pas égal à
* contient
* ne contient pas
* commence par
* se termine par
* la valeur est présente
* la valeur est absente
* est supérieur ou égal à
* est inférieur ou égal à

>[!NOTE]
>
>Si vous connaissiez la manière dont les règles d’inclusion étaient configurées avant la version 17.6.1 de Target (juin 2017), vous remarquerez que certains opérateurs et options ont changé. Seuls les opérateurs applicables à l’option sélectionnée s’affichent et certains opérateurs ont été renommés (« correspond à » est devenu « est égal à ») pour être plus cohérents et intuitifs. Toutes les règles d’exclusion existantes créées avant cette version ont été automatiquement migrées vers la nouvelle structure. Aucune restructuration n’est nécessaire de votre part.

Vous pouvez créer autant de règles d’inclusion que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

## Critères dynamiques et exemples de promotion

Les critères et les promotions dynamiques sont beaucoup plus puissants que les critères et les promotions statiques, et donnent de meilleurs résultats et un meilleur engagement.

Les exemples suivants illustrent la façon dont vous pouvez utiliser les promotions dynamiques dans le cadre de vos efforts marketing :

### Est égal

En utilisant l&#39;opérateur &quot;égal à&quot; dans les promotions dynamiques, lorsqu&#39;un visiteur consulte un article sur votre site Web (tel qu&#39;un produit, un article ou un film), vous pouvez promouvoir d&#39;autres éléments à partir de :

* de la même marque ;
* de la même catégorie ;
* de la même catégorie ET de la même marque-mère ;
* du même magasin.

### N’est pas égal à

En utilisant l&#39;opérateur &quot;n&#39;est pas égal à&quot; dans les promotions dynamiques, lorsqu&#39;un visiteur consulte un élément de votre site Web (tel qu&#39;un produit, un article ou un film), vous pouvez promouvoir d&#39;autres éléments à partir de :

* d’un autre programme télévisé ;
* d’un autre genre de film ;
* d’une autre gamme de produit ;
* un autre code de style.

### Est compris entre

En utilisant l&#39;opérateur &quot;se situe entre&quot; dans les promotions dynamiques, lorsqu&#39;un visiteur consulte un élément de votre site Web (tel qu&#39;un produit, un article ou un film), vous pouvez promouvoir d&#39;autres éléments qui sont :

* sont plus chers ;
* sont moins chers ;
* coûtent plus ou moins de 30 % ;
* sont des épisodes ultérieurs de la même saison ;
* sont des livres antérieurs dans une série.

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

Auparavant, aucun résultat n’était renvoyé si une valeur était vide. La liste déroulante « Si *x* est vide » permet de choisir l’action appropriée à exécuter si le critère contient des valeurs vides, comme illustré ci-dessous :

![](assets/empty_value.png)

Pour sélectionner une action spécifique, survolez l’icône représentant un engrenage (![](assets/icon_gear.png)), puis choisissez l’action souhaitée :

| Action | Disponible pour | Détails |
|--- |--- |--- |
| Ignorer cette règle de filtrage | Correspondance de paramètres de profil<br>Correspondance de paramètres | Il s’agit de l’action par défaut pour la correspondance des attributs de profil et la correspondance de paramètres.<br>Cette option indique que la règle est ignorée. Par exemple, s’il existe trois règles de filtrage et que la troisième règle ne transmet aucune valeur, vous pouvez simplement ignorer la troisième règle avec les valeurs vides au lieu de ne renvoyer aucun résultat. |
| Ne promeut aucun élément | Correspondance de l&#39;attribut d&#39;entité<br>MatchingProfile<br>Correspondance de paramètre | Il s’agit de l’action par défaut pour la correspondance des attributs d’entité.<br>[!DNL Target]Cette action est la manière dont a géré les valeurs vides avant l’ajout de cette option : aucun résultat ne sera affiché pour ce critère. |
| Utiliser une valeur statique | Correspondance des attributs d’entité<br>Correspondance de paramètres de profil<br>Correspondance de paramètres | Si une valeur est vide, vous pouvez choisir d’utiliser une valeur statique. |

## Exemples de correspondance des attributs de profil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL La Correspondance] d’attributs de profil vous permet de recommander uniquement les éléments qui correspondent à un attribut du profil visiteur, comme dans les exemples ci-dessous.

### Exemple 1 : Éléments recommandés pour la marque préférée de l’utilisateur

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. Avec une telle règle, si un visiteur recherche des shorts de course d’une marque spécifique, seules les recommandations qui correspondent à la marque préférée de cet utilisateur s’affichent (la valeur stockée dans `profile.favoritebrand` du profil du visiteur).

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Exemple 2 : Correspondance des tâches avec les demandeurs d&#39;emploi

Supposons que vous essayez de faire correspondre les emplois aux demandeurs d&#39;emploi. Vous souhaitez recommander uniquement les tâches situées dans la même ville que le demandeur d’emploi.

Vous pouvez utiliser des règles d’inclusion pour faire correspondre l’emplacement d’un demandeur d’emploi de son profil visiteur à une liste d’emplois, comme dans l’exemple suivant :

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

## Exemples de correspondance d’attributs d’entité

[!UICONTROL La Correspondance] d’attributs d’entité vous permet de recommander uniquement les éléments qui correspondent à un attribut de l’élément actuellement affiché par l’utilisateur, de l’élément consulté le plus récemment, de l’élément acheté le plus récemment, de l’élément consulté le plus fréquemment par l’utilisateur ou d’un élément stocké dans un attribut personnalisé dans le profil du visiteur, comme dans les exemples ci-dessous.

### Exemple 3 : Mise à niveau vers un produit plus cher

Supposons que vous soyez un détaillant de vêtements et que vous souhaitiez encourager les utilisateurs à envisager des articles plus chers et donc plus rentables. Vous pouvez utiliser les opérateurs &quot;égal à&quot; et &quot;est compris entre&quot; pour promouvoir des articles plus chers provenant de la même catégorie et de la même marque. Par exemple, un détaillant de chaussures de sport peut promouvoir des chaussures de sport plus chères afin d’augmenter la vente d’un visiteur qui s’intéresse aux chaussures de sport.

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### Exemple 4 : Promotion de produits de marque privée

Vous pouvez mélanger des filtres dynamiques et statiques pour promouvoir des produits de marque privée. Par exemple, une société d&#39;approvisionnement de bureau peut promouvoir les cartouches de toner de la marque de la maison de la société afin de générer une vente plus rentable pour un visiteur qui regarde le toner — et promouvoir les stylos de la marque de la maison de la société pour générer une vente plus rentable pour un visiteur qui regarde les stylos.

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

## Avertissements {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Différents attributs de type de données peuvent ne pas être compatibles dans les critères ou promotions dynamiques au moment de l’exécution avec les opérateurs « est égal à » et « n’est pas égal à ». You should use [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory], and [!UICONTROL Environment] values wisely on the right hand side if the left hand side has predefined attributes or custom attributes.

![](assets/left_right.png)

Le tableau suivant répertorie les règles efficaces et celles qui peuvent ne pas être compatibles au moment de l’exécution :

| Règles compatibles | Règles potentiellement incompatibles |
|--- |--- |
| value - est compris entre - 90 % et 110 % de l’article actif - salesValue | salesValue - est compris entre - 90 % et 110 % de l’article actif - value |
| value - est compris entre - 90 % et 110 % de l’article actif - value | clearancePrice - est compris entre - 90 % et 110 % de l’article actif - margin |
| margin - est comprise entre - 90 % et 110 % de l’article actif - margin | storeInventory - est égal à - de l’article actif - inventory |
| inventory - est égal à - de l’article actif - inventory |  |
