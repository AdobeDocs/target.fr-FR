---
keywords: données dynamiques ; ressources ; données ; offres ; offres personnalisées ; offres personnelles ; remplacer le jeton
description: Découvrez comment transmettre des données dynamiques dans [!DNL Adobe Target] Offres.
title: Comment puis-je transférer des données dynamiques dans des offres ?
feature: Experiences and Offers
exl-id: b8f9c6eb-1000-41a2-aa3f-bc42c1ef5669
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 63%

---

# Transmission de données dynamiques dans les offres

Vous pouvez afficher dynamiquement les informations sur les visiteurs stockées dans la variable [!DNL Adobe Target] profile. De même, les informations sur l’activité (comme le nom de l’activité ou le nom de l’expérience) peuvent également être utilisées pour créer une offre unique qui renvoie dynamiquement un contenu personnalisé en fonction des intérêts du visiteur, du comportement passé et du profil global.

## Cas d’entreprise

* Promotion d’une offre réduite pour « redéfinir » ou « reconstituer » le dernier produit acheté. Au lieu de créer une offre distincte pour chaque élément de votre catalogue, vous pouvez créer une offre avec du texte dynamique qui lit le « dernier produit acheté » depuis le profil et affiche un lien dans l’offre.
* Un visiteur arrive sur votre page d’entrée avec `keyword=world` `cup`. Vous affichez les termes *coupe du monde* dans l’offre.
* Personnalisez une étiquette Recommendations avec des informations telles que (1) le dernier élément ajouté au panier d’un visiteur (une paire de Nike Air Max 1000), (2) la préférence de couleur du visiteur (noir) et (3) la catégorie préférée du visiteur autre que les chaussures (sweat-shirts à capuche). Exemple : « Accessoirisez vos « Nike Air Max 1000 » avec ces « sweat-shirts à capuche » « noirs » ! »

## Avantages techniques

Les préférences, les comportements et l’état spécifiques au visiteur pouvant être stockés dans le profil du visiteur, vous pouvez répéter ce message lors de leurs prochaines visites. Les offres dynamiques offrent une plus grande échelle en vous permettant de configurer une offre unique dans une activité qui affiche des messages personnalisés pour tous vos visiteurs. Le contenu de votre site web change automatiquement pour refléter les modifications des intentions du visiteur.

## Exemple

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Code offre HTML : `Get your ${profile.keyword} information here!`
* Le visiteur voit : Trouvez vos informations sur la Coupe du Monde ici !

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

Pour [!DNL Recommendations] conceptions, voir d’autres exemples dans [Aperçu de la conception](/help/main/c-recommendations/c-design-overview/design-overview.md).

## Mise en œuvre

Pour les paramètres de profil transmis dans une mbox, utilisez la syntaxe :

`${profile.parameter}`

Pour les paramètres de profil créés dans un script de profil, utilisez la syntaxe :

`${user.parameter}`

Lors de l’utilisation d’attributs dynamiques dans une [!DNL Recommendations] conception, vous devez insérer une barre oblique inverse ( \ ) avant le symbole du dollar ( $ ) pour que la valeur dynamique soit correctement rendue :

`\${user.endpoint.lastViewedEntity}`

Ces variables sont remplacées par la valeur du côté serveur. Aucun guillemet ni autre code JavaScript n’est nécessaire pour l’affichage.

Les valeurs par défaut peuvent également être spécifiées pour les valeurs que vous souhaitez exposer aux offres. La syntaxe se présente comme suit :

`${user.testAttribute default="All Items!"}`

Lorsque `testAttribute` n’existe pas ou n’est pas renseigné, sélectionnez « Tous les éléments ». est écrit. Si une valeur d’attribut vide est valide et que vous souhaitez l’écrire plutôt que de présenter la valeur par défaut, utilisez :

`${user.testAttribute default="All Items!" show_blank="true"}`

Vous pouvez également inclure les valeurs à afficher dans une séquence d’échappement et d’annulation d’échappement. Si votre valeur comporte une apostrophe, par exemple, vous pouvez ajouter une séquence d’échappement afin de ne pas interrompre le code JavaScript sur la page. (Les offres sont écrites en JavaScript. Une apostrophe peut donc être prise pour un guillemet simple.) Par exemple :

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`

Pour les paramètres d’offre (offer.name, offer.id) utilisés dans le contenu d’une offre :

Si cette offre est l’une des nombreuses offres définies sur une expérience, la valeur de la dernière offre ajoutée renseigne la valeur du paramètre. En d’autres termes, ces paramètres sont évalués au niveau de l’expérience.