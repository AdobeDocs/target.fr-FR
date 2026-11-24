---
keywords: conception personnalisée;velocity;décimale;virgule;personnaliser le concept
description: Découvrez comment utiliser le langage de conception open-source [!DNL Velocity] pour personnaliser des conceptions de recommandations dans [!DNL Target] Recommandations.
title: Personnalisation d’une conception à l’aide de Velocity
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
TQID: 'https://experienceleague.adobe.com/cccBRfwqqn-eL2hraSDAoJHPYSCkcA9tVne3OWDXxEU'
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
source-git-commit: f9c9c7b2b78ec020fcabae420686b8955e350a0e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 21%
---
# Personnaliser une conception à l’aide de [!DNL Velocity] {#customize-design}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser le langage de conception open source [!DNL Velocity] pour personnaliser des conceptions de recommandations dans [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

## Vue d’ensemble des [!DNL Velocity] {#velocity-overview}

Vous trouverez des informations sur [!DNL Velocity] à l’adresse [https://velocity.apache.org](https://velocity.apache.org).

Toute la logique [!DNL Velocity], la syntaxe, etc. peuvent être utilisées pour une conception de recommandation. Cela signifie que les boucles *for*, les instructions *if* et d’autres codes peuvent être créés avec [!DNL Velocity] au lieu de JavaScript.

Les attributs d’entité envoyés à [!DNL Recommendations] dans la mbox `productPage` ou le téléchargement CSV peuvent être affichés dans une conception, à l’exception des attributs « à plusieurs valeurs ». Tout type d’attribut peut être envoyé. Cependant, [!DNL Target] ne transmet pas d’attributs de type « à plusieurs valeurs » en tant que tableau sur lequel une conception peut effectuer une itération (par exemple, `entityN.categoriesList`).

Ces valeurs sont référencées par la syntaxe suivante :

```
$entityN.variable
```

Les noms des attributs d’entité doivent suivre une notation abrégée [!DNL Velocity], composée d’un caractère *$* de début, suivi d’un identifiant de langage de modèle (VTL) [!DNL Velocity]. L’identifiant VTL doit commencer par un caractère alphabétique (a-z ou A-Z).

Les noms d&#39;attributs d&#39;entité [!DNL Velocity] sont limités aux types de caractères suivants :

* Alphabétiques (a-z, A-Z)
* Numériques (0-9)
* Trait d’union ( - )
* Trait de soulignement ( _ )

Les attributs suivants sont disponibles sous la forme de tableaux [!DNL Velocity]. Par conséquent, elles peuvent être itérées ou référencées par le biais d’un index.

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

Pour plus d’informations sur les variables [!DNL Velocity] (attributs), consultez la [documentation Velocity](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Si un script de profil est utilisé dans une conception, le caractère $ précédant le nom du script doit être placé dans une séquence d’échappement avec une `\` (barre oblique inverse). Par exemple :

`\${user.script_name}`

>[!NOTE]
>
>Le nombre maximal d&#39;entités pouvant être référencées dans une conception, que ce soit par des boucles codées en dur ou traversantes, est de 99. Le script de conception peut contenir jusqu’à 65 000 caractères.

Une conception qui affiche quelque chose de similaire à l’illustration suivante :

![Exemple d&#39;un design 4 x 1 intitulé « Autres activités amusantes », avec quatre éléments qui montrent chacun une photo, un nom, un prix, une note et une distance](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

peut utiliser le code suivant :

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
>Pour ajouter du texte après la valeur d’un attribut, avant une balise indiquant que le nom de l’attribut est terminé, utilisez une notation formelle pour entourer le nom de l’attribut. Par exemple :`${entity1.thumbnailUrl}.gif`

`algorithm.name` et `algorithm.dayCount` peuvent également être utilisés comme attributs d’entité dans les conceptions, de sorte qu’une conception puisse être utilisée pour tester plusieurs critères et que le nom du critère puisse être affiché de manière dynamique dans la conception. Cela indique au visiteur que le visiteur consulte les « meilleurs vendeurs » ou les « personnes qui ont consulté ceci ont acheté cela ». Le `dayCount` (le nombre de jours de données utilisés dans les critères, par exemple « meilleurs vendeurs au cours des 2 derniers jours ») peut également être affiché.

## Utiliser des nombres dans [!DNL Velocity] conceptions {#numbers}

Par défaut, les conceptions [!DNL Velocity] traitent tous les attributs d&#39;entité comme des valeurs de chaîne. Un attribut d’entité peut devoir être traité comme une valeur numérique pour effectuer une opération mathématique ou pour le comparer à une autre valeur numérique. Pour traiter un attribut d’entité comme une valeur numérique, procédez comme suit :

1. Déclarez une variable factice et initialisez-la sur un entier arbitraire ou sur une valeur double.
1. Assurez-vous que l’attribut d’entité à utiliser n’est pas vide (obligatoire pour que l’analyseur de conception de [!DNL Target Recommendations] valide et enregistre la conception).
1. Transmettez l’attribut d’entité dans la méthode `parseInt` ou `parseDouble` sur la variable factice créée à l’étape 1 pour transformer la chaîne en entier ou en valeur double.
1. Effectuez l’opération mathématique ou la comparaison sur la nouvelle valeur numérique.

### Exemple : calcul d’un prix de remise

Pour réduire le prix affiché d’un article de 0,99 $ afin d’appliquer une remise, la méthode suivante peut être utilisée :

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

Pour afficher un nombre approprié d’étoiles en fonction de l’évaluation client numérique moyenne d’un article, la méthode suivante peut être utilisée :

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

Pour afficher la durée d’un film en heures et en minutes lorsque la durée est stockée en minutes, l’approche suivante peut être utilisée :

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## Affichage d’un article clé avec les produits recommandés {#key-item}

Une conception peut afficher l’élément clé avec les autres produits recommandés. Par exemple, l’élément actif peut être affiché pour référence à côté des recommandations.

Pour ce faire, créez une colonne dans la conception qui utilise l’attribut `$key` sur lequel la recommandation est basée, au lieu de l’attribut `$entity`. Par exemple, le code de la colonne clé peut se présenter comme suit :

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

![Conception avec quatre colonnes, la première colonne affichant l&#39;élément clé marqué comme le produit actuel](/help/main/c-recommendations/c-design-overview/assets/rec_key.png)

Lors de la création d’une activité [!DNL Recommendations], si l’élément clé est extrait du profil du visiteur, par exemple « dernier élément acheté », [!DNL Target] affiche un produit aléatoire dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC). En effet, un profil n’est pas disponible lors de la conception de l’activité. Lorsque les visiteurs consultent la page, ils voient l’élément clé attendu.

## Exécution de remplacements dans une valeur de chaîne {#replacements}

Une conception peut remplacer des valeurs dans une chaîne. Par exemple, le délimiteur décimal avec point utilisé aux États-Unis peut être remplacé par le délimiteur avec virgule utilisé en Europe et dans d’autres pays.

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
</div>
```

## Personnalisation de la taille de conception et vérification des valeurs vides {#default}

Un script [!DNL Velocity] peut contrôler le dimensionnement dynamique de l’affichage de l’entité. La conception suivante prend en compte un résultat 1 à plusieurs pour éviter de créer des éléments HTML vides lorsque trop peu d&#39;entités correspondantes sont renvoyées depuis [!DNL Recommendations]. Ce script est idéal pour les scénarios où les recommandations de sauvegarde n’auraient pas de sens et où le **[!UICONTROL Rendu de conception partiel]** est activé.

L’extrait HTML suivant remplace la partie HTML existante dans la conception par défaut 4 x 2 (le CSS n’est pas inclus ici, par souci de concision) :

* S’il existe une cinquième entité, le script insère une balise closing div et ouvre une nouvelle ligne avec `<div class="at-table-row">`.
* Avec 4x2, le nombre maximal de résultats affichés est de huit, mais cela peut être personnalisé pour des listes plus petites ou plus grandes en modifiant `$count <=8`.
* La logique n’équilibre pas les entités sur plusieurs lignes. Par exemple, s’il y a cinq ou six entités à afficher, elles ne deviennent pas dynamiquement trois en haut et deux en bas (ou trois en haut et trois en bas). La ligne supérieure affiche quatre éléments avant de commencer une deuxième ligne.

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
