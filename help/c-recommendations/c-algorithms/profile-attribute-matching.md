---
keywords: règles d’inclusion ; critères d’inclusion ; recommandations ; promotion ; promotions ; filtrage dynamique ; dynamique ; correspondance d’attributs de profil
description: Découvrez comment filtrer dynamiquement dans Adobe [!DNL Target] Recommendations en comparant des éléments (entités) à une valeur dans le profil de l’utilisateur.
title: Comment puis-je filtrer par attribut de Profil correspondant aux Activités Recommendations ?
feature: Recommandations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 7%

---

# ![Correspondance d&#39;attribut ](/help/assets/premium.png) PREMIUMProfile

Filtrez dynamiquement dans [!DNL Adobe Target] [!DNL Recommendations] en comparant des éléments (entités) à une valeur dans le profil de l’utilisateur.

Utilisez [!UICONTROL Correspondance d’attributs de Profil] lorsque vous souhaitez afficher des recommandations qui correspondent à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée.

>[!NOTE]
>
>Le [processus de création et d&#39;utilisation des règles d&#39;inclusion](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) pour les critères et les promotions est similaire, tout comme les cas d&#39;utilisation et les exemples.

Les scénarios suivants montrent comment utiliser [!UICONTROL la correspondance d’attributs de Profil] :

* Une société qui vend des lunettes stocke une couleur d&#39;image préférée du visiteur sous la forme &quot;noix&quot;. Pour ce visiteur spécifique, les recommandations sont configurées pour renvoyer uniquement les cadres en verre qui correspondent à &quot;noix&quot; en couleur.
* Un paramètre de profil peut être défini pour la taille des vêtements (par exemple, Petit, Moyen ou Grand) d’un visiteur lorsqu’il navigue sur le site Web de votre société. Une recommandation peut être configurée pour correspondre à ce paramètre de profil et renvoyer des produits spécifiques à la taille préférée des vêtements de l’utilisateur.

## Exemples de correspondance des attributs de profil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL La ] correspondance des attributs de profil vous permet de recommander uniquement les éléments qui correspondent à un attribut du profil visiteur, comme dans les exemples ci-dessous.

### Éléments recommandés pour la marque préférée de l’utilisateur

Par exemple, vous pouvez utiliser l&#39;option [!UICONTROL Correspondance d&#39;attribut de Profil] pour créer une règle qui recommande des éléments uniquement lorsque la marque est égale à la valeur ou au texte stocké dans `profile.favoritebrand`. Avec une telle règle, si un visiteur recherche des shorts de course d’une marque spécifique, seules les recommandations qui correspondent à la marque préférée de cet utilisateur s’affichent (la valeur stockée dans `profile.favoritebrand` du profil du visiteur).

![Marque préférée](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Correspondance des tâches avec les demandeurs d&#39;emploi

Supposons que vous essayez de faire correspondre les emplois aux demandeurs d&#39;emploi. Vous souhaitez recommander uniquement les tâches situées dans la même ville que le demandeur d’emploi.

Vous pouvez utiliser des règles d’inclusion pour faire correspondre l’emplacement d’un demandeur d’emploi de son profil visiteur à une liste d’emplois, comme dans l’exemple suivant :

![Ville de l’utilisateur](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Éléments recommandés en fonction de la taille

Pour un exemple visuel de l’impact de la correspondance des attributs de profil sur les recommandations, envisagez un site Web qui vend des ventilateurs électriques.

Lorsqu’un visiteur clique sur plusieurs images de fans sur ce site Web, chaque page définit la valeur du paramètre `entity.size` en fonction de la taille du ventilateur de l’image (petite ou grande).

Supposons que vous ayez créé un script de profil pour effectuer le suivi et comptabiliser le nombre de fois où la valeur de `entity.size` est définie sur faible ou grand.

Si le visiteur revient alors à la Page d&#39;accueil, il verra des recommandations filtrées selon si l’utilisateur a cliqué sur un plus grand nombre de fans ou de fans de petite taille.

Recommendations basé sur l&#39;affichage d&#39;un plus grand nombre de fans de petite taille sur le site Web :

![recommandations pour les petits fans](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basé sur l’affichage d’un plus grand nombre de fans sur le site Web :

![recommandations concernant les grands fans](/help/c-recommendations/c-algorithms/assets/large-fans.png)
