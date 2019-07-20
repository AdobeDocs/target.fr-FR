---
description: Utilisez le langage de conception Velocity libre pour personnaliser des conceptions de recommandations.
keywords: conception personnalisée;velocity;décimale;virgule;personnaliser le concept
seo-description: Utilisez le langage de conception Velocity libre pour personnaliser des conceptions de recommandations.
seo-title: Personnalisation d’une conception à l’aide de Velocity
solution: Target
title: Personnalisation d’une conception à l’aide de Velocity
title-outputclass: Premium
topic: Premium
uuid: 80701a15-c5eb-4089-a92e-117eda11faa2
badge: Premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Personnaliser une conception à l’aide de Velocity{#customize-a-design-using-velocity}

Utilisez le langage de conception Velocity libre pour personnaliser des conceptions de recommandations.

## Velocity overview {#section_C431ACA940BC4210954C7AEFF6D03EA5}

Vous trouverez des informations concernant Velocity à l’adresse [](https://velocity.apache.org)https://velocity.apache.org.

Toute la syntaxe et tout le code Velocity peuvent servir pour une conception de recommandation. Vous pouvez donc créer des *boucles*, des conditions (« *si* ») et tout autre code en utilisant Velocity au lieu de JavaScript.

Toute variable envoyée à [!DNL Recommendations] dans la mbox `productPage` ou au fichier CSV transféré peut être affichée dans une conception. Ces valeurs sont référencées par la syntaxe suivante :

```
$entityN.variable
```

Les noms de variables doivent être suivis de la formule abrégée Velocity, qui consiste à indiquer le caractère *$*, suivi d’un identifiant de langue de modèle Velocity (VTL). L’identifiant VTL doit commencer par un caractère alphabétique (a-z ou A-Z).

Les noms de variables Velocity sont limités aux types de caractères suivants :

* Alphabétiques (a-z, A-Z)
* Numériques (0-9)
* Trait d’union ( - )
* Trait de soulignement ( _ )

Les variables suivantes sont disponibles en tant que matrices Velocity. À ce titre, elles peuvent être itérées ou référencées par l’intermédiaire d’un index.

* `entities`
* `entityN.categoriesList`

Par exemple :

```
#foreach ($category in $entity1.categoriesList) 
<br/>$category 
#end
```

OU

```
#if ($entities[0].categoriesList.size() >= 3 ) 
$entities[0].categoriesList[2] 
#end
```

Pour plus d’informations sur les variables Velocity, voir [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Si vous utilisez un script de profil dans votre conception, le $ précédant le nom du script doit être échappé avec un \. Par exemple, `\${user.script_name}`.

>[!NOTE]
>
>Le nombre maximum d’entités qu’il est possible de référencer dans une conception, que ce soit par le biais de boucles ou d’un codage en dur, est de 99. Le script du modèle peut contenir jusqu’à 65 000 caractères.

Par exemple, si vous souhaitez qu’une conception affiche ce qui suit :

![](assets/velocity_example.png)

utilisez le code suivant :

```
<table style="border:1px solid #CCCCCC;"> 
 
<tr> 
 
<td colspan="3" style="font-size: 130%; border-bottom:1px solid  
#CCCCCC;"> You May Also Like... </td> 
 
</tr> 
 
<tr> 
 
<td style="border-right:1px solid #CCCCCC;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity1.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity1.id</a></div> 
 
By $entity1.message <a href="?x14=brand;q14=$entity1.message"> 
(More)</a><br/> 
 
sku: $entity1.prodId<br/> Price: $$entity1.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
<td style="border-right:1px solid #CCCCCC; padding-left:10px;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity2.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity2.id</a></div> 
 
By $entity2.message <a href="?x14=brand;q14=$entity2.message"> 
(More)</a><br/> 
 
sku: $entity2.prodId<br/> 
 
Price: $$entity2.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
<td style="padding-left:10px;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity3.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity3.id</a></div> 
 
By $entity3.message <a href="?x14=brand;q14=$entity3.message"> 
(More)</a><br/> 
 
sku: $entity3.prodId<br/> Price: $$entity3.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
</tr> 
 
</table>
```

>[!NOTE] {class="- topic/note "}
>
>Si vous souhaitez ajouter des informations après la valeur de la variable, vous devez utiliser une notation formelle. Par exemple : `${entity1.thumbnailUrl}.gif`.

Vous pouvez aussi utiliser `algorithm.name` et `algorithm.dayCount` comme variables dans les conceptions ; ainsi, une conception peut servir à tester plusieurs critères et le nom du critère peut être affiché de manière dynamique dans la conception. Cela indique au visiteur qu’il consulte « les meilleurs vendeurs » ou « les personnes qui ont consulté ceci ont acheté cela ». Vous pouvez même utiliser ces variables pour afficher le `dayCount` (nombre de jours de données utilisé dans les critères, comme « éléments les plus vendus au cours des deux derniers jours », etc.).

## Scenario: Display key item with recommended products {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

Vous pouvez modifier votre conception pour afficher votre élément clé à côté des autres produits recommandés. Par exemple, vous voulez peut-être afficher l’élément actuel pour référence à côté des recommandations.

Pour ce faire, créez une colonne dans votre conception qui utilise l’attribut `$key` sur lequel vous basez votre recommandation plutôt que l’attribut `$entity`. Par exemple, le code pour votre colonne clé peut ressembler à ceci :

```
<div class="at-table-column"> 
   <a href="$key.pageURL"> 
      <img src=$key.thumbnailUrl" class="at-thumbnail"/> 
      <br/><h3>$key.name</h3> 
      <br/><p class="at-light">$key.message</p> 
      <br/><p class="at-light">$key.value</p> 
   </a> 
</div>
```

Le résultat est une conception comme la suivante, où une colonne affiche l’élément clé.

![](assets/rec_key.png)

Lors de la création de votre activité [!DNL Recommendations], si l’article clé est tiré du profil du visiteur, par exemple le « dernier article acheté », [!DNL Target] affiche un produit aléatoire dans le [!UICONTROL compositeur d’expérience visuelle] (CEV). Cela est dû à l’indisponibilité du profil lors de la conception de l’activité. Quand les visiteurs visualisent la page, ils visualiseront l’élément clé attendu.

## Scenario: Replace the decimal point with the comma delimiter in a sales price {#section_01F8C993C79F42978ED00E39956FA8CA}

Vous pouvez modifier votre conception pour remplacer le séparateur décimal utilisé aux États-Unis par le séparateur virgule utilisé en Europe et dans d’autres pays.

Le code suivant présente une ligne unique dans un exemple de tarification de vente conditionnelle :

```
<span class="price">$entity1.value.replace(".", ",") €</span><br>
```

Le code suivant est un exemple conditionnel complet d’un prix de vente :

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") €</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") €<br> #else 
    <span class="price">$entity1.value.replace(".", ",") €</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## Scenario: Create a 4x2 default Recommendations design with null-checking logic {#default}

Using a Velocity script to control for dynamic sizing of the entity display, the following template accommodates a 1-to-many result to avoid creating empty HTML elements when there aren't enough matching entities returned from [!DNL Recommendations]. This script is best for scenarios when back-up recommendations wouldn't make sense and [!UICONTROL Partial Template Rendering] is enabled.

L'extrait HTML suivant remplace la partie HTML existante dans la conception par défaut 4 x 2 (le CSS n'est pas inclus ici, par souci de concision) :

* If a fifth entity exists, the script inserts a closing div and opens a new row with `<div class="at-table-row">`.
* With 4x2, the maximum results shown will be eight, but this could be customized for smaller or larger lists by modifying `$count <=8`.
* N'oubliez pas que la logique n'équilibrera pas les entités sur plusieurs lignes. Par exemple, s'il y a cinq ou six entités à afficher, elles ne seront pas dynamiquement trois fois plus haut et deux sur la partie inférieure (ou trois sur la partie inférieure). La rangée supérieure affiche quatre éléments avant de commencer une seconde ligne.

```
<div class="at-table">
  <div class="at-table-row">
    #set($count=1) 
    #foreach($e in $entities)  
        #if($e.id != "" && $count < $entities.size() && $count <=8) 
            #if($count==5) 
                </div>
                <div class="at-table-row">
            #end
            <div class="at-table-column">
                <a href="$e.pageUrl"><img src="$e.thumbnailUrl" class="at-thumbnail" />
                    <br/>
                    <h3>$e.name</h3>
                    <br/>
                    <p class="at-light">$e.message</p>
                    <br/>
                    <p class="at-light">$$e.value</p>
                </a>
            </div>
            #set($count = $count + 1) 
        #end 
    #end
    </div>
  </div>
```
