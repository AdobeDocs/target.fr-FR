---
description: Vous pouvez afficher les valeurs de profil et les informations sur l'activité directement dans une offre HTML ou JSON.
keywords: données dynamiques ; fichiers ; data ; offres ; offres personnalisées ; offres personnelles ; remplacer le jeton
seo-description: Vous pouvez afficher les valeurs de profil et les informations sur l'activité directement dans une offre HTML ou JSON.
seo-title: Transmission de données dynamiques dans les offres
solution: Target
title: Transmission de données dynamiques dans les offres
topic: Premium
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Transmission de données dynamiques dans les offres{#pass-dynamic-data-into-offers}

Vous pouvez afficher dynamiquement les informations sur les visiteurs stockées dans le profil Target. De même, les informations sur l&#39;activité (comme le nom de l&#39;activité ou le nom de l&#39;expérience) peuvent également être utilisées pour créer une offre unique qui renvoie dynamiquement un contenu personnalisé en fonction des intérêts du visiteur, du comportement passé et du profil global.

**Analyses de cas**

* Promouvez une offre réduite pour « redéfinir » ou « reconstituer » le dernier produit acheté. Au lieu de créer une offre distincte pour chaque élément de votre catalogue, vous pouvez créer une offre avec du texte dynamique qui lit le « dernier produit acheté » depuis le profil et affiche un lien dans l&#39;offre.
* Un visiteur arrive sur votre page d’entrée avec `keyword=world` `cup`. Vous affichez les termes *coupe du monde* dans l’offre.
* Personnalisez une étiquette de recommandations avec des informations telles que (1) le dernier élément ajouté au panier d&#39;un visiteur (Nike Air Max 1000 s), (2) la préférence de couleur du visiteur (noir) et (3) la catégorie préférée des non-chaussures du visiteur (hoodies). Exemple : « Accesturez votre « Nike Air Max 1000 s » avec ces « grilles » noires « noires » !  » »


**Avantages techniques**

Comme les préférences, les comportements, l&#39;état, etc. spécifiques à l&#39;utilisateur, peut être stocké dans le profil de l&#39;utilisateur, vous pouvez répéter ce message lors de ses prochaines visites. Les offres dynamiques offrent une plus grande échelle en vous permettant de configurer une offre unique dans une activité qui affiche des messages personnalisés pour tous vos visiteurs. Lorsque le mode d&#39;intention du visiteur change, le contenu de votre site Web reflète automatiquement ces modifications.

**Exemple**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Code offre HTML : `Get your ${profile.keyword} information here!`
* L’utilisateur voit : Restez informé sur la Coupe du monde ici !

Les valeurs suivantes peuvent être « remplacées par un jeton » :

| Valeurs | Exemples |
|--- |--- |
| Paramètres de profil internes à la mbox | `${profile.age}` |
| Paramètres de profil de script | `${user.lifetimeSpend}` |
| Paramètres mbox | `${mbox.favoriteColor}` |
| Informations sur la campagne | `${campaign.name}`, `${campaign.recipe.name}`, `${campaign.id}`, `${campaign.recipe.id}`, et `${campaign.recipe.trafficType}` |
| Identifiant visiteur unique | `${user.pcId}` |
| ID de session unique | `${user.sessionId}` |
| Première session du visiteur (vrai ou faux) | `${user.isFirstSession}` |
| Comportement passé | `{$user.endpoint.lastPurchasedEntity}`, `{$user.endpoint.lastViewedEntity}`, `{$user.endpoint.mostViewedEntity}`, `{$user.endpoint.categoryAffinity}` |

Consigner les informations dans la console à des fins de débogage, telles `${campaign.name}`que `${campaign.id}``${campaign.recipe.name}``${campaign.recipe.id}``${offer.name}``${offer.id}`, `${campaign.name}`

Pour les conceptions de recommandations, reportez-vous à d&#39;autres exemples de [Présentation de la conception](/help/c-recommendations/c-design-overview/design-overview.md).

**Mise en œuvre**

Pour les paramètres de profil transmis à une mbox, utilisez la syntaxe : `${profile.parameter}` Pour les paramètres de profil créés dans un script de profil, utilisez la syntaxe :

`${user.parameter}`

Lors de l&#39;utilisation d&#39;attributs dynamiques dans une conception de recommandations, vous devez insérer une barre oblique inverse (&#39;\&#39;) avant le symbole du dollar (&#39;$&#39;) pour que la valeur dynamique soit correctement rendue : `\${user.endpoint.lastViewedEntity}`

Ces variables sont remplacées par la valeur du côté serveur. Aucun guillemet ni autre code JavaScript n’est nécessaire pour l’affichage.

Des valeurs par défaut peuvent également être précisées pour les valeurs à présenter dans les offres. La syntaxe se présente comme suit :

`${user.testAttribute default="All Items!"}`

Lorsque `testAttribute` n’existe pas ou n’est pas renseigné, sélectionnez « Tous les éléments ». est écrit. Si une valeur d’attribut vide est valide et que vous souhaitez l’écrire plutôt que de présenter la valeur par défaut, utilisez :

`${user.testAttribute default="All Items!" show_blank="true"}`

Vous pouvez également inclure les valeurs à afficher dans une séquence d’échappement et d’annulation d’échappement. Si, par exemple, votre valeur contient une apostrophe, incluez-la dans une séquence d’échappement afin qu’elle ne rompe pas le code JavaScript dans la page. (Les offres sont écrites en JavaScript. Une apostrophe peut donc être prise pour un guillemet simple.) Par exemple :

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`