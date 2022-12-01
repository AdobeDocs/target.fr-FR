---
keywords: clé de recommandation;logique de recommandation;catégorie actuelle;attribut personnalisé;dernier article acheté;dernier article consulté;article le plus consulté;article le plus consulté;catégorie préférée;popularité;article récemment consulté;dernier achat;dernier article consulté;le dernier article consulté;favori;récemment consulté
description: Découvrez comment utiliser les recommandations basées sur des clés qui utilisent le contexte du comportement des visiteurs pour afficher des résultats pertinents dans Adobe [!DNL Target] Activités Recommendations.
title: Comment puis-je baser la recommandation sur une clé de recommandation ?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '3936'
ht-degree: 40%

---

# Baser la recommandation sur une clé de recommandation

Recommendations selon des algorithmes utilise le contexte de comportement du visiteur pour afficher des résultats pertinents dans [!DNL Adobe Target] [!DNL Recommendations] activités.

Chaque type d’algorithme fournit des algorithmes différents adaptés à son type, comme illustré dans le tableau suivant :

| Type d’algorithme | Quand utiliser | Algorithmes disponibles |
| --- | --- | --- |
| [!UICONTROL Basé sur le panier] | Effectuez des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>Les personnes qui les ont consultés ont consulté ceux-ci</li><li>Les personnes qui les ont consultés ont acheté ces</li><li>Les personnes qui ont acheté ceux-ci ont acheté ceux-là</li></ul> |
| [!UICONTROL Basé sur la popularité] | Effectuez des recommandations en fonction de la popularité globale d’un élément sur votre site ou de la popularité des éléments au sein de la catégorie, de la marque, du genre, préférée ou la plus consultée d’un utilisateur, etc. | <ul><li>Les plus consultés sur le site</li><li>Les plus consultés par catégorie</li><li>Attribut d’élément le plus consulté</li><li>Meilleurs vendeurs sur le site</li><li>Meilleurs vendeurs par catégorie</li><li>Meilleurs vendeurs par attribut d’article</li><li>Mesure Début par Analytics</li></ul> |
| [!UICONTROL Basé sur des éléments] | Effectuez des recommandations sur la base de la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Les personnes ayant consulté ceci ont acheté cela</li><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Éléments avec des attributs similaires</li></ul> |
| [!UICONTROL Basé sur les utilisateurs] | Effectuez des recommandations en fonction du comportement de l’utilisateur. | <ul><li>Éléments récemment consultés</li><li>Recommandé pour vous</li></ul> |
| [!UICONTROL Critères personnalisés] | Faites des recommandations en fonction d’un fichier personnalisé que vous chargez. | <ul><li>Algorithme personnalisé</li></ul> |

Chaque critère est défini dans son propre onglet. Le trafic est réparti uniformément entre vos différents tests de critères. En d’autres termes, si vous avez deux critères, le trafic est réparti uniformément entre les deux. Si vous avez deux critères et deux conceptions, le trafic est réparti uniformément entre les quatre combinaisons. Vous pouvez également spécifier le pourcentage des visiteurs du site qui visualisent le contenu par défaut, à des fins de comparaison. Dans ce cas, le pourcentage spécifié des visiteurs qui visualisent le contenu par défaut et les autres sont répartis entre vos combinaisons de critères et de conception.

