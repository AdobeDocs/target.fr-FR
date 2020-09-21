---
keywords: recommendations;frequently asked questions;faq
description: Liste des questions fréquentes (FAQ) sur les conceptions des recommandations Adobe Target.
title: Questions fréquentes sur la conception
feature: designs
uuid: ac222ade-ddd9-4b32-a16f-4d83b8766384
translation-type: tm+mt
source-git-commit: afbec50cb0ec4e689bfaa77296ffda91bc6de3a5
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 87%

---


# ![PREMIUM](/help/assets/premium.png) FAQ sur la conception {#design-faq}

List of frequently asked questions (FAQs) about [!DNL Adobe Target] recommendations designs.

## Le prix de mon article recommandé n’affiche pas les deux valeurs à droite de la décimale. Comment les afficher ?

Par défaut, les valeurs numériques (comme `entity.value`) renvoyées dans les modèles de conception n’affichent aucun zéro après la virgule. Par exemple, si un article vaut 35,00 $, `entity.value` est égal à 35. 35, et non 35,00 $ s’affiche donc uniquement sur la page.

Deux solutions permettent de résoudre ce problème:

* Vous pouvez utiliser un script Velocity ou JavaScript pour appliquer une mise en forme à la valeur renvoyée.

* Vous pouvez transmettre le prix de l’article dans deux attributs d’entité distincts. Le premier, `entity.value`, peut être utilisé pour les comparaisons numériques (comme les règles de comparaison de prix). Le second doit être un attribut personnalisé, tel que `entity.displayValue` qui stocke la valeur de l’entité en tant que chaîne pour permettre un rendu correct.

   Par exemple :

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## Pourquoi la catégorie ne s’affiche-t-elle pas dans la conception ? J’utilise $entity1.categoryId. {#section_073309B8051049C7953D396A93EA0713}

L’ID de catégorie ne peut pas s’afficher dans la conception. Comme plusieurs catégories peuvent être stockées, le système ne saurait pas quelle catégorie afficher.

## Comment dois-je modifier une conception pour obtenir une mise à jour instantanée ? {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

La modification d’une conception en cours d’utilisation prend du temps. Pour modifier la conception instantanément, créez une nouvelle conception, sélectionnez-la dans l’activité, puis enregistrez la recommandation.

## Comme puis-je capturer des informations clés pour affichage dans la conception ? Exemple : si nous souhaitons afficher la catégorie d’un produit clé, comment encoderais-je cette valeur dans la conception de Velocity ? {#section_F08043B14BA24BC8815FEF25F4F84C39}

Le paramètre `$key. *`valeur`*` capte la plupart des informations des produits clés à afficher dans la conception. Exemple : si vous souhaitiez afficher la miniature d’un produit clé, vous utiliseriez `$key.thumbnailURL`.

## Quelle version de Velocity est utilisée ?{#section_28F00E15A4A54A768782A3F5BB0CDB21}

La version 1.7 sans outil ou bibliothèque ajoutée. La fonctionnalité de base de Velocity est disponible.

## Comment procéder pour remplacer une valeur d’entité existante par une valeur vierge ? Par exemple, le paramètre entity.message d’un élément doit être effacé lorsqu’une promotion se termine. {#section_B88F2C2925DC4508974B2F8B13F961CB}

L’envoi d’un espace insécable JavaScript semble faire cela. Demandez aux développeurs d’envoyer `\u00A0` comme valeur. Exemple : `entity.message=\u00A0`. Vous pouvez considérer cette valeur comme la valeur par défaut lorsqu’aucune valeur n’est présente à la place de la valeur null.

## Puis-je utiliser un script de profil dans une conception de recommandations ?{#section_6BD55203984A4D80A0C6F241AD7806DF}

Oui. Cependant, vous devez ajouter une barre oblique inversée (\) avant le $ dans le nom du script de profil.
