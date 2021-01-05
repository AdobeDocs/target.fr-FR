---
keywords: dynamic data;assets;data;offers;personalized offers;personal offers;token replace
description: Vous pouvez afficher les valeurs de profil et les informations sur les campagnes directement dans une offre HTML ou JSON.
title: Transmission de données dynamiques dans les offres
feature: offers
translation-type: tm+mt
source-git-commit: 431ccc937a3ad4aaf735b31b4790ead43a6fc4d9
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 94%

---


# Transmission de données dynamiques dans les offres{#pass-dynamic-data-into-offers}

Vous pouvez afficher dynamiquement les informations sur les visiteurs stockées dans le profil Target. De même, les informations sur l’activité (comme le nom de l’activité ou le nom de l’expérience) peuvent également être utilisées pour créer une offre unique qui renvoie dynamiquement un contenu personnalisé en fonction des intérêts du visiteur, du comportement passé et du profil global.

**Analyses de cas**

* Promotion d’une offre réduite pour « redéfinir » ou « reconstituer » le dernier produit acheté. Au lieu de créer une offre distincte pour chaque élément de votre catalogue, vous pouvez créer une offre avec du texte dynamique qui lit le « dernier produit acheté » depuis le profil et affiche un lien dans l’offre.
* Un visiteur arrive sur votre page d’entrée avec `keyword=world` `cup`. Vous affichez les termes *coupe du monde* dans l’offre.
* Personnalisez une étiquette Recommendations avec des informations telles que (1) le dernier élément ajouté au panier d’un visiteur (une paire de Nike Air Max 1000), (2) la préférence de couleur du visiteur (noir) et (3) la catégorie préférée du visiteur autre que les chaussures (sweat-shirts à capuche). Exemple : « Accessoirisez vos « Nike Air Max 1000 » avec ces « sweat-shirts à capuche » « noirs » ! »


**Avantages techniques**

Comme les préférences, les comportements, l’état, etc., spécifiques à l’utilisateur, peuvent être stockés dans le profil de l’utilisateur, vous pouvez répéter ce message lors de ses prochaines visites. Les offres dynamiques offrent une plus grande échelle en vous permettant de configurer une offre unique dans une activité qui affiche des messages personnalisés pour tous vos visiteurs. Le contenu de votre site web change automatiquement pour refléter les modifications des intentions du visiteur.

**Exemple**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Code offre HTML : `Get your ${profile.keyword} information here!`
* L’utilisateur voit : Restez informé sur la Coupe du monde ici !

Les valeurs suivantes peuvent être « remplacées par un jeton » :

| Valeur | Exemples |
|--- |--- |
| Paramètres de profil internes à la mbox | `${profile.age}` |
| Paramètres de profil de script | `${user.lifetimeSpend}` |
| Paramètres mbox | `${mbox.favoriteColor}` |
| Informations sur la campagne | `${campaign.name}`, `${campaign.recipe.name}`, `${campaign.id}`, `${campaign.recipe.id}`, et `${campaign.recipe.trafficType}` |
| Identifiant visiteur unique | `${user.pcId}` |
| ID de session unique | `${user.sessionId}` |
| Première session du visiteur (vrai ou faux) | `${user.isFirstSession}` |
| Comportement passé | `${user.endpoint.lastPurchasedEntity}`, `${user.endpoint.lastViewedEntity}`, `${user.endpoint.mostViewedEntity}`, `${user.endpoint.categoryAffinity}` |

Consigner les informations dans la console à des fins de débogage, telles que `${campaign.name}`, `${campaign.id}`, `${campaign.recipe.name}`, `${campaign.recipe.id}`, `${offer.name}`, `${offer.id}`, `${campaign.name}`

Pour les conceptions de Recommendations, reportez-vous à d’autres exemples de [Présentation de conceptions](/help/c-recommendations/c-design-overview/design-overview.md).

**Mise en œuvre**

Pour les paramètres de profil transmis dans une mbox, utilisez la syntaxe : `${profile.parameter}`. Pour les paramètres de profil créés dans un Profil script, utilisez la syntaxe :

`${user.parameter}`

Lors de l’utilisation d’attributs dynamiques dans une conception Recommendations, vous devez insérer une barre oblique inverse ( \ ) avant le signe dollar ( $ ) pour que la valeur dynamique s’affiche correctement : `\${user.endpoint.lastViewedEntity}`

Ces variables sont remplacées par la valeur du côté serveur. Aucun guillemet ni autre code JavaScript n’est nécessaire pour l’affichage.

Des valeurs par défaut peuvent également être précisées pour les valeurs à présenter dans les offres. La syntaxe se présente comme suit :

`${user.testAttribute default="All Items!"}`

Lorsque `testAttribute` n’existe pas ou n’est pas renseigné, sélectionnez « Tous les éléments ». est écrit. Si une valeur d’attribut vide est valide et que vous souhaitez l’écrire plutôt que de présenter la valeur par défaut, utilisez :

`${user.testAttribute default="All Items!" show_blank="true"}`

Vous pouvez également inclure les valeurs à afficher dans une séquence d’échappement et d’annulation d’échappement. Si, par exemple, votre valeur contient une apostrophe, incluez-la dans une séquence d’échappement afin qu’elle ne rompe pas le code JavaScript dans la page. (Les offres sont écrites en JavaScript. Une apostrophe peut donc être prise pour un guillemet simple.) Par exemple :

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`