Pour plus d’informations sur la création de critères et la définition de ses types d’algorithmes et algorithmes, voir [Création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Différents algorithmes de recommandations se prêtent au placement sur différents types de pages. Reportez-vous aux sections suivantes pour plus d’informations sur chaque type d’algorithme et ses algorithmes disponibles.

## Basé sur le panier {#cart-based}

Le [!UICONTROL Basé sur le panier] le type d’algorithme permet de recommander des articles en fonction du contenu du panier actuel du visiteur. Les clés de recommandation sont fournies par le biais du paramètre mbox . `cartIds` dans des valeurs séparées par des virgules. Seules les 10 premières valeurs sont prises en compte.

La logique de recommandation basée sur le panier est similaire au[!UICONTROL Recommandé pour vous]&quot;algorithme basé sur l’utilisateur et au[!UICONTROL Les personnes qui les ont consultés ont acheté ces]&quot; et &quot;[!UICONTROL Les personnes qui ont acheté ceux-ci ont acheté ceux-là]&quot; des algorithmes reposant sur des éléments.

[!DNL Target] utilise des techniques de filtrage collaboratif pour déterminer les similitudes entre chaque élément du panier du visiteur, puis combine ces similitudes comportementales entre chaque élément pour obtenir une liste fusionnée.

[!DNL Target] offre également aux marketeurs le choix d’examiner le comportement des visiteurs au cours d’une ou de plusieurs sessions :

* **[!UICONTROL Session unique]**: En fonction de ce que les autres visiteurs ont fait au cours d’une seule session.

   L’examen du comportement au sein d’une seule session peut s’avérer judicieux lorsqu’il existe un sentiment que les produits s’accompagnent fortement les uns des autres en fonction d’une utilisation, d’une occasion ou d’un événement. Par exemple, un visiteur achète une imprimante et peut également avoir besoin d’encre et de papier. Ou bien, un visiteur achète du beurre d&#39;arachide et peut aussi avoir besoin de pain et de gelée.

* **[!UICONTROL Sessions]**: En fonction de ce que les autres visiteurs ont fait au cours de plusieurs sessions.

   L’examen du comportement au cours de plusieurs sessions peut s’avérer judicieux lorsqu’il existe un sentiment que les produits s’accompagnent fortement les uns des autres en fonction des préférences ou des goûts des visiteurs. Par exemple, un visiteur aime Star Wars et peut également aimer Indiana Jones, même s’il ne souhaite pas nécessairement regarder les deux films au cours de la même session. Ou, un visiteur aime le jeu de société &quot;Codenames&quot; et peut également aimer le jeu de société &quot;Avalon&quot;, même si le visiteur ne peut pas jouer les deux simultanément. 

[!DNL Target] émet des recommandations pour chaque visiteur en fonction des éléments de son panier actuel, que vous examiniez le comportement du visiteur au cours d’une seule session ou entre plusieurs sessions.

Les algorithmes suivants sont disponibles avec la variable [!UICONTROL Basé sur le panier] type d’algorithme :

### [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]

Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté.

Cette logique renvoie d’autres produits que les utilisateurs ont consultés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet de créer d’autres opportunités de conversion en recommandant des éléments que d’autres visiteurs qui ont également consulté un élément. Par exemple, les visiteurs qui consultent des vélos sur votre site peuvent également consulter des casques de vélo, des kits de cyclisme, des verrous, etc. Vous pouvez créer une recommandation à l’aide de cette logique, qui suggère que d’autres produits vous aident à augmenter les recettes.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant consulté ceci ont acheté ces

Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Ces critères renvoient d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu des résultats.

Cette logique renvoie d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de ventes croisées en affichant une recommandation sur une page de produits, par exemple, qui affiche les articles que d’autres visiteurs ont consultés sur l’article acheté. Si, par exemple, le visiteur consulte un pôle de pêche, la recommandation peut afficher d’autres articles achetés par d’autres visiteurs, tels que des boîtes de pêche, des écharpes et des leurres de pêche. Lorsque les visiteurs parcourent votre site, vous leur fournissez des recommandations d’achat supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant acheté ceci ont acheté cela

Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié.

Cette logique renvoie d’autres produits que les utilisateurs ont achetés après l’avoir acheté : le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de ventes croisées en affichant une recommandation sur une page de résumé du panier, par exemple, qui affiche les articles que d’autres acheteurs ont également achetés. Si, par exemple, le visiteur achète une combinaison, la recommandation peut afficher d’autres articles achetés par d’autres visiteurs, tels que des cravates, des chaussures et des liens. Lorsque les visiteurs passent en revue leurs achats, vous leur fournissez des recommandations supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

## [!UICONTROL Basé sur la popularité]

Le [!UICONTROL Basé sur la popularité] le type d’algorithme vous permet de faire des recommandations en fonction de la popularité globale d’un élément sur votre site ou de la popularité des éléments dans la catégorie, la marque, le genre, préférée ou la plus consultée d’un utilisateur, etc.

Les algorithmes suivants sont disponibles avec la variable [!UICONTROL Basé sur la popularité] type d’algorithme :

### Les plus consultés sur le site {#most-viewed}

La recommandation est déterminée par l’article qui a été consulté le plus souvent. Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de produit
* 5 points pour chaque consultation consécutive
* À la fin de la session, toutes les valeurs sont divisées par 2

Par exemple, l’affichage de surfboardA, puis de surfboardB dans une même session donne A : 10, B : 5. Lorsque la session se termine, vous avez A : 5, B : 2.5. Si vous affichez les mêmes éléments lors de la session suivante, les valeurs deviennent A : 15 B : 7.5.

Utilisez cet algorithme sur les pages générales, telles que les pages d’accueil, les pages d’entrée et les publicités hors site.

### Les plus consultés par catégorie {#most-viewed-category}

La recommandation est déterminée par la catégorie associée au plus haut niveau d’activité, à l’aide de la même méthode que celle utilisée pour « Article le plus consulté », sauf que le score porte sur les catégories et non sur les produits.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de catégorie
* 5 points pour chaque consultation consécutive

Les catégories consultées pour la première fois reçoivent dix points. Les visites suivantes dans la même catégorie reçoivent cinq points. À chaque visite, les catégories non actuelles qui ont été consultées auparavant sont décrémentées de 1.

Par exemple, l’affichage de categorieA, puis de categorieB dans une même session donne A : 9, B : 10. Si vous affichez les mêmes éléments lors de la session suivante, les valeurs passent à A : 20, B : 9.

Utilisez cet algorithme sur les pages générales, telles que les pages d’accueil, les pages d’entrée et les publicités hors site.

Si vous sélectionnez l’algorithme Les plus consultés par catégorie , vous pouvez sélectionner les clés Recommendations suivantes :

* Catégorie en cours
* Catégorie préférée

### Attribut d’élément le plus consulté

Recommande des éléments ou des médias similaires aux éléments ou médias les plus consultés sur votre site.

Cet algorithme vous permet de sélectionner l’attribut d’élément sur lequel vous souhaitez baser la recommandation, par exemple &quot;Nom&quot; ou &quot;Marque&quot;.

Vous sélectionnez ensuite les attributs de profil stockés dans le profil du visiteur à faire correspondre, par exemple &quot;Marque préférée&quot;, &quot;Dernier élément ajouté au panier&quot; ou &quot;Programme le plus consulté&quot;.

### Meilleurs vendeurs sur le site {#top-sellers}

Affiche les éléments inclus dans les commandes les plus effectuées sur le site. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande.

Cet algorithme vous permet de créer des recommandations pour les articles les plus vendus sur votre site, afin d’augmenter les conversions et les recettes. Cette logique est particulièrement adaptée aux nouveaux visiteurs de votre site.

### Meilleurs vendeurs par catégorie

Affiche les éléments inclus dans les commandes les plus effectuées par catégorie. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande.

Cet algorithme vous permet de créer des recommandations pour les articles les plus vendus sur votre site en fonction de la catégorie afin d’augmenter les conversions et les recettes. Cette logique est particulièrement adaptée aux nouveaux visiteurs de votre site.

Si vous sélectionnez l’algorithme Les plus consultés par catégorie , vous pouvez sélectionner les clés Recommendations suivantes :

* Catégorie en cours
* Catégorie préférée

### Meilleurs vendeurs par attribut d’article

(Informations à venir)

### Mesure Début par Analytics

Affiche le &quot;x supérieur&quot; où *x* est arbitraire ; [!DNL Analytics] mesure. Lors de l’utilisation de données comportementales à partir de mbox, vous pouvez utiliser Meilleures ventes ou Meilleures vues (x = &quot;Vendue&quot; ou x = &quot;Consultée&quot;). Si vous utilisez des données comportementales provenant de [!DNL Adobe Analytics], vous pouvez utiliser x = &quot;Ajouts au panier&quot; ou un autre [!DNL Analytics] mesure.

## [!UICONTROL Basé sur des éléments]

Le [!UICONTROL Basé sur des éléments] type de recommandation permet d’effectuer des recommandations en fonction de la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté.

Les algorithmes suivants sont disponibles avec la variable [!UICONTROL Basé sur des éléments] type d’algorithme :

### Les personnes ayant consulté ceci ont consulté cela {#viewed-viewed}

Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté.

Cette logique renvoie d’autres produits que les utilisateurs ont consultés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet de créer d’autres opportunités de conversion en recommandant des éléments que d’autres visiteurs qui ont également consulté un élément. Par exemple, les visiteurs qui consultent des vélos sur votre site peuvent également consulter des casques de vélo, des kits de cyclisme, des verrous, etc. Vous pouvez créer une recommandation à l’aide de cette logique, qui suggère que d’autres produits vous aident à augmenter les recettes.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant consulté ceci ont acheté cela {#viewed-bought}

Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Ces critères renvoient d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu des résultats.

Cette logique renvoie d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de ventes croisées en affichant une recommandation sur une page de produits, par exemple, qui affiche les articles que d’autres visiteurs ont consultés sur l’article acheté. Si, par exemple, le visiteur consulte un pôle de pêche, la recommandation peut afficher d’autres articles achetés par d’autres visiteurs, tels que des boîtes de pêche, des écharpes et des leurres de pêche. Lorsque les visiteurs parcourent votre site, vous leur fournissez des recommandations d’achat supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant acheté ceci ont acheté cela {#bought-bought}

Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié.

Cette logique renvoie d’autres produits que les utilisateurs ont achetés après l’avoir acheté : le produit spécifié n’est pas inclus dans le jeu de résultats.

Cette logique vous permet d’augmenter les opportunités de ventes croisées en affichant une recommandation sur une page de résumé du panier, par exemple, qui affiche les articles que d’autres acheteurs ont également achetés. Si, par exemple, le visiteur achète une combinaison, la recommandation peut afficher d’autres articles achetés par d’autres visiteurs, tels que des cravates, des chaussures et des liens. Lorsque les visiteurs passent en revue leurs achats, vous leur fournissez des recommandations supplémentaires.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Éléments avec des attributs similaires {#similar-attributes}

Recommande des éléments ou des médias similaires à d’autres éléments ou médias selon l’activité de la page ou le comportement du visiteur précédent.

Si vous sélectionnez des Éléments/Médias avec des attributs similaires, vous avez la possibilité de définir des règles de similarité de contenu.

L’utilisation de la similarité de contenu pour générer des recommandations est particulièrement efficace pour les nouveaux éléments, qui ne sont pas susceptibles d’apparaître dans les recommandations à l’aide des personnes ayant consulté ceci, consulté cela et d’une autre logique basée sur le comportement passé. Vous pouvez également utiliser la similarité de contenu pour générer des recommandations utiles pour les nouveaux visiteurs, qui n’ont pas d’achats antérieurs ni d’autres données historiques.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés Recommendations suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

Pour plus d’informations, voir [Similarité de contenu](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL Basé sur les utilisateurs]

Le type d’algorithme Basé sur l’utilisateur vous permet d’effectuer des recommandations en fonction du comportement de l’utilisateur.

Les algorithmes suivants sont disponibles avec la variable [!UICONTROL Basé sur les utilisateurs] type d’algorithme :

### Éléments récemment consultés {#recently-viewed}

Utilise l’historique du visiteur (sur plusieurs sessions) pour présenter les *x* derniers éléments consultés par le visiteur, en fonction du nombre d’emplacements dans la conception.

L’algorithme Éléments récemment consultés renvoie le résultat spécifique à un [environnement](/help/main/administrating-target/hosts.md). Si deux sites appartiennent à différents environnements et qu’un visiteur bascule entre les deux sites, chaque site n’affiche que les éléments récemment consultés du site approprié. Si deux sites se trouvent dans le même environnement et qu’un visiteur bascule entre les deux sites, il voit les mêmes éléments récemment consultés pour les deux sites.

>[!NOTE]
>
>Vous ne pouvez pas utiliser la variable [!UICONTROL Éléments récemment consultés] critères pour les recommandations de sauvegarde.

Les éléments/médias récemment consultés peuvent être filtrés de sorte que seuls les éléments ayant un attribut particulier soient affichés.

* Les critères récemment consultés sont configurables au même titre que les autres critères contenus dans les recommandations.
* Vous pouvez utiliser les [collections](/help/main/c-recommendations/c-products/collections.md), [exclusions](/help/main/c-recommendations/c-products/exclusions.md), et [inclusions](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.

Cas d’utilisation possibles : une entreprise multinationale avec plusieurs entreprises peut avoir un visiteur qui affiche des éléments sur plusieurs propriétés numériques. Dans ce cas, vous pouvez limiter les éléments récemment consultés de manière à les afficher uniquement pour la propriété respective dans laquelle ils ont été consultés. Cela empêche les éléments récemment consultés de s’afficher sur un autre site de propriété numérique.

Utilisez cet algorithme sur les pages générales, telles que les pages d’accueil, les pages d’entrée et les publicités hors site.

>[!NOTE]
>
>[!UICONTROL Éléments récemment consultés] respecte les paramètres globaux des exclusions et le paramètre de collection sélectionné pour l’activité. Si un élément est exclu par une exclusion globale ou n’est pas contenu dans la collection sélectionnée, il ne s’affiche pas. Par conséquent, lors de l’utilisation d’un [!UICONTROL Éléments récemment consultés] , le paramètre &quot;Toutes les collections&quot; doit généralement être utilisé.

### Recommandé pour vous {#recommended-for-you}

Recommande des éléments en fonction de l’historique de navigation, d’affichage et d’achat de chaque visiteur.

Cet algorithme vous permet de fournir du contenu et des expériences personnalisés aux nouveaux visiteurs et aux visiteurs récurrents. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur. Elle est mise à jour en cours de session et personnalisée à mesure que l’utilisateur navigue sur votre site.

Les vues et les achats sont utilisés pour déterminer les articles recommandés. La clé de recommandation spécifiée (par exemple, Article actuel) est utilisée pour appliquer les filtres de règle d’inclusion que vous sélectionnez.

Par exemple, vous pouvez effectuer les opérations suivantes :

* Excluez les éléments qui ne répondent pas à certains critères (produits en rupture de stock, articles publiés il y a plus de 30 jours, films classés R, etc.).
* Limiter les éléments inclus à une seule catégorie ou à la catégorie actuelle.

Si vous sélectionnez cet algorithme, vous pouvez sélectionner les clés de filtrage suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

## Critères personnalisés {#custom}

Le type d’algorithme Critères personnalisés vous permet d’effectuer des recommandations en fonction d’un fichier personnalisé que vous chargez.

La recommandation est déterminée par un article stocké dans un profil de visiteur, utilisant les attributs user.*x>* ou profile.attributs *x*.

Si cette option est sélectionnée, la valeur `entity.id` doit être présente dans l’attribut de profil.

Lorsque vous basez des recommandations sur des attributs personnalisés, vous devez sélectionner l’attribut personnalisé, puis le type de recommandation.

Vous pouvez effectuer un filtrage en temps réel en plus de vos propres critères de sortie personnalisés. Vous pouvez par exemple limiter vos éléments recommandés uniquement à ceux de la catégorie ou de la marque préférée d’un visiteur. Vous avez ainsi la possibilité de combiner les calculs hors ligne avec filtrage en temps réel.

Cette fonctionnalité signifie que vous pouvez utiliser [!DNL Target] pour ajouter de la personnalisation en plus de vos recommandations calculées hors ligne ou de listes gérées de manière personnalisée. Elle combine la puissance de vos analystes des données et de votre recherche avec la livraison approuvée, le filtrage d’exécution, les tests A/B, le ciblage, la génération de rapports, les intégrations et bien d’autres fonctions Adobe encore.

Avec l’ajout de règles d’inclusion dans les critères personnalisés, les recommandations qui seraient statiques deviennent dynamiques et fondées sur les intérêts du visiteur.

* Les critères personnalisés sont configurables au même titre que les autres critères contenus dans les recommandations.
* Vous pouvez utiliser les [collections](/help/main/c-recommendations/c-products/collections.md), [exclusions](/help/main/c-recommendations/c-products/exclusions.md), et [inclusions](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.

Les cas d’utilisation possibles incluent :

* Vous souhaitez recommander des films à partir d’une liste gérée de façon personnalisée, mais uniquement si le visiteur ne les a pas déjà vus.
* Vous souhaitez exécuter un algorithme hors ligne et utiliser les résultats pour alimenter vos recommandations, mais vous devez vous assurer que les éléments en rupture de stock ne sont jamais recommandés.
* Vous souhaitez inclure uniquement les articles extraits de la catégorie préférée de ce visiteur.

## Clés de recommandation {#keys}

Les clés de recommandation suivantes sont disponibles dans la variable [!UICONTROL Clé de recommandation] liste déroulante :

### Article actuel {#current-item}

La recommandation est déterminée par l’article que le visiteur consulte actuellement.

Les recommandations présentent d’autres articles susceptibles d’intéresser les visiteurs qui consultent l’article spécifié.

Lorsque cette option est sélectionnée, la valeur `entity.id` doit être transmise comme un paramètre à la mbox d’affichage.

Peut être utilisé avec les algorithmes suivants :

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]

Utilisez la variable [!UICONTROL Article actuel] clé de recommandations sur votre site sur :

* Pages d’un seul article (pages de produit, par exemple).
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Dernier article acheté {#last-purchased}

La recommandation est déterminée par le dernier article acheté par chaque visiteur unique. Ces données sont capturées automatiquement, de sorte qu’aucune valeur ne doit être transmise sur la page.

Peut être utilisé avec les algorithmes suivants :

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]

Utilisez la variable [!UICONTROL Dernier article acheté] clé de recommandations sur votre site sur :

* Page d’accueil, page Mon compte, publicités hors site.
* Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

#### Clé de recommandations personnalisée

Vous pouvez axer les recommandations sur la valeur d’un attribut de profil personnalisé. Supposons, par exemple, que vous souhaitiez afficher les films recommandés en fonction de la séquence que le visiteur a ajoutée le plus récemment à sa file d’attente.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Dernier affichage ajouté à la liste de surveillance »).
1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** (par exemple « Personnes qui ont vu ceci, vu cela »).

   ![Boîte de dialogue Créer de nouveaux critères](/help/main/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Si votre attribut de profil personnalisé ne correspond pas directement à un ID d’entité unique, il est nécessaire d’expliquer à [!DNL Recommendations] la manière dont vous souhaitez que la correspondance à une entité se produise. Supposons, par exemple, que vous souhaitiez afficher les principaux articles de la marque préférée d’un visiteur.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Marque préférée »).

1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** que vous souhaitez utiliser avec cette clé (par exemple, « Meilleurs vendeurs »).

   L’option [!UICONTROL Groupe par valeur unique de] s’affiche.

1. Sélectionnez l’attribut d’entité correspondant à la clé choisie. Dans ce cas, « Marque préférée » correspond à `entity.brand`.

   [!DNL Recommendations] génère désormais une liste des « Meilleurs vendeurs » pour chaque marque et montre au visiteur la liste des « Meilleurs vendeurs » en fonction de la valeur stockée dans l’attribut de profil Marque préférée du visiteur.

   ![Boîte de dialogue Créer de nouveaux critères 2](/help/main/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Dernier article consulté {#last-viewed}

La recommandation est déterminée par le dernier élément consulté par chaque visiteur unique. Ces données sont capturées automatiquement, de sorte qu’aucune valeur ne doit être transmise sur la page.

Peut être utilisé avec les algorithmes suivants :

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]

Utilisez la variable [!UICONTROL Dernier article consulté] clé de recommandations sur votre site sur :

* Page d’accueil, page Mon compte, publicités hors site.
* Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

### Article le plus consulté {#most-viewed-logic}

Affiche les éléments ou médias les plus consultés sur votre site.

Cette logique vous permet d’afficher des recommandations basées sur les éléments les plus consultés sur votre site afin d’augmenter les conversions d’autres éléments. Par exemple, un site de médias peut afficher des recommandations sur sa page d’accueil pour ses vidéos les plus visionnées afin d’encourager les visiteurs à regarder d’autres vidéos.

Cette clé de recommandation peut être utilisée avec les algorithmes suivants :

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]

### Catégorie en cours {#current-category}

La recommandation est déterminée par la catégorie de produits que le visiteur consulte actuellement.

Les recommandations présentent des articles dans la catégorie de produits spécifiée.

Lorsque cette option est sélectionnée, la valeur `entity.categoryId` doit être transmise comme paramètre à la mbox d’affichage.

Cette clé de recommandation peut être utilisée avec les algorithmes suivants :

* Meilleurs vendeurs
* Les plus consultés

Utilisez la variable [!UICONTROL Catégorie en cours] clé de recommandations sur votre site sur :

* Pages d’une seule catégorie.
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Catégorie préférée {#favorite-category}

La recommandation est déterminée par la catégorie de produits préférée du visiteur.

Les recommandations présentent des articles dans la catégorie de produits spécifiée.

Lorsque cette option est sélectionnée, la valeur `entity.categoryId` doit être transmise comme paramètre à la mbox d’affichage.

Cette clé de recommandation peut être utilisée avec les algorithmes suivants :

* Meilleurs vendeurs
* Les plus consultés

Utilisez la variable [!UICONTROL Catégorie en cours] clé de recommandations sur votre site sur :

* Pages d’une seule catégorie.
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Affinité du site {#site-affinity}

Recommande des éléments selon la certitude d’une relation entre ceux-ci. Vous pouvez configurer ce critère pour déterminer la quantité de données requises avant qu’une recommandation ne soit présentée à l’aide du curseur Règles d’inclusion. Si vous sélectionnez par exemple très forte, les produits qui ont le plus de chances d’avoir une correspondance sont recommandés.

Par exemple, si vous définissez une très forte affinité et si votre conception comporte cinq éléments dont trois qui correspondent à la force du seuil de connexion, les deux éléments qui ne répondent pas aux exigences de force minimales ne sont pas affichés dans vos recommandations et sont remplacés par les éléments de sauvegarde. Les éléments avec l’affinité la plus forte s’affichent en premier.

Par exemple, un détaillant en ligne peut recommander des articles au cours de visites ultérieures auxquels un visiteur a manifesté de l’intérêt au cours de sessions précédentes. L’activité de la session de chaque visiteur est capturée afin de calculer une affinité en fonction d’un modèle de récence et de fréquence. À mesure que ce visiteur revient sur votre site, l’affinité du site est utilisée pour afficher des recommandations basées sur des actions passées sur votre site.

Certains clients qui proposent plusieurs collections de produits et plusieurs comportements de site obtiendront de meilleurs résultats en définissant une affinité faible.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté
