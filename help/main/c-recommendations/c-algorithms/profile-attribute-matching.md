---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance d’attributs de profil
description: Découvrez comment filtrer dynamiquement dans [!DNL Target Recommendations] en comparant des éléments (entités) à une valeur dans le profil de l’utilisateur.
title: Correspondance des attributs de profil
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
TQID: 'https://experienceleague.adobe.com/Gm91Mww5ylvNjUcmzp6KwxIG6LTibvI44LnW67KFzqk'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 5%
---
# Correspondance des attributs de profil {#profile-attribute-matching}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment filtrer les recommandations de manière dynamique dans [!DNL Adobe Target Recommendations] en comparant des éléments (entités) à une valeur dans le profil du visiteur.

>[!ENDSHADEBOX]

Utilisez **[!UICONTROL Correspondance des attributs de profil]** pour afficher les recommandations correspondant à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée. Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Pour plus d’informations, voir [Utilisation de règles d’inclusion dynamiques et statiques](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

Les scénarios suivants montrent comment la **[!UICONTROL correspondance des attributs de profil]** peut être utilisée :

* Une entreprise qui vend des lunettes stocke la couleur de monture préférée d&#39;un visiteur comme « noyer ». Pour ce visiteur, les recommandations sont configurées pour renvoyer uniquement les montures de lunettes correspondant à la couleur « noyer ».
* Un paramètre de profil peut être défini pour la taille des vêtements (par exemple, Petit, Medium ou Grand) d’un visiteur ou d’une visiteuse lorsque celui-ci ou celle-ci navigue sur le site web de la société. Une recommandation peut être configurée pour correspondre à ce paramètre de profil et renvoyer uniquement les produits dans la taille de vêtement souhaitée du visiteur.

## Exemples de correspondance d’attributs de profil

**[!UICONTROL La correspondance des attributs de profil]** recommande uniquement les éléments qui correspondent à un attribut du profil du visiteur, comme dans les exemples suivants.

### Recommandation d’articles de la marque préférée de l’utilisateur

L&#39;option **[!UICONTROL Correspondance des attributs de profil]** peut créer une règle qui recommande des éléments uniquement lorsque la marque est égale à la valeur ou au texte stocké dans `profile.favoritebrand`. Avec une telle règle, si un visiteur recherche des shorts de course d’une marque particulière, seules les recommandations correspondant à sa marque préférée (la valeur stockée dans `profile.favoritebrand` dans le profil du visiteur) s’affichent.

![Marque préférée](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Correspondance des tâches avec les chercheurs d&#39;emploi

Pour faire correspondre les emplois aux demandeurs d&#39;emploi, seuls les emplois qui se trouvent dans la même ville que le demandeur d&#39;emploi sont recommandés. Les règles d’inclusion peuvent faire correspondre l’emplacement d’une personne à la recherche d’un emploi, du profil du visiteur à une liste d’emplois, comme dans l’exemple suivant :

![Ville de l’utilisateur](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Éléments recommandés en fonction de la taille

L’exemple suivant montre comment la correspondance des attributs de profil affecte les recommandations sur un site web qui vend des ventilateurs électriques.

Lorsqu&#39;un visiteur clique sur différentes images de fans sur ce site web, chaque page définit la valeur du paramètre `entity.size` selon que la taille du fan dans l&#39;image est petite ou grande. Un script de profil suit et compte le nombre de fois où la valeur de `entity.size` est définie sur petite ou grande.

Si le visiteur revient ensuite à la page d’accueil, des recommandations filtrées s’affichent selon que l’utilisateur a cliqué sur plus de petits fans ou de grands fans.

Recommandations basées sur l’affichage de plus de petits fans sur le site web :

![recommandations relatives aux petits fans](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommandations basées sur l’affichage de davantage de fans volumineux sur le site web :

![recommandations relatives aux grands fans](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
