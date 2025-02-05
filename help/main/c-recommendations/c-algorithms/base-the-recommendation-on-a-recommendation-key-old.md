---
keywords: clé de recommandation;logique de recommandation;catégorie actuelle;attribut personnalisé;dernier article acheté;dernier article consulté;élément le plus consulté;élément le plus consulté;catégorie préférée;popularité;dernier article consulté;dernier achat;dernier consulté;le plus consulté;favori;récemment consulté
description: Découvrez comment utiliser des recommandations basées sur des clés qui utilisent le contexte du comportement du visiteur pour afficher des résultats pertinents dans les activités Adobe [!DNL Target] Recommendations.
title: Comment baser la recommandation sur une clé de recommandation ?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '3845'
ht-degree: 33%

---

# Baser la recommandation sur une clé de recommandation

Les Recommendations basées sur des algorithmes utilisent le contexte du comportement du visiteur pour afficher des résultats pertinents dans [!DNL Adobe Target] activités [!DNL Recommendations].

Chaque type d’algorithme fournit différents algorithmes appropriés à son type, comme indiqué dans le tableau suivant :

| Type d’algorithme | Quand l’utiliser | Algorithmes disponibles |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Faites des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>Les Personnes Qui Ont Consulté Ces/Ces Ont Consulté Ces/Ces</li><li>Les Personnes Qui Les Ont Consultés Les Ont Achetés</li><li>Les Personnes Qui Ont Acheté Ces Éléments Ont Acheté Ceux-Ci</li></ul> |
| [!UICONTROL Popularity-Based] | Faites des recommandations en fonction de la popularité globale d’un élément sur votre site ou en fonction de la popularité des éléments dans la catégorie, la marque, le genre préféré ou le plus consulté d’un utilisateur, etc. | <ul><li>Les plus consultés sur le site</li><li>Les plus consultés par catégorie</li><li>Éléments les plus consultés par attribut d’élément</li><li>Meilleurs vendeurs sur le site</li><li>Meilleurs vendeurs par catégorie</li><li>Meilleurs vendeurs par attribut d&#39;article</li><li>Meilleure mesure par Analytics</li></ul> |
| [!UICONTROL Item-Based] | Faites des recommandations basées sur la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Les personnes ayant consulté ceci ont acheté cela</li><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Éléments avec des attributs similaires</li></ul> |
| [!UICONTROL User-Based] | Faites des recommandations basées sur le comportement de l’utilisateur. | <ul><li>Éléments récemment consultés</li><li>Recommandé pour vous</li></ul> |
| [!UICONTROL Custom Criteria] | Faites des recommandations basées sur un fichier personnalisé que vous téléchargez. | <ul><li>Algorithme personnalisé</li></ul> |

Chaque critère est défini dans son propre onglet. Le trafic est réparti uniformément entre vos différents tests de critères. En d’autres termes, si vous avez deux critères, le trafic est réparti uniformément entre les deux. Si vous avez deux critères et deux conceptions, le trafic est réparti uniformément entre les quatre combinaisons. Vous pouvez également spécifier le pourcentage des visiteurs du site qui visualisent le contenu par défaut, à des fins de comparaison. Dans ce cas, le pourcentage spécifié de visiteurs voit le contenu par défaut et le reste est réparti entre vos combinaisons de critères et de conception.

