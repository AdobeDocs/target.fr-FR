---
description: Introduction aux activités de recommandations Target qui affichent automatiquement les produits ou le contenu susceptibles d'intéresser vos clients en fonction des activités passées de l'utilisateur ou d'autres algorithmes. Les recommandations aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.
keywords: Recommandations;
seo-description: Introduction aux activités des recommandations Adobe Target qui affichent automatiquement les produits ou le contenu susceptibles d'intéresser vos clients en fonction des activités passées de l'utilisateur ou d'autres algorithmes. Les recommandations aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.
seo-title: Présentation des activités de recommandations dans Adobe Target
solution: Target
title: Présentation des recommandations
title-outputclass: Premium
topic: Premium
badge: Premium
translation-type: tm+mt
source-git-commit: 04a4585e1d56f1754b65a248715fa5bdd4f8986f

---


# ![Présentation PREMIUM](/help/assets/premium.png) des recommandations

The text in this article comes from the *Introduction to Recommendations* webinar, which you can view in its entirety below.

The *Introduction to Recommendations* webinar includes an in-depth exploration of how to leverage the value of [!DNL Adobe Target Recommendations]. Découvrez comment cette activité [!DNL Target] affiche automatiquement les produits ou le contenu susceptibles d’intéresser vos clients en optimisant les suggestions en temps réel basées sur les visites précédentes. Vous pouvez ensuite approfondir l’analyse de l’interface utilisateur de [!DNL Target] pour une présentation détaillée de la création d’une activité [!DNL Recommendations].

## Introduction

Nous savons tous les types de recommandations que nous voyons dans le commerce de détail. De plus en plus de clients attendent ce type de recommandations et les utilisent comme point de départ pour explorer d'autres options disponibles. Si vous pensez à votre propre comportement d'achat, ces recommandations fonctionnent vraiment bien. Presque tous les membres d'Adobe ont acheté un produit que nous avons vu en premier dans une recommandation, que ce soit dans une boutique ou sur une propriété numérique.

L'illustration suivante présente une recommandation qui affiche les accessoires couramment achetés avec un nouveau téléphone, y compris les stations, les cas et les casques.

