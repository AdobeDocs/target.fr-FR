---
keywords: recommendation key;recommendation logic;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: Recommendations basé sur les clés utilise le contexte de comportement des visiteurs pour afficher les résultats pertinents dans les activités Adobe Target Recommendations.
title: Baser la recommandation sur une clé de recommandation
feature: criteria
mini-toc-levels: 2
translation-type: tm+mt
source-git-commit: 00749d54d0416c57364ff648bd0911e636c84bc7
workflow-type: tm+mt
source-wordcount: '1452'
ht-degree: 97%

---


# Baser la recommandation sur une clé de recommandation

Recommendations based on keys utilize visitor behavior context to show relevant results in [!DNL Adobe Target] [!DNL Recommendations] activities.

Il existe deux types de recommandations :

* **Popularité :** dresse la liste des éléments d’après les critères Les plus consultés, Les plus vendus et Mesure maximale. La clé est vide pour les critères de popularité.
* **Basé sur une clé :** inclut le reste des critères. Recommandations propose un large éventail de choix de types de clé. Les options vont de « élément actif » à « paramètres de profil » pour vous permettre de définir par voie programmatique la clé des valeurs à recommander. Vous pouvez tester plusieurs critères les uns par rapport aux autres en basant chaque critère sur une clé différente.

Chaque critère est défini dans son propre onglet. Le trafic est réparti uniformément entre vos différents tests de critères. En d’autres termes, si vous avez deux critères, le trafic est réparti uniformément entre les deux. Si vous avez deux critères et deux conceptions, le trafic est réparti uniformément entre les quatre combinaisons. Vous pouvez également spécifier le pourcentage des visiteurs du site qui visualisent le contenu par défaut, à des fins de comparaison. Dans ce cas, le pourcentage spécifié des visiteurs du site qui visualisent le contenu par défaut et les autres sont répartis entre vos combinaisons critère/conception.

1. Créez une recommandation ou sélectionnez une recommandation existante, puis cliquez sur **[!UICONTROL Modifier]**.
1. Pour changer de clé de recommandation, sélectionnez la nouvelle clé dans la liste déroulante [!UICONTROL Clé de recommandation] puis cliquez sur **[!UICONTROL Sauvegarder]**.

   Différentes logiques renvoient vers différentes clés de recommandation. Par conséquent, différentes recommandations renvoient à des emplacements sur différents types de page. Pour plus d’informations sur chaque clé, consultez les sections suivantes.

## Article actuel

La recommandation est déterminée par l’article que le visiteur consulte actuellement.

Les recommandations présentent d’autres articles susceptibles d’intéresser les visiteurs qui consultent l’article spécifié.

Lorsque cette option est sélectionnée, la valeur `entity.id` doit être transmise comme un paramètre à la mbox d’affichage.

### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

### Où l’utiliser sur votre site

Pages d’un seul article (pages de produit, par exemple).

Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

## Catégorie en cours

La recommandation est déterminée par la catégorie de produits que le visiteur consulte actuellement.

Les recommandations présentent des articles dans la catégorie de produits spécifiée.

Lorsque cette option est sélectionnée, la valeur `entity.categoryId` doit être transmise comme paramètre à la mbox d’affichage.

### Logique (critère)

* Meilleurs vendeurs
* Les plus consultés

### Où l’utiliser sur votre site

Pages d’une seule catégorie.

Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

## Attribut personnalisé {#custom}

La recommandation est déterminée par un article stocké dans un profil de visiteur, utilisant les attributs user.*x>* ou profile.attributs *x*.

Si cette option est sélectionnée, la valeur `entity.id` doit être présente dans l’attribut de profil.

### Logique (critère)

* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Comportement global]
* [!UICONTROL Les plus consultés]
* [!UICONTROL Meilleurs vendeurs]

Si la clé est un attribut de profil personnalisé et que le type d’algorithme est Le plus consulté ou Meilleurs vendeurs, une nouvelle liste déroulante intitulée « Grouper par valeur unique de » s’affiche et indique la liste des attributs d’entité connus (ID d’exception, catégorie, marge, valeur, inventaire et environnement). Ce champ est obligatoire.

### Où l’utiliser sur votre site

Peut être utilisé sur n’importe quelle page.

### Utilisation d’une clé de recommandations personnalisée

Vous pouvez axer les recommandations sur la valeur d’un attribut de profil personnalisé. Supposons, par exemple, que vous souhaitiez afficher les films recommandés en fonction de la séquence que le visiteur a ajoutée le plus récemment à sa file d’attente.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Dernier affichage ajouté à la liste de surveillance »).
1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** (par exemple « Personnes qui ont vu ceci, vu cela »).

   ![Boîte de dialogue Créer de nouveaux critères](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Si votre attribut de profil personnalisé ne correspond pas directement à un ID d’entité unique, il est nécessaire d’expliquer à [!DNL Recommendations] la manière dont vous souhaitez que la correspondance à une entité se produise. Supposons, par exemple, que vous souhaitiez afficher les principaux articles de la marque préférée d’un visiteur.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Marque préférée »).

1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** que vous souhaitez utiliser avec cette clé (par exemple, « Meilleurs vendeurs »).

   L’option [!UICONTROL Groupe par valeur unique de] s’affiche.

1. Sélectionnez l’attribut d’entité correspondant à la clé choisie. Dans ce cas, « Marque préférée » correspond à `entity.brand`.

   [!DNL Recommendations] génère désormais une liste des « Meilleurs vendeurs » pour chaque marque et montre au visiteur la liste des « Meilleurs vendeurs » en fonction de la valeur stockée dans l’attribut de profil Marque préférée du visiteur.

   ![Boîte de dialogue Créer de nouveaux critères 2](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

## Dernier article acheté

La recommandation est déterminée par le dernier article acheté par chaque visiteur unique. Ces données sont capturées automatiquement. Aucune valeur ne doit donc être transmise sur la page.

### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

### Où l’utiliser sur votre site

Page d’accueil, page Mon compte, publicités hors site.

Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

## Dernier article consulté

La recommandation est déterminée par le dernier élément consulté par chaque visiteur unique. Ces données sont capturées automatiquement. Aucune valeur ne doit donc être transmise sur la page.

### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

### Où l’utiliser sur votre site

Page d’accueil, page Mon compte, publicités hors site.

Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

## Article le plus consulté

La recommandation est déterminée par l’élément le plus souvent consulté, à l’aide de la même méthode que celle de la catégorie préférée.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de produit
* 5 points pour chaque consultation consécutive
* À la fin de la session, toutes les valeurs sont divisées par 2

Par exemple, l’affichage de surfboardA, puis de surfboardB dans une même session donne A : 10, B : 5. À la fin de la session, vous avez A : 5, B : 2,5. Si vous consultez les mêmes éléments au cours de la prochaine session, les valeurs deviennent A : 15 B : 7,5.

### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

## Catégorie préférée

La recommandation est déterminée par la catégorie associée au plus haut niveau d’activité, à l’aide de la même méthode que celle utilisée pour « Article le plus consulté », sauf que le score porte sur les catégories et non sur les produits.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de catégorie
* 5 points pour chaque consultation consécutive

Les catégories consultées pour la première fois reçoivent dix points. Les visites suivantes dans la même catégorie reçoivent cinq points. À chaque visite, les catégories non actuelles qui ont été consultées auparavant sont décrémentées de 1.

Par exemple, l’affichage de categorieA, puis de categorieB dans une même session donne A : 9, B : 10. Si vous affichez les mêmes éléments lors de la session suivante, les valeurs passent à A : 20, B : 9.

### Logique (critère)

* [!UICONTROL Meilleurs vendeurs]
* [!UICONTROL Les plus consultés]

### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

## Popularité

La recommandation est déterminée par la popularité des éléments de votre site. La popularité comprend les articles les plus vendus et les plus consultés selon les données de la mbox et, si vous utilisez Adobe Analytics, toutes les mesures disponibles dans le rapport sur les produits. Les articles sont classés en fonction de la logique de recommandation sélectionnée.

### Logique (critère)

* [!UICONTROL Meilleurs vendeurs]
* [!UICONTROL Les plus consultés]
* Mesures de rapport de produit (si vous utilisez Adobe Analytics)

### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

## Éléments récemment consultés {#recently-viewed}

Utilise l’historique du visiteur (sur plusieurs sessions) pour présenter les *x* derniers éléments consultés par le visiteur, en fonction du nombre d’emplacements dans la conception.

Le critère Éléments récemment consultés renvoie désormais des résultats spécifiques à un [environnement](/help/administrating-target/hosts.md) donné. Si deux sites appartiennent à différents environnements et qu’un visiteur bascule entre les deux sites, chaque site n’affiche que les éléments récemment consultés du site approprié. Si deux sites se trouvent dans le même environnement et qu’un visiteur bascule entre les deux sites, le visiteur voit les mêmes éléments récemment consultés pour les deux sites.

### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

>[!NOTE]
>
>Les éléments récemment consultés respectent les paramètres globaux Exclusions et le paramètre Collection sélectionné pour l’activité. Si un élément est exclu par une exclusion globale ou ne figure pas dans la collection sélectionnée, il ne sera pas affiché. Par conséquent, lors de l’utilisation d’un critère Eléments récemment consultés, le paramètre « Toutes les collections » doit généralement être utilisé.