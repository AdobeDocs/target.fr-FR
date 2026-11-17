---
keywords: automated personalization;ap;audiences;ensemble;forêt aléatoire;bandit manchot;échantillonnage de thompson;ml;machine learning
description: Découvrez comment utiliser les activités [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target] qui utilisent le machine learning avancé pour faire correspondre différentes variations d’offre à chaque visiteur.
title: Qu’est-ce qu’une activité [!UICONTROL Automated Personalization] (AP) ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
TQID: 'https://experienceleague.adobe.com/BBtKgNRTlqNFFoAjr1LQkhHyZeAlXG2h8D7bsndh4kQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 15%
---
# Prise en main d’[!UICONTROL Automated Personalization] {#automated-personalization-overview}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment une activité **[!UICONTROL Automated Personalization]** correspond aux variations d’offre pour chaque visiteur et ce que vous devez prendre en compte lorsque vous l’utilisez.

>[!ENDSHADEBOX]

>[!NOTE]
>
>**[!UICONTROL Automated Personalization]** est disponible dans le cadre de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md#premium).

Les activités **[!UICONTROL Automated Personalization]** (AP) dans [!DNL Adobe Target] combinent des offres ou des messages et utilisent le machine learning avancé pour faire correspondre différentes variations d’offre à chaque visiteur en fonction de son profil client individuel, afin de personnaliser le contenu et de stimuler l’effet élévateur.

Les marketeurs implémentent un fichier sur leur site, ce qui leur permet de pointer et de cliquer sur n’importe quel contenu, puis de créer visuellement des options de contenu supplémentaires pour cette zone à l’aide du **[!UICONTROL Compositeur d’expérience visuelle]** (VEC). L’algorithme détermine ensuite automatiquement l’élément de contenu à diffuser à chaque visiteur, en fonction de toutes les données comportementales dont dispose le système à propos de ce visiteur.

**[!UICONTROL Automated Personalization]** s’adapte aux changements de comportement des visiteurs, de sorte qu’il peut s’exécuter sans date de fin définie pour offrir un effet élévateur et une personnalisation continus. Ce mode est parfois appelé « toujours activé ». Le marketeur n’a pas besoin d’exécuter un test, d’analyser les résultats, puis de proposer un gagnant avant de réaliser l’effet élévateur. **[!UICONTROL Automated Personalization]** est également utile dans la phase de découverte des tests et lorsque vous ciblez divers visiteurs. Pour plus d’informations sur ses différences avec le **[!UICONTROL ciblage automatique]**, consultez [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

Les termes suivants sont utiles pour aborder **[!UICONTROL Automated Personalization]** :

| Terme | Définition |
|---|---|
| Bandit à plusieurs bras | Une approche du type bandit à plusieurs bras de l’optimisation équilibre l’apprentissage exploratoire et l’exploitation de cet apprentissage. |
| Forêt aléatoire | Une approche de machine learning de pointe. En termes de science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en construisant de nombreux arbres de décision en fonction des attributs du visiteur et de la visite. |
| Échantillonnage de Thompson | L’objectif de l’échantillonnage de Thompson est de déterminer quelle expérience est la meilleure globalement (non personnalisée), tout en réduisant le « coût » de la recherche de cette expérience. L’échantillonnage de Thompson sélectionne toujours un gagnant, même s’il n’existe aucune différence statistique entre deux expériences. Pour plus d’informations, voir [Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Fonctionnement du modèle de personnalisation {#how-ap-works}

**[!UICONTROL Automated Personalization]** utilise un algorithme Forêt aléatoire pour la personnalisation. Random Forest est une approche d&#39;apprentissage automatique de premier plan. En termes de science des données, il s’agit d’une méthode de classification ou de régression d’ensemble qui fonctionne en construisant de nombreux arbres de décision en fonction des attributs du visiteur et de la visite. Dans [!DNL Target], la forêt aléatoire est utilisée pour déterminer quelle expérience devrait avoir la plus forte probabilité de conversion (ou le chiffre d’affaires le plus élevé par visite) pour chaque visiteur spécifique.

Par exemple, les visiteurs qui utilisent Chrome, qui sont des membres fidèles Gold et qui accèdent à votre site le mardi peuvent être plus susceptibles de convertir avec l’expérience A. Les visiteurs New Yorkais peuvent être plus susceptibles de convertir avec l’expérience B.

Pour plus d&#39;informations sur Forêt aléatoire dans [!DNL Target], consultez [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

| Aspect | Fonctionnement |
|---|---|
| **Optimisation pour chaque visite** | L’algorithme prédit la probabilité qu’un visiteur effectue une conversion (ou le chiffre d’affaires estimé de la conversion) pour offrir la meilleure expérience. Un visiteur est éligible à une nouvelle expérience à la fin d’une session existante, sauf s’il se trouve dans la population témoin. Un visiteur dans la population témoin voit la même expérience que lors de la première visite. L’expérience ne change pas au cours d’une session, afin de maintenir la cohérence visuelle. |
| **Adaptation aux changements de comportement des visiteurs** | Le bandit manchot passe toujours une petite fraction du trafic pour continuer à apprendre tout au long de la vie de l&#39;activité et pour éviter la surexploitation des tendances apprises précédemment. Les modèles sous-jacents sont reconstruits toutes les 24 heures à l’aide des dernières données de comportement des visiteurs. Si l’algorithme ne peut pas déterminer les expériences gagnantes pour des visiteurs individuels, il affiche l’expérience globale la plus performante, trouvée à l’aide de l’[Échantillonnage de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling), tout en continuant à rechercher des gagnants personnalisés. |
| **Mesure de l’objectif** | Le modèle optimise en permanence une mesure d’objectif unique, qui peut être basée sur la conversion ou sur le chiffre d’affaires (plus précisément, **[!UICONTROL Chiffre d’affaires par visite]**). |
| **Données et audiences** | [!DNL Target] collecte automatiquement des informations sur les visiteurs afin de créer les modèles de personnalisation. Pour plus d’informations sur les attributs utilisés dans **[!UICONTROL le ciblage automatique]** et **[!UICONTROL Automated Personalization]**, voir [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md). [!DNL Target] utilise également automatiquement toutes les audiences partagées [!DNL Adobe Experience Cloud]. Vous n’avez donc rien à faire de spécifique pour ajouter des audiences au modèle. Pour plus d’informations, voir [Audiences Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md). |
| **Données personnalisées** | Les marketeurs peuvent charger des données hors ligne, telles que des informations CRM ou des scores de propension à l’attrition des clients, ou d’autres données personnalisées pour créer des modèles de personnalisation. Les données peuvent être entrées avec [des paramètres de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}, [des paramètres de profil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank} ou [des API côté serveur pour la mise à jour du profil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}. |

## Vidéo de formation : Types d’activités {#training-video}

Cette vidéo explique les types d’activités disponibles dans [!DNL Target]. **[!UICONTROL Automated Personalization]** est discuté à partir de 17 h 55.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)
