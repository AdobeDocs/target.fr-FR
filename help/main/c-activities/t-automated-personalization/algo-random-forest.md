---
keywords: forêt aléatoire;arborescence de décision;ap;Automated Personalization
description: Découvrez comment utilise l [!DNL Adobe Target] algorithme Forêt aléatoire dans les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target].
title: Comment utilise [!DNL Target] t-on l’algorithme Forêt aléatoire ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1413'
ht-degree: 41%

---

# Algorithme Forêt aléatoire

Le principal algorithme de personnalisation utilisé dans les activités (AP) et [!DNL Auto-Target] est Random Forest. Des méthodes d&#39;ensemble, telles que Random Forest, utilisent de multiples algorithmes d&#39;apprentissage pour obtenir de meilleures performances prédictives que celles qui pourraient être obtenues à partir de n&#39;importe lequel des algorithmes d&#39;apprentissage constitutifs. L’algorithme Forêt aléatoire dans [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target] est une méthode de classification ou de régression qui fonctionne en construisant une multitude d’arbres de décision lors de l’entraînement.

Lorsqu’on pense aux statistiques, on imagine généralement un modèle de régression unique utilisé pour prédire un résultat. Cependant, les dernières recherches en science des données suggèrent que les « méthodes d’ensemble », où plusieurs modèles sont créés à partir du même ensemble de données avant d’être combinés suivant une logique intelligente, offrent de meilleurs résultats qu’une méthode basée sur un modèle unique.

L’algorithme Forêt aléatoire est l’algorithme de personnalisation sous-jacent clé utilisé dans les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target]. Random Forest combine des centaines d&#39;arbres de décision pour arriver à une meilleure prédiction qu&#39;un seul arbre pourrait faire seul.

## Qu’est-ce qu’un arbre de décision ? {#section_7F5865D8064447F4856FED426243FDAC}

L’objectif d’une arborescence de décision est de ventiler toutes les données de visite disponibles à partir desquelles un système peut apprendre, puis de regrouper ces données, les visites au sein de chaque groupe étant aussi similaires que possible les unes aux autres au regard de la mesure d’objectif. Toutefois, entre les groupes, les visites sont aussi différentes que possible, en ce qui concerne la mesure d’objectif (par exemple, le taux de conversion). L’arborescence de décision examine les différentes variables qu’elle possède dans l’ensemble de formation afin de déterminer comment diviser les données d’une manière mutuellement exclusive et exhaustive (MECE) en ces groupes (ou « feuilles ») pour maximiser cet objectif.

Dans un exemple simple, supposons deux variables d’entrée :

* Sexe (avec deux valeurs possibles, homme ou femme)
* Code postal (avec cinq valeurs potentielles dans le petit jeu de données : 11111, 22222, 33333, 44444 ou 55555)

Si la mesure d’objectif est la conversion, l’arborescence détermine d’abord laquelle des deux variables explique la plus grande variation du taux de conversion des données de la visite.

Disons que le code postal représente le meilleur indicateur de prédiction. Cette variable forme ainsi la première « branche » de l’arbre. L’arbre de décision détermine alors comment répartir les données de visite, de sorte que les taux de conversion des enregistrements de chaque division soient aussi similaires que possible et que les taux de conversion entre les divisions soient aussi différents que possible. Dans cet exemple, supposons que 11111, 22222, 33333 représentent une division et 44444 et 55555 une seconde division.

Cette action génère le premier calque de l’arborescence de décision :

![image decsion_tree_1](assets/decsion_tree_1.png)

L’arbre de décision pose la question « Quelle est la variable la plus prédictive ? » Dans cet exemple, il n’y a que deux variables, la réponse est donc clairement le genre. L’arborescence cherche maintenant à effectuer un exercice similaire pour diviser les données *dans chaque branche*. Commençons par examiner la branche 11111, 22222 et 33333. Dans ces codes postaux, si le taux de conversion est différent entre les hommes et les femmes, deux feuilles (hommes et femmes) viennent s’ajouter pour compléter cette branche. Dans les autres branches, 44444 et 55555, supposons qu&#39;il n&#39;y a pas de différence statistique entre la façon dont les femmes et les hommes convertissent. Le cas échéant, la première branche représente la dernière division.

L’exemple se traduit par l’arborescence ci-dessous :

![image decsion_tree_2](assets/decsion_tree_2.png)

## Comment les arbres de décision sont-ils utilisés par Random Forest ? {#section_536C105EF9F540C096D60450CAC6F627}

Les arbres de décision peuvent offrir un outil statistique extrêmement puissant. Ils présentent néanmoins certains inconvénients. Ils peuvent notamment « surapprendre » des données, avec pour résultat qu’un arbre individuel prédit incorrectement les données futures qui n’ont pas été utilisées pour générer l’arbre initial. Ce problème est connu sous le nom de [compromis biais-variance](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) en apprentissage statistique. Les forêts aléatoires aident à surmonter ce défi de suradaptation. Au plus haut niveau, une forêt aléatoire est une collection d’arbres de décision générés de manière légèrement différente à partir du même ensemble de données, qui « votent » collectivement pour offrir un meilleur modèle qu’un arbre individuel. Les arbres sont construits en sélectionnant de manière aléatoire un sous-ensemble d&#39;enregistrements de visite avec remplacement (connu sous le nom d&#39;ensachage), et en sélectionnant de manière aléatoire un sous-ensemble des attributs, de sorte que la forêt se compose d&#39;arbres de décision légèrement différents. Cette méthode introduit de petites variations dans les arbres qui sont créés dans la forêt aléatoire. L’ajout de cette dose de variance contrôlée permet d’améliorer la valeur prédictive de l’algorithme.

