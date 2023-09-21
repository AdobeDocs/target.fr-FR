---
keywords: forêt aléatoire;arbre de décision;ap;Automated Personalization
description: Découvrez comment [!DNL Adobe Target] utilise l’algorithme Forêt aléatoire dans les deux [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage automatique] activités.
title: Comment [!DNL Target] Utilisez l’algorithme Forêt aléatoire ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1431'
ht-degree: 41%

---

# Algorithme Forêt aléatoire

L’algorithme de personnalisation principal utilisé à la fois pour et [!DNL Auto-Target] Les activités sont l’algorithme Forêt aléatoire. Les méthodes d’ensemble, telles que l’algorithme Forêt aléatoire, utilisent plusieurs algorithmes d’apprentissage pour obtenir de meilleures performances prédictives que celles qui peuvent être obtenues à partir de n’importe quel algorithme d’apprentissage constitutif. Algorithme Forêt aléatoire dans [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] est une méthode de classification ou de régression qui fonctionne en construisant une multitude d’arbres de décision lors de son entraînement.

Lorsqu’on pense aux statistiques, on imagine généralement un modèle de régression unique utilisé pour prédire un résultat. Cependant, les dernières recherches en science des données suggèrent que les « méthodes d’ensemble », où plusieurs modèles sont créés à partir du même ensemble de données avant d’être combinés suivant une logique intelligente, offrent de meilleurs résultats qu’une méthode basée sur un modèle unique.

L’algorithme Forêt aléatoire est l’algorithme de personnalisation sous-jacent clé utilisé dans [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] activités. L’algorithme Forêt aléatoire combine ensemble des centaines d’arbres de décision pour obtenir une meilleure prédiction qu’un seul arbre ne pourrait faire seul.

## Qu&#39;est-ce qu&#39;un arbre de décision ? {#section_7F5865D8064447F4856FED426243FDAC}

L’objectif d’une arborescence de décision est de ventiler toutes les données de visite disponibles qu’un système peut apprendre puis de regrouper ces données, dans lesquelles les visites au sein de chaque groupe sont aussi similaires que possible les unes aux autres par rapport à la mesure d’objectif. Toutefois, entre les groupes, les visites sont aussi différentes que possible, en ce qui concerne la mesure d’objectif (par exemple, le taux de conversion). L’arbre de décision examine les différentes variables qu’il possède dans l’ensemble de formation afin de déterminer comment séparer les données d’une façon collectivement exhaustive et mutuelle (MECE) en ces groupes (ou &quot;feuilles&quot;) pour maximiser cet objectif.

Dans un exemple simple, supposons deux variables d’entrée :

* Sexe (avec deux valeurs possibles, homme ou femme)
* Code postal (avec cinq valeurs potentielles dans le petit jeu de données : 1111, 22222, 3333, 4444 ou 55555)

Si la mesure d’objectif est la conversion, l’arborescence commence par déterminer la variable qui explique la plus grande variation du taux de conversion des données de visite.

Disons que le code postal représente le meilleur indicateur de prédiction. Cette variable forme ainsi la première « branche » de l’arbre. L’arbre de décision détermine alors comment répartir les données de visite, de sorte que les taux de conversion des enregistrements de chaque division soient aussi similaires que possible et que les taux de conversion entre les divisions soient aussi différents que possible. Dans cet exemple, supposons que 1111, 2222, 33333 sont un partage et que 4444 et 55555 sont un second partage.

Cette action entraîne la première couche de l’arborescence de décision :

![image decsion_tree_1](assets/decsion_tree_1.png)

L’arbre de décision pose la question &quot;Quelle est la variable la plus prédictive ?&quot; Dans cet exemple, il n&#39;y a que deux variables, donc la réponse ici est clairement le genre. L’arborescence tente désormais de terminer un exercice similaire pour fractionner les données. *dans chaque branche*. Commençons par examiner la branche 11111, 22222 et 33333. Dans ces codes postaux, si le taux de conversion est différent entre les hommes et les femmes, deux feuilles (hommes et femmes) viennent s’ajouter pour compléter cette branche. Dans les autres branches, 44444 et 55555, supposons qu&#39;il n&#39;y ait aucune différence statistique entre la conversion des femmes et des hommes. Le cas échéant, la première branche représente la dernière division.

L’exemple génère l’arborescence suivante :

![image decsion_tree_2](assets/decsion_tree_2.png)

## Comment les arbres de décision sont-ils utilisés par l’algorithme Forêt aléatoire ? {#section_536C105EF9F540C096D60450CAC6F627}

Les arbres de décision peuvent offrir un outil statistique extrêmement puissant. Ils présentent néanmoins certains inconvénients. Ils peuvent notamment « surapprendre » des données, avec pour résultat qu’un arbre individuel prédit incorrectement les données futures qui n’ont pas été utilisées pour générer l’arbre initial. Ce problème est connu sous le nom de [compromis biais-variance](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) en apprentissage statistique. Les forêts aléatoires aident à surmonter ce défi de surajustement. Au plus haut niveau, une forêt aléatoire est une collection d’arbres de décision générés de manière légèrement différente à partir du même ensemble de données, qui « votent » collectivement pour offrir un meilleur modèle qu’un arbre individuel. Les arbres sont créés en sélectionnant de manière aléatoire un sous-ensemble d’enregistrements de visite avec un remplacement (appelé balisage) et en sélectionnant aléatoirement un sous-ensemble des attributs, de sorte que la forêt se compose d’arbres de décision légèrement différents. Cette méthode introduit de petites variations dans les arbres qui sont créés dans la forêt aléatoire. L’ajout de cette dose de variance contrôlée permet d’améliorer la valeur prédictive de l’algorithme.

