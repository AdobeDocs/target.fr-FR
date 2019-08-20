---
description: Liste des questions fréquentes relatives aux conceptions de recommandations.
keywords: recommandations, foire aux questions, faq
seo-description: Liste des questions fréquentes relatives aux conceptions de recommandations.
seo-title: Questions fréquentes sur la conception
solution: Target
title: Questions fréquentes sur la conception
title-outputclass: Premium
topic: Premium
uuid: ac222ade-ddd9-4b32-a16f-4d83b8766384
badge: Premium
translation-type: tm+mt
source-git-commit: 279b6bef59e0b486a9aad7f3b6117edbbe377688

---


# ![PREMIUM](/help/assets/premium.png) FAQ sur la conception {#design-faq}

Liste des questions fréquentes relatives aux conceptions de recommandations.

## Le prix de mon article recommandé n'affiche pas les deux valeurs à droite de la virgule. Comment puis-je les afficher ?

Par défaut, les valeurs numériques (telles `entity.value`que) renvoyées dans les modèles de conception n'affichent aucun zérèse de fin après la virgule. Par exemple, si un élément est 35,00 $, `entity.value` est égal à 35 et 35 seulement à la page, et non à 35,00 $.

Deux options sont disponibles pour résoudre ce problème.

* Vous pouvez utiliser un script Velocity ou Javascript pour appliquer un formatage à la valeur renvoyée.

* Vous pouvez transmettre le prix de l'article en deux attributs d'entité distincts. La première, `entity.value`elle peut être utilisée pour les comparaisons numériques (comme les règles de comparaison de prix). La seconde doit être un attribut personnalisé, tel `entity.displayValue` que le fait de stocker la valeur de l'entité comme chaîne pour permettre un rendu correct.

   Par exemple :

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## Pourquoi la catégorie ne s’affiche-t-elle pas dans la conception ? J’utilise $entity1.categoryId. {#section_073309B8051049C7953D396A93EA0713}

L’ID de catégorie ne peut pas s’afficher dans la conception. Comme plusieurs catégories peuvent être stockées, le système ne saurait pas quelle catégorie afficher.

## Comment dois-je modifier une conception pour obtenir une mise à jour instantanée ? {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

La modification d’une conception en cours d’utilisation prend du temps. Pour modifier la conception instantanément, créez une nouvelle conception, sélectionnez-la dans la campagne et enregistrez la recommandation.

## Comme puis-je capturer des informations clés pour affichage dans la conception ? Exemple : si nous souhaitons afficher la catégorie d’un produit clé, comment encoderais-je cette valeur dans la conception de Velocity ? {#section_F08043B14BA24BC8815FEF25F4F84C39}

Le paramètre `$key. *`valeur`*` capte la plupart des informations des produits clés à afficher dans la conception. Exemple : si vous souhaitiez afficher la miniature d’un produit clé, vous utiliseriez `$key.thumbnailURL`.

## Quelle version de Velocity est utilisée ?{#section_28F00E15A4A54A768782A3F5BB0CDB21}

La version 1.7 sans outil ou bibliothèque ajoutée. La fonctionnalité de base de Velocity est disponible.

## Comment procéder pour remplacer une valeur d’entité existante par une valeur vierge ? Par exemple, le paramètre entity.message d’un élément doit être effacé lorsqu’une promotion se termine. {#section_B88F2C2925DC4508974B2F8B13F961CB}

L’envoi d’un espace insécable JavaScript semble réaliser l’opération. Demandez aux développeurs d’envoyer `\u00A0` comme valeur. Exemple : `entity.message=\u00A0`. Vous pouvez considérer cette valeur comme la valeur par défaut lorsqu’aucune valeur n’est présente à la place de la valeur null.

## Puis-je utiliser un script de profil dans une conception de recommandations ?{#section_6BD55203984A4D80A0C6F241AD7806DF}

Oui. Cependant, vous devez ajouter une barre oblique inversée (\) avant le $ dans le nom du script de profil.
