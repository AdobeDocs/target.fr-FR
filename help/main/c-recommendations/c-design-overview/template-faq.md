---
keywords: recommandations;foire aux questions;faq
description: Questions fréquentes (FAQ) sur les conceptions [!DNL Target Recommendations] et réponses.
title: Questions fréquentes sur la conception
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
TQID: 'https://experienceleague.adobe.com/xRu0XEnc8wX8PZngba7CO67mFdja7HALL-1OSnhAmuY'
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
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 19%
---
# Questions fréquentes sur la conception {#design-faq}

>[!BEGINSHADEBOX]

**Sur cette page :** Trouvez des réponses aux questions fréquentes sur les conceptions [!DNL Adobe Target] [!DNL Recommendations].

>[!ENDSHADEBOX]

+++ Comment le prix d&#39;un article recommandé peut-il afficher les deux chiffres à droite de la décimale ?

Par défaut, les valeurs numériques (telles que `entity.value`) renvoyées dans les conceptions n’affichent pas de zéros de fin après la décimale. Par exemple, si un article coûte 35,00 $, `entity.value` est égal à 35 et seul 35 est affiché sur la page, et non 35,00 $.

Deux solutions permettent de résoudre ce problème:

* Les scripts Velocity ou JavaScript peuvent mettre en forme la valeur renvoyée.

* Le prix de l’article peut être transmis dans deux attributs d’entité distincts. Le premier, `entity.value`, peut être utilisé pour les comparaisons numériques (comme les règles de comparaison de prix). Le second doit être un attribut personnalisé, tel que `entity.displayValue`, qui stocke la valeur de l’entité sous la forme d’une chaîne pour permettre un rendu correct.

  Par exemple :

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

+++

+++ Pourquoi la catégorie n’est-elle pas affichée dans la conception lorsque $entity1.categoryId est utilisé ?

L’ID de catégorie ne peut pas être affiché dans une conception. Plusieurs catégories peuvent être stockées. Par conséquent, le système ne sait pas quelle catégorie afficher.

+++

+++ Comment modifier une conception pour obtenir une mise à jour instantanée ?

La modification d’une conception en cours d’utilisation prend du temps. Pour modifier la conception instantanément, créez une nouvelle conception, puis sélectionnez-la dans l’activité et enregistrez la recommandation.

+++

+++ Comment les informations clés, telles que la catégorie du produit clé, peuvent-elles être affichées dans une conception ?

Les paramètres `$key` capturent la plupart des informations du produit clé pour les afficher dans la conception. Par exemple, pour afficher la miniature du produit clé, utilisez `$key.thumbnailURL`.

+++

+++ Quelle version de Velocity est utilisée ?

Version 1.7, sans outils ni bibliothèques supplémentaires ajoutés. La fonctionnalité de base de Velocity est disponible.

+++

+++ Comment une valeur d’entité existante peut-elle être remplacée par une valeur vide, par exemple lorsque le paramètre entity.message d’un élément doit être effacé à la fin d’une promotion ?

L’envoi d’un espace insécable JavaScript semble réaliser l’opération. Les développeurs envoient `\u00A0` comme valeur, par exemple `entity.message=\u00A0`. L’utilisation de cette valeur comme valeur par défaut lorsqu’aucune valeur n’est présente, au lieu d’une valeur nulle, peut également être prise en compte.

+++

+++ Un script de profil peut-il être utilisé dans une conception [!DNL Recommendations] ?

Oui. Pour utiliser un script de profil dans une conception [!DNL Recommendations], encapsulez le nom dans `\${...}`. Par exemple, si le script de profil s’appelle `user.basket`, faites-lui référence en tant que `\${user.basket}` dans la conception. La barre oblique inverse implique que le script de profil n’est pas rendu par Velocity, de sorte qu’aucune opération ne peut être effectuée sur le script de profil dans un modèle Velocity. La valeur est imprimée directement sur la page.

+++