## Comment procéder [!DNL Target] les algorithmes de personnalisation utilisent l’algorithme Forêt aléatoire ? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### Création des modèles

Le diagramme suivant résume la manière dont les modèles sont créés pour [!UICONTROL Ciblage automatique] et [!UICONTROL Automated Personalization] activités :

![image random_forest_flow](assets/random_forest_flow.png){width="650" zoomable="yes"}

1. Target collecte des données sur les visiteurs lors de la diffusion aléatoire d’expériences ou d’offres
1. Après [!DNL Target] atteint une masse critique de données, [!DNL Target] Exécution de la conception des fonctionnalités
1. [!DNL Target] crée des modèles Forêt aléatoire pour chaque expérience ou offre ;
1. [!DNL Target] vérifie si le modèle atteint un score de qualité minimal.
1. [!DNL Target] envoie le modèle en production pour personnaliser le trafic à venir.

[!DNL Target] utilise les données qu’il collecte automatiquement et les données personnalisées que vous fournissez pour créer ses algorithmes de personnalisation. Ces modèles identifient la meilleure expérience ou offre à présenter aux visiteurs. En règle générale, un modèle est créé par expérience (si un [!UICONTROL Ciblage automatique] activité) ou par offre (si une [!UICONTROL Automated Personalization] activité). [!DNL Target] affiche ensuite l’expérience ou l’offre qui génère la mesure de succès prédite la plus élevée (par exemple, le taux de conversion). Ces modèles doivent être optimisés au moyen de visites aléatoires avant de pouvoir être utilisés pour la prédiction. C’est pourquoi lorsqu’une activité démarre, même les visiteurs appartenant au groupe personnalisé sont dirigés aléatoirement vers des expériences ou des offres différentes jusqu’à ce que les algorithmes de personnalisation soient prêts.

Chaque modèle doit être validé afin de s’assurer qu’il permet de prédire le comportement des visiteurs avant son utilisation dans votre activité. Les modèles sont validés en fonction de leur zone sous la courbe (AUC). En raison de la nécessité de la validation, le moment exact auquel un modèle commence à diffuser des expériences personnalisées dépend des détails des données. En pratique, et en raison des impératifs de planification du trafic, le nombre minimal de conversions n’est généralement pas suffisant pour valider chaque modèle.

Lorsqu’un modèle est validé pour une expérience ou une offre, l’icône d’horloge située à gauche du nom de l’expérience/offre se transforme en case à cocher verte. Lorsqu’il existe des modèles valides pour au moins deux expériences ou offres, certaines visites commencent à être personnalisées.

### Transformation des fonctionnalités

Avant d’être traitées par l’algorithme de personnalisation, les données font l’objet d’une transformation des caractéristiques, qui peut s’apparenter à une préparation des données collectées dans les enregistrements d’apprentissage en vue de leur utilisation par les modèles de personnalisation.

Les transformations des caractéristiques dépendent du type d’attribut. Il existe principalement deux types d’attributs (ou « caractéristiques », comme ils sont parfois appelés par les analystes en données) :

* **Catégorielle :** les caractéristiques catégorielles ne peuvent pas être dénombrées mais peuvent être triées en différents groupes. Il peut s’agir de caractéristiques telles que le pays, le sexe ou le code postal.
* **Numérique :** les caractéristiques numériques peuvent être mesurées ou dénombrées, par exemple l’âge, le revenu, etc.

Pour les caractéristiques catégorielles, un jeu de toutes les caractéristiques possibles est conservé et la transformation de probabilité est utilisée pour réduire la taille des données. Pour les fonctions numériques, la mise à l’échelle permet de s’assurer que les fonctions sont comparables dans leur ensemble.

### Équilibrage de l&#39;apprentissage et de la personnalisation avec le bandit à plusieurs bras

Après [!DNL Target] dispose de modèles de personnalisation conçus pour personnaliser votre trafic. Il existe un compromis clair auquel vous devrez faire face pour les futurs visiteurs de votre activité. Devriez-vous personnaliser tout le trafic en fonction du modèle actuel ou continuez-vous à apprendre des nouveaux visiteurs en leur diffusant aléatoirement des offres ? Vous devez vous assurer que l’algorithme de personnalisation assimile sans cesse les nouvelles tendances qui se dégagent du comportement de vos visiteurs, tout en personnalisant l’essentiel du trafic.

Le bandit à plusieurs bras est le suivant : [!DNL Target] vous aide à atteindre cet objectif. Le bandit à plusieurs bras garantit que le modèle &quot;dépense&quot; toujours une petite fraction de trafic pour continuer à apprendre tout au long de la vie de l’activité d’apprentissage et pour empêcher la surexploitation des tendances apprises précédemment.

Dans le monde de la science des données, le problème du bandit à plusieurs bras est un exemple classique du dilemme de l&#39;exploration contre l&#39;exploitation dans lequel un ensemble de bandits à un bras, chacun avec une probabilité de récompense inconnue, est donné. L’idée clé est de développer une stratégie qui résulte en ce que le bras doté de la plus haute probabilité de succès soit joué afin que la récompense totale soit maximisée. Le bandit à plusieurs bras est utilisé dans le système pour la notation en ligne une fois les modèles en ligne créés. Ce processus aide à l’apprentissage en ligne pendant l’exploration. L’algorithme à plusieurs bras actuel est un algorithme gourmand d’épsilon (ε). Dans cet algorithme, avec la probabilité 1- ε, le meilleur bras est choisi. Et avec la probabilité ε, n’importe quel autre bras est choisi de manière aléatoire.
