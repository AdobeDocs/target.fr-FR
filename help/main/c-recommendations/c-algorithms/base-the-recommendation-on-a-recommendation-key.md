---
keywords: clé de recommandation;logique de recommandation;catégorie actuelle;attribut personnalisé;dernier article acheté;dernier article consulté;élément le plus consulté;élément le plus consulté;catégorie préférée;popularité;dernier article consulté;dernier achat;dernier consulté;le plus consulté;favori;récemment consulté
description: Découvrez comment utiliser des recommandations basées sur des clés qui utilisent le contexte du comportement du visiteur pour afficher des résultats pertinents dans les activités [!UICONTROL Recommendations].
title: Comment baser la [!UICONTROL recommandation] sur une [!UICONTROL clé de recommandation] ?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
TQID: 'https://experienceleague.adobe.com/1gI3rMMf9s5ogc4BvBz4fMUqxed1Nqad0XoaR8SlU58'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '3740'
ht-degree: 12%
---
# Baser la recommandation sur une clé de recommandation {#base-on-recommendation-key}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez les types d’algorithmes, les algorithmes et les clés de recommandation disponibles pour baser les recommandations dans les activités [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Les recommandations basées sur des algorithmes utilisent le contexte du comportement du visiteur pour afficher des résultats pertinents dans les activités [!DNL Adobe Target] [!DNL Recommendations]. Chaque type d’algorithme propose son propre jeu d’algorithmes. Pour un résumé des types d&#39;algorithmes et de leurs algorithmes, consultez [Prise en main des critères](/help/main/c-recommendations/c-algorithms/algorithms.md#section_885B3BB1B43048A88A8926F6B76FC482).

Chaque critère est défini dans son propre onglet. Le trafic est réparti de manière égale entre les tests de critères : avec deux critères, le trafic est réparti de manière égale entre eux, et avec deux critères et deux conceptions, le trafic est réparti de manière égale entre les quatre combinaisons. Un pourcentage de visiteurs et visiteuses du site peut également être défini pour afficher le contenu par défaut à des fins de comparaison. Dans ce cas, le pourcentage spécifié de visiteurs voit le contenu par défaut et le reste est réparti entre les combinaisons de critères et de conception.

