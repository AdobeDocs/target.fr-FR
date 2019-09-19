---
description: Présentation des activités de Target Recommendations qui affichent automatiquement les produits ou le contenu susceptibles d’intéresser vos clients en fonction de l’activité précédente de l’utilisateur ou d’autres algorithmes. Les recommandations aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.
keywords: Recommandations;intro;introduction;webinar;démo
seo-description: Présentation des activités de recommandations d’Adobe Target qui affichent automatiquement les produits ou le contenu susceptibles d’intéresser vos clients en fonction des activités passées des utilisateurs ou d’autres algorithmes. Les recommandations aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.
seo-title: Présentation des activités de recommandations dans Adobe Target
solution: Target
title: Présentation des recommandations
title-outputclass: Premium
topic: Premium
badge: Premium
translation-type: tm+mt
source-git-commit: 516433edd366fad5950c99d748aa7f6f718dd5fd

---


# ![PREMIUM](/help/assets/premium.png) Introduction aux recommandations

Le texte de cet article provient du webinaire *Introduction aux recommandations* , que vous pouvez consulter dans son intégralité ci-dessous.

Le webinaire *Introduction à Recommendations* comprend une exploration en profondeur de la manière de tirer parti de la valeur de [!DNL Adobe Target Recommendations]. Découvrez comment cette activité [!DNL Target] affiche automatiquement les produits ou le contenu susceptibles d’intéresser vos clients en optimisant les suggestions en temps réel basées sur les visites précédentes. Vous pouvez ensuite approfondir l’analyse de l’interface utilisateur de [!DNL Target] pour une présentation détaillée de la création d’une activité [!DNL Recommendations].

## Introduction

Nous connaissons tous les types de recommandations que nous voyons dans la vente au détail. Les clients s’attendent de plus en plus à ce type de recommandations et les utilisent comme point de départ pour explorer d’autres options disponibles. Si vous pensez à votre propre comportement d'achat, ce genre de recommandations fonctionne vraiment bien. Presque tout le monde parmi nous a acheté un produit que nous avons vu en premier dans une recommandation quelque part, que ce soit dans un magasin ou sur une propriété numérique.

L’illustration suivante présente une recommandation qui affiche les accessoires couramment achetés avec un nouveau téléphone, y compris les postes de charge, les boîtiers et les écouteurs.

