---
keywords: personnalisation automatisée;ap;audiences;ensemble;random forest;bandit à plusieurs bras;échantillonnage thompson;ml;apprentissage automatique
description: Découvrez comment utiliser les activités Automated Personalization (AP) dans Adobe [!DNL Target] qui utilisent l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur.
title: Qu’est-ce qu’une activité Automated Personalization (AP) ?
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: 7c15a0795e94b6c6317cb5b4018899be71f03a40
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 81%

---

# ![PREMIUM](/help/main/assets/premium.png) Automated Personalization (AP)

[!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target] combiner des offres ou des messages et utilise l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur en fonction de son profil client spécifique afin de personnaliser le contenu et de générer des conversions.

>[!NOTE]
>
>[!UICONTROL La personnalisation automatisée] fait partie de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Si vous possédez une licence [!DNL Target Premium], la carte [!DNL Target Premium] remplace la carte [!DNL Target Standard] dans [!DNL Adobe Experience Cloud].

À l’instar du [!UICONTROL ciblage automatique], [!UICONTROL la personnalisation automatisée] utilise un algorithme de forêt aléatoire, c’est-à-dire une méthode d’ensemble issue de la science des données, en tant qu’algorithme de personnalisation principal pour déterminer la meilleure expérience à présenter à un visiteur. [!UICONTROL Automated Personalization] peut s’avérer être un atout majeur lors de la phase de découverte des tests. Elle permet également à l’apprentissage automatique de déterminer le contenu le plus efficace lors du ciblage de différents visiteurs. Avec le temps, l’algorithme apprend à effectuer des prédictions plus efficaces et affiche le contenu le plus à même de satisfaire vos objectifs.