Pour plus d’informations sur la création de critères et la définition de leurs types d’algorithmes et algorithmes, voir [Créer des critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Différents algorithmes s’adaptent à différents types de pages. Les sections suivantes décrivent chaque type d’algorithme et ses algorithmes.

## Basé sur le panier {#cart-based}

Le type d’algorithme **[!UICONTROL Basé sur le panier]** recommande des articles en fonction du contenu du panier actuel du visiteur. Les clés de recommandation sont fournies sous forme de valeurs séparées par des virgules dans le paramètre [mbox `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}. Seules les 10 premières valeurs sont prises en compte.

La logique de recommandation basée sur le panier est similaire à l’algorithme basé sur l’utilisateur « **[!UICONTROL Recommandé pour vous]** » et aux algorithmes basés sur l’article « **[!UICONTROL Personnes qui ont consulté ceci, acheté cela]** » et « **[!UICONTROL Personnes qui ont acheté cela, acheté cela]** ».

[!DNL Target] utilise des techniques de filtrage collaboratif pour déterminer les similitudes de chaque élément du panier du visiteur, puis combine les similitudes comportementales de tous les éléments dans une liste fusionnée.

Les marketeurs peuvent choisir si [!DNL Target] examine le comportement des visiteurs au cours d&#39;une seule session ou de plusieurs sessions :

* **[!UICONTROL Session unique]** : basée sur ce que les autres visiteurs ont fait au cours d’une seule session.

  Une seule session convient aux produits qui « vont » fortement les uns avec les autres en fonction d’un usage, d’une occasion ou d’un événement. Par exemple, un visiteur qui achète une imprimante peut également avoir besoin d’encre et de papier, et un visiteur qui achète du beurre d’arachide peut également avoir besoin de pain et de gelée.

* **[!UICONTROL Entre les sessions]** : basé sur ce que les autres visiteurs ont fait entre plusieurs sessions.

  Plusieurs sessions s’adaptent aux produits qui s’associent fortement en fonction des préférences ou des goûts des visiteurs. Par exemple, un visiteur qui aime Star Wars peut également aimer Indiana Jones, même s’il ne souhaite pas nécessairement regarder les deux films au même moment. De même, un visiteur qui aime le jeu de société « Codenames » peut également aimer le jeu de société « Avalon », même si le visiteur ne peut pas jouer aux deux jeux simultanément.

[!DNL Target] émet des recommandations pour chaque visiteur en fonction des éléments de son panier actuel, que le comportement du visiteur soit pris en compte au cours d’une seule session ou de plusieurs sessions.

Les algorithmes suivants sont disponibles avec le type d’algorithme **[!UICONTROL Basé sur le panier]** :

| Algorithme | Fonctionnement | Quand l’utiliser | Clés de recommandation |
| --- | --- | --- | --- |
| **[!UICONTROL Les Personnes Qui Ont Consulté Ces/Ces Ont Également Consulté]** | Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté. Renvoie les autres produits que les utilisateurs ont consultés après avoir consulté celui-ci. Le produit spécifié n&#39;est pas inclus dans le jeu de résultats. | Créez d’autres opportunités de conversion en recommandant des éléments que les autres visiteurs qui ont consulté un élément ont également consultés. Par exemple, les visiteurs qui consultent des vélos sur le site peuvent également consulter des casques de vélo, des kits de cyclisme, des serrures, etc., de sorte qu’une recommandation peut suggérer d’autres produits qui contribuent à augmenter les recettes. | **[!UICONTROL Article Actuel]**, **[!UICONTROL Dernier Article Acheté]**, **[!UICONTROL Dernier Article Consulté]**, **[!UICONTROL Article Le Plus Consulté]** |
| **[!UICONTROL Les Personnes Qui Les Ont Consultés Ont Également Acheté]** | Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Retourne les autres produits achetés après avoir consulté celui-ci. Le produit spécifié n&#39;est pas inclus dans le jeu de résultats. | Augmentez les opportunités de vente croisée en affichant une recommandation sur une page produit, par exemple, qui affiche les articles achetés par d’autres visiteurs qui les ont consultés. Si le visiteur consulte un poteau de pêche, la recommandation peut afficher d’autres articles achetés par d’autres visiteurs, tels que des boîtes à palets, des échassiers et des leurres de pêche. Lorsque les visiteurs et visiteuses parcourent le site, ils reçoivent des recommandations d’achat supplémentaires. | **[!UICONTROL Article Actuel]**, **[!UICONTROL Dernier Article Acheté]**, **[!UICONTROL Dernier Article Consulté]**, **[!UICONTROL Article Le Plus Consulté]** |
| **[!UICONTROL Les Personnes Qui Ont Acheté Ces Ont Également Acheté]** | Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié. Retourne les autres produits achetés après l&#39;achat de celui-ci. Le produit spécifié n&#39;est pas inclus dans le jeu de résultats. | Augmentez les opportunités de vente croisée en affichant une recommandation sur une page de résumé du panier, par exemple, qui affiche les articles que d’autres acheteurs ont également achetés. Si le visiteur achète un costume, la recommandation peut afficher des articles supplémentaires que d’autres visiteurs ont achetés en même temps que le costume, tels que des cravates, des chaussures et des boutons de manchette. Lorsque les visiteurs passent en revue leurs achats, ils reçoivent des recommandations supplémentaires. | **[!UICONTROL Article Actuel]**, **[!UICONTROL Dernier Article Acheté]**, **[!UICONTROL Dernier Article Consulté]**, **[!UICONTROL Article Le Plus Consulté]** |

## [!UICONTROL Basé Sur La Popularité]

Le type d&#39;algorithme **[!UICONTROL Basé sur la popularité]** recommande des éléments en fonction de leur popularité globale sur le site ou de leur popularité au sein de la catégorie, de la marque, du genre, etc. préférés ou les plus consultés de l&#39;utilisateur.

Les algorithmes suivants sont disponibles avec le type d’algorithme **[!UICONTROL Basé sur la popularité]** :

| Algorithme | Fonctionnement | Quand l’utiliser | Clés de recommandation |
| --- | --- | --- | --- |
| **[!UICONTROL Les plus consultés sur le site]** | La recommandation est déterminée par l’élément qui a été consulté le plus souvent, en fonction des critères de récence/fréquence. Voir [Score le plus consulté sur le site](#most-viewed). | Pages générales, telles les pages d’accueil et les publicités hors site. | |
| **[!UICONTROL Les plus consultés par catégorie]** | La recommandation est déterminée par la catégorie qui a reçu le plus d’activités, en utilisant la même méthode que pour l’élément le plus consulté, sauf que les catégories sont notées au lieu des produits. Voir [Les plus consultés par score de catégorie](#most-viewed-category). | Pages générales, telles les pages d’accueil et les publicités hors site. | **[!UICONTROL Catégorie Actuelle]**, **[!UICONTROL Catégorie Favorite]** |
| **[!UICONTROL Éléments les plus consultés par attribut d&#39;élément]** | Recommande des éléments ou des médias similaires aux éléments ou aux médias les plus consultés sur le site. L’attribut d’élément sur lequel baser la recommandation est sélectionné, par exemple, « Nom » ou « Marque ». Ensuite, les attributs de profil stockés dans le profil du visiteur pour correspondre sont sélectionnés, par exemple « Marque préférée », « Dernier élément ajouté au panier » ou « Programme le plus consulté ». | | |
| **[!UICONTROL Les plus consultés par attribut de profil]** | Recommande les éléments les plus consultés regroupés par attribut de profil du visiteur plutôt que par informations d’élément, comme le font **[!UICONTROL Les plus consultés par catégorie]** et **[!UICONTROL Les plus consultés par attribut d’élément]**. [!DNL Target] conserve une liste de classement distincte par valeur d’attribut et, au moment de la diffusion, affiche à chaque visiteur la liste correspondant à sa propre valeur stockée. Voir [Algorithmes d’attributs de profil](#profile-attribute-algorithms). | | |
| **[!UICONTROL Meilleurs vendeurs sur le site]** | Affiche les articles inclus dans les commandes les plus terminées de l&#39;ensemble du site. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande. | Créez des recommandations pour les articles les plus vendus sur le site afin d’augmenter la conversion et les recettes. Cette logique est adaptée aux nouveaux visiteurs et visiteuses du site. | |
| **[!UICONTROL Meilleurs vendeurs par catégorie]** | Affiche les articles inclus dans les commandes les plus terminées par catégorie. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande. | Créez des recommandations pour les articles les plus vendus sur le site en fonction de la catégorie afin d’augmenter la conversion et les recettes. Cette logique est adaptée aux nouveaux visiteurs et visiteuses du site. | **[!UICONTROL Catégorie Actuelle]**, **[!UICONTROL Catégorie Favorite]** |
| **[!UICONTROL Meilleurs vendeurs par attribut d&#39;article]** | Recommande des articles ou des médias similaires aux articles ou aux médias les plus achetés sur le site. L’attribut d’élément sur lequel baser la recommandation est sélectionné, par exemple, « Nom » ou « Marque ». Ensuite, les attributs de profil stockés dans le profil du visiteur pour correspondre sont sélectionnés, par exemple « Marque préférée », « Dernier élément ajouté au panier » ou « Programme le plus consulté ». | | |
| **[!UICONTROL Meilleurs vendeurs par attribut de profil]** | Recommande les articles les plus vendus regroupés par attribut de profil du visiteur plutôt que par informations d&#39;article, comme le font **[!UICONTROL Meilleurs vendeurs par catégorie]** et **[!UICONTROL Meilleurs vendeurs par attribut d&#39;article]**. [!DNL Target] conserve une liste des meilleurs vendeurs distincte par valeur d’attribut et, au moment de la livraison, affiche à chaque visiteur la liste correspondant à sa propre valeur stockée. Voir [Algorithmes d’attributs de profil](#profile-attribute-algorithms). | | |
| **[!UICONTROL Meilleure mesure par Analytics]** | Affiche le « Top x » où *x* est une mesure [!DNL Analytics] arbitraire. Lors de l’utilisation de données comportementales provenant de mbox, il est possible d’utiliser **[!UICONTROL Les plus vendus]** ou **[!UICONTROL les plus consultés]** (x = « vendus » ou x = « consultés »). Lors de l’utilisation de données comportementales provenant de [!DNL Adobe Analytics], x = « Ajouts au panier » ou une autre mesure [!DNL Analytics] peut être utilisée. | | |

### [!UICONTROL Les plus consultés sur le site] {#most-viewed}

La recommandation est l’élément qui a été consulté le plus souvent, déterminé par les critères de récence/fréquence comme suit :

* 10 points pour la première consultation de produit
* 5 points pour chaque consultation consécutive
* À la fin d’une session, divisez toutes les valeurs par 2

Par exemple, la visualisation de la planche de surf A puis de la planche de surf B en une seule session donne les résultats suivants : A : 10, B : 5. Lorsque la session se termine, le résultat est A : 5, B : 2.5. Si les mêmes éléments sont affichés lors de la session suivante, les valeurs passent à A : 15, B : 7.5.

### [!UICONTROL Notation la plus consultée par catégorie] {#most-viewed-category}

La recommandation correspond à la catégorie qui a reçu le plus d’activités. Elle utilise la même méthode que l’« élément le plus consulté », sauf que les catégories sont notées à la place des produits, avec les critères de récence/fréquence suivants :

* 10 points pour la première consultation de catégorie
* 5 points pour chaque consultation consécutive

À chaque visite, le score de chaque catégorie non actuelle qui a été consultée auparavant est décrémenté de 1.

Par exemple, l’affichage de la catégorie A puis de la catégorie B dans une session aboutit à A : 9, B : 10. Si les mêmes éléments sont affichés lors de la session suivante, les valeurs deviennent A : 20, B : 9.

### Algorithmes d’attribut de profil {#profile-attribute-algorithms}

>[!CONTEXTUALHELP]
>id="target_recommendations_profile_attribute"
>title="Attribut de profil"
>abstract="Vous pouvez créer un attribut de profil à l’aide de scripts de profil. Une fois qu’un script de profil est créé et activé, son attribut de profil correspondant peut être utilisé avec cet algorithme."

**[!UICONTROL Les plus consultés par attribut de profil]** et **[!UICONTROL les plus vendus par attribut de profil]** dépendent d&#39;un script de profil pour renseigner l&#39;attribut. Le nom du script doit commencer par le préfixe `recsAttribute`, donc [!DNL Target] le stocke en tant que `user.recsAttribute<Name>`. Un script peut être écrit pour toute caractéristique de visiteur appropriée au cas d’utilisation. Pour plus d&#39;informations sur la définition des attributs de profil avec des scripts de profil, voir [Paramètres de profil](https://experienceleague.adobe.com/en/docs/target/using/audiences/visitor-profiles/profile-parameters).

Par exemple, le script suivant, nommé `recsAttributeRegion`, base les recommandations sur la région du visiteur :

```
var region = mbox.param('userRegion');
if (region) return region;
```

De même, le script suivant, nommé `recsAttributeLoyaltyTier`, base les recommandations sur le niveau de fidélité du visiteur :

```
var tier = mbox.param('visitorLoyaltyTier');
if (tier) return tier;
```

Une fois le script créé et activé, l’entrée **[!UICONTROL Région]** ou **[!UICONTROL Niveau de fidélité]** correspondante est disponible dans le menu déroulant Attribut de profil de la fenêtre de création de critères. Le préfixe `recsAttribute` lui-même n’est pas affiché dans la liste déroulante.

## [!UICONTROL Basé Sur Un Élément]

Le type d&#39;algorithme **[!UICONTROL Basé sur un élément]** recommande des éléments similaires à un élément que l&#39;utilisateur consulte actuellement ou a récemment consulté.

Les algorithmes suivants sont disponibles avec le type d&#39;algorithme **[!UICONTROL Basé sur un élément]** :

| Algorithme | Fonctionnement | Quand l’utiliser | Clés de recommandation |
| --- | --- | --- | --- |
| **[!UICONTROL Les Personnes Qui Ont Consulté Ceci Ont Consulté Cela]** | Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté. Renvoie les autres produits que les utilisateurs ont consultés après avoir consulté celui-ci. Le produit spécifié n&#39;est pas inclus dans le jeu de résultats. | Créez d’autres opportunités de conversion en recommandant des éléments que les autres visiteurs qui ont consulté un élément ont également consultés. Par exemple, les visiteurs qui consultent des vélos sur le site peuvent également consulter des casques de vélo, des kits de cyclisme, des serrures, etc., de sorte qu’une recommandation peut suggérer d’autres produits qui contribuent à augmenter les recettes. | **[!UICONTROL Article Actuel]**, **[!UICONTROL Dernier Article Acheté]**, **[!UICONTROL Dernier Article Consulté]**, **[!UICONTROL Article Le Plus Consulté]** |
| **[!UICONTROL Les Personnes Qui Ont Consulté Ceci Ont Acheté Cela]** | Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Retourne les autres produits achetés après avoir consulté celui-ci. Le produit spécifié n&#39;est pas inclus dans le jeu de résultats. | Augmentez les opportunités de vente croisée en affichant une recommandation sur une page produit, par exemple, qui affiche les articles achetés par d’autres visiteurs qui les ont consultés. Si le visiteur consulte un poteau de pêche, la recommandation peut afficher d’autres articles achetés par d’autres visiteurs, tels que des boîtes à palets, des échassiers et des leurres de pêche. Lorsque les visiteurs et visiteuses parcourent le site, ils reçoivent des recommandations d’achat supplémentaires. | **[!UICONTROL Article Actuel]**, **[!UICONTROL Dernier Article Acheté]**, **[!UICONTROL Dernier Article Consulté]**, **[!UICONTROL Article Le Plus Consulté]** |
| **[!UICONTROL Les Personnes Qui Ont Acheté Ceci Ont Acheté Cela]** | Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié. Retourne les autres produits achetés après l&#39;achat de celui-ci. Le produit spécifié n&#39;est pas inclus dans le jeu de résultats. | Augmentez les opportunités de vente croisée en affichant une recommandation sur une page de résumé du panier, par exemple, qui affiche les articles que d’autres acheteurs ont également achetés. Si le visiteur achète un costume, la recommandation peut afficher des articles supplémentaires que d’autres visiteurs ont achetés en même temps que le costume, tels que des cravates, des chaussures et des boutons de manchette. Lorsque les visiteurs passent en revue leurs achats, ils reçoivent des recommandations supplémentaires. | **[!UICONTROL Article Actuel]**, **[!UICONTROL Dernier Article Acheté]**, **[!UICONTROL Dernier Article Consulté]**, **[!UICONTROL Article Le Plus Consulté]** |
| **[!UICONTROL Éléments avec des attributs similaires]** | Recommande des éléments ou des médias similaires à d’autres éléments ou médias selon l’activité de la page ou le comportement du visiteur précédent. Si **[!UICONTROL Éléments avec des attributs similaires]** ou **[!UICONTROL Média avec des attributs similaires]** est sélectionné, des règles de similarité de contenu peuvent être définies. Pour plus d&#39;informations, voir [Similarité de contenu](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity). | La similarité de contenu est effective pour les nouveaux éléments, qui ne sont pas susceptibles d’apparaître dans les recommandations à l’aide de **[!UICONTROL Personnes qui ont consulté ceci]**, **[!UICONTROL Consulté cela]** et d’une autre logique basée sur le comportement passé. Il peut également générer des recommandations pour les nouveaux visiteurs et visiteuses qui n’ont aucun achat précédent ou autre donnée historique. | **[!UICONTROL Article Actuel]**, **[!UICONTROL Dernier Article Acheté]**, **[!UICONTROL Dernier Article Consulté]**, **[!UICONTROL Article Le Plus Consulté]** |

## [!UICONTROL Basé Sur L&#39;Utilisateur]

Le type d&#39;algorithme **[!UICONTROL Basé sur l&#39;utilisateur]** recommande des éléments en fonction du comportement de l&#39;utilisateur.

Les algorithmes suivants sont disponibles avec le type d&#39;algorithme **[!UICONTROL Basé sur l&#39;utilisateur]** :

| Algorithme | Fonctionnement | Quand l’utiliser | Clés de recommandation |
| --- | --- | --- | --- |
| **[!UICONTROL Éléments récemment consultés]** | Utilise l’historique du visiteur (sur plusieurs sessions) pour présenter les *x* derniers éléments consultés par le visiteur, en fonction du nombre d’emplacements dans la conception. Voir [Détails des éléments récemment consultés](#recently-viewed). | Pages générales, telles les pages d’accueil et les publicités hors site. | |
| **[!UICONTROL Recommandé]** | Recommande des articles en fonction de l’historique de navigation, d’affichage et d’achat de chaque visiteur. Les vues et les achats sont utilisés pour déterminer les articles recommandés. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur, est mise à jour en cours de session et devient plus personnalisée au fur et à mesure que l’utilisateur parcourt le site. | Proposez du contenu et des expériences personnalisés aux nouveaux visiteurs et aux visiteurs récurrents. La clé de recommandation spécifiée (par exemple, **[!UICONTROL Élément actuel]**) est utilisée pour appliquer les filtres de règle d&#39;inclusion sélectionnés, par exemple, pour exclure les éléments qui ne répondent pas à certains critères (produits en rupture de stock, articles publiés il y a plus de 30 jours, films classés R, etc.), ou pour limiter les éléments inclus à une seule catégorie ou à la catégorie actuelle. | Clés de filtrage : **[!UICONTROL Élément actuel]**, **[!UICONTROL Dernier élément acheté]**, **[!UICONTROL Dernier élément consulté]**, **[!UICONTROL Élément le plus consulté]** |

### [!UICONTROL Détails des éléments récemment consultés] {#recently-viewed}

L’algorithme **[!UICONTROL Éléments récemment consultés]** renvoie des résultats spécifiques à un [environnement](/help/main/administrating-target/hosts.md) donné. Si deux sites appartiennent à différents environnements et qu’un visiteur bascule entre les deux sites, chaque site n’affiche que les éléments récemment consultés du site approprié. Si deux sites se trouvent dans le même environnement et qu’un visiteur passe d’un site à l’autre, il voit les mêmes éléments récemment consultés pour les deux sites.

Les critères **[!UICONTROL Éléments récemment consultés]** ne peuvent pas être utilisés pour les recommandations de sauvegarde.

**[!UICONTROL Éléments récemment consultés]** ou **[!UICONTROL Médias récemment consultés]** peuvent être filtrés afin que seuls les éléments dotés d’un attribut particulier s’affichent.

* **[!UICONTROL Les critères récemment consultés]** peuvent être configurés, comme les autres critères des recommandations.
* Les [collections](/help/main/c-recommendations/c-products/collections.md), [exclusions](/help/main/c-recommendations/c-products/exclusions.md) et [inclusions](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le Prix et l’Inventaire) peuvent être utilisées de la même manière que pour tout autre critère.

Un cas d’utilisation est une société multinationale ayant plusieurs entreprises, où un visiteur peut afficher des éléments dans plusieurs propriétés numériques. Les éléments récemment consultés peuvent ensuite être limités à la propriété où ils ont été consultés, de sorte qu’ils ne s’affichent pas sur le site d’une autre propriété.

>[!NOTE]
>
>**[!UICONTROL Éléments récemment consultés]** respecte à la fois les paramètres d&#39;exclusions globales et le paramètre de collection sélectionné pour l&#39;activité. Si un élément est exclu par une exclusion globale ou s&#39;il n&#39;est pas contenu dans la collection sélectionnée, il n&#39;est pas affiché. Par conséquent, lors de l’utilisation d’un critère **[!UICONTROL Éléments récemment consultés]**, le paramètre « Toutes les collections » doit généralement être utilisé.

## Critères personnalisés {#custom}

Le type d’algorithme **[!UICONTROL Critères personnalisés]** recommande des éléments en fonction d’un fichier personnalisé chargé.

La recommandation est déterminée par un élément stocké dans le profil d’un visiteur, à l’aide des attributs utilisateur.*x* ou profil.*x*. Si cette option est sélectionnée, la valeur `entity.id` doit être présente dans l’attribut de profil. Lorsque les recommandations sont basées sur des attributs personnalisés, l’attribut personnalisé doit d’abord être sélectionné, puis le type de recommandation.

Le filtrage en temps réel peut être appliqué à la sortie des critères personnalisés. Par exemple, les éléments recommandés peuvent être limités à ceux de la catégorie ou de la marque préférée d’un visiteur. Cela combine des calculs hors ligne avec le filtrage en temps réel. [!DNL Target] peut donc ajouter une personnalisation aux recommandations calculées hors ligne ou aux listes personnalisées. La science et la recherche des données de l’organisation sont ensuite combinées avec la diffusion, le filtrage d’exécution, les tests A/B, le ciblage, le compte rendu des performances et les intégrations d’Adobe.

Les règles d’inclusion sur **[!UICONTROL Critères personnalisés]** transforment sinon les recommandations statiques en recommandations dynamiques basées sur les intérêts du visiteur.

* Les critères personnalisés sont configurables au même titre que les autres critères contenus dans les recommandations.
* Les [collections](/help/main/c-recommendations/c-products/collections.md), [exclusions](/help/main/c-recommendations/c-products/exclusions.md) et [inclusions](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le Prix et l’Inventaire) peuvent être utilisées de la même manière que pour tout autre critère.

Les cas d’utilisation possibles sont les suivants :

* Recommandez des films à partir d’une liste personnalisée, mais uniquement si le visiteur ne les a pas déjà regardés.
* Exécutez un algorithme hors ligne et utilisez les résultats pour alimenter les recommandations, tout en vous assurant que les articles en rupture de stock ne sont jamais recommandés.
* Inclure uniquement les éléments provenant de la catégorie préférée de ce visiteur.

## Clés de recommandation {#keys}

Les clés de recommandation suivantes sont disponibles à partir de la liste déroulante **[!UICONTROL Clé de recommandation]** :

| Clé | Comment cela est déterminé | Éléments à transmettre | Utiliser sur | Ne pas utiliser sur | Algorithmes |
| --- | --- | --- | --- | --- | --- |
| **[!UICONTROL Élément Actuel]** | L’élément que le visiteur consulte actuellement. Les recommandations présentent d’autres articles susceptibles d’intéresser les personnes qui consultent l’article spécifié. | La valeur `entity.id` doit être transmise en tant que paramètre dans la mbox d’affichage. | Pages d’un seul article (pages de produit, par exemple). | Pages de résultats de recherche nulles. | **[!UICONTROL Éléments avec des attributs similaires]**, **[!UICONTROL Personnes ayant consulté ceci, consulté cela]**, **[!UICONTROL Personnes ayant consulté cela, acheté cela]**, **[!UICONTROL Personnes ayant acheté cela, acheté cela]** |
| **[!UICONTROL Dernier article acheté]** | Dernier article acheté par chaque visiteur unique. | Rien. Elles sont capturées automatiquement. | Page d’accueil, page Mon compte, publicités hors site. | Pages de produits ou pages relatives aux achats. | **[!UICONTROL Éléments avec des attributs similaires]**, **[!UICONTROL Personnes ayant consulté ceci, consulté cela]**, **[!UICONTROL Personnes ayant consulté cela, acheté cela]**, **[!UICONTROL Personnes ayant acheté cela, acheté cela]** |
| **[!UICONTROL Dernier article consulté]** | Dernier élément consulté par chaque visiteur unique. | Rien. Elles sont capturées automatiquement. | Page d’accueil, page Mon compte, publicités hors site. | Pages de produits ou pages relatives aux achats. | **[!UICONTROL Éléments avec des attributs similaires]**, **[!UICONTROL Personnes ayant consulté ceci, consulté cela]**, **[!UICONTROL Personnes ayant consulté cela, acheté cela]**, **[!UICONTROL Personnes ayant acheté cela, acheté cela]** |
| **[!UICONTROL Article le plus consulté]** | Éléments ou médias les plus consultés sur le site. Cette logique affiche des recommandations en fonction des éléments les plus consultés afin d’augmenter les conversions d’autres éléments. Par exemple, un site multimédia peut afficher des recommandations sur sa page d’accueil pour ses vidéos les plus consultées afin d’encourager les visiteurs à regarder d’autres vidéos. | | | | **[!UICONTROL Éléments avec des attributs similaires]**, **[!UICONTROL Personnes ayant consulté ceci, consulté cela]**, **[!UICONTROL Personnes ayant consulté cela, acheté cela]**, **[!UICONTROL Personnes ayant acheté cela, acheté cela]** |
| **[!UICONTROL Catégorie en cours]** | Catégorie de produits actuellement consultée par le visiteur ou la visiteuse. Les recommandations présentent des articles dans la catégorie de produits spécifiée. | La valeur `entity.categoryId` doit être transmise en tant que paramètre à la mbox d’affichage. | Pages d’une seule catégorie. | Pages de résultats de recherche nulles. | **[!UICONTROL Meilleurs Vendeurs]**, **[!UICONTROL Les Plus Consultés]** |
| **[!UICONTROL Catégorie préférée]** | Catégorie de produits préférée du visiteur. Les recommandations présentent des articles dans la catégorie de produits spécifiée. | La valeur `entity.categoryId` doit être transmise en tant que paramètre à la mbox d’affichage. | Pages d’une seule catégorie. | Pages de résultats de recherche nulles. | **[!UICONTROL Meilleurs Vendeurs]**, **[!UICONTROL Les Plus Consultés]** |

### Clé de recommandation personnalisée

Les recommandations peuvent être basées sur la valeur d’un attribut de profil personnalisé. Par exemple, les films recommandés peuvent être affichés en fonction du dernier film ajouté par un visiteur à la file d’attente.

1. Sélectionnez l’attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « **[!UICONTROL Dernier affichage ajouté à la liste de contrôle]** »).

1. Sélectionnez la **[!UICONTROL logique de recommandation]** (par exemple, « **[!UICONTROL Personnes qui ont consulté ceci, qui ont consulté cela]** »).

Si l’attribut de profil personnalisé ne correspond pas directement à un ID d’entité unique, indiquez comment [!DNL Recommendations] correspond à une entité. Par exemple, pour afficher les articles les plus vendus de la marque préférée d’un visiteur :

1. Sélectionnez l’attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Marque préférée »).

1. Sélectionnez la **[!UICONTROL logique de recommandation]** à utiliser avec cette clé (par exemple, « **[!UICONTROL Meilleurs vendeurs]** »).

   L&#39;option Regrouper par valeur unique de **[!UICONTROL s&#39;affiche.]**

1. Sélectionnez l&#39;attribut d&#39;entité correspondant à la clé choisie. Dans ce cas, « **[!UICONTROL Marque préférée]** » correspond à `entity.brand`.

   [!DNL Recommendations] génère désormais une liste « **[!UICONTROL Meilleurs vendeurs]** » pour chaque marque et affiche au visiteur la liste appropriée « **[!UICONTROL Meilleurs vendeurs]** » en fonction de la valeur stockée dans l’attribut de profil **[!UICONTROL Marque préférée]** du visiteur.

### [!UICONTROL Affinité Du Site] {#site-affinity}

Recommande des éléments selon la certitude d’une relation entre ceux-ci. Ce critère peut être configuré pour définir la quantité de données requise avant l’affichage d’une recommandation à l’aide du curseur **[!UICONTROL Règles d’inclusion]**. Par exemple, lorsque l’option Très fort est sélectionnée, les produits présentant la plus grande certitude de correspondance sont recommandés.

Par exemple, si une affinité très forte est définie et que la conception comprend cinq éléments, dont trois respectent le seuil de résistance de la connexion, les deux éléments qui ne respectent pas les exigences de résistance minimale ne sont pas affichés dans les recommandations et sont remplacés par les éléments de sauvegarde définis. Les éléments avec l’affinité la plus forte s’affichent en premier.

Autre exemple, un retailer en ligne peut recommander des éléments lors de visites ultérieures qui ont suscité l’intérêt d’un visiteur au cours de sessions précédentes. L’activité de la session de chaque visiteur est capturée afin de calculer une affinité en fonction d’un modèle de récence et de fréquence. À mesure que le visiteur revient sur le site, l’affinité du site est utilisée pour afficher des recommandations basées sur des actions passées sur le site.

Une faible affinité de site peut donner les meilleurs résultats pour les clients avec des collections de produits et des comportements de site divers.

Cette logique peut être utilisée avec les clés de recommandation suivantes : **[!UICONTROL Article actuel]**, **[!UICONTROL Dernier article acheté]**, **[!UICONTROL Dernier article consulté]**, **[!UICONTROL Article le plus consulté]**.
