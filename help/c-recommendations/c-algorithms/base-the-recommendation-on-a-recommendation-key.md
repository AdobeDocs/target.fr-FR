---
keywords: clé de recommandation ; logique de recommandation ; catégorie actuelle ; attribut personnalisé ; dernier article acheté ; dernier article consulté ; élément le plus consulté ; élément le plus consulté ; catégorie préférée ; popularité ; article récemment consulté ; dernier article acheté ; dernier article consulté ; favori ; récemment consulté
description: Découvrez comment utiliser des recommandations basées sur des clés qui utilisent le contexte de comportement des visiteurs pour afficher des résultats pertinents dans les activités Adobe [!DNL Target] Recommendations.
title: Comment puis-je baser la recommandation sur une clé de recommandation ?
feature: Recommandations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2932'
ht-degree: 67%

---

# Baser la recommandation sur une clé de recommandation

Recommendations basé sur les clés utilise le contexte de comportement du visiteur pour afficher les résultats pertinents dans les activités [!DNL Adobe Target] [!DNL Recommendations].

Il existe deux types de recommandations :

* **Popularité :** dresse la liste des éléments d’après les critères Les plus consultés, Les plus vendus et Mesure maximale. La clé est vide pour les critères de popularité.
* **Basé sur une clé :** inclut le reste des critères. Recommandations propose un large éventail de choix de types de clé. Les options vont de « élément actif » à « paramètres de profil » pour vous permettre de définir par voie programmatique la clé des valeurs à recommander. Vous pouvez tester plusieurs critères les uns par rapport aux autres en basant chaque critère sur une clé différente.

Chaque critère est défini dans son propre onglet. Le trafic est réparti uniformément entre vos différents tests de critères. En d’autres termes, si vous avez deux critères, le trafic est réparti uniformément entre les deux. Si vous avez deux critères et deux conceptions, le trafic est réparti uniformément entre les quatre combinaisons. Vous pouvez également spécifier le pourcentage des visiteurs du site qui visualisent le contenu par défaut, à des fins de comparaison. Dans ce cas, le pourcentage spécifié des visiteurs du site qui visualisent le contenu par défaut et les autres sont répartis entre vos combinaisons critère/conception.

1. Créez un nouveau critère ou sélectionnez un critère existant et cliquez sur **[!UICONTROL Modifier]**.
1. Pour modifier la clé de recommandation, sélectionnez la nouvelle clé dans la liste déroulante [!UICONTROL Clé de recommandation], puis cliquez sur **[!UICONTROL Enregistrer]** ou **[!UICONTROL Mettre à jour]**.

   Différentes logiques renvoient vers différentes clés de recommandation. Par conséquent, différentes recommandations renvoient à des emplacements sur différents types de page. Consultez les sections suivantes pour plus d’informations sur chaque clé de recommandation.

## Clés de recommandation

Les clés de recommandation suivantes sont disponibles dans la liste déroulante [!UICONTROL Clé de recommandation] :

### Article actuel {#current-item}

La recommandation est déterminée par l’article que le visiteur consulte actuellement.

Les recommandations présentent d’autres articles susceptibles d’intéresser les visiteurs qui consultent l’article spécifié.

Lorsque cette option est sélectionnée, la valeur `entity.id` doit être transmise comme un paramètre à la mbox d’affichage.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

