---
keywords: forêt aléatoire;arborescence de décision;ap;Automated Personalization
description: Découvrez comment [!DNL Adobe Target] utilise l’algorithme Forêt aléatoire dans les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage automatique].
title: Comment [!DNL Target] utilise-t-il l'algorithme Forêt aléatoire ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
TQID: 'https://experienceleague.adobe.com/Ui8E8CkiiJSdqim9fzIgPDdsKG1MMtuu3EUuAqgmm0M'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 7%
---
# Algorithme Forêt aléatoire {#random-forest-algorithm}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment [!DNL Target] utilise l’algorithme Forêt aléatoire pour créer les modèles de personnalisation des activités **[!UICONTROL Automated Personalization]** et **[!UICONTROL Ciblage automatique]**.

>[!ENDSHADEBOX]

Le principal algorithme de personnalisation utilisé dans les activités de **[!UICONTROL Automated Personalization]** (AP) et de **[!UICONTROL ciblage automatique]** est Random Forest. Il s’agit d’une méthode de classification ou de régression qui fonctionne en construisant une multitude d’arbres de décision lors de son entraînement.

Forêt aléatoire est une méthode d’ensemble. Lorsqu’on pense aux statistiques, on imagine généralement un modèle de régression unique utilisé pour prédire un résultat. Les dernières recherches en science des données suggèrent que les « méthodes d&#39;ensemble », où plusieurs modèles sont créés à partir du même ensemble de données, puis intelligemment combinés, produisent de meilleurs résultats que la prédiction basée sur un seul modèle, ou que ceux qui pourraient être obtenus à partir de l&#39;un des algorithmes d&#39;apprentissage constitutifs.

## Qu’est-ce qu’un arbre de décision ? {#section_7F5865D8064447F4856FED426243FDAC}

Une arborescence de décision répartit toutes les données de visite qu’un système peut apprendre en groupes. Les visites au sein de chaque groupe sont aussi similaires que possible les unes aux autres au regard de la mesure d’objectif (par exemple, le taux de conversion) et les visites entre les groupes sont aussi différentes que possible. Pour ce faire, l’arborescence examine les variables de l’ensemble d’entraînement et divise les données de manière exclusive mutuelle et exhaustive (MECE) en groupes (ou « feuilles ») qui optimisent cet objectif.

Dans l’exemple simple suivant, la mesure d’objectif est la conversion et il existe deux variables d’entrée :

* Sexe (avec deux valeurs possibles, homme ou femme)
* Code postal (avec cinq valeurs potentielles dans le petit jeu de données : 11111, 22222, 33333, 44444 ou 55555)

### Première division {#first-split}

L’arborescence détermine d’abord laquelle des deux variables explique la plus grande variation du taux de conversion des données de visite. Supposons que le code postal soit le plus prédictif. Cette variable forme la première « branche » de l’arborescence. L’arborescence divise ensuite les données de visite en groupes, comme décrit ci-dessus. Supposons que 11111, 22222 et 33333 soient une scission et que 44444 et 55555 soient une deuxième scission.

![Premier calque de l’arborescence de décision](assets/decsion_tree_1.png){width="440" align="center"}

### Fractionner au sein de chaque branche {#second-split}

L&#39;arbre pose la question, « Quelle est la variable la plus prédictive ? » et effectue un exercice similaire pour fractionner les données *dans chaque branche*. Seul le genre demeure, c&#39;est donc la réponse ici. Dans les branches 11111, 22222 et 33333, supposons qu’il existe une différence de conversion entre les hommes et les femmes. Il y a alors deux feuilles (hommes et femmes), et cette branche est complète. Dans la branche 44444 et 55555, supposons qu’il n’y ait pas de différence statistique entre la conversion des hommes et des femmes. Dans ce cas, la première division est la dernière.

![Arborescence de décision complète](assets/decsion_tree_2.png){width="480" align="center"}

## Comment les arbres de décision sont-ils utilisés par Random Forest ? {#section_536C105EF9F540C096D60450CAC6F627}

Les arbres de décision peuvent offrir un outil statistique extrêmement puissant. Ils présentent néanmoins certains inconvénients. Plus important encore, ils peuvent « suradapter » les données, de sorte qu’une arborescence individuelle prédise mal les données futures qui n’ont pas été utilisées pour créer l’arborescence initiale. Ce problème est connu sous le nom de [compromis biais-variance](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) en apprentissage statistique.

Les forêts aléatoires aident à surmonter ce défi. Une forêt aléatoire est une collection de centaines d&#39;arbres de décision qui sont construits légèrement différemment sur le même ensemble de données et qui « votent » ensemble pour produire un meilleur modèle qu&#39;un arbre individuel. Les arbres sont construits en sélectionnant de manière aléatoire un sous-ensemble d&#39;enregistrements de visite avec remplacement (connu sous le nom d&#39;ensachage) et en sélectionnant de manière aléatoire un sous-ensemble des attributs, de sorte que la forêt se compose d&#39;arbres de décision légèrement différents. Cette méthode introduit de petites variations dans les arbres. L’ajout de cette quantité contrôlée de variance permet d’améliorer la précision prédictive de l’algorithme.

## Comment les algorithmes de personnalisation [!DNL Target] utilisent-ils Random Forest ? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### Comment les modèles sont créés

