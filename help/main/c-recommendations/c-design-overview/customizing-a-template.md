---
keywords: conception personnalisée;velocity;décimale;virgule;personnaliser le concept
description: Découvrez comment utiliser le langage de conception open-source Velocity pour personnaliser des conceptions de recommandations dans les Recommandations Adobe  [!DNL Target] .
title: Comment personnaliser une conception à l’aide de Velocity ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 72%

---

# Personnalisation d’une conception à l’aide de Velocity

Utilisez le langage de conception open-source Velocity pour personnaliser des conceptions de recommandations dans [!DNL Adobe Target Recommendations].

## Présentation de Velocity {#section_C431ACA940BC4210954C7AEFF6D03EA5}

Vous trouverez des informations concernant Velocity à l’adresse [https://velocity.apache.org](https://velocity.apache.org).

Toute la syntaxe et tout le code Velocity peuvent servir pour une conception de recommandation. Vous pouvez donc créer des *boucles*, des conditions (« *si* ») et tout autre code en utilisant Velocity au lieu de JavaScript.

Les attributs d’entité envoyés à [!DNL Recommendations] dans la mbox `productPage` ou le transfert CSV peuvent être affichés dans une conception, à l’exception des attributs &quot;à plusieurs valeurs&quot;. N’importe quel type d’attribut peut être envoyé. Cependant, [!DNL Target] ne transmet pas d’attributs de type &quot;multi-valeur&quot; en tant que tableau sur lequel un modèle peut itérer (par exemple `entityN.categoriesList`).

Ces valeurs sont référencées par la syntaxe suivante :

```
$entityN.variable
```

Les noms d’attribut d’entité doivent suivre la notation abrégée Velocity, qui consiste en un caractère *$* de début, suivi d’un identifiant de langage de modèle Velocity (VTL). L’identifiant VTL doit commencer par un caractère alphabétique (a-z ou A-Z).

Les noms d’attributs d’entité Velocity sont limités aux types de caractères suivants :

* Alphabétiques (a-z, A-Z)
* Numériques (0-9)
* Trait d’union ( - )
* Trait de soulignement ( _ )

Les attributs suivants sont disponibles sous forme de tableaux Velocity. À ce titre, elles peuvent être itérées ou référencées par l’intermédiaire d’un index.

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

Pour plus d’informations sur les variables Velocity (attributs), voir [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Si vous utilisez un script de profil dans votre conception, le $ précédant le nom du script doit être échappé avec une `\` (barre oblique inverse). Par exemple :

`\${user.script_name}`

>[!NOTE]
>
>Le nombre maximum d’entités qu’il est possible de référencer dans une conception, que ce soit par le biais de boucles ou d’un codage en dur, est de 99. Le script du modèle peut contenir jusqu’à 65 000 caractères.

Par exemple, si vous souhaitez qu’une conception affiche ce qui suit :

![velocity_example image](assets/velocity_example.png)

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

>[!NOTE]
>
>Si vous souhaitez ajouter du texte après la valeur d’un attribut avant une balise qui indique que le nom de l’attribut est terminé, vous pouvez utiliser une notation formelle pour joindre le nom de l’attribut. Par exemple : `${entity1.thumbnailUrl}.gif`.

Vous pouvez également utiliser `algorithm.name` et `algorithm.dayCount` comme attributs d’entité dans les conceptions. Ainsi, une conception peut être utilisée pour tester plusieurs critères et le nom du critère peut être affiché de manière dynamique dans la conception. Cela indique au visiteur qu’il consulte « les meilleurs vendeurs » ou « les personnes qui ont consulté ceci ont acheté cela ». Vous pouvez même utiliser ces attributs pour afficher le `dayCount` (nombre de jours de données utilisé dans les critères, comme &quot;éléments les plus vendus au cours des deux derniers jours&quot;, etc.).

## Utilisation de nombres dans les modèles Velocity

Par défaut, les modèles Velocity traitent tous les attributs d’entité comme des valeurs de chaîne. Vous pouvez considérer un attribut d’entité comme une valeur numérique afin d’effectuer une opération mathématique ou de le comparer à une autre valeur numérique. Pour traiter un attribut d’entité comme une valeur numérique, procédez comme suit :

1. Déclarez une variable factice et initialisez-la sur un entier arbitraire ou sur une valeur double.
1. Assurez-vous que l’attribut d’entité que vous souhaitez utiliser n’est pas vide (obligatoire pour l’analyseur de modèles de [!DNL Target Recommendations] afin de valider et d’enregistrer le modèle).
1. Transmettez l’attribut d’entité dans la méthode `parseInt` ou `parseDouble` sur la variable factice que vous avez créée à l’étape 1 pour transformer la chaîne en entier ou en valeur double.
1. Effectuez l’opération mathématique ou la comparaison sur la nouvelle valeur numérique.

### Exemple : calcul d’un prix de remise

Supposons que vous souhaitiez réduire le prix affiché d’un article de 0,99 $ pour appliquer une remise. Pour obtenir ce résultat, vous pouvez utiliser l’approche suivante :

```
#set( $double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### Exemple : choix du nombre d’étoiles à afficher en fonction de l’évaluation d’un article

Supposons que vous souhaitiez afficher un nombre approprié d’étoiles en fonction de l’évaluation client numérique moyenne d’un article. Pour obtenir ce résultat, vous pouvez utiliser l’approche suivante :

```
#set( $double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $double.parseDouble($entity1.get('rating')) )
    #if( $rating >= 4.5 )
        <img src="5_stars.jpg">
    #elseif( $rating >= 3.5 )
        <img src="4_stars.jpg">
    #elseif( $rating >= 2.5 )
        <img src="3_stars.jpg">
    #elseif( $rating >= 1.5 )
        <img src="2_stars.jpg">
    #else
        <img src="1_star.jpg">
    #end
#else
    <img src="no_rating_default.jpg">
#end
```

### Exemple : calcul du temps en heures et en minutes en fonction de la durée en minutes d’un article

Supposons que vous stockiez la durée d’un film en minutes, mais que vous souhaitiez afficher la durée en heures et en minutes. Pour obtenir ce résultat, vous pouvez utiliser l’approche suivante :

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## Affichage d’un article clé avec les produits recommandés {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

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

![image rec_key](assets/rec_key.png)

Lors de la création de votre activité [!DNL Recommendations], si l’élément clé est tiré du profil du visiteur, par exemple &quot;dernier article acheté&quot;, [!DNL Target] affiche un produit aléatoire dans le [!UICONTROL Visual Experience Composer] (VEC). Cela est dû à l’indisponibilité du profil lors de la conception de l’activité. Quand les visiteurs visualisent la page, ils visualiseront l’élément clé attendu.

## Exécution de remplacements dans une valeur de chaîne {#section_01F8C993C79F42978ED00E39956FA8CA}

Vous pouvez modifier votre conception afin de remplacer les valeurs d’une chaîne. Par exemple, en remplaçant le séparateur décimal avec point utilisé aux États-Unis par le séparateur avec virgule utilisé en Europe et dans d’autres pays.

Le code suivant présente une ligne unique dans un exemple de tarification de vente conditionnelle :

```
<span class="price">$entity1.value.replace(".", ",") &euro;</span><br>
```

Le code suivant est un exemple conditionnel complet d’un prix de vente :

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") &euro;</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") &euro;<br> #else 
    <span class="price">$entity1.value.replace(".", ",") &euro;</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## Personnalisation de la taille du modèle et vérification des valeurs vides {#default}

En utilisant un script Velocity pour contrôler le dimensionnement dynamique de l’affichage de l’entité, le modèle suivant prend en charge un résultat de 1 à plusieurs pour éviter la création d’éléments HTML vides lorsqu’il n’y a pas assez d’entités correspondantes renvoyées [!DNL Recommendations]. Ce script est idéal pour les scénarios lorsque les recommandations de sauvegarde n’ont pas de sens et que [!UICONTROL Partial Template Rendering] est activé.

L’extrait HTML suivant remplace la partie HTML existante dans la conception par défaut 4 x 2 (le CSS n’est pas inclus ici, par souci de concision) :

* S’il existe une cinquième entité, le script insère une balise closing div et ouvre une nouvelle ligne avec `<div class="at-table-row">`.
* Avec 4 x 2, le nombre maximal de résultats affichés est de huit, mais il peut être personnalisé pour les plus petites ou plus grandes listes en modifiant `$count <=8`.
* N’oubliez pas que la logique n’équilibrera pas les entités sur plusieurs lignes. Par exemple, s’il y a cinq ou six entités à afficher, elles ne seront pas placées dynamiquement trois en haut et deux en bas (ou trois en haut et trois en bas). La rangée supérieure affichera quatre éléments avant de commencer une seconde ligne.

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