![Recommandation montrant les accessoires que d'autres ont achetés avec un nouveau téléphone.](/help/c-recommendations/assets/intro-1.png)

Mais ce à quoi nous ne pensons pas toujours, c’est à quel point les premières marques numériques accroissent les attentes des clients. De plus en plus, la façon dont nous consommons les médias et le contenu est motivée par des recommandations personnalisées. Pensez à la première chose que vous voyez quand vous ouvrez Netflix, Spotify ou YouTube. Ces marques démarrent l’expérience client avec des recommandations. Dans un monde où il existe plus d'alternatives que jamais, il est essentiel que vous puissiez identifier le contenu le plus pertinent pour votre client au moment de l'interaction.

![Recommandation présentant les premières marques numériques](/help/c-recommendations/assets/intro-2.png)

Les marketeurs utilisent [!DNL Adobe Target] pour piloter des expériences personnalisées dans un large éventail de secteurs, de types de clients et de canaux.

[!DNL Adobe Target] fournit du contenu personnalisé partout.

![Illustration montrant comment Target émet des recommandations à différents endroits](/help/c-recommendations/assets/intro-3.png)

* **Publication**: Les éditeurs Web recommandent [!DNL Target Recommendations] des articles aux visiteurs du site et suscitent un intérêt accru.
* **Didacticiels** vidéo : [!DNL Adobe Creative Cloud] utilise [!DNL Target] pour recommander des didacticiels vidéo aux utilisateurs de Photoshop dans l’application Photoshop.
* **Jeu**: Les sociétés de jeux utilisent [!DNL Target] pour recommander des jeux et du contenu aux utilisateurs sur leurs consoles.
* **Ventes** B2B : Les sociétés [d’entreprise à entreprise utilisent Target pour recommander des vidéos, des livres blancs et des publications de blog aux prospects B2B ; diffuser des téléchargements ; et fournir de l’aide aux clients](https://theblog.adobe.com/testing-shifts-high-gear-intel)existants.

* **Voyage**: [Un voyageur allemand utilise Target pour recommander des hôtels et plus aux voyageurs](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Vente au détail**: [Un détaillant B2B de premier plan utilise Target pour recommander des catégories et des produits de premier plan pour renvoyer des visiteurs dans le navigateur et dans son application](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)mobile.

Il ne s’agit que de quelques exemples d’utilisation de Target par les clients pour la diffusion de recommandations personnalisées.

Qu'est-ce qui fait de grandes recommandations ?

![Illustration montrant les trois éléments qui font de superbes recommandations](/help/c-recommendations/assets/intro-4.png)

Les grandes recommandations doivent être pertinentes et personnalisées. Cela signifie que vous avez besoin de trois éléments pour stimuler la pertinence et la personnalisation :

* **Les contrôles** du spécialiste du marketing permettent de déterminer la pertinence des éléments recommandés. En tant que spécialiste du marketing, vous apportez un contexte précieux au tableau et vous savez quels attributs de vos produits ou contenus sont pertinents pour un modèle de recommandations à prendre en compte. Si vous dirigez un site de vidéos, vous savez que les utilisateurs peuvent être intéressés par la vue de films du même réalisateur, mais ils ne se soucient probablement pas de voir des films qui ont été produits par le même studio. [!DNL Target] vous permet d’utiliser des contrôles qui vous permettent d’améliorer vos algorithmes grâce à ces connaissances de domaine.
* **Des modèles** sophistiqués pour donner un sens à des millions d’éléments dans votre catalogue et des événements d’interaction. [!DNL Target] possède des capacités d'apprentissage automatique sophistiquées, qui s'appuient sur plus d'une décennie d'expérience et nous gérons des milliards de recommandations par année.
* **Contexte** utilisateur afin de vous assurer que les recommandations sont pertinentes et opportunes pour vos utilisateurs. Vous ne souhaitez pas recommander la vidéo que quelqu’un vient de regarder ou la chemise que quelqu’un vient d’ajouter à son panier. Le profil utilisateur enrichi de Target peut être utilisé dans les recommandations pour garantir la personnalisation.

## Mise en oeuvre des recommandations Target

Commencez par une stratégie.

![Illustration présentant la stratégie des recommandations](/help/c-recommendations/assets/intro-5.png)

* **Quels éléments voulez-vous recommander ?** Tout d'abord, pensez aux éléments que vous souhaitez recommander. Il peut s’agir de produits, de vidéos ou de contenu.
* **Où voulez-vous afficher les recommandations ?** Ensuite, réfléchissez à l'endroit où vous voulez faire des recommandations. Développez les canaux (Web, mobile, en magasin, kiosque, etc.). Quelles parties du parcours du client contiennent des recommandations ? Quelles pages de votre site contiennent des recommandations ?
* **Comment déterminerez-vous si les recommandations sont efficaces ?** Supposons que vous ayez une expérience sans recommandations et une expérience avec des recommandations, ou que vous ayez deux types de recommandations différents. Comment détermineriez-vous quelle expérience est la meilleure pour vos clients ? Certaines mesures peuvent être plus difficiles à mesurer que d’autres. Par exemple, l’impact des recommandations sur la valeur de durée de vie du client est souvent difficile à obtenir directement. Il est donc souvent plus facile d’obtenir une mesure moins abstraite et plus concrète, par exemple, les recettes par visite, la valeur de commande moyenne ou le nombre de clics. Dans certains cas, vous pouvez réduire une mesure, par exemple, le nombre d’appels d’assistance.

Une fois votre stratégie élaborée, vous êtes prêt à commencer la mise en oeuvre de [!DNL Target Recommendations].

La création de votre mise en oeuvre de recommandations comprend trois étapes générales :

![Illustration montrant les étapes de création de votre implémentation de recommandations](/help/c-recommendations/assets/intro-6.png)

1. Apprenez [!DNL Target] à connaître votre contexte ou vos produits.
1. Capturer le comportement de l’utilisateur.
1. Obtenez des recommandations avec le contexte approprié.

### Enseigner [!DNL Target] votre contexte ou vos produits

Lorsque vous commencez par [!DNL Recommendations], vous transmettez des informations sur chaque élément que vous souhaitez recommander. [!DNL Target] offre plusieurs options d’intégration pour créer votre catalogue.

![Illustration montrant comment expliquer à Target votre contexte ou vos produits](/help/c-recommendations/assets/intro-7.png)

La méthode la plus simple et la plus fréquemment utilisée consiste à envoyer un fichier CSV chaque jour ou chaque semaine depuis votre système de gestion des informations sur les produits ou votre système de gestion de contenu. Mais vous pouvez également transmettre des informations sur la couche de données à partir de votre page à l’aide de la bibliothèque [!DNL Adobe Target] JavaScript, utiliser nos API pour transmettre des informations directement depuis votre système source ou utiliser notre [!DNL Adobe Analytics] intégration si vous transmettez déjà des données de catalogue à [!DNL Analytics].

Il peut arriver que vous souhaitiez utiliser plusieurs options ensemble, par exemple, transmettre la plupart des données quotidiennement par le biais d’un fichier CSV et transmettre les mises à jour de stock plus fréquemment par le biais d’une API.

Votre service informatique sera généralement impliqué dans la mise en place de cette étape.

Quelle que soit la méthode choisie, vous devez inclure des métadonnées sur chaque élément dans trois catégories :

![Illustration montrant les informations de métadonnées pour votre catalogue](/help/c-recommendations/assets/intro-8.png)

* Données à afficher à l’utilisateur qui reçoit la recommandation. Par exemple, le nom du film et l’URL d’une image miniature.
* Données utiles pour l’application de contrôles marketing et de marchandisage. Par exemple, l’évaluation du film afin de ne pas recommander les films NC-17.
* Données utiles pour déterminer la similarité des éléments avec d’autres éléments. Par exemple, le genre du film ou les acteurs présents dans le film.

### Capturer le comportement de l’utilisateur

Vous devez ensuite ajouter des balises ou tirer parti de votre [!DNL Analytics] implémentation existante pour effectuer le suivi des événements de conversion (tels que les vues et les achats) qui pilotent [!DNL Target] les algorithmes.

![Illustration montrant comment capturer le comportement des utilisateurs](/help/c-recommendations/assets/intro-9.png)

Vous devez vous assurer que [!DNL Target] vous connaissez bien les éléments que vos utilisateurs consultent et achètent. Si les achats ne sont pas pertinents dans votre contexte, vous pouvez effectuer le suivi d’un autre type d’événement de conversion, par exemple télécharger un fichier PDF, répondre à une enquête, vous abonner à un bulletin d’information, regarder une vidéo, etc.

Si vous utilisez déjà [!DNL Target] pour exécuter des activités de tests A/B sur votre site, vous avez peut-être déjà terminé cette étape. Ou si vous utilisez déjà [!DNL Adobe Analytics] pour créer des rapports sur les visites sur le site et le comportement de conversion, vous pouvez [!DNL Analytics] les utiliser comme source de données comportementales. Dans le cas contraire, il est plus facile de le configurer à l’aide d’un gestionnaire de balises tel qu’ [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Il est également possible d’envoyer des interactions hors ligne ou in-app à [!DNL Target] l’aide d’une API en temps réel.

### Obtenir des recommandations avec le contexte approprié

Transmettez des informations sur l’utilisateur et le contexte au point d’interaction pour [!DNL Target] renvoyer des recommandations pertinentes et personnalisées.

![Illustration montrant comment obtenir des recommandations avec le contexte approprié](/help/c-recommendations/assets/intro-10.png)

Outre le comportement des utilisateurs dans l’agrégat, vous devez transmettre [!DNL Target] le contexte spécifique dans lequel les recommandations sont affichées. Cela inclut des informations sur la page et des informations provenant du profil utilisateur. [!DNL Target] utilise ces informations pour faire des recommandations personnalisées. Par exemple, sur un site Web de vente au détail, vous souhaitez connaître le produit et la catégorie de produits actuellement affichés par le visiteur. Vous souhaitez également obtenir des informations sur cet utilisateur (marque favorite, catégorie de produits préférée, niveau de fidélité, etc.). Ces informations sont importantes pour [!DNL Target] pouvoir filtrer les éléments et améliorer la personnalisation des recommandations.

## Créer votre première activité de recommandations

Qu'est-ce qu'une [!DNL Recommendations] activité ?

![Illustration montrant les parties qui font une bonne activité de recommandations](/help/c-recommendations/assets/intro-11.png)

Une [!DNL Recommendations] activité est composée des composants suivants :

* **Public**: Qui devrait voir ces recommandations ?
* **Critères**: Quels éléments doivent être recommandés ?
* **Conception**: Comment afficher les éléments recommandés ?

![Illustration montrant ce qui constitue une activité de recommandations : Audiences, critères et conceptions](/help/c-recommendations/assets/intro-12.png)

Offre immédiate, [!DNL Target] 14 audiences intégrées, 42 critères intégrés et 10 modèles de conception intégrés. Vous pouvez personnaliser chacun de ces éléments ou ajouter les vôtres. Nous avons déjà eu des [webinaires sur la création d’audiences](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) dans [!DNL Target]. Cette section se concentre sur la définition des critères, qui définissent les éléments à recommander.

Target utilise le concept de la carte de critères. Une carte de critères est comme une recette de personnalisation.

![Illustration de la carte de critères](/help/c-recommendations/assets/intro-13.png)

Il est important de choisir ou de créer les critères appropriés pour obtenir les résultats de la personnalisation désirée. Un critère est comme un entonnoir qui vous emmène de l’ensemble de votre catalogue à votre ensemble final de recommandations.

![Illustration de l'entonnoir](/help/c-recommendations/assets/intro-14.png)

Les sections suivantes décrivent les différentes parties de cet entonnoir et leur fonctionnement [!DNL Target]:

### Filtres statiques (collections et exclusions)

Les filtres statiques sont des règles largement applicables liées aux attributs de catalogue que vous ne prévoyez pas de modifier fréquemment.

![Illustration Collections et exclusions](/help/c-recommendations/assets/intro-16.png)

Par exemple, dans un contexte de contenu, vous pouvez inclure tous les films dans les recommandations, mais exclure les films classés NC-17. Dans un contexte de vente au détail, vous pouvez avoir plusieurs marques dans différentes parties du monde, mais vous souhaitez recommander uniquement les produits disponibles aux États-Unis. Vous pouvez également exclure des produits d’une étiquette privée régionale.

Il s’agit de tous les attributs de catalogue largement applicables que vous pouvez utiliser dans plusieurs recommandations et que vous ne vous attendez pas à ce qu’ils changent fréquemment.

### Algorithme (clé de recommandation et logique)

L’étape suivante consiste à choisir une clé de recommandation et une logique. C’est là que vous décidez de la base de votre recommandation.

![Illustration de l’algorithme](/help/c-recommendations/assets/intro-17.png)

La première chose que vous devez choisir est la clé de recommandation. La clé de recommandation est ce que vous recherchez pour choisir la recommandation. C'est ce sur quoi vous basez votre recommandation.

Vous pouvez baser votre recommandation sur :

* Élément actuellement consulté par le visiteur
* Catégorie actuellement affichée par le visiteur
* Article que le visiteur a acheté ou ajouté pour la dernière fois au panier
* Attribut personnalisé associé à un visiteur ou à un élément

En fonction de ces clés, vous choisissez ensuite la logique de recommandation souhaitée :

* Articles avec des attributs similaires
* Éléments les plus consultés dans une catégorie particulière
* Les clients qui ont acheté cet article ont également acheté ces articles
* Un attribut personnalisé

Inclut [!DNL Target] un portefeuille d’algorithmes prêts à l’emploi.

![Portefeuille d’algorithmes, illustration](/help/c-recommendations/assets/intro-15.png)

* **Les algorithmes** basés sur la popularité incluent Les plus consultés et Les meilleurs vendeurs.
* **Les algorithmes** basés sur le contenu incluent la similarité de contenu.
* **Les algorithmes** de filtrage collaboratif basé sur les éléments incluent Visionné/Consulté, Visionné/Acheté et Acheté/Acheté. Notez que "buy" peut être n’importe quelle conversion.
* **Les algorithmes** personnalisés incluent les algorithmes Récemment consultés, Affinité du site et filtrage collaboratif amélioré du profil.
* **Apportez vos propres algorithmes** pour utiliser vos propres algorithmes personnalisés.

### Règles de fonctionnement en ligne

La dernière étape consiste à appliquer des règles de fonctionnement en ligne. C’est là que vous responsabilisez vos algorithmes avec les connaissances de domaine et le contexte actuel en fonction de ce que le visiteur fait sur votre propriété numérique.

![Illustration des règles de commerce en ligne](/help/c-recommendations/assets/intro-18.png)

Par exemple, dans le contexte du contenu, vous pouvez exclure les films que le visiteur a précédemment visionnés, recommander des films du même réalisateur ou stimuler des films du même genre. Dans le contexte de la vente au détail, vous pouvez exclure les produits en rupture de stock, afficher les articles dans une plage de prix comprise entre 5 et 500 euros ou dynamiser les articles de la même marque.

## Démonstration

Une fois les tâches illustrées dans l'entonnoir de recommandation décrit ci-dessus terminées, vous restez avec votre recommandation finale. Pour visionner une démonstration intégrée au produit [!DNL Target], la démonstration commence à 21h00 dans le webinaire *de base d’* Adobe Target, lié à la section ci-dessous.

## Webinaire sur les bases d’Adobe Target : Introduction à Recommendations {#intro-to-recs}

[Présentation des recommandations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)