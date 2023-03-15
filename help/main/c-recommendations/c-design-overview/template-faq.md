---
keywords: recommandations;foire aux questions;faq
description: Consultez une liste de questions fréquentes (FAQ) relatives aux conceptions Recommandations Adobe  [!DNL Target]  et parcourez les réponses.
title: Où puis-je obtenir des réponses aux questions relatives à la conception pour Recommandations  [!DNL Target]  ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 100%

---

# Questions fréquentes sur la conception

Liste des questions fréquentes (FAQ) relatives aux conceptions [!DNL Adobe Target] [!DNL Recommendations].

## Le prix de mon article recommandé n’affiche pas les deux valeurs à droite de la décimale. Comment les afficher ?

Par défaut, les valeurs numériques (comme `entity.value`) renvoyées dans les modèles de conception n’affichent aucun zéro après la virgule. Par exemple, si un article vaut 35,00 $, `entity.value` est égal à 35. 35, et non 35,00 $ s’affiche donc uniquement sur la page.

Deux solutions permettent de résoudre ce problème:

* Vous pouvez utiliser un script Velocity ou JavaScript pour appliquer une mise en forme à la valeur renvoyée.

* Vous pouvez transmettre le prix de l’article dans deux attributs d’entité distincts. Le premier, `entity.value`, peut être utilisé pour les comparaisons numériques (comme les règles de comparaison de prix). Le second doit être un attribut personnalisé, tel que `entity.displayValue` qui stocke la valeur de l’entité en tant que chaîne pour permettre un rendu correct.

   Par exemple :

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## Pourquoi la catégorie ne s’affiche-t-elle pas dans la conception ? J’utilise `$entity1.categoryId`. {#section_073309B8051049C7953D396A93EA0713}

L’ID de catégorie ne peut pas s’afficher dans la conception. Comme plusieurs catégories peuvent être stockées, le système ne saurait pas quelle catégorie afficher.

## Comment dois-je modifier une conception pour obtenir une mise à jour instantanée ? {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

La modification d’une conception en cours d’utilisation prend du temps. Pour modifier la conception instantanément, créez une nouvelle conception, puis sélectionnez-la dans l’activité et enregistrez la recommandation.

## Comme puis-je capturer des informations clés pour affichage dans la conception ? Exemple : si nous souhaitons afficher la catégorie d’un produit clé, comment encoderais-je cette valeur dans la conception de Velocity ? {#section_F08043B14BA24BC8815FEF25F4F84C39}

Le paramètre `$key. *`valeur`*` capte la plupart des informations des produits clés à afficher dans la conception. Exemple : si vous souhaitiez afficher la miniature d’un produit clé, vous utiliseriez `$key.thumbnailURL`.

## Quelle version de Velocity est utilisée ? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

La version 1.7 sans outil ou bibliothèque ajoutée. La fonctionnalité de base de Velocity est disponible.

## Comment procéder pour remplacer une valeur d’entité existante par une valeur vierge ? Par exemple, le paramètre entity.message d’un élément doit être effacé lorsqu’une promotion se termine. {#section_B88F2C2925DC4508974B2F8B13F961CB}

L’envoi d’un espace insécable JavaScript semble réaliser l’opération. Demandez aux développeurs d’envoyer `\u00A0` comme valeur. Exemple : `entity.message=\u00A0`. Vous pouvez considérer cette valeur comme la valeur par défaut lorsqu’aucune valeur n’est présente à la place de la valeur null.

## Puis-je utiliser un script de profil dans une conception [!DNL Recommendations] ? {#section_6BD55203984A4D80A0C6F241AD7806DF}

Oui. Pour utiliser un script de profil dans une conception [!DNL Recommendations], encapsulez le nom dans `\${...}`. Par exemple, si votre script de profil s’appelle `user.basket`, référencez-le en tant que `\${user.basket}` dans la conception. Notez que la barre oblique inverse implique que le script de profil n’est pas rendu par Velocity. Par conséquent, vous ne pouvez effectuer aucune opération sur le script de profil dans un modèle Velocity. La valeur sera directement imprimée sur la page.