![Recommandation présentant les accessoires d'autres utilisateurs achetés avec un nouveau téléphone.](/help/c-recommendations/assets/intro-1.png)

Mais ce que nous ne pensons pas toujours, c'est de savoir comment les marques numériques améliorent la barre des attentes des clients. De plus en plus, la manière dont nous consommons le média et le contenu est pilotée par des recommandations personnalisées. Réfléchissez à la première chose que vous voyez lorsque vous ouvrez Netflix, Spotify ou YouTube. Ces marques démarrent l'expérience client avec des recommandations. Dans un monde où plus d'alternatives sont disponibles, il est essentiel d'identifier le contenu le plus pertinent pour votre client au moment de l'interaction.

![Recommandation présentant les marques numériques](/help/c-recommendations/assets/intro-2.png)

Marketers use [!DNL Adobe Target] to drive personalized experiences across a wide variety of industries, customer types, and channels.

[!DNL Adobe Target] diffuse du contenu personnalisé partout.

![Illustration montrant comment Target diffuse des recommandations à divers endroits](/help/c-recommendations/assets/intro-3.png)

* **Publication**: Les éditeurs Web utilisent [!DNL Target Recommendations] pour recommander des articles aux visiteurs du site et renforcer l'engagement.
* **Didacticiels vidéo**: [!DNL Adobe Creative Cloud] permet [!DNL Target] de recommander des didacticiels vidéo aux utilisateurs Photoshop dans l'application Photoshop.
* **Jeux**: Les sociétés de Gaming utilisent [!DNL Target] pour recommander des jeux et du contenu aux utilisateurs sur leurs consoles.
* **Ventes B 2 B**: Les sociétés d'entreprise utilisent [!DNL Target] pour recommander des vidéos, des livres blancs et des publications de blog aux prospects B 2 B ; fournir des téléchargements ; et fournir une aide aux clients existants (https://theblog.adobe.com/testing-shifts-high-gear-intel).
* **Voyage**: Un organisateur de voyages allemand utilise [!DNL Target] pour recommander des hôtels et plus encore pour les voyageurs (https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).
* **Vente au détail**: Un revendeur B 2 B important est utilisé pour [!DNL Target] recommander des catégories et des produits à retour aux visiteurs dans le navigateur et dans son application mobile (https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/).

Ce n'est là que quelques-unes des façons dont les clients utilisent Target pour fournir des recommandations personnalisées.

Qu'est-ce qui apporte de grandes recommandations ?

![Illustration présentant les trois éléments qui font d'excellents recommandations](/help/c-recommendations/assets/intro-4.png)

Les recommandations importantes doivent être pertinentes et personnalisées. Cela signifie que vous avez besoin de trois éléments pour favoriser la pertinence et la personnalisation :

* **Les contrôles** du spécialiste du marketing permettent de favoriser la pertinence des éléments recommandés. En tant que spécialiste du marketing, vous avez un contexte précieux sur le tableau et vous savez quels attributs de vos produits ou contenus sont pertinents pour un modèle de recommandations à prendre en compte. Si vous exécutez un site de vidéos, vous savez que les utilisateurs peuvent vouloir visionner des vidéos du même directeur, mais sans doute se soucier de voir les films générés par le même studio. [!DNL Target] vous permet d'utiliser des commandes qui permettent d'améliorer vos algorithmes avec ce domaine.
* **Des modèles élaborés** pour obtenir des millions d'éléments dans vos catalogues et événements d'interaction. [!DNL Target] dispose de fonctionnalités d'apprentissage automatique élaborées reposant sur une décennie d'expérience et nous gérons des milliards de recommandations par an.
* **Contexte utilisateur** pour garantir que les recommandations sont opportunes et pertinentes pour vos utilisateurs. Vous ne souhaitez pas recommander la vidéo qu'une personne vient de regarder ou la chemise que quelqu'un vient d'ajouter à son panier. Le profil utilisateur enrichi de Target peut être utilisé dans les recommandations pour garantir la personnalisation.

## Implémentation des recommandations Target

Commencez par une stratégie.

![Illustration présentant la stratégie des recommandations](/help/c-recommendations/assets/intro-5.png)

* **Quels éléments recommandez-vous ?** Réfléchissez d'abord aux éléments que vous souhaitez recommander. Il peut s'agir de produits, de vidéos ou de contenu.
* **Où souhaitez-vous afficher les recommandations ?** Ensuite, réfléchissez à l'endroit où vous souhaitez créer des recommandations. Large éventail de canaux (web, mobile, en magasin, kiosque, etc.). Quelles parties du parcours client contiennent des recommandations ? Quelles pages de votre site contiennent des recommandations ?
* **Comment déterminer si les recommandations réussissent ?** Supposons que vous ayez une expérience sans recommandations et une expérience avec des recommandations, ou que vous ayez deux types de recommandations différents. Comment déterminer quelle expérience a été meilleure pour vos clients ? Certaines mesures peuvent être plus difficiles que d'autres à mesurer. Par exemple, l'impact des recommandations sur la valeur de durée de vie du client est souvent difficile à atteindre. Il est donc souvent plus facile d'obtenir une mesure abstraite moins abstraite, par exemple, les recettes par visite, la valeur de commande moyenne ou le nombre de clics. Dans certains cas, vous envisagez peut-être de minimiser une mesure, par exemple le nombre d'appels d'assistance.

After you come up with your strategy, you are ready to start the implementation of [!DNL Target Recommendations].

La création de votre implémentation des recommandations comprend trois grandes étapes :

![Illustration illustrant les étapes à suivre pour créer votre implémentation de recommandations](/help/c-recommendations/assets/intro-6.png)

1. Teach [!DNL Target] about your context or products.
1. Capturer le comportement de l'utilisateur.
1. Obtenez des recommandations avec le contexte approprié.

### Teach [!DNL Target] about your context or products

When you start with [!DNL Recommendations], you pass information about every item you want to recommend. [!DNL Target] propose plusieurs options d'intégration pour créer votre catalogue.

![Illustration expliquant comment enseigner Target au sujet de votre contexte ou de vos produits](/help/c-recommendations/assets/intro-7.png)

La méthode la plus simple et la plus fréquemment utilisée consiste à envoyer un fichier CSV quotidiennement ou hebdomadaire à partir de votre système de gestion des informations sur les produits ou de votre système de gestion de contenu. But you can also pass information on the data layer from your page using the [!DNL Adobe Target] Javascript library, leverage our APIs to pass information directly from your source system, or use our [!DNL Adobe Analytics] integration if you are already passing catalog data to [!DNL Analytics].

Il arrive que vous souhaitiez utiliser plusieurs options ensemble, par exemple en transférant la plupart des données quotidiennement par le biais d'un fichier CSV et en transmettant plus fréquemment les mises à jour d'inventaire au moyen d'une API.

Votre service informatique est généralement impliqué dans la définition de cette étape.

Quelle que soit la méthode choisie, vous devez inclure des métadonnées sur chaque élément en trois catégories :

![Illustration présentant les métadonnées de votre catalogue](/help/c-recommendations/assets/intro-8.png)

* Données que vous souhaitez afficher pour l'utilisateur qui reçoit la recommandation. Par exemple, le nom de l'animation et d'une URL de miniature.
* Données utiles pour appliquer des commandes de marketing et de marchandisage. Par exemple, la note de l'animation de sorte que vous ne recommandiez pas de séquences NC -17.
* Données utiles pour déterminer la similarité des éléments avec d'autres éléments. Par exemple, le genre du film ou les acteurs qui se trouvent dans le film.

### Capturer le comportement des utilisateurs

Next, you should add tags or leverage you existing [!DNL Analytics] implementation to track the conversion events (such as views and purchases) that drive [!DNL Target] algorithms.

![Illustration montrant comment capturer le comportement des utilisateurs](/help/c-recommendations/assets/intro-9.png)

You need to ensure that [!DNL Target] is aware of the items that your users are viewing and purchasing. Si l'achat n'est pas adapté à votre contexte, vous pouvez effectuer un suivi sur un autre type d'événement de conversion, par exemple le téléchargement d'un PDF, l'exécution d'une enquête, l'abonnement à un bulletin d'information, l'affichage d'une vidéo, etc.

If you are already using [!DNL Target] to run A/B Tests activities on your site, you might have already completed this step. Or if you are already using [!DNL Adobe Analytics] to report on site visits and conversion behavior, you can use [!DNL Analytics] as your behavioral datasource. If not, it’s easiest to set this up using a tag manager such as [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). It’s also possible to send offline or in-app interactions to [!DNL Target] via real-time API.

### Obtenir des recommandations avec le contexte approprié

Pass information about the user and context at the point of interaction to [!DNL Target] to return relevant and personalized recommendations.

![Illustration montrant comment obtenir des recommandations avec le contexte approprié](/help/c-recommendations/assets/intro-10.png)

Besides user behavior in aggregate, you need to pass [!DNL Target] the specific context where recommendations are being shown. Ceci inclut les informations sur la page et les informations du profil utilisateur. [!DNL Target] utilise ces informations pour fournir des recommandations personnalisées. Par exemple, sur un site Web de vente au détail, vous souhaitez connaître la catégorie produit et produit que le visiteur est en train de consulter. Vous souhaitez également connaître les informations relatives à cet utilisateur (marque préférée, catégorie de produit préférée, niveau de fidélité, etc.). This information is important so that [!DNL Target] can filter items and improve the personalization of recommendations.

## Créer votre première activité de recommandations

What is a [!DNL Recommendations] activity?

![Illustration montrant les parties qui font une bonne activité de recommandations](/help/c-recommendations/assets/intro-11.png)

A [!DNL Recommendations] activity is made up of the following components:

* **Public**: Qui doit voir ces recommandations ?
* **Critères**: Quels éléments doivent être recommandés ?
* **Conception**: Comment les articles recommandés doivent-ils être affichés ?

![Illustration montrant ce qui constitue une activité de recommandations : Audiences, critères et conceptions](/help/c-recommendations/assets/intro-12.png)

[!DNL Target] Comprend 14 audiences intégrées, 42 critères intégrés et 10 modèles de conception intégrés. Vous pouvez personnaliser chacun de ces éléments ou ajouter vos propres éléments. We’ve had previous [webinars about building audiences](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. Cette section se concentre sur la définition des critères qui définissent les éléments de witch recommandés.

Target utilise le concept de carte de critères. Une carte de critères est une recette de personnalisation.

![Illustration de carte de critères](/help/c-recommendations/assets/intro-13.png)

Il est important de choisir ou de créer les critères appropriés pour obtenir les résultats de la personnalisation souhaités. Un critère est un entonnoir qui conduit votre catalogue entier à votre jeu final de recommandations.

![Illustration Entonnoir](/help/c-recommendations/assets/intro-14.png)

The following sections describe the various parts of this funnel and how they work in [!DNL Target]:

### Filtres statiques (collections et exclusions)

Les filtres statiques sont des règles largement applicables liées aux attributs de catalogue que vous ne prévoyez pas de modifier fréquemment.

![Illustration Collections et exclusions](/help/c-recommendations/assets/intro-16.png)

Par exemple, dans un contexte de contenu, vous souhaitez peut-être inclure toutes les vidéos dans les recommandations, mais exclure les séquences NC -17 notées. Dans un contexte de vente au détail, vous pouvez avoir plusieurs marques dans différentes régions du monde, mais vous ne souhaitez recommander que les produits disponibles aux États-Unis. Vous pouvez également exclure les produits d'une étiquette privée régionale.

Il s'agit d'attributs de catalogue largement applicables que vous pouvez utiliser dans plusieurs recommandations et que vous ne prévoyez pas de les modifier fréquemment.

### Algorithme (clé de recommandation et logique)

L'étape suivante consiste à choisir une clé et une logique de recommandation. C'est là que vous déterminez la base de votre recommandation.

![Illustration d'algorithme](/help/c-recommendations/assets/intro-17.png)

La première chose que vous devez choisir est la clé de recommandation. La clé de recommandation est ce que vous recherchez pour choisir la recommandation. C'est à cela que vous basez votre recommandation.

Vous pouvez baser votre recommandation sur :

* L'élément consulté par le visiteur
* Catégorie actuellement consultée par le visiteur
* L'article que le visiteur a acheté en dernier ou ajouté au panier
* Attribut personnalisé lié à un visiteur ou à un élément

En fonction de ces clés, vous choisissez ensuite la logique de recommandation :

* Articles avec des attributs similaires
* Les articles les plus consultés d'une catégorie spécifique
* Les clients qui ont acheté cet article ont également acheté ces éléments
* Attribut personnalisé

Out of the box, [!DNL Target] includes a portfolio of algorithms.

![Portefeuille d'algorithmes](/help/c-recommendations/assets/intro-15.png)

* **Les algorithmes basés sur la popularité** incluent les articles Les plus consultés et les Meilleurs vendeurs.
* **Les algorithmes basés sur le contenu** incluent la similarité de contenu.
* **Les algorithmes de filtrage collaboratif basés sur un élément** sont Affichés/Affichés, Affichés/Achetés et Achetés/Achetés. Notez que « acheté » peut être n'importe quelle conversion.
* **Les algorithmes personnalisés** sont les suivants : Récemment affichés, Affinité du site et Filtrage collaboratif amélioré du profil.
* **Les algorithmes de votre choix** vous permettent d'utiliser vos propres algorithmes personnalisés.

### Règles de fonctionnement en ligne

La dernière étape consiste à appliquer des règles métier en ligne. C'est là que vous définissez vos algorithmes avec les connaissances de domaine et le contexte actuel en fonction de ce que le visiteur fait sur votre propriété numérique.

![Illustration des règles de commerce en ligne](/help/c-recommendations/assets/intro-18.png)

Par exemple, dans le contexte du contenu, vous pouvez exclure les films que le visiteur a précédemment regardés, recommander des films par le même directeur ou amplifier des films dans le même genre. Dans le contexte de vente au détail, vous souhaitez peut-être exclure les produits en rupture de stock, afficher les éléments d'une plage de prix comprise entre 5 et 500 $ ou augmenter les éléments de la même marque.

## Démonstration

Une fois les tâches illustrées dans l'entonnoir de recommandation décrites ci-dessus, vous laissez votre recommandation finale. To watch an in-product demonstration inside [!DNL Target], the demo begins at 21:00 in the *Adobe Target Basics Webinar*, linked to below.

## Webinaire sur les bases d’Adobe Target : Introduction à Recommendations {#intro-to-recs}

[Présentation des recommandations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)