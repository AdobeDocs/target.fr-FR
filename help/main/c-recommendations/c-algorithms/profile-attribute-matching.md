---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance d’attributs de profil
description: Découvrez comment filtrer de manière dynamique en  [!DNL Target Recommendations]  des éléments (entités) par rapport à une valeur du profil de l’utilisateur.
title: Comment filtrer par correspondance d’attributs de profil dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Correspondance des attributs de profil

Filtrez dynamiquement dans [!DNL Adobe Target Recommendations] en comparant des éléments (entités) à une valeur dans le profil de l’utilisateur.

Utilisez [!UICONTROL Profile Attribute Matching] lorsque vous souhaitez afficher des recommandations correspondant à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée.

>[!NOTE]
>
>Le [processus de création et d’utilisation des règles d’inclusion](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) pour les critères et les promotions est similaire, ainsi que les cas d’utilisation et les exemples.

Les scénarios suivants montrent comment utiliser [!UICONTROL Profile Attribute Matching] :

* Une entreprise qui vend des lunettes stocke la couleur de monture préférée d&#39;un visiteur comme « noyer ». Pour ce visiteur spécifique, les recommandations sont configurées pour renvoyer uniquement les montures de lunettes correspondant à la couleur « noyer ».
* Un paramètre de profil peut être défini pour la taille des vêtements (par exemple, Petit, Medium ou Grand) d’un visiteur ou d’une visiteuse qui navigue sur le site web de votre société. Une recommandation peut être configurée pour correspondre à ce paramètre de profil et renvoyer des produits spécifiques uniquement à la taille de vêtement préférée de l’utilisateur.

## Exemples de correspondance d’attributs de profil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] vous permet de recommander uniquement les éléments qui correspondent à un attribut du profil du visiteur, comme dans les exemples ci-dessous.

### Recommandation d’articles de la marque préférée de l’utilisateur

Par exemple, vous pouvez utiliser l’option [!UICONTROL Profile Attribute Matching] pour créer une règle qui recommande des articles uniquement lorsque la marque est égale à la valeur ou au texte stocké dans `profile.favoritebrand`. Avec une telle règle, si un visiteur regarde un short de course d’une marque particulière, seules les recommandations correspondant à sa marque préférée s’affichent (la valeur stockée dans `profile.favoritebrand` dans le profil du visiteur).

![Marque préférée](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Correspondance des tâches avec les chercheurs d&#39;emploi

Supposons que vous essayiez de faire correspondre des emplois à des chercheurs d&#39;emploi. Vous souhaitez recommander uniquement les emplois qui se trouvent dans la même ville que le demandeur d&#39;emploi.

Vous pouvez utiliser des règles d’inclusion pour faire correspondre l’emplacement d’une personne à la recherche d’un emploi, du profil du visiteur à une liste d’emplois, comme dans l’exemple suivant :

![Ville de l’utilisateur](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Éléments recommandés en fonction de la taille

Pour obtenir un exemple visuel de la manière dont la correspondance d’attributs de profil affecte les recommandations, consultez un site web qui vend des ventilateurs électriques.

Lorsqu’un visiteur clique sur différentes images de fans sur ce site web, chaque page définit la valeur du paramètre `entity.size` en fonction de la taille du fan dans l’image, qu’elle soit petite ou grande.

Supposons que vous ayez créé un script de profil pour suivre et compter le nombre de fois où la valeur de `entity.size` est définie sur petite ou grande.

Si le visiteur revient ensuite à la page d’accueil , des recommandations filtrées s’affichent selon que l’utilisateur a cliqué sur plus de petits fans ou de grands fans.

Recommendations basé sur l&#39;affichage de plus petits fans sur le site :

![recommandations relatives aux petits fans](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basé sur l&#39;affichage de plus grands fans sur le site web :

![recommandations relatives aux grands fans](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