Pour obtenir plus d’informations sur la manière dont [!UICONTROL Automated Personalization] diffère de [!UICONTROL Ciblage automatique], voir [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

Les spécialistes du marketing implémentent un fichier sur leur site, qui leur permet de pointer et cliquer sur n’importe quel contenu puis de créer et de sélectionner visuellement des options de contenu supplémentaires pour cette zone à l’aide du [!UICONTROL compositeur d’expérience visuelle] (VEC). Ensuite, l’algorithme détermine automatiquement quel élément de contenu diffuser pour chaque visiteur individuel en fonction de toutes les données de comportement détenues par le système sur le visiteur, offrant ainsi une expérience personnalisée. La [!UICONTROL personnalisation automatisée] pouvant s’adapter aux changements de comportement du visiteur, elle peut être exécutée sans date de fin définie pour offrir une personnalisation et un effet élévateur continus. Cette fonctionnalité est parfois appelée mode « toujours actif ». Ainsi, le spécialiste du marketing n’a pas besoin d’exécuter un test et d’analyser les résultats avant de diffuser le meilleur contenu sans réaliser l’effet élévateur de l’optimisation (l’ordre des opérations standard pour mettre en œuvre le résultat d’une activité A/B standard).

Les termes suivants concernent [!UICONTROL la personnalisation automatisée :]

| Terme | Définition |
|---|---|
| Bandit à plusieurs bras | Une approche du type bandit à plusieurs bras de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage. |
| Forêt aléatoire | La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. Dans le jargon de la science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en générant un grand nombre d’arbres de décision en fonction des attributs du visiteur et de la visite. Dans Target, le concept de la forêt aléatoire est utilisé pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. Pour plus d’informations sur l’application de la forêt aléatoire dans Target, voir [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). |
| Échantillonnage de Thompson | L’objectif de l’échantillonnage de Thompson est de déterminer la meilleure expérience globale (non personnalisée), tout en minimisant le &quot;coût&quot; de la recherche de cette expérience. L’échantillonnage de Thompson désigne toujours un gagnant, même s’il n’existe aucune différence statistique entre deux expériences. Pour plus d’informations, voir [Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Tenez compte des aspects suivants lors de l’utilisation de la [!UICONTROL personnalisation automatisée] :

**[!UICONTROL Automated Personalization] utilise un algorithme Forêt aléatoire pour personnaliser l’expérience.**

La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. Dans le jargon de la science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en générant un grand nombre d’arbres de décision en fonction des attributs du visiteur et de la visite. Dans Target, le concept de la forêt aléatoire est utilisé pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. Par exemple, les visiteurs qui utilisent Chrome, ont le statut de membre Or et accèdent à votre site le mardi peuvent être plus susceptibles de convertir avec l’expérience A, tandis que les visiteurs de New York peuvent être plus susceptibles de convertir avec l’expérience B. Pour plus d’informations sur l’application de la forêt aléatoire dans Target, voir [Algorithme de forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

**Le modèle de personnalisation optimise l’expérience à chaque visite.**

* L’algorithme prédit la probabilité de conversion d’un visiteur (ou les recettes estimées de la conversion) afin de servir la meilleure expérience.
* Un visiteur est éligible pour une nouvelle expérience au terme d’une session existante (à moins qu’il appartienne au groupe témoin, auquel cas l’expérience présentée au visiteur lors de sa première visite reste la même lors de ses visites ultérieures).
* Au sein d’une session, l’expérience présentée ne change pas afin de maintenir la cohérence visuelle.

**Le modèle de personnalisation s’adapte aux changements de comportement du visiteur.**

* Le bandit à plusieurs bras garantit que le modèle &quot;dépense&quot; toujours une petite partie du trafic pour continuer à apprendre tout au long de la vie de l’activité et pour empêcher la surexploitation des tendances apprises précédemment.
* Les modèles sous-jacents sont recréés toutes les 24 heures à l’aide des dernières données de comportement des visiteurs afin de garantir que Target reste toujours en phase avec l’évolution des préférences des visiteurs.
* Si l’algorithme ne peut pas déterminer les expériences gagnantes pour les visiteurs individuels, il affiche automatiquement l’expérience globale la plus performante tout en continuant à rechercher des gagnants personnalisés. L’expérience la plus performante est trouvée en utilisant l’[échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**Le modèle assure l’optimisation continue d’une mesure d’objectif unique.**

* Cette mesure peut être basée sur la conversion ou sur les recettes (plus spécifiquement les [!UICONTROL recettes par visiteur]).

**Target collecte automatiquement des informations sur les visiteurs pour créer les modèles de personnalisation.**

* Pour plus d’informations sur les attributs utilisés dans le [!UICONTROL ciblage automatique] et la [!UICONTROL personnalisation automatisée], voir [Collection de données de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/ap-data.md).

**Target utilise automatiquement toutes les audiences partagées de [!DNL Adobe Experience Cloud] pour créer les modèles de personnalisation**.

* Vous n’avez rien besoin de faire de particulier pour ajouter des audiences au modèle. Pour plus d’informations sur l’utilisation de [!DNL Experience Cloud Audiences] avec [!DNL Target], voir [Audiences d’Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

**Les marketeurs peuvent télécharger des données hors ligne, les scores de propension ou d’autres données personnalisées pour créer des modèles de personnalisation.**

Les données hors ligne, telles que les informations de gestion de la relation client ou les scores de propension de l’attrition client, peuvent être extrêmement utiles pour la création des modèles de personnalisation. Il existe plusieurs façons de saisir des données dans les algorithmes de personnalisation de [!UICONTROL personnalisation automatisée] et de [!UICONTROL ciblage automatique].

* [Paramètres mbox](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [Paramètres de profil](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [API côté serveur pour la mise à jour du profil](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}

Pour plus d’informations sur les données collectées automatiquement et utilisées par les algorithmes de personnalisation [!UICONTROL Personnalisation automatisée] et [!UICONTROL ciblage automatique], voir [Collection de données de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/ap-data.md).

## ![Badge d’aperçu](/help/main/assets/overview.png) Vidéo de formation : Types d’activité

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium]. [!UICONTROL Automated Personalization est abordée à partir de 5:55.]

* Décrivez les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)
