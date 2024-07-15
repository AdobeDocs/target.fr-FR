---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance des attributs de profil
description: Découvrez comment filtrer dynamiquement dans  [!DNL Target Recommendations] en comparant les éléments (entités) à une valeur du profil de l’utilisateur.
title: Comment Filtrer Par Correspondance D’Attributs De Profil Dans Les Activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b6a55260fd49e07e2b217f6becfbc778251a5d0d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Correspondance des attributs de profil

Filtrez dynamiquement dans [!DNL Adobe Target Recommendations] en comparant les éléments (entités) à une valeur du profil de l’utilisateur.

Utilisez [!UICONTROL Profile Attribute Matching] lorsque vous souhaitez afficher des recommandations qui correspondent à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée.

>[!NOTE]
>
>Le [ processus de création et d’utilisation des règles d’inclusion](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) pour les critères et les promotions est similaire, tout comme les cas d’utilisation et les exemples.

Les scénarios suivants montrent comment utiliser [!UICONTROL Profile Attribute Matching] :

* Une société qui vend des lunettes stocke la couleur d’image préférée d’un visiteur comme &quot;noix&quot;. Pour ce visiteur spécifique, les recommandations sont configurées afin de renvoyer uniquement les images de lunettes qui correspondent à &quot;noix&quot; en couleur.
* Un paramètre de profil peut être défini en fonction de la taille des vêtements (par exemple, petit, Medium ou grand) d’un visiteur lorsqu’il navigue sur le site web de votre entreprise. Une recommandation peut être configurée pour correspondre à ce paramètre de profil et renvoyer des produits spécifiques uniquement à la taille d’habillement préférée de l’utilisateur.

## Exemples de correspondance d’attributs de profil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] vous permet de ne recommander que les éléments qui correspondent à un attribut du profil du visiteur, comme dans les exemples ci-dessous.

### Recommander des articles de la marque préférée de l’utilisateur

Par exemple, vous pouvez utiliser l’option [!UICONTROL Profile Attribute Matching] pour créer une règle qui recommande des éléments uniquement lorsque la marque est égale à la valeur ou au texte stocké dans `profile.favoritebrand`. Avec une telle règle, si un visiteur consulte des shorts de course d’une marque spécifique, seules les recommandations qui correspondent à la marque préférée de cet utilisateur s’affichent (la valeur stockée dans `profile.favoritebrand` dans le profil du visiteur).

![Marque préférée](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Correspondance d&#39;emplois avec les demandeurs d&#39;emploi

Supposons que vous essayez de faire correspondre des emplois à des demandeurs d&#39;emploi. Vous souhaitez recommander uniquement les tâches qui se trouvent dans la même ville que le chercheur d’emploi.

Vous pouvez utiliser des règles d’inclusion pour faire correspondre l’emplacement d’un demandeur d’emploi du profil du visiteur à une liste de tâches, comme dans l’exemple suivant :

![Ville de l’utilisateur](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Éléments recommandés en fonction de la taille

Pour un exemple visuel de l’impact de la correspondance des attributs de profil sur les recommandations, imaginez un site web qui vend des ventilateurs électriques.

Lorsqu’un visiteur clique sur différentes images de fans sur ce site web, chaque page définit la valeur du paramètre `entity.size` en fonction de la taille du fan de l’image (petite ou grande).

Supposons que vous ayez créé un script de profil pour effectuer le suivi et compter le nombre de fois où la valeur de `entity.size` est définie sur &quot;petit&quot; par rapport à &quot;grand&quot;.

Si le visiteur revient ensuite à la page d’accueil, il voit des recommandations filtrées selon que l’on a cliqué sur davantage de petits fans ou de grands fans.

Recommendations en fonction de l’affichage d’un plus grand nombre de petits fans sur le site web :

![recommandations pour les petits fans](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations en fonction de l’affichage d’un plus grand nombre de fans sur le site web :

![recommandations de fans volumineux](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)