* Pages d’un seul article (pages de produit, par exemple).
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Catégorie en cours {#current-category}

La recommandation est déterminée par la catégorie de produits que le visiteur consulte actuellement.

Les recommandations présentent des articles dans la catégorie de produits spécifiée.

Lorsque cette option est sélectionnée, la valeur `entity.categoryId` doit être transmise comme paramètre à la mbox d’affichage.

#### Logique (critère)

* Meilleurs vendeurs
* Les plus consultés

#### Où l’utiliser sur votre site

* Pages d’une seule catégorie.
* Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Attribut personnalisé  {#custom}

La recommandation est déterminée par un article stocké dans un profil de visiteur, utilisant les attributs user.*x>* ou profile.attributs *x*.

Si cette option est sélectionnée, la valeur `entity.id` doit être présente dans l’attribut de profil.

Lorsque vous basez des recommandations sur des attributs personnalisés, vous devez sélectionner l’attribut personnalisé, puis le type de recommandation.

Vous pouvez effectuer un filtrage en temps réel en plus de vos propres critères de sortie personnalisés. Vous pouvez par exemple limiter vos éléments recommandés uniquement à ceux de la catégorie ou de la marque préférée d’un visiteur. Vous avez ainsi la possibilité de combiner les calculs hors ligne avec filtrage en temps réel.

Cette fonctionnalité signifie que vous pouvez utiliser [!DNL Target] pour ajouter une personnalisation en plus de vos recommandations calculées hors ligne ou de vos listes personnalisées. Elle combine la puissance de vos analystes des données et de votre recherche avec la livraison approuvée, le filtrage d’exécution, les tests A/B, le ciblage, la génération de rapports, les intégrations et bien d’autres fonctions Adobe encore.

Avec l’ajout de règles d’inclusion dans les critères personnalisés, les recommandations qui seraient statiques deviennent dynamiques et fondées sur les intérêts du visiteur.

* Les critères personnalisés sont configurables au même titre que les autres critères contenus dans les recommandations.
* Vous pouvez utiliser les [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), et [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.

Les cas d’utilisation possibles incluent :

* Vous souhaitez recommander des films à partir d’une liste gérée de façon personnalisée, mais uniquement si le visiteur ne les a pas déjà vus.
* Vous voulez exécuter un algorithme en mode hors ligne et utiliser les résultats pour alimenter vos recommandations, mais vous devez vous assurer que les articles épuisés ne soient jamais recommandés.
* Vous souhaitez inclure uniquement les articles extraits de la catégorie préférée de ce visiteur.

#### Logique (critère)

* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Comportement global]
* [!UICONTROL Les plus consultés]
* [!UICONTROL Meilleurs vendeurs]

Si la clé est un attribut de profil personnalisé et que le type d’algorithme est Le plus consulté ou Meilleurs vendeurs, une nouvelle liste déroulante intitulée « Grouper par valeur unique de » s’affiche et indique la liste des attributs d’entité connus (ID d’exception, catégorie, marge, valeur, inventaire et environnement). Ce champ est obligatoire.

#### Où l’utiliser sur votre site

* Peut être utilisé sur n’importe quelle page.

#### Clé de recommandations personnalisée

Vous pouvez axer les recommandations sur la valeur d’un attribut de profil personnalisé. Supposons, par exemple, que vous souhaitiez afficher les films recommandés en fonction de la séquence que le visiteur a ajoutée le plus récemment à sa file d’attente.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Dernier affichage ajouté à la liste de surveillance »).
1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** (par exemple « Personnes qui ont vu ceci, vu cela »).

   ![Boîte de dialogue Créer de nouveaux critères](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Si votre attribut de profil personnalisé ne correspond pas directement à un ID d’entité unique, il est nécessaire d’expliquer à [!DNL Recommendations] la manière dont vous souhaitez que la correspondance à une entité se produise. Supposons, par exemple, que vous souhaitiez afficher les principaux articles de la marque préférée d’un visiteur.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Marque préférée »).

1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** que vous souhaitez utiliser avec cette clé (par exemple, « Meilleurs vendeurs »).

   L’option [!UICONTROL Groupe par valeur unique de] s’affiche.

1. Sélectionnez l’attribut d’entité correspondant à la clé choisie. Dans ce cas, « Marque préférée » correspond à `entity.brand`.

   [!DNL Recommendations] génère désormais une liste des « Meilleurs vendeurs » pour chaque marque et montre au visiteur la liste des « Meilleurs vendeurs » en fonction de la valeur stockée dans l’attribut de profil Marque préférée du visiteur.

   ![Boîte de dialogue Créer de nouveaux critères 2](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Catégorie préférée {#favorite-category}

La recommandation est déterminée par la catégorie associée au plus haut niveau d’activité, à l’aide de la même méthode que celle utilisée pour « Article le plus consulté », sauf que le score porte sur les catégories et non sur les produits.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de catégorie
* 5 points pour chaque consultation consécutive

Les catégories consultées pour la première fois reçoivent dix points. Les visites suivantes dans la même catégorie reçoivent cinq points. À chaque visite, les catégories non actuelles qui ont été consultées auparavant sont décrémentées de 1.

Par exemple, l’affichage de categorieA, puis de categorieB dans une même session donne A : 9, B : 10. Si vous affichez les mêmes éléments lors de la session suivante, les valeurs passent à A : 20, B : 9.

#### Logique (critère)

* [!UICONTROL Meilleurs vendeurs]
* [!UICONTROL Les plus consultés]

#### Où l’utiliser sur votre site

* Pages générales, telles les pages d’accueil et les publicités hors site.

### Dernier article acheté {#last-purchased}

La recommandation est déterminée par le dernier article acheté par chaque visiteur unique. Ces données sont capturées automatiquement. Aucune valeur ne doit donc être transmise sur la page.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

* Page d’accueil, page Mon compte, publicités hors site.
* Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

### Dernier article consulté  {#last-viewed}

La recommandation est déterminée par le dernier élément consulté par chaque visiteur unique. Ces données sont capturées automatiquement. Aucune valeur ne doit donc être transmise sur la page.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

* Page d’accueil, page Mon compte, publicités hors site.
* Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

### Article le plus consulté  {#most-viewed}

La recommandation est déterminée par l’élément le plus souvent consulté, à l’aide de la même méthode que celle de la catégorie préférée.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de produit
* 5 points pour chaque consultation consécutive
* À la fin de la session, toutes les valeurs sont divisées par 2

Par exemple, l’affichage de surfboardA, puis de surfboardB dans une même session donne A : 10, B : 5. À la fin de la session, vous avez A : 5, B : 2,5. Si vous consultez les mêmes éléments au cours de la prochaine session, les valeurs deviennent A : 15 B : 7,5.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

* Pages générales, telles les pages d’accueil et les publicités hors site.

### Popularité  {#popularity}

La recommandation est déterminée par la popularité des éléments de votre site. La popularité comprend les articles les plus vendus et les plus consultés selon les données de la mbox et, si vous utilisez Adobe Analytics, toutes les mesures disponibles dans le rapport sur les produits. Les articles sont classés en fonction de la logique de recommandation sélectionnée.

#### Logique (critère)

* [!UICONTROL Meilleurs vendeurs]
* [!UICONTROL Les plus consultés]
* Mesures de rapport de produit (si vous utilisez Adobe Analytics)

#### Où l’utiliser sur votre site

* Pages générales, telles les pages d’accueil et les publicités hors site.

### Éléments récemment consultés  {#recently-viewed}

Utilise l’historique du visiteur (sur plusieurs sessions) pour présenter les *x* derniers éléments consultés par le visiteur, en fonction du nombre d’emplacements dans la conception.

Le critère Éléments récemment consultés renvoie des résultats spécifiques à un [environnement ](/help/administrating-target/hosts.md) donné. Si deux sites appartiennent à différents environnements et qu’un visiteur bascule entre les deux sites, chaque site n’affiche que les éléments récemment consultés du site approprié. Si deux sites se trouvent dans le même environnement et qu’un visiteur bascule entre les deux sites, le visiteur voit les mêmes éléments récemment consultés pour les deux sites.

>[!NOTE]
>
>Vous ne pouvez pas utiliser les critères [!UICONTROL Éléments récemment consultés] pour les recommandations de sauvegarde.

Les éléments/médias récemment consultés peuvent être filtrés de sorte que seuls les éléments ayant un attribut particulier soient affichés.

* Les critères récemment consultés sont configurables au même titre que les autres critères contenus dans les recommandations.
* Vous pouvez utiliser les [collections](/help/c-recommendations/c-products/collections.md), [exclusions](/help/c-recommendations/c-products/exclusions.md), et [inclusions](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (y compris les règles spéciales pour le prix et l’inventaire), de la même manière que tout autre critère.

Les cas d’utilisation possibles incluent :

Une multinationale regroupant plusieurs entreprises peut comporter des éléments d’affichage de visiteur répartis entre plusieurs propriétés numériques. Dans ce cas, vous pouvez limiter les éléments récemment consultés de manière à les afficher uniquement pour la propriété respective dans laquelle ils ont été consultés. Ceci empêche les éléments récemment consultés de s’afficher sur un autre site de propriété numérique.

#### Où l’utiliser sur votre site

* Pages générales, telles les pages d’accueil et les publicités hors site.

>[!NOTE]
>
>[!UICONTROL Les ] objets récemment consultés respectent à la fois les exclusions des paramètres globaux et le paramètre de collecte sélectionné pour l’activité. Si un élément est exclu par une exclusion globale ou n’est pas contenu dans la collection sélectionnée, il ne s’affiche pas. Par conséquent, lorsque vous utilisez un critère [!UICONTROL Éléments récemment consultés], le paramètre &quot;Toutes les collections&quot; doit généralement être utilisé.

## Logique de recommandation

[!DNL Target Recommendations] applique des algorithmes élaborés pour déterminer quand les actions d’un visiteur remplissent les critères définis dans votre activité. La clé de recommandation détermine quelles options de la logique des recommandations sont disponibles.

La logique de recommandation suivante (critères) est disponible dans la liste déroulante [!UICONTROL Logique de recommandation] :

### Éléments/Médias avec des attributs similaires {#similar-attributes}

Recommande des éléments ou des médias similaires à d’autres éléments ou médias selon l’activité de la page ou le comportement du visiteur précédent.

Si vous sélectionnez Éléments/Média avec des attributs similaires, vous avez la possibilité de définir des règles de similarité de contenu.

L’utilisation de la similarité de contenu pour générer des recommandations est particulièrement efficace pour les nouveaux éléments, qui ne sont pas susceptibles d’apparaître dans les recommandations à l’aide de personnes ayant consulté ceci, consulté cela et d’une autre logique basée sur le comportement passé. Vous pouvez également utiliser la similarité de contenu pour générer des recommandations utiles pour les nouveaux visiteurs, qui n’ont pas d’achats antérieurs ni d’autres données historiques.

Pour plus d’informations, voir [Similarité de contenu](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les plus consultés {#most-viewed-logic}

Affiche les éléments ou médias les plus consultés sur votre site.

Cette logique vous permet d’afficher des recommandations basées sur les éléments les plus consultés sur votre site afin d’augmenter les conversions pour d’autres éléments. Par exemple, un site de médias pourrait afficher des recommandations sur sa page d&#39;accueil pour ses vidéos les plus visionnées afin d&#39;encourager les visiteurs à regarder d&#39;autres vidéos.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Catégorie en cours
* Attribut personnalisé
* Catégorie préférée
* Popularité

### Les personnes ayant acheté ceci ont acheté cela {#bought-bought}

Recommande les éléments achetés le plus souvent par des clients en même temps que l’élément spécifié.

Cette logique renvoie d’autres produits que les utilisateurs ont achetés après avoir acheté celui-ci ; le produit spécifié n&#39;est pas inclus dans l&#39;ensemble de résultats.

Cette logique vous permet d’augmenter les opportunités de ventes croisées en affichant une recommandation sur une page de résumé du panier, par exemple, qui affiche les articles que d’autres acheteurs ont également achetés. Si, par exemple, le visiteur achète une combinaison, la recommandation peut afficher d’autres articles achetés avec la combinaison, tels que des cravates, des chaussures et des liens. Lorsque les visiteurs examinent leurs achats, vous leur fournissez des recommandations supplémentaires.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Attribut personnalisé
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant consulté ceci ont acheté cela {#viewed-bought}

Recommande les éléments achetés le plus souvent au cours de la session où l’élément spécifié est consulté. Ces critères renvoient d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n’est pas inclus dans le jeu des résultats.

Cette logique renvoie d’autres produits que les utilisateurs ont achetés après avoir consulté celui-ci ; le produit spécifié n&#39;est pas inclus dans l&#39;ensemble de résultats.

Cette logique vous permet d&#39;augmenter les opportunités de ventes croisées en affichant une recommandation sur une page de produits, par exemple, qui affiche les articles que d&#39;autres visiteurs qui ont consulté l&#39;article acheté ont déjà consultés. Si, par exemple, le visiteur voit un pôle de pêche, la recommandation peut afficher d’autres articles achetés par d’autres visiteurs, tels que des boîtes à pêche, des échassiers et des leurres de pêche. Lorsque les visiteurs naviguent sur votre site, vous leur fournissez des recommandations d’achat supplémentaires.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Attribut personnalisé
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Les personnes ayant consulté ceci ont consulté cela {#viewed-viewed}

Recommande les éléments consultés le plus souvent au cours de la session où l’élément spécifié est consulté.

Cette logique renvoie d’autres produits que les utilisateurs ont consultés après avoir consulté celui-ci ; le produit spécifié n&#39;est pas inclus dans l&#39;ensemble de résultats.

Cette logique vous permet de créer d’autres opportunités de conversion en recommandant des éléments que d’autres visiteurs qui ont consulté un élément ont également consultés. Par exemple, les visiteurs qui vue des vélos sur votre site peuvent également regarder des casques de vélo, des kits de vélo, des serrures, etc. Vous pouvez créer une recommandation à l’aide de cette logique qui suggère d’autres produits pour vous aider à augmenter vos recettes.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Attribut personnalisé
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Affinité du site {#site-affinity}

Recommande des éléments selon la certitude d’une relation entre ceux-ci. Vous pouvez configurer ce critère pour déterminer la quantité de données requises avant qu’une recommandation ne soit présentée à l’aide du curseur Règles d’inclusion. Si vous sélectionnez par exemple très forte, les produits qui ont le plus de chances d’avoir une correspondance sont recommandés.

Par exemple, si vous définissez une très forte affinité et si votre conception comporte cinq éléments dont trois qui correspondent à la force du seuil de connexion, les deux éléments qui ne répondent pas aux exigences de force minimales ne sont pas affichés dans vos recommandations et sont remplacés par les éléments de sauvegarde. Les éléments avec l’affinité la plus forte s’affichent en premier.

Par exemple, un détaillant en ligne peut recommander des articles au cours de visites ultérieures auxquels un visiteur s’est intéressé au cours de sessions antérieures. L’Activité de chaque visiteur session est capturée pour calculer une affinité en fonction d’un modèle de récence et de fréquence. À mesure que ce visiteur revient sur votre site, l’affinité du site est utilisée pour afficher des recommandations en fonction des actions passées sur votre site.

Certains clients qui proposent plusieurs collections de produits et plusieurs comportements de site obtiendront de meilleurs résultats en définissant une affinité faible.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté

### Meilleurs vendeurs {#top-sellers}

Affiche les éléments inclus dans les commandes les plus terminées. Plusieurs unités d’un même élément figurant dans une même commande sont comptabilisées comme une seule commande.

Cette logique vous permet de créer des recommandations pour les articles les plus vendus sur votre site afin d’augmenter les conversions et les recettes. Cette logique est particulièrement adaptée aux nouveaux visiteurs de votre site.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Catégorie préférée
* Popularité

### Recommendations utilisateur {#user-based}

Recommande les éléments en fonction de l&#39;historique de navigation, d&#39;affichage et d&#39;achat de chaque visiteur. Ces éléments sont généralement appelés &quot;Recommandé pour vous&quot;.

Ce critère vous permet de fournir du contenu et des expériences personnalisés aux nouveaux visiteurs et aux  de retour. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur et est mise à jour en cours de session et devient plus personnalisée lorsque l’utilisateur parcourt votre site.

Les vues et les achats sont utilisés pour déterminer les articles recommandés. La clé de recommandation spécifiée (par exemple, Article actuel) est utilisée pour appliquer les filtres de règle d’inclusion que vous sélectionnez.

Par exemple, vous pouvez effectuer les opérations suivantes :

* Exclure les éléments qui ne répondent pas à certains critères (produits en rupture de stock, articles publiés il y a plus de 30 jours, films classés R, etc.).
* Limiter les articles inclus à une seule catégorie ou à la catégorie actuelle.

Cette logique peut être utilisée avec les clés de recommandation suivantes :

* Article actuel
* Dernier article acheté
* Dernier article consulté
* Article le plus consulté
