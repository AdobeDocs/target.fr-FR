---
keywords: personnalisation automatisée;ap;audiences;ensemble;random forest;bandit à plusieurs bras;échantillonnage thompson;ml;apprentissage automatique
description: Découvrez comment utiliser les activités [!UICONTROL Automated Personalization] (AP) dans  [!DNL Adobe Target] qui utilisent l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur.
title: Qu’est-ce qu’une activité [!UICONTROL Automated Personalization] (AP) ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 28%

---

# [!UICONTROL Automated Personalization] (AP)

Les activités [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target] combinent des offres ou des messages et utilisent l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur selon leur profil client spécifique afin de personnaliser le contenu et de générer des conversions.

>[!NOTE]
>
>[!UICONTROL Automated Personalization] est disponible dans le cadre de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md#premium).

À l’instar de [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] utilise un [ algorithme Forêt aléatoire ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), une méthode d’ensemble issue de la science des données, en tant qu’algorithme de personnalisation principal pour déterminer la meilleure expérience à présenter à un visiteur. [!UICONTROL Automated Personalization] peut s’avérer utile lors de la phase de découverte des tests. Elle permet également à l’apprentissage automatique de déterminer le contenu le plus efficace lors du ciblage de différents visiteurs. Avec le temps, l’algorithme apprend à effectuer des prédictions plus efficaces et affiche le contenu le plus à même de satisfaire vos objectifs.

Pour plus d’informations sur les différences de [!UICONTROL Automated Personalization] avec [!UICONTROL Auto-Target], voir [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

Les marketeurs implémentent un fichier sur leur site, qui leur permet de pointer et cliquer sur n’importe quel contenu, puis de créer et de sélectionner visuellement des options de contenu supplémentaires pour cette zone à l’aide du [!UICONTROL Visual Experience Composer] (VEC). Ensuite, l’algorithme détermine automatiquement quel élément de contenu diffuser pour chaque visiteur individuel en fonction de toutes les données de comportement détenues par le système sur le visiteur, offrant ainsi une expérience personnalisée. [!UICONTROL Automated Personalization] pouvant s’adapter aux changements de comportement du visiteur, il peut être exécuté sans date de fin définie pour offrir un effet élévateur et une personnalisation continus. Ce mode est parfois appelé &quot;toujours actif&quot;. Ainsi, le spécialiste du marketing n’a pas besoin d’exécuter un test et d’analyser les résultats avant de diffuser le meilleur contenu sans réaliser l’effet élévateur de l’optimisation (l’ordre des opérations standard pour mettre en œuvre le résultat d’une activité A/B standard).

Les termes suivants sont utiles pour discuter de [!UICONTROL Automated Personalization] :

| Terme | Définition |
|---|---|
| Bandit à plusieurs bras | Une approche du type bandit à plusieurs bras de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage. |
| Forêt aléatoire | Une approche d’apprentissage automatique de pointe. En termes de science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en créant de nombreux arbres de décision en fonction des attributs du visiteur et de la visite. |
| Échantillonnage de Thompson | L’objectif de l’échantillonnage de Thompson est de déterminer la meilleure expérience globale (non personnalisée), tout en minimisant le &quot;coût&quot; de la recherche de cette expérience. L’échantillonnage de Thompson désigne toujours un gagnant, même s’il n’existe aucune différence statistique entre deux expériences. Pour plus d’informations, voir [Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Tenez compte des détails suivants lors de l’utilisation de [!UICONTROL Automated Personalization] :

## [!UICONTROL Automated Personalization] utilise un algorithme Forêt aléatoire pour personnaliser

Random Forest est une méthode d’apprentissage automatique de pointe. En termes de science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en créant de nombreux arbres de décision en fonction des attributs du visiteur et de la visite. Dans [!DNL Target], l’algorithme Forêt aléatoire est utilisé pour déterminer l’expérience qui devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. Par exemple, les visiteurs qui utilisent Chrome, sont des membres du programme de fidélité Gold et accèdent à votre site le mardi peuvent être plus susceptibles de convertir leur visite avec l’expérience A. Les visiteurs de New York sont plus susceptibles de convertir leur visite avec l’expérience B. Pour plus d’informations sur l’algorithme Forêt aléatoire dans [!DNL Target], voir [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Le modèle de personnalisation optimise pour chaque visite

* L’algorithme prédit la probabilité de conversion d’un visiteur (ou les recettes estimées de la conversion) pour offrir la meilleure expérience.
* Un visiteur est éligible pour une nouvelle expérience à la fin d’une session existante, sauf s’il fait partie de la population témoin. Si le visiteur fait partie de la population témoin, l’expérience que le visiteur voit lors de sa première visite est la même que celle qu’il a vue lors de ses visites suivantes.
* L’expérience présentée ne change pas au sein d’une session pour maintenir la cohérence visuelle.

## Le modèle de personnalisation s’adapte aux changements de comportement du visiteur.

* Le bandit à plusieurs bras garantit que le modèle &quot;dépense&quot; toujours une petite partie du trafic pour continuer à apprendre tout au long de la vie de l’activité et pour empêcher la surexploitation des tendances apprises précédemment.
* Les modèles sous-jacents sont reconstruits toutes les 24 heures à l’aide des dernières données de comportement des visiteurs afin de garantir que [!DNL Target] utilise toujours l’évolution des préférences des visiteurs.
* Si l’algorithme ne peut pas déterminer les expériences gagnantes pour les visiteurs individuels, il affiche automatiquement l’expérience globale la plus performante tout en continuant à rechercher des gagnants personnalisés. L’expérience la plus performante est trouvée en utilisant l’[échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

## Le modèle optimise continuellement une mesure d’objectif unique

* Cette mesure peut être basée sur la conversion ou sur les recettes (plus spécifiquement, [!UICONTROL Revenue per Visitor]).

## [!DNL Target] collecte automatiquement des informations sur les visiteurs pour créer les modèles de personnalisation

* Pour plus d’informations sur les attributs utilisés dans [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization], voir [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## [!DNL Target] utilise automatiquement toutes les [!DNL Adobe Experience Cloud] audiences partagées pour créer les modèles de personnalisation

* Vous n’avez rien à faire de spécifique pour ajouter des audiences au modèle. Pour plus d’informations sur l’utilisation de [!DNL Experience Cloud Audiences] avec [!DNL Target], voir [Audiences d’Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

## Les marketeurs peuvent charger des données hors ligne, des scores de propension ou d’autres données personnalisées pour créer des modèles de personnalisation.

Les données hors ligne, telles que les informations de gestion de la relation client ou les scores de propension d’attrition des clients, peuvent s’avérer particulièrement utiles lors de la création de modèles de personnalisation. Il existe plusieurs façons de saisir des données dans les algorithmes de personnalisation [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target].

* [paramètres de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}
* [Paramètres de profil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}
* [API côté serveur pour la mise à jour du profil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}

Pour plus d’informations sur les données collectées automatiquement et utilisées par les algorithmes de personnalisation [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target], voir [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Vidéo de formation : Types d’activités

Cette vidéo explique les types d’activités disponibles dans [!DNL Target]. [!UICONTROL Automated Personalization] est abordé à partir de 05:55.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/29340?captions=fre_fr)