Pour plus d’informations sur la création de critères et la définition de leurs types d’algorithmes et algorithmes, voir [Créer des critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Les différents algorithmes de recommandations se prêtent à un placement sur différents types de pages. Reportez-vous aux sections suivantes pour plus d’informations sur chaque type d’algorithme et ses algorithmes disponibles.

## Basé sur le panier {#cart-based}

Le type d’algorithme [!UICONTROL Cart-Based] permet de recommander des articles en fonction du contenu du panier actuel du visiteur. Les clés de recommandation sont fournies par le biais du paramètre [mbox `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} dans des valeurs séparées par des virgules. Seules les 10 premières valeurs sont prises en compte.

La logique de recommandation basée sur le panier est similaire à l’algorithme basé sur l’utilisateur « [!UICONTROL Recommended For You] » et aux algorithmes basés sur les éléments « [!UICONTROL People Who Viewed These, Bought Those] » et « [!UICONTROL People Who Bought These, Bought Those] ».

[!DNL Target] utilise des techniques de filtrage collaboratif pour déterminer les similitudes de chaque élément du panier du visiteur, puis combine ces similitudes comportementales entre chaque élément pour obtenir une liste fusionnée.

[!DNL Target] permet également aux spécialistes du marketing d’examiner le comportement des visiteurs au cours d’une ou de plusieurs sessions :

* **[!UICONTROL Single Session]** : en fonction de ce que les autres visiteurs ont fait au cours d’une seule session.

  Il peut être judicieux d’examiner le comportement au sein d’une seule session lorsque l’on a le sentiment que les produits « s’accompagnent » fortement les uns les autres en fonction d’un usage, d’une occasion ou d’un événement. Par exemple, un visiteur achète une imprimante et peut également avoir besoin d’encre et de papier. Ou encore, un visiteur achète du beurre d’arachide et peut également avoir besoin de pain et de gelée.

* **[!UICONTROL Across Sessions]** : en fonction de ce que les autres visiteurs ont fait au cours de plusieurs sessions.

  Il peut être logique d’examiner le comportement sur plusieurs sessions lorsque l’on a le sentiment que les produits « vont » fortement les uns avec les autres en fonction des préférences ou des goûts des visiteurs. Par exemple, un visiteur aime Star Wars et pourrait aussi aimer Indiana Jones, même s’il ne souhaite pas nécessairement regarder les deux films au même moment. Ou, un visiteur aime le jeu de société « Noms de code » et peut également aimer le jeu de société « Avalon », même si le visiteur ne peut pas jouer aux deux jeux simultanément. 

[!DNL Target] émet des recommandations pour chaque visiteur en fonction des éléments de son panier actuel, que vous examiniez le comportement des visiteurs au cours d’une seule session ou de plusieurs sessions.

Les algorithmes suivants sont disponibles avec le type d’algorithme [!UICONTROL Cart-Based] :

### [!UICONTROL People Who Viewed This, Viewed Those]

Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté.

Cette logique renvoie d’autres produits que les personnes ont consultés après l’avoir consultés ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet de créer des opportunités de conversion supplémentaires en recommandant des éléments que d’autres visiteurs et visiteuses qui ont consulté un élément ont également consultés. Par exemple, les visiteurs qui consultent des vélos sur votre site peuvent également consulter des casques de vélo, des kits de cyclisme, des serrures, etc. Vous pouvez créer une recommandation à l’aide de cette logique qui suggère que d’autres produits vous aident à augmenter les recettes.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les Personnes Qui Ont Consulté Ceci Ont Acheté Ces

Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Ces critères renvoient d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu des résultats.

Cette logique renvoie d’autres produits achetés par des personnes après l’affichage de celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de vente croisée en affichant une recommandation sur une page produit, par exemple, qui affiche les articles achetés par d’autres visiteurs qui les ont consultés. Par exemple, si le visiteur consulte un poteau de pêche, la recommandation peut afficher des articles supplémentaires achetés par d’autres visiteurs, tels que des boîtes à palets, des échassiers et des leurres de pêche. Lorsque les visiteurs parcourent votre site, vous leur fournissez des recommandations d’achat supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les Personnes Qui Ont Acheté Ceci Ont Acheté Cela

Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié.

Cette logique renvoie d’autres produits achetés après l’achat de celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de vente croisée en affichant une recommandation sur une page de résumé du panier, par exemple, qui affiche les articles que d’autres acheteurs ont également achetés. Par exemple, si le visiteur achète un costume, la recommandation peut afficher des articles supplémentaires que d’autres visiteurs ont achetés en même temps que le costume, tels que des cravates, des chaussures habillées et des boutons de manchette. Lorsque les visiteurs passent en revue leurs achats, vous leur fournissez des recommandations supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

## [!UICONTROL Popularity-Based]

Le type d’algorithme [!UICONTROL Popularity-Based] vous permet de faire des recommandations en fonction de la popularité globale d’un élément sur l’ensemble de votre site ou de la popularité des éléments au sein de la catégorie, de la marque, du genre, etc. favori ou le plus consulté d’un utilisateur.

Les algorithmes suivants sont disponibles avec le type d’algorithme [!UICONTROL Popularity-Based] :

### Les plus consultés sur le site {#most-viewed}

La recommandation est déterminée par l’élément qui a été consulté le plus souvent. Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de produit
* 5 points pour chaque consultation consécutive
* À la fin de la session, toutes les valeurs sont divisées par 2

Par exemple, l’affichage de surfboardA, puis de surfboardB dans une même session donne A : 10, B : 5. Lorsque la session se termine, vous avez A : 5, B : 2.5. Si vous affichez les mêmes éléments lors de la session suivante, les valeurs deviennent A : 15 B : 7,5.

Utilisez cet algorithme sur les pages générales, telles que les pages d’accueil ou de destination et les annonces hors site.

### Les plus consultés par catégorie {#most-viewed-category}

La recommandation est déterminée par la catégorie associée au plus haut niveau d’activité, à l’aide de la même méthode que celle utilisée pour « Article le plus consulté », sauf que le score porte sur les catégories et non sur les produits.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de catégorie
* 5 points pour chaque consultation consécutive

Les catégories consultées pour la première fois reçoivent dix points. Les visites suivantes dans la même catégorie reçoivent cinq points. À chaque visite, les catégories non actuelles qui ont été consultées auparavant sont décrémentées de 1.

Par exemple, l’affichage de categorieA, puis de categorieB dans une même session donne A : 9, B : 10. Si vous affichez les mêmes éléments lors de la session suivante, les valeurs passent à A : 20, B : 9.

Utilisez cet algorithme sur les pages générales, telles que les pages d’accueil ou de destination et les annonces hors site.

Si vous sélectionnez l’algorithme Les plus consultés par catégorie , vous pouvez sélectionner les clés Recommendations suivantes :

* Catégorie en cours
* Catégorie préférée

### Éléments les plus consultés par attribut d’élément

Recommande des éléments ou des médias similaires aux éléments ou médias les plus consultés sur votre site.

Cet algorithme vous permet de sélectionner l’attribut d’élément sur lequel vous souhaitez baser la recommandation, par exemple « Nom » ou « Marque ».

Vous pouvez ensuite sélectionner les attributs de profil stockés dans le profil du visiteur à faire correspondre, par exemple « Marque préférée », « Dernier élément ajouté au panier » ou « Programme le plus consulté ».

### Meilleurs vendeurs sur le site {#top-sellers}

Affiche les articles inclus dans les commandes les plus terminées de l&#39;ensemble du site. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande.

Cet algorithme vous permet de créer des recommandations pour les articles les plus vendus sur votre site afin d’augmenter la conversion et les recettes. Cette logique est particulièrement adaptée aux nouveaux visiteurs de votre site.

### Meilleurs vendeurs par catégorie

Affiche les articles inclus dans les commandes les plus terminées par catégorie. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande.

Cet algorithme vous permet de créer des recommandations pour les articles les plus vendus sur votre site en fonction de la catégorie, afin d’augmenter la conversion et les recettes. Cette logique est particulièrement adaptée aux nouveaux visiteurs de votre site.

Si vous sélectionnez l’algorithme Les plus consultés par catégorie , vous pouvez sélectionner les clés Recommendations suivantes :

* Catégorie en cours
* Catégorie préférée

### Meilleurs vendeurs par attribut d&#39;article

Recommande des articles ou des médias similaires aux articles ou aux médias les plus achetés sur votre site.

Cet algorithme vous permet de sélectionner l’attribut d’élément sur lequel vous souhaitez baser la recommandation, par exemple « Nom » ou « Marque ».

Vous pouvez ensuite sélectionner les attributs de profil stockés dans le profil du visiteur à faire correspondre, par exemple « Marque préférée », « Dernier élément ajouté au panier » ou « Programme le plus consulté ».

### Meilleure mesure par Analytics

Affiche le « Top x » où *x* est une mesure de [!DNL Analytics] arbitraire. Lors de l’utilisation de données comportementales provenant de mbox, vous pouvez utiliser les objets les plus vendus ou les plus consultés (x = « Vendu » ou x = « Consulté »). Si vous utilisez des données comportementales issues de [!DNL Adobe Analytics], vous pouvez utiliser x = « Ajouts au panier » ou une autre mesure de [!DNL Analytics].

## [!UICONTROL Item-Based]

Le type de recommandation [!UICONTROL Item-Based] permet d’effectuer des recommandations en fonction de la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté.

Les algorithmes suivants sont disponibles avec le type d’algorithme [!UICONTROL Item-Based] :

### Les personnes ayant consulté ceci ont consulté cela {#viewed-viewed}

Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté.

Cette logique renvoie d’autres produits que les personnes ont consultés après l’avoir consultés ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet de créer des opportunités de conversion supplémentaires en recommandant des éléments que d’autres visiteurs et visiteuses qui ont consulté un élément ont également consultés. Par exemple, les visiteurs qui consultent des vélos sur votre site peuvent également consulter des casques de vélo, des kits de cyclisme, des serrures, etc. Vous pouvez créer une recommandation à l’aide de cette logique qui suggère que d’autres produits vous aident à augmenter les recettes.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant consulté ceci ont acheté cela {#viewed-bought}

Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Ces critères renvoient d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu des résultats.

Cette logique renvoie d’autres produits achetés par des personnes après l’affichage de celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de vente croisée en affichant une recommandation sur une page produit, par exemple, qui affiche les articles achetés par d’autres visiteurs qui les ont consultés. Par exemple, si le visiteur consulte un poteau de pêche, la recommandation peut afficher des articles supplémentaires achetés par d’autres visiteurs, tels que des boîtes à palets, des échassiers et des leurres de pêche. Lorsque les visiteurs parcourent votre site, vous leur fournissez des recommandations d’achat supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant acheté ceci ont acheté cela {#bought-bought}

Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié.

Cette logique renvoie d’autres produits achetés après l’achat de celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de vente croisée en affichant une recommandation sur une page de résumé du panier, par exemple, qui affiche les articles que d’autres acheteurs ont également achetés. Par exemple, si le visiteur achète un costume, la recommandation peut afficher des articles supplémentaires que d’autres visiteurs ont achetés en même temps que le costume, tels que des cravates, des chaussures habillées et des boutons de manchette. Lorsque les visiteurs passent en revue leurs achats, vous leur fournissez des recommandations supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Éléments avec des attributs similaires {#similar-attributes}

Recommande des éléments ou des médias similaires à d’autres éléments ou médias selon l’activité de la page ou le comportement du visiteur précédent.

Si vous sélectionnez Éléments/médias avec des attributs similaires, vous avez la possibilité de définir des règles de similarité de contenu.

L’utilisation de la similarité de contenu pour générer des recommandations est particulièrement efficace pour les nouveaux éléments, qui ne sont pas susceptibles de s’afficher dans les recommandations utilisant les personnes qui ont consulté ceci ou cela, ou une autre logique basée sur un comportement passé. Vous pouvez également utiliser la similarité de contenu pour générer des recommandations utiles pour les nouveaux visiteurs, qui n’ont pas d’achats antérieurs ni d’autres données historiques.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

Pour plus d’informations, voir [Similarité de contenu](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL User-Based]

Le type d’algorithme Basé sur l’utilisateur permet de faire des recommandations en fonction du comportement de l’utilisateur.

Les algorithmes suivants sont disponibles avec le type d’algorithme [!UICONTROL User-Based] :

### Éléments récemment consultés {#recently-viewed}

Utilise l’historique du visiteur (sur plusieurs sessions) pour présenter les *x* derniers éléments consultés par le visiteur, en fonction du nombre d’emplacements dans la conception.

L’algorithme Éléments récemment consultés renvoie un résultat spécifique à un [environnement](/help/main/administrating-target/hosts.md) donné. Si deux sites appartiennent à différents environnements et qu’un visiteur bascule entre les deux sites, chaque site n’affiche que les éléments récemment consultés du site approprié. Si deux sites se trouvent dans le même environnement et qu’un visiteur passe d’un site à l’autre, il voit les mêmes éléments récemment consultés pour les deux sites.

>[!NOTE]
>
>Vous ne pouvez pas utiliser les critères de [!UICONTROL Recently Viewed Items] pour les recommandations de sauvegarde.

[!UICONTROL Recently Viewed Items]/Media peut être filtré de sorte que seuls les éléments dotés d’un attribut particulier s’affichent.

* Les critères récemment consultés sont configurables au même titre que les autres critères contenus dans les recommandations.
* Vous pouvez utiliser les [collections](/help/main/c-recommendations/c-products/collections.md), [exclusions](/help/main/c-recommendations/c-products/exclusions.md) et [inclusions](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le Prix et l&#39;Inventaire) de la même manière que tout autre critère.

Parmi les cas d’utilisation possibles, une société multinationale comptant plusieurs entreprises peut avoir un visiteur qui consulte des éléments dans plusieurs propriétés numériques. Dans ce cas, vous pouvez limiter les éléments récemment consultés de manière à les afficher uniquement pour la propriété respective dans laquelle ils ont été consultés. Cela empêche les éléments récemment consultés de s’afficher sur le site d’une autre propriété numérique.

Utilisez cet algorithme sur les pages générales, telles que les pages d’accueil ou de destination et les annonces hors site.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] respecte à la fois les paramètres globaux des exclusions et le paramètre de collection sélectionné pour l’activité. Si un élément est exclu par une exclusion globale ou s&#39;il n&#39;est pas contenu dans la collection sélectionnée, il ne s&#39;affichera pas. Par conséquent, lors de l’utilisation d’un critère de [!UICONTROL Recently Viewed Items], le paramètre « Toutes les collections » doit généralement être utilisé.

### Recommandé pour vous {#recommended-for-you}

Recommande des articles en fonction de l’historique de navigation, d’affichage et d’achat de chaque visiteur.

Cet algorithme vous permet de fournir du contenu et des expériences personnalisés aux nouveaux visiteurs et aux visiteurs récurrents. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur. Elle est mise à jour en cours de session et devient plus personnalisée au fur et à mesure que l’utilisateur parcourt votre site.

Les vues et les achats sont utilisés pour déterminer les articles recommandés. La clé de recommandation spécifiée (par exemple, Élément actuel) est utilisée pour appliquer les filtres de règle d’inclusion que vous sélectionnez.

Par exemple, vous pouvez effectuer les opérations suivantes :

* Excluez les articles qui ne répondent pas à certains critères (produits en rupture de stock, articles publiés il y a plus de 30 jours, films classés R, etc.).
* Limiter les éléments inclus à une seule catégorie ou à la catégorie actuelle.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés de filtrage suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

## Critères personnalisés {#custom}

Le type d’algorithme Critères personnalisés vous permet de faire des recommandations basées sur un fichier personnalisé que vous téléchargez.

La recommandation est déterminée par un article stocké dans un profil de visiteur, utilisant les attributs user.*x>* ou profile.attributs *x*.

Si cette option est sélectionnée, la valeur `entity.id` doit être présente dans l’attribut de profil.

Lorsque vous basez des recommandations sur des attributs personnalisés, vous devez sélectionner l’attribut personnalisé, puis le type de recommandation.

Vous pouvez effectuer un filtrage en temps réel en plus de vos propres critères de sortie personnalisés. Vous pouvez par exemple limiter vos éléments recommandés uniquement à ceux de la catégorie ou de la marque préférée d’un visiteur. Vous avez ainsi la possibilité de combiner les calculs hors ligne avec filtrage en temps réel.

Cette fonctionnalité signifie que vous pouvez utiliser [!DNL Target] pour ajouter une personnalisation en plus de vos recommandations calculées hors ligne ou de vos listes personnalisées. Elle combine la puissance de vos analystes des données et de votre recherche avec la livraison approuvée, le filtrage d’exécution, les tests A/B, le ciblage, la génération de rapports, les intégrations et bien d’autres fonctions Adobe encore.

Avec l’ajout de règles d’inclusion dans les critères personnalisés, les recommandations qui seraient statiques deviennent dynamiques et fondées sur les intérêts du visiteur.

* Les critères personnalisés sont configurables au même titre que les autres critères contenus dans les recommandations.
* Vous pouvez utiliser les [collections](/help/main/c-recommendations/c-products/collections.md), [exclusions](/help/main/c-recommendations/c-products/exclusions.md) et [inclusions](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le Prix et l&#39;Inventaire) de la même manière que tout autre critère.

Les cas d’utilisation possibles incluent :

* Vous souhaitez recommander des films à partir d’une liste gérée de façon personnalisée, mais uniquement si le visiteur ne les a pas déjà vus.
* Vous souhaitez exécuter un algorithme hors ligne et utiliser les résultats pour alimenter vos recommandations, mais vous devez vous assurer que les articles en rupture de stock ne sont jamais recommandés.
* Vous souhaitez inclure uniquement les articles extraits de la catégorie préférée de ce visiteur.

## Clés de recommandation {#keys}

Les clés de recommandation suivantes sont disponibles à partir de la liste déroulante [!UICONTROL Recommendation Key] :

### Article actuel {#current-item}

La recommandation est déterminée par l’article que le visiteur consulte actuellement.

Les recommandations présentent d’autres articles susceptibles d’intéresser les visiteurs qui consultent l’article spécifié.

Lorsque cette option est sélectionnée, la valeur `entity.id` doit être transmise comme un paramètre à la mbox d’affichage.

Peut être utilisé avec les algorithmes suivants :

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Utilisez la clé [!UICONTROL Current Item] recommendations sur votre site sur :

* Pages d’un seul article (pages de produit, par exemple).
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Dernier article acheté {#last-purchased}

La recommandation est déterminée par le dernier article acheté par chaque visiteur unique. Ceci est capturé automatiquement, de sorte qu’aucune valeur ne doit être transmise sur la page.

Peut être utilisé avec les algorithmes suivants :

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Utilisez la clé [!UICONTROL Last Purchased Item] recommendations sur votre site sur :

* Page d’accueil, page Mon compte, publicités hors site.
* Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

#### Clé de recommandations personnalisées

Vous pouvez axer les recommandations sur la valeur d’un attribut de profil personnalisé. Supposons, par exemple, que vous souhaitiez afficher les films recommandés en fonction de la séquence que le visiteur a ajoutée le plus récemment à sa file d’attente.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Recommendation Key]** (par exemple, « Dernier affichage ajouté à la liste de contrôle »).
1. Sélectionnez ensuite votre **[!UICONTROL Recommendation Logic]** (par exemple, « Personnes qui ont consulté ceci ou cela »).

   ![Boîte de dialogue Créer de nouveaux critères](/help/main/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Si votre attribut de profil personnalisé ne correspond pas directement à un ID d’entité unique, il est nécessaire d’expliquer à [!DNL Recommendations] la manière dont vous souhaitez que la correspondance à une entité se produise. Supposons, par exemple, que vous souhaitiez afficher les articles les plus vendus de la marque préférée d’un visiteur.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Recommendation Key]** (par exemple, « Marque préférée »).

1. Sélectionnez ensuite le **[!UICONTROL Recommendation Logic]** que vous souhaitez utiliser avec cette clé (par exemple, « Meilleurs vendeurs »).

   L’option [!UICONTROL Group By Unique Value Of] s’affiche.

1. Sélectionnez l’attribut d’entité correspondant à la clé que vous avez choisie. Dans ce cas, « Marque préférée » correspond à `entity.brand`.

   [!DNL Recommendations] génère désormais une liste des « Meilleurs vendeurs » pour chaque marque et affiche au visiteur la liste des « Meilleurs vendeurs » appropriée en fonction de la valeur stockée dans l’attribut de profil de la marque préférée du visiteur.

   ![Boîte de dialogue Créer de nouveaux critères 2](/help/main/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Dernier article consulté {#last-viewed}

La recommandation est déterminée par le dernier élément consulté par chaque visiteur unique. Ceci est capturé automatiquement, de sorte qu’aucune valeur ne doit être transmise sur la page.

Peut être utilisé avec les algorithmes suivants :

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Utilisez la clé [!UICONTROL Last Viewed Item] recommendations sur votre site sur :

* Page d’accueil, page Mon compte, publicités hors site.
* Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

### Article le plus consulté {#most-viewed-logic}

Affiche les éléments ou les médias qui sont consultés le plus souvent sur votre site.

Cette logique vous permet d’afficher des recommandations en fonction des éléments les plus consultés de votre site afin d’augmenter les conversions d’autres éléments. Par exemple, un site multimédia peut afficher des recommandations sur sa page d’accueil pour ses vidéos les plus consultées afin d’encourager les visiteurs à regarder d’autres vidéos.

Cette clé de recommandation peut être utilisée avec les algorithmes suivants :

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

### Catégorie en cours {#current-category}

La recommandation est déterminée par la catégorie de produits que le visiteur consulte actuellement.

Les recommandations présentent des articles dans la catégorie de produits spécifiée.

Lorsque cette option est sélectionnée, la valeur `entity.categoryId` doit être transmise comme paramètre à la mbox d’affichage.

Cette clé de recommandation peut être utilisée avec les algorithmes suivants :

* Meilleurs vendeurs
* Les plus consultés

Utilisez la clé [!UICONTROL Current Category] recommendations sur votre site sur :

* Pages d’une seule catégorie.
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Catégorie préférée {#favorite-category}

La recommandation est déterminée par la catégorie de produits préférée du visiteur.

Les recommandations présentent des articles dans la catégorie de produits spécifiée.

Lorsque cette option est sélectionnée, la valeur `entity.categoryId` doit être transmise comme paramètre à la mbox d’affichage.

Cette clé de recommandation peut être utilisée avec les algorithmes suivants :

* Meilleurs vendeurs
* Les plus consultés

Utilisez la clé [!UICONTROL Current Category] recommendations sur votre site sur :

* Pages d’une seule catégorie.
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Affinité du site {#site-affinity}

Recommande des éléments selon la certitude d’une relation entre ceux-ci. Vous pouvez configurer ce critère pour déterminer la quantité de données requises avant qu’une recommandation ne soit présentée à l’aide du curseur Règles d’inclusion. Par exemple, si vous sélectionnez très fort, les produits avec la plus grande certitude d&#39;une correspondance sont recommandés.

Par exemple, si vous définissez une très forte affinité et si votre conception comporte cinq éléments dont trois qui correspondent à la force du seuil de connexion, les deux éléments qui ne répondent pas aux exigences de force minimales ne sont pas affichés dans vos recommandations et sont remplacés par les éléments de sauvegarde. Les éléments avec l’affinité la plus forte s’affichent en premier.

Par exemple, un détaillant en ligne peut recommander des articles lors de visites ultérieures qui ont suscité l’intérêt d’un visiteur au cours de sessions précédentes. L’activité de la session de chaque visiteur est capturée afin de calculer une affinité en fonction d’un modèle de récence et de fréquence. À mesure que ce visiteur revient sur votre site, l’affinité du site est utilisée pour afficher des recommandations basées sur des actions passées sur votre site.

Certains clients qui proposent plusieurs collections de produits et plusieurs comportements de site obtiendront de meilleurs résultats en définissant une affinité faible.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté
