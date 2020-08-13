---
keywords: automated personalization;Audiences;ensemble;random forest
description: Automated Personalization (AP) associe des offres ou des messages et utilise l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur selon leur profil client spécifique afin de personnaliser le contenu et de générer des conversions.
title: Automated Personalization
feature: ap
topic: Advanced
uuid: cf9489f2-45b2-4028-8956-36d0afe0ee0a
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 98%

---


# ![PREMIUM](/help/assets/premium.png) Personnalisation automatisée{#automated-personalization}

La [!UICONTROL personnalisation automatisée] (PA) associe des offres ou des messages et utilise l’apprentissage automatique avancé pour faire correspondre différentes variations d’offre à chaque visiteur selon leur profil client spécifique afin de personnaliser le contenu et de générer des conversions.

>[!NOTE]
>
>[!UICONTROL La personnalisation automatisée] fait partie de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Si vous possédez une licence [!DNL Target Premium], la carte [!DNL Target Premium] remplace la carte [!DNL Target Standard] dans [!DNL Adobe Experience Cloud].

À l’instar du [!UICONTROL ciblage automatique], [!UICONTROL la personnalisation automatisée] utilise un algorithme de forêt aléatoire, c’est-à-dire une méthode d’ensemble issue de la science des données, en tant qu’algorithme de personnalisation principal pour déterminer la meilleure expérience à présenter à un visiteur. [!UICONTROL Automated Personalization] peut s’avérer être un atout majeur lors de la phase de découverte des tests. Elle permet également à l’apprentissage automatique de déterminer le contenu le plus efficace lors du ciblage de différents visiteurs. Avec le temps, l’algorithme apprend à effectuer des prédictions plus efficaces et affiche le contenu le plus à même de satisfaire vos objectifs.

Pour plus d’informations sur la manière dont la [!UICONTROL Personnalisation automatisée] diffère de la fonction de [!UICONTROL Ciblage automatique], voir [Ciblage automatique pour les expériences personnalisées](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

Les spécialistes du marketing implémentent un fichier sur leur site, qui leur permet de pointer et cliquer sur n’importe quel contenu puis de créer et de sélectionner visuellement des options de contenu supplémentaires pour cette zone à l’aide du [!UICONTROL compositeur d’expérience visuelle] (VEC). Ensuite, l’algorithme détermine automatiquement quel élément de contenu diffuser pour chaque visiteur individuel en fonction de toutes les données de comportement détenues par le système sur le visiteur, offrant ainsi une expérience personnalisée. La [!UICONTROL personnalisation automatisée] pouvant s’adapter aux changements de comportement du visiteur, elle peut être exécutée sans date de fin définie pour offrir une personnalisation et un effet élévateur continus. Cette fonctionnalité est parfois appelée mode « toujours actif ». Ainsi, le spécialiste du marketing n’a pas besoin d’exécuter un test et d’analyser les résultats avant de diffuser le meilleur contenu sans réaliser l’effet élévateur de l’optimisation (l’ordre des opérations standard pour mettre en œuvre le résultat d’une activité A/B standard).

Les termes suivants concernent [!UICONTROL la personnalisation automatisée :]

| Terme | Définition |
|---|---|
| Bandit à plusieurs bras | Une approche du type bandit à plusieurs bras de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage. |
| Forêt aléatoire | La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. Dans le jargon de la science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en générant un grand nombre d’arbres de décision en fonction des attributs du visiteur et de la visite. Dans Target, le concept de la forêt aléatoire est utilisé pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. Pour plus d’informations sur l’application de la forêt aléatoire dans Target, voir [Algorithme Forêt aléatoire](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
| Échantillonnage de Thompson | L’échantillonnage de Thompson a pour but de déterminer la meilleure expérience globale (non personnalisée), tout en minimisant le « coût » de son identification. L’échantillonnage de Thompson désigne toujours un gagnant, même s’il n’existe aucune différence statistique entre deux expériences. Pour plus d’informations, voir [Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Tenez compte des aspects suivants lors de l’utilisation de la [!UICONTROL personnalisation automatisée] :

**[!UICONTROL Automated Personalization]utilise un algorithme Forêt aléatoire pour personnaliser l’expérience.**

La forêt aléatoire est l’une des approches les plus utilisées dans le domaine de l’apprentissage automatique. Dans le jargon de la science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en générant un grand nombre d’arbres de décision en fonction des attributs du visiteur et de la visite. Dans Target, le concept de la forêt aléatoire est utilisé pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou les recettes par visite les plus élevées) pour chaque visiteur spécifique. Par exemple, les visiteurs qui utilisent Chrome, ont le statut de membre Or et accèdent à votre site le mardi peuvent être plus susceptibles de convertir avec l’expérience A, tandis que les visiteurs de New York peuvent être plus susceptibles de convertir avec l’expérience B. Pour plus d’informations sur l’application de la forêt aléatoire dans Target, voir [Algorithme de forêt aléatoire](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

**Le modèle de personnalisation optimise l’expérience à chaque visite.**

* L’algorithme prédit la probabilité de conversion d’un visiteur (ou les recettes estimées de la conversion) afin de servir la meilleure expérience.
* Un visiteur est éligible pour une nouvelle expérience au terme d’une session existante (à moins qu’il appartienne au groupe témoin, auquel cas l’expérience présentée au visiteur lors de sa première visite reste la même lors de ses visites ultérieures).
* Au sein d’une session, l’expérience présentée ne change pas afin de maintenir la cohérence visuelle.

**Le modèle de personnalisation s’adapte aux changements de comportement du visiteur.**

* Le bandit à plusieurs bras garantit que le modèle utilise toujours une petite partie du trafic pour continuer d’apprendre tout au long de la vie de l’activité et prévenir la surexploitation des tendances apprises précédemment.
* Les modèles sous-jacents sont recréés toutes les 24 heures à l’aide des dernières données de comportement des visiteurs afin de garantir que Target reste toujours en phase avec l’évolution des préférences des visiteurs.
* Si l’algorithme ne peut pas déterminer les expériences gagnantes pour les visiteurs individuels, il affiche automatiquement l’expérience globale la plus performante tout en continuant à rechercher des gagnants personnalisés. L’expérience la plus performante est trouvée en utilisant l’[échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**Le modèle assure l’optimisation continue d’une mesure d’objectif unique.**

* Cette mesure peut être basée sur la conversion ou sur les recettes (plus spécifiquement les [!UICONTROL recettes par visiteur]).

**Target collecte automatiquement des informations sur les visiteurs pour créer les modèles de personnalisation.**

* Pour plus d’informations sur les attributs utilisés dans le [!UICONTROL ciblage automatique] et la [!UICONTROL personnalisation automatisée], voir [Collection de données de personnalisation automatisée](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**Target utilise automatiquement toutes les audiences partagées de[!DNL Adobe Experience Cloud]pour créer les modèles de personnalisation**.

* Vous ne devez rien faire de particulier pour ajouter des audiences au modèle. Pour plus d’informations sur l’utilisation de [!DNL Experience Cloud Audiences] avec [!DNL Target], voir [Audiences d’Experience Cloud](../../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969).

**Les marketeurs peuvent télécharger des données hors ligne, les scores de propension ou d’autres données personnalisées pour créer des modèles de personnalisation.**

Les données hors ligne, telles que les informations de gestion de la relation client ou les scores de propension de l’attrition client, peuvent être extrêmement utiles pour la création des modèles de personnalisation. Il existe plusieurs façons de saisir des données dans les algorithmes de personnalisation de [!UICONTROL personnalisation automatisée] et de [!UICONTROL ciblage automatique].

* [Paramètres mbox](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [Paramètres de profil](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [API côté serveur pour la mise à jour du profil](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)

Pour plus d’informations sur les données collectées automatiquement et utilisées par les algorithmes de personnalisation [!UICONTROL Personnalisation automatisée] et [!UICONTROL ciblage automatique], voir [Collection de données de personnalisation automatisée](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## ![Badge](/help/assets/overview.png) de présentation Vidéo de formation : Types d’Activité

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium]. [!UICONTROL Automated Personalization est abordée à partir de 5:55.]

* Décrivez les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)