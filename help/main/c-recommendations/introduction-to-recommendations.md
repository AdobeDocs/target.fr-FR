---
keywords: recommandations;intro;introduction;webinaire;démo
description: Découvrez les activités Recommendations dans Adobe  [!DNL Target] . Celles-ci affichent automatiquement le contenu susceptible d’intéresser vos clients selon l’activité précédente de l’utilisateur ou d’autres algorithmes.
title: Que sont les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '2113'
ht-degree: 91%

---

# Présentation des recommandations

Le texte de cet article provient du webinaire *Présentation de Recommendations*, que vous pouvez visualiser intégralement ci-dessous.

Le webinaire *Présentation de Recommendations* comprend une exploration en profondeur de la manière de tirer parti de la valeur de [!DNL Adobe Target Recommendations]. Découvrez comment cette activité [!DNL Target] affiche automatiquement les produits ou le contenu susceptibles d’intéresser vos clients en optimisant les suggestions en temps réel basées sur les visites précédentes. Vous pouvez ensuite approfondir l’analyse de l’interface utilisateur de [!DNL Target] pour une présentation détaillée de la création d’une activité [!DNL Recommendations].

## Introduction

Nous connaissons tous les types de recommandations que nous rencontrons dans le commerce de détail. Les clients attendent de plus en plus ces types de recommandations et les utilisent pour explorer d’autres solutions possibles. Si vous pensez à votre propre comportement d’achat, vous savez que ces recommandations fonctionnent bien. Nous avons presque tous acheté un produit que nous avons d’abord vu dans une recommandation, que ce soit dans un magasin ou sur une propriété numérique.

L’illustration suivante montre une recommandation qui affiche les accessoires qui sont couramment achetés avec un nouveau téléphone, notamment les stations, les coques et les casques.

![Recommandation montrant les accessoires achetés par d’autres visiteurs avec un nouveau téléphone.](/help/main/c-recommendations/assets/intro-1.png)

Mais ce à quoi nous ne pensons pas toujours, c&#39;est comment les marques numériques augmentent la barre des attentes des clients. Nous nous fions de plus en plus aux recommandations personnalisées pour consommer des médias et du contenu. Que voyez-vous en premier lorsque vous accédez à Netflix, Spotify ou YouTube ? Ces marques commencent l’expérience client avec des recommandations. Dans un monde où plus d’alternatives sont disponibles que jamais, il est essentiel que vous puissiez identifier le contenu le plus pertinent pour votre client au moment de l’interaction.

![Recommandation montrant des marques numériques](/help/main/c-recommendations/assets/intro-2.png)

Les marketeurs utilisent [!DNL Adobe Target] pour proposer des expériences personnalisées dans divers secteurs et canaux et pour différents types de clients.

[!DNL Adobe Target] diffuse partout du contenu personnalisé.

![Illustration montrant comment Target diffuse des recommandations à divers emplacements](/help/main/c-recommendations/assets/intro-3.png)

* **Publication** : les éditeurs web utilisent [!DNL Target Recommendations] pour recommander des articles aux visiteurs du site et augmenter l’engagement.
* **Tutoriels vidéo** : [!DNL Adobe Creative Cloud] utilise [!DNL Target] pour recommander des tutoriels vidéo aux utilisateurs de Photoshop dans l’application Photoshop.
* **Jeux** : les éditeurs de jeux utilisent [!DNL Target] pour recommander sur leurs consoles des jeux et du contenu aux utilisateurs.
* **Ventes B2B** : [les entreprises B2B utilisent Target pour recommander des vidéos, des articles techniques et des publications de blog aux prospects B2B, proposer des téléchargements et offrir une aide aux clients existants](https://theblog.adobe.com/testing-shifts-high-gear-intel).

* **Tourisme** : [une agence de voyages allemande utilise Target pour recommander des hôtels et d’autres services aux voyageurs](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Vente au détail** : [un détaillant B2B important utilise Target pour recommander des catégories et des produits aux visiteurs récurrents dans le navigateur et son application mobile](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/).

Ce ne sont que quelques exemples de la façon dont les clients utilisent Target pour proposer des recommandations personnalisées.

Quels éléments permettent de créer des recommandations de grande qualité ?

![Illustration montrant les trois éléments permettant de créer des recommandations de grande qualité](/help/main/c-recommendations/assets/intro-4.png)

Des recommandations de grande qualité doivent être pertinentes et personnalisées. Vous avez donc besoin de trois éléments pour obtenir la pertinence et la personnalisation :

* Les **contrôles marketeur** pour favoriser la pertinence des articles recommandés. En tant que marketeur, vous apportez vos connaissances précieuses en matière de contexte et vous savez quels attributs des produits ou contenus sont pertinents pour un modèle de recommandations. Si vous gérez un site de vidéos, vous savez que les utilisateurs pourraient être intéressés de voir des films du même réalisateur, mais probablement ne se soucient pas de voir des films produits par le même studio. [!DNL Target] vous propose des contrôles qui permettent d’améliorer vos algorithmes avec ces connaissances de domaine.
* Des **modèles élaborés** pour comprendre des millions d’articles dans vos catalogues et événements d’interaction. [!DNL Target] dispose de capacités d’apprentissage machine élaborées reposant sur une dizaine d’années d’expérience. De plus, Adobe gère des milliards de recommandations par an.
* Un **contexte utilisateur** pour être sûr que les recommandations sont opportunes et pertinentes pour vos utilisateurs. Vous ne voulez pas recommander la vidéo que quelqu&#39;un vient de regarder ou la chemise que quelqu&#39;un vient d&#39;ajouter à son panier. Le profil utilisateur riche de Target peut être utilisé dans les recommandations pour garantir la personnalisation.

## Implémentation de [!DNL Target] Recommendations

Commencez par une stratégie.

![Illustration montrant la stratégie de recommandations](/help/main/c-recommendations/assets/intro-5.png)

* **Quels éléments voulez-vous recommander ?** Réfléchissez d’abord aux éléments que vous souhaitez recommander. Il peut s’agir de produits, de films ou de contenu.
* **Où souhaitez-vous afficher les recommandations ?** Réfléchissez ensuite à l’emplacement où vous souhaitez effectuer des recommandations. Il s’agit en fait des canaux (web, mobile, en magasin, kiosque, etc.). Quelles parties du parcours client contiendront des recommandations ? Quelles pages de votre site contiendront des recommandations ?
* **Comment allez-vous déterminer les performances des recommandations ?** Supposons que vous ayez une expérience sans recommandations et une autre avec recommandations ou qu’il existe deux types de recommandations différents. Comment allez-vous déterminer la meilleure expérience pour vos clients ? Certaines mesures peuvent être plus difficiles que d’autres à obtenir. Par exemple, l’impact des recommandations sur la valeur de la durée de vie du client est souvent difficile à connaître. Il est donc souvent plus facile d’obtenir une mesure moins abstraite, par exemple, les recettes par visite, la valeur de commande moyenne ou le nombre de clics. Dans certains cas, vous rechercherez peut-être à minimiser une mesure, comme le nombre d’appels au service d’assistance.

Une fois votre stratégie définie, vous pouvez commencer l’implémentation de [!DNL Target Recommendations].

La création de votre implémentation de recommandations comprend trois grandes étapes :

![Illustration montrant les étapes pour créer votre implémentation de recommandations](/help/main/c-recommendations/assets/intro-6.png)

1. Apprendre votre contexte et vos produits à [!DNL Target].
1. Capturer le comportement des utilisateurs.
1. Obtenir des recommandations avec le contexte approprié.

### Apprendre votre contexte et vos produits à [!DNL Target]

Lorsque vous commencez à utiliser [!DNL Recommendations], vous transmettez des informations sur chaque article à recommander. [!DNL Target] propose plusieurs options d’intégration pour créer votre catalogue.

![Illustration montrant comment apprendre votre contexte et vos produits à Target ](/help/main/c-recommendations/assets/intro-7.png)

La méthode la plus simple et la plus souvent utilisée consiste à envoyer un fichier CSV tous les jours ou toutes les semaines depuis votre système de gestion des informations sur les produits ou de votre système de gestion de contenu. Vous pouvez également transmettre des informations sur la couche de données depuis votre page à l’aide de la bibliothèque JavaScript [!DNL Adobe Target], utiliser nos API pour transmettre des informations directement depuis votre système source ou tirer parti de notre intégration [!DNL Adobe Analytics] si vous transmettez déjà des données de catalogue à [!DNL Analytics].

Il se peut parfois que vous souhaitiez combiner plusieurs solutions, en transmettant par exemple la plupart des données quotidiennement par le biais d’un fichier CSV et en transférant plus souvent les mises à jour d’inventaire via une API.

Votre service informatique interviendra généralement pour configurer cette étape.

Quelle que soit la méthode choisie, vous devez inclure des métadonnées sur chaque élément dans trois catégories :

![Illustration montrant des informations de métadonnées pour votre catalogue](/help/main/c-recommendations/assets/intro-8.png)

* Données que vous souhaitez afficher pour l’utilisateur recevant la recommandation (le nom du film et une URL d’image miniature, par exemple).
* Données qui s’avèrent utiles pour appliquer des contrôles marketing et de marchandisage (classement du film pour ne pas recommander des films interdits au moins de 16 ans, par exemple).
* Données s’avérant utiles pour déterminer la similarité d’un article avec d’autres articles (le genre du film ou les acteurs qui jouent dans le film, par exemple).

### Capture du comportement des utilisateurs

Vous devez ensuite ajouter des balises ou utiliser l’implémentation de [!DNL Analytics] existante pour suivre les événements de conversion (tels que les vues et les achats) qui pilotent les algorithmes [!DNL Target].

![Illustration montrant comment capturer le comportement des utilisateurs](/help/main/c-recommendations/assets/intro-9.png)

Vous devez veiller à ce que [!DNL Target] connaisse les articles que vos utilisateurs consultent et achètent. Si les achats ne sont pas pertinents pour votre contexte, vous pouvez effectuer le suivi d’un autre type d’événement de conversion, par exemple, le téléchargement d’un PDF, la réalisation d’une enquête, l’abonnement à une newsletter, le visionnage d’une vidéo, etc.

Si vous utilisez déjà [!DNL Target] pour exécuter des activités de test A/B sur votre site, vous avez peut-être déjà effectué cette étape. Si vous utilisez déjà [!DNL Adobe Analytics] pour signaler les visites sur le site et le comportement de conversion, vous pouvez employer [!DNL Analytics] comme source de données comportementales. Si ce n’est pas le cas, il est plus facile de configurer cette configuration à l’aide d’un gestionnaire de balises tel que des balises dans [[!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}. Il est également possible d’envoyer des interactions hors ligne ou in-app à [!DNL Target] via l’API en temps réel.

### Obtention de recommandations avec le contexte approprié

Transmettez des informations sur l’utilisateur et le contexte au moment de l’interaction à [!DNL Target] pour renvoyer des recommandations pertinentes et personnalisées.

![Illustration montrant comment obtenir des recommandations avec le contexte approprié](/help/main/c-recommendations/assets/intro-10.png)

Outre le comportement de utilisateur dans une forme agrégée, vous devez transmettre à [!DNL Target] le contexte spécifique où les recommandations sont affichées, notamment des informations sur la page et provenant du profil utilisateur. [!DNL Target] utilise ces informations pour effectuer des recommandations personnalisées. Par exemple, sur un site web de vente au détail, vous souhaitez connaître le produit et la catégorie de produits que le visiteur est en train de consulter. Vous souhaitez également obtenir des informations sur l’utilisateur (marque préférée, catégorie de produits préférée, niveau de fidélité, etc.). Ces informations sont importantes ; elles permettent à [!DNL Target] de filtrer les éléments et d’améliorer la personnalisation des recommandations.

## Création de votre première activité Recommendations

Qu’est-ce qu’une activité de [!DNL Recommendations] ?

![Illustration montrant les éléments qui constituent une bonne activité Recommendations](/help/main/c-recommendations/assets/intro-11.png)

Une activité de [!DNL Recommendations] est constituée des composants suivants :

* **Audience** : qui doit voir ces recommandations ?
* **Critères** : quels éléments doivent être recommandés ?
* **Conception** : comment les articles recommandés doivent-ils être affichés ?

![Illustration montrant les éléments qui constituent une activité Recommendations : audiences, critères et conceptions](/help/main/c-recommendations/assets/intro-12.png)

[!DNL Target] comprend 14 audiences, 42 critères et 10 modèles de conception intégrés, prêts à l’emploi. Vous pouvez personnaliser chaque élément ou ajouter les vôtres. Nous avons déjà eu [webinaires sur la création d’audiences](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. Cette section est axée sur la définition des critères qui définissent les éléments recommandés.

Target utilise le concept de carte de critères. Une carte de critères peut être comparée à une recette pour la personnalisation.

![Illustration d’une carte de critères](/help/main/c-recommendations/assets/intro-13.png)

Il est important de choisir ou de créer les critères appropriés pour obtenir les résultats souhaités en ce qui concerne la personnalisation. Un critère est comme un entonnoir qui vous mène de votre catalogue entier à votre ensemble final de recommandations.

![Illustration d’un entonnoir](/help/main/c-recommendations/assets/intro-14.png)

Les sections suivantes décrivent les différentes parties de cet entonnoir et leur fonctionnement dans [!DNL Target] :

### Filtres statiques (collections et exclusions)

Les filtres statiques sont des règles largement applicables liées aux attributs de catalogue que vous ne prévoyez pas de changer souvent.

![Illustration de collections et d’exclusions](/help/main/c-recommendations/assets/intro-16.png)

Par exemple, dans un contexte de contenu, vous souhaiterez peut-être inclure tous les films dans les recommandations, mais exclure les ceux classés NC-17 aux États-Unis. Dans un contexte de vente au détail, vous pouvez avoir plusieurs marques dans différentes zones géographiques, mais ne vouloir recommander que les produits disponibles aux États-Unis. Vous pourriez également vouloir exclure les produits d’un label privé régional.

Il s’agit d’attributs de catalogue largement applicables que vous souhaitez peut-être utiliser dans plusieurs recommandations et que vous ne prévoyez pas de modifier souvent.

### Algorithme (clé et logique de recommandation)

L’étape suivante consiste à choisir une clé et une logique de recommandation. C’est durant cette étape que vous déterminez la base de votre recommandation.

![Illustration d’algorithme](/help/main/c-recommendations/assets/intro-17.png)

Vous devez choisir en premier lieu la clé de recommandation. La clé de recommandation correspond à ce que vous recherchez pour choisir la recommandation. C’est sur quoi vous basez votre recommandation.

Vous pouvez baser votre recommandation sur :

* l’article actuellement consulté par le visiteur ;
* la catégorie actuellement consultée par le visiteur ;
* le dernier article acheté ou ajouté au panier par le visiteur ;
* l’attribut personnalisé associé à un visiteur ou à un article.

En fonction de ces clés, vous sélectionnez ensuite la logique de recommandation souhaitée :

* Articles avec des attributs similaires
* les articles les plus consultés dans une catégorie spécifique ;
* les clients ayant acheté cet article ont également acheté ces articles ;
* un attribut personnalisé.

[!DNL Target] comprend un portefeuille d’algorithmes prêts à l’emploi.

![Illustration du portefeuille d’algorithmes](/help/main/c-recommendations/assets/intro-15.png)

* **Les algorithmes reposant sur la popularité** comprennent les articles les plus consultés et les plus vendus.
* **Les algorithmes reposant sur le contenu** incluent la similarité de contenu.
* Les **algorithmes de filtrage collaboratif basés sur les éléments** comprennent Consultés/Consultés, Consultés/Achetés et Achetés/Achetés. « Achetés » peut correspondre à n’importe quelle conversion.
* Les **algorithmes personnalisés** comprennent Récemment consultés, Affinité du site et Filtrage collaboratif amélioré du profil.
* Les **algorithmes BYO** vous permettent d’utiliser vos propres algorithmes personnalisés.

### Règles métier en ligne

La dernière étape consiste à appliquer des règles métier en ligne. C’est pendant cette étape que vous enrichissez vos algorithmes avec les connaissances du domaine et le contexte actuel d’après les actions du visiteur sur votre propriété numérique.

![Illustration des règles métier en ligne](/help/main/c-recommendations/assets/intro-18.png)

Par exemple, dans le contexte du contenu, vous pouvez exclure les films que le visiteur a déjà regardés, recommander des films réalisés par le même réalisateur ou proposer d’autres films appartenant au même genre. Dans le contexte de la vente au détail, vous souhaiterez peut-être exclure les produits en rupture de stock, afficher les articles dont le prix est compris entre 5 et 500 euros ou proposer d’autres articles de la même marque.

## Démonstration

Une fois que vous avez effectué les tâches illustrées dans l’entonnoir de recommandation décrit ci-dessus, vous obtenez votre recommandation finale. Pour voir une démonstration intégrée au produit dans [!DNL Target], accédez à la séquence à 21:00 dans le *webinaire sur les notions fondamentales d’Adobe Target*.

## Webinaire sur les bases d’Adobe [!DNL Target] : présentation de Recommendations {#intro-to-recs}

[Présentation de Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