[!DNL Target] utilise les données qu&#39;il collecte automatiquement et les données personnalisées que vous lui fournissez pour créer ses algorithmes de personnalisation. Le diagramme suivant résume la création de modèles pour les activités de **[!UICONTROL ciblage automatique]** et **[!UICONTROL Automated Personalization]** :

![Flux qui résume la création de modèles Forêt aléatoire](assets/random_forest_flow.png){width="850" zoomable="yes"}

1. [!DNL Target] collecte des données sur les visiteurs tout en diffusant des expériences ou des offres de manière aléatoire.
1. Une fois que [!DNL Target] a atteint une masse critique de données, [!DNL Target] effectue l’ingénierie des fonctionnalités.
1. [!DNL Target] crée des modèles Forêt aléatoire pour chaque expérience ou offre.
1. [!DNL Target] valide le modèle en vérifiant s&#39;il répond à un score de qualité seuil.
1. [!DNL Target] pousse le modèle en production pour personnaliser le trafic futur.

Ces modèles identifient la meilleure expérience ou offre à présenter aux visiteurs. En règle générale, un modèle est créé par expérience (dans une activité de **[!UICONTROL ciblage automatique]**) ou par offre (dans une activité d’**[!UICONTROL Automated Personalization]**). [!DNL Target] affiche ensuite l’expérience ou l’offre qui génère la mesure de succès prédite la plus élevée (par exemple, le taux de conversion). Les modèles doivent être entraînés lors de visites diffusées de manière aléatoire avant de pouvoir être utilisés à des fins de prédiction. Par conséquent, même les visiteurs qui se trouvent dans le groupe personnalisé s’affichent de manière aléatoire différentes expériences ou offres lorsqu’une activité démarre pour la première fois, jusqu’à ce que les algorithmes de personnalisation soient prêts.

Les modèles sont validés en fonction de leur aire sous la courbe (AUC), afin de vous assurer que chaque modèle prédit correctement le comportement des visiteurs et visiteuses avant son utilisation dans votre activité. L’heure exacte à laquelle un modèle commence à diffuser des expériences personnalisées dépend des détails des données, car le modèle doit d’abord être validé. En pratique, et en raison des impératifs de planification du trafic, le nombre minimal de conversions n’est généralement pas suffisant pour valider chaque modèle.

Lorsqu’un modèle devient valide pour une expérience ou une offre, l’icône d’horloge située à gauche du nom de l’expérience ou de l’offre se transforme en case à cocher verte. Lorsqu’il existe des modèles valides pour au moins deux expériences ou offres, certaines visites commencent à devenir personnalisées.

### Transformation de caractéristiques

Avant que les données ne passent par l’algorithme de personnalisation, elles subissent une transformation de caractéristique, qui peut être considérée comme la préparation des données collectées dans les enregistrements d’entraînement en vue de leur utilisation par les modèles de personnalisation. La transformation dépend du type d’attribut (ou de « fonctionnalité », comme les spécialistes des données la décrivent parfois) :

| Type de caractéristique | Description | Transformation |
|---|---|---|
| **Catégorique** | Ne peut pas être comptabilisé, mais peut être trié en différents groupes, tels que le pays, le genre ou le code postal. | Un ensemble de toutes les fonctionnalités possibles est conservé et la transformation de vraisemblance est utilisée pour réduire la taille des données. |
| **Numérique** | Peuvent être mesurées ou comptabilisées, comme l’âge ou le revenu. | Le redimensionnement permet de s’assurer que les fonctionnalités sont comparables dans l’ensemble. |

### Trouver le juste équilibre entre l’apprentissage et la personnalisation avec le bandit manchot

Une fois que [!DNL Target] a créé les modèles de personnalisation, vous faites face à un compromis pour les futurs visiteurs de votre activité. Vous pouvez personnaliser tout le trafic en fonction du modèle actuel ou continuer à apprendre des nouveaux visiteurs en leur proposant des offres aléatoires de manière aléatoire. L’algorithme de personnalisation doit toujours en savoir plus sur les nouvelles tendances de vos visiteurs et visiteuses tandis qu’il personnalise la plupart du trafic. Le bandit manchot est la manière dont [!DNL Target] atteint cet objectif : il s’assure que le modèle « dépense » toujours une petite fraction du trafic pour continuer à apprendre tout au long de la vie de l’activité et pour éviter la surexploitation des tendances apprises précédemment.

Dans le monde de la science des données, le problème du bandit manchot est un exemple classique du dilemme exploration contre exploitation, dans lequel une collection de bandits manchots, chacun avec une probabilité de récompense inconnue, est donnée. L&#39;idée clé est de développer une stratégie qui aboutit au bras avec la plus forte probabilité de succès joué, de sorte que la récompense totale obtenue soit maximisée. Le bandit manchot est utilisé dans le système pour la notation en ligne une fois les modèles en ligne créés. Ce processus facilite l’apprentissage en ligne pendant l’exploration. L&#39;algorithme multi-bras actuel est un algorithme gourmand en epsilon (ε). Dans cet algorithme, avec la probabilité 1 - ε, le meilleur bras est choisi. Avec la probabilité ε, tout autre bras est choisi aléatoirement.