## Comment les algorithmes de personnalisation [!DNL Target] utilisent-ils Random Forest ? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### Comment les modèles sont créés

Le diagramme suivant résume la création de modèles pour les activités [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] :

![image random_forest_flow](assets/random_forest_flow.png){width="650" zoomable="yes"}

1. Target collecte des données sur les visiteurs tout en diffusant des expériences ou des offres de manière aléatoire
1. Une fois que [!DNL Target] a atteint une masse critique de données, [!DNL Target] effectue l’ingénierie des fonctionnalités
1. [!DNL Target] crée des modèles Forêt aléatoire pour chaque expérience ou offre
1. [!DNL Target] vérifie si le modèle atteint un score de qualité seuil
1. [!DNL Target] envoie le modèle en production pour personnaliser le trafic futur

[!DNL Target] utilise les données qu’il collecte automatiquement et les données personnalisées que vous lui fournissez pour créer ses algorithmes de personnalisation. Ces modèles identifient la meilleure expérience ou offre à présenter aux visiteurs. En règle générale, un modèle est créé par expérience (si une activité [!UICONTROL Auto-Target]) ou par offre (si une activité [!UICONTROL Automated Personalization]). [!DNL Target] affiche ensuite l’expérience ou l’offre qui génère la mesure de succès prédite la plus élevée (par exemple, le taux de conversion). Ces modèles doivent être optimisés au moyen de visites aléatoires avant de pouvoir être utilisés pour la prédiction. C’est pourquoi lorsqu’une activité démarre, même les visiteurs appartenant au groupe personnalisé sont dirigés aléatoirement vers des expériences ou des offres différentes jusqu’à ce que les algorithmes de personnalisation soient prêts.

Chaque modèle doit être validé pour s’assurer qu’il permet de prédire le comportement des visiteurs et visiteuses avant son utilisation dans votre activité. Les modèles sont validés en fonction de leur aire sous la courbe (AUC). En raison du besoin de validation, l’heure exacte à laquelle un modèle commence à diffuser des expériences personnalisées dépend des détails des données. En pratique, et en raison des impératifs de planification du trafic, le nombre minimal de conversions n’est généralement pas suffisant pour valider chaque modèle.

Lorsqu’un modèle est validé pour une expérience ou une offre, l’icône d’horloge située à gauche du nom de l’expérience/offre se transforme en case à cocher verte. Lorsqu’il existe des modèles valides pour au moins deux expériences ou offres, certaines visites commencent à devenir personnalisées.

### Transformation de caractéristiques

Avant d’être traitées par l’algorithme de personnalisation, les données font l’objet d’une transformation des caractéristiques, qui peut s’apparenter à une préparation des données collectées dans les enregistrements d’apprentissage en vue de leur utilisation par les modèles de personnalisation.

Les transformations des caractéristiques dépendent du type d’attribut. Il existe principalement deux types d’attributs (ou « caractéristiques », comme ils sont parfois appelés par les analystes en données) :

* **Catégorielle :** les caractéristiques catégorielles ne peuvent pas être dénombrées mais peuvent être triées en différents groupes. Il peut s’agir de caractéristiques telles que le pays, le sexe ou le code postal.
* **Numérique :** les caractéristiques numériques peuvent être mesurées ou dénombrées, par exemple l’âge, le revenu, etc.

Pour les caractéristiques catégorielles, un jeu de toutes les caractéristiques possibles est conservé et la transformation de probabilité est utilisée pour réduire la taille des données. Pour les fonctions numériques, le redimensionnement permet de s’assurer que les fonctions sont comparables dans tous les cas.

### Trouver le juste équilibre entre l’apprentissage et la personnalisation avec le bandit manchot

Une fois que [!DNL Target] a créé des modèles de personnalisation pour personnaliser votre trafic, vous devez faire un compromis pour les futurs visiteurs de votre activité. Devez-vous personnaliser tout le trafic en fonction du modèle actuel ou devez-vous continuer à apprendre des nouveaux visiteurs en leur proposant des offres aléatoires de manière aléatoire ? Vous devez vous assurer que l’algorithme de personnalisation assimile sans cesse les nouvelles tendances qui se dégagent du comportement de vos visiteurs, tout en personnalisant l’essentiel du trafic.

Le bandit à plusieurs bras est la façon dont [!DNL Target] vous aide à atteindre cet objectif. Le bandit à plusieurs bras garantit que le modèle « dépense » toujours une petite fraction du trafic pour continuer à apprendre tout au long de la vie de l’apprentissage par activité et pour éviter la surexploitation des tendances apprises précédemment.

Dans le monde de la science des données, le problème du bandit manchot est un exemple classique du dilemme exploration contre exploitation dans lequel une collection de bandits manchots, chacun avec une probabilité de récompense inconnue, est donnée. L’idée clé est de développer une stratégie qui résulte en ce que le bras doté de la plus haute probabilité de succès soit joué afin que la récompense totale soit maximisée. Le bandit manchot est utilisé dans le système pour la notation en ligne une fois les modèles en ligne créés. Ce processus facilite l’apprentissage en ligne pendant l’exploration. L&#39;algorithme multi-bras actuel est un algorithme gourmand en epsilon (ε). Dans cet algorithme, avec la probabilité 1- ε, le meilleur bras est choisi. Et avec la probabilité ε, n’importe quel autre bras est choisi de manière aléatoire.
