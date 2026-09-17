---
keywords: Target Standard;Recommandations;Target Premium;Automated Personalization;ciblage automatique;ciblage auto;autorisations;qu’est-ce qu’Adobe Target
description: Découvrez les principes de base d’Adobe [!DNL Target] Standard et d’Adobe [!DNL Target] Premium.[!DNL Target] Premium inclut des fonctionnalités avancées qui ne sont pas disponibles dans le produit standard.
landing-page-description: Personnalisez l’expérience client afin de maximiser les recettes de vos sites web et mobiles, de vos applications, de vos médias sociaux et de vos autres canaux digitaux.
short-description: Personnalisez l’expérience client afin de maximiser les recettes de vos sites web et mobiles, de vos applications, de vos médias sociaux et de vos autres canaux digitaux.
title: Qu’est-ce que Target ?
feature: Overview
exl-id: 0e729c71-618b-4ab8-93a3-d37e73ec2740
TQID: https://experienceleague.adobe.com/Mr8fwY1FNfJShSezC50YX1QeBagmuovUySsQUO8jPqo
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 9a55efe5570867a822e4f6c0494a505e456bd536
workflow-type: tm+mt
source-wordcount: '1644'
ht-degree: 33%
---
# Présentation de [!DNL Target]

[!DNL Adobe Target], qui fait partie de la [!DNL Adobe Experience Cloud], propose des outils complets pour personnaliser les expériences client sur le web, les sites mobiles, les applications, les médias sociaux et d’autres canaux numériques.

[!DNL Target] permet de maximiser les recettes et peut être mis sous licence en tant que [!DNL Target Standard] ou [!DNL Target Premium].

## [!UICONTROL Target Standard] {#section_ACD5EFF17AAB4E979CBEFA0145CCD905}

[!DNL Target Standard] est le front-end de [!DNL Adobe Target], permettant la création visuelle et la gestion de tests A/B et d’activités de ciblage basées sur des règles. [!DNL Target] prend en charge l’insertion de code personnalisé dans et en dehors du workflow [[!UICONTROL Compositeur d’expérience visuelle]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!DNL Target Standard] offre une stratégie d’implémentation simplifiée pour vos propriétés numériques, avec une seule ligne de code sur chaque page gérant toutes les communications entre votre site et [!DNL Target].

Les bonnes pratiques du secteur sont intégrées dans [!DNL Target Standard], ce qui le rend adapté aux utilisateurs nouveaux et expérimentés. Vous pouvez facilement partager des données, des résultats et collaborer avec les membres de l’équipe à l’aide du [!DNL Adobe Experience Cloud].

## [!DNL Target Premium] {#premium}

[!BADGE Premium ]{type=Positive}

[!DNL Target Premium] est une offre avancée qui nécessite une licence pour ajouter des fonctionnalités premium à [!DNL Target Standard]. Tous les articles [!DNL Target Premium] des guides de [!DNL Target] incluent le badge [!UICONTROL Premium] en haut de chaque page ou en ligne près du texte concerné. Vous pouvez cliquer sur le badge [!UICONTROL Premium] et accéder à cette section.

**[!DNL Target Premium]comprend les fonctionnalités suivantes**

### [!UICONTROL Automated Personalization]

[](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) (AP) utilise des algorithmes de machine learning avancés pour offrir des expériences personnalisées et améliorer les taux de conversion des interactions numériques.

AP enregistre l’activité des visiteurs, créant des profils pour cibler le contenu sur des visiteurs similaires. AP suit les réponses au contenu pour les individus et la population, en utilisant une modélisation sophistiquée pour cibler automatiquement chaque visiteur en fonction de tout ce qui est connu à son sujet.

AP est entièrement automatisé, apprend en permanence avec une analyse humaine minimale. Il crée des modèles pour déterminer les produits susceptibles d’intéresser un visiteur, et collecte et stocke des informations dans les profils des visiteurs. Plusieurs algorithmes garantissent le meilleur modèle pour votre système.

### [!UICONTROL ciblage automatique]

Le [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) s’appuie sur un machine learning avancé pour identifier les expériences hautement performantes définies par les spécialistes marketing. Il offre ensuite à chaque visiteur l’expérience la plus adaptée en fonction des profils individuels des clients et du comportement des visiteurs précédents présentant des profils similaires. Le [!UICONTROL ciblage automatique] permet de personnaliser le contenu et de générer des conversions.

### Recommandations

Les activités [Recommandations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) affichent automatiquement les produits ou le contenu susceptibles d’intéresser votre clientèle selon l’activité antérieure des utilisateurs et utilisatrices. [!UICONTROL Recommandations] aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.

Une recommandation détermine comment un produit est proposé à un client, en fonction de ses activités sur le site. Par exemple :

* Encouragez les utilisateurs qui achètent un sac à dos à envisager l’achat de chaussures ou de bâtons de randonnée.

  Créez une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide du critère « Les personnes qui ont acheté ceci ont également acheté ».

* Augmentez le temps que les visiteurs passent sur votre site multimédia en recommandant du contenu vidéo similaire à celui qu’ils visionnent actuellement.

  Créez une recommandation qui suggère d’autres vidéos en utilisant le critère « Les personnes qui ont consulté ceci ont également consulté ».

* Suggérez aux clients qui ont consulté des informations sur les plans d’épargne de votre banque de lire également les informations relatives aux plans d’épargne retraite personnels.

  Affichez les autres produits que les utilisateurs ont achetés après avoir consulté un produit sans afficher le premier produit dans les recommandations, en utilisant le critère « Les personnes qui ont consulté ceci ont également acheté ».

### Recommandations en tant qu’offre

[Recommendations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md) vous permet d’inclure des recommandations dans les activités [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique] et [!UICONTROL Ciblage d’expérience] (XT).

Cette fonctionnalité offre de nouvelles fonctionnalités, telles que :

* Testez et ciblez le contenu des recommandations et des non-recommandations dans la même activité.
* Testez facilement l’emplacement des recommandations sur la page, y compris l’ordre de plusieurs recommandations.
* Envoyez automatiquement le trafic vers l’expérience de recommandations la plus performante à l’aide de l’[!UICONTROL  Affectation automatique ].
* À l’aide du ciblage automatique [!UICONTROL , affectez de manière dynamique les visiteurs à des expériences de recommandations personnalisées en fonction de profils individuels].

### Autorisations des utilisateurs d’Enterprise

La fonctionnalité [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838) vous permet de créer différents projets (appelés « Profils de produits » dans [!DNL Adobe Admin Console for Enterprise]). [!UICONTROL Autorisations des utilisateurs d’Enterprise] vous permettent d’attribuer des autorisations différentes à un utilisateur unique, ce qui détermine ses droits d’accès pour chaque projet. Ces projets distincts sont comparables au fonctionnement des suites de rapports dans [!DNL Adobe Analytics]. À chacun d’eux peuvent appartenir des utilisateurs désignés avec des rôles spécifiques s’appliquant à une série de propriétés. Les clients sont donc en mesure de restreindre l’accès à leurs utilisateurs pour l’affichage, la modification, l’approbation et la publication. Vous pouvez restreindre les utilisateurs et les utilisatrices en fonction de la zone géographique, de l’environnement (développement/test/production), du canal ou d’autres critères personnalisés.

## Fonctionnalités de Beta {#beta}

[!BADGE ]{type=Informative}

L’équipe [!DNL Adobe Target] active souvent de nouvelles fonctionnalités pour certains clients à des fins de test et de commentaires. Une fois la période de test terminée, ces fonctionnalités sont activées pour tous les clients dans les prochaines versions d’[!DNL Target Standard/Premium] et annoncées dans les notes de mise à jour.

Les articles des guides [!DNL Target] décrivant les fonctionnalités de Beta incluent le badge Beta en haut de chaque page ou en ligne près du texte concerné. Vous pouvez cliquer sur le badge Beta et inclure un lien vers cette section.

## Recommandations Classic {#section_9554068100054D2DBDB298CBE5A0E413}

>[!IMPORTANT]
>
>[!DNL Recommendations Classic] est un ancien produit et n’est plus disponible sous licence pour les nouveaux clients. Pour une expérience [!DNL Recommendations] optimale, effectuez la mise à niveau [!DNL Recommendations] vers les activités disponibles dans [!DNL Adobe Target Premium], comme décrit ci-dessus.

[!DNL Recommendations Classic] affiche automatiquement les produits ou le contenu susceptibles d’intéresser vos clients, en fonction des activités passées des visiteurs de votre site web. Ce module vous aide à orienter les clientes et clients vers des éléments dont ils n’auraient pas eu connaissance autrement, en améliorant ainsi les ventes générées sur votre site web.

Pour plus d’informations, consultez la [documentation sur Recommendations Classic](/help/main/assets/adobe-recommendations-classic.pdf).

## Experience League : kit de bienvenue Adobe [!DNL Target] {#kit}

Créez votre programme d’optimisation et de personnalisation sur [!DNL Adobe Target] avec ce kit de bienvenue. Le kit de bienvenue comprend des informations clés, des outils et des ressources pour vous aider à préparer et à lancer votre première activité [!DNL Target]. Le kit contient des idées pour des gains rapides à court terme et pour des stratégies d’optimisation à long terme.

[Le kit de bienvenue Adobe Target](/help/main/c-intro/target-welcome-kit.md)

## Vidéo de formation : Types d’activités (9:03) ![Badge d’aperçu](/help/main/assets/overview.png)

La vidéo suivante décrit les types d’activités disponibles dans [!DNL Target Standard/Premium] et explique comment le workflow guidé en trois étapes de [!DNL Target] vous permet d’atteindre les objectifs fixés pour votre site.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

>[!CONTEXTUALHELP]
>id="target_sample_size_ab_daily_traffic"
>title="Trafic quotidien"
>abstract="Nombre d’utilisateurs participant à votre expérience chaque jour. Si vous ne connaissez pas votre trafic quotidien, choisissez \« Volume de trafic\ » ci-dessus et le calculateur le résoudra à l’aide de vos autres entrées."

>[!CONTEXTUALHELP]
>id="target_sample_size_setup"
>title="Configurer le test"
>abstract="Ces champs définissent votre test A/B, ce que vous prévoyez de voir et le degré de confiance que vous devez avoir dans les résultats. Le champ lié à ce que vous avez sélectionné ci-dessus sera résolu automatiquement pour . Renseignez le reste avec vos valeurs attendues."

>[!CONTEXTUALHELP]
>id="target_sample_size_number_experiences"
>title="Nombre d’expériences"
>abstract="Nombre de variantes dans votre expérience, contrôle compris. Un test A/B comporte 2 bras. Cinq variantes plus un contrôle égale 6. Plus d&#39;armes nécessitent proportionnellement plus de trafic pour maintenir la puissance statistique."

>[!CONTEXTUALHELP]
>id="target_sample_size_duration"
>title="Durée du test A/B"
>abstract="Nombre de jours d’exécution de l’expérience. Des durées plus longues donnent à votre expérience plus de temps pour collecter des données, ce qui vous permet de détecter de manière fiable des effets plus petits. Des durées plus courtes nécessitent des effets plus importants ou davantage de trafic quotidien pour obtenir un résultat fiable."

>[!CONTEXTUALHELP]
>id="target_sample_size_minimum_detectable_effect"
>title="Effet Minimal Détectable"
>abstract="La plus petite amélioration qui vaille la peine d’être détectée est la modification minimale de votre mesure sur laquelle vous agiriez. Il s’agit de la taille de l’effet élévateur en points de pourcentage, et non du pourcentage de changement par rapport à votre ligne de base. Par exemple, si votre ligne de base est de 5 % et qu’un effet élévateur de 1 point de pourcentage est important, saisissez 1."

>[!CONTEXTUALHELP]
>id="target_sample_size_expected_improvement"
>title="Amélioration attendue"
>abstract="Amélioration attendue de l’expérience."

>[!CONTEXTUALHELP]
>id="target_sample_size_variance"
>title="Variance"
>abstract="Quelle est la répartition des valeurs de votre mesure, et non sa moyenne ? Une mesure telle qu’un taux de clics (principalement des 0 et des 1) présente un faible écart, tandis qu’une mesure telle que le chiffre d’affaires par utilisateur (quelques personnes qui dépensent beaucoup, beaucoup de faibles) peut présenter un écart beaucoup plus élevé. Si vous n’êtes pas sûr, laissez la valeur par défaut de 1."

>[!CONTEXTUALHELP]
>id="target_sample_size_confidence_level"
>title="Niveau de confiance"
>abstract="Le degré de confiance dont vous avez besoin pour être sûr qu’un résultat n’est pas simplement une chance aléatoire avant de l’appeler réel, le seuil de signification statistique. Un niveau de confiance de 95 % signifie qu’il y a au plus 5 % de chances qu’un résultat faux positif soit obtenu. Des valeurs plus élevées réduisent le nombre de faux positifs, mais requièrent davantage de données."

>[!CONTEXTUALHELP]
>id="target_sample_size_statistical_power"
>title="Puissance statistique"
>abstract="La probabilité de détecter un effet s’il existe réellement, la sensibilité de l’expérience. 80% de puissance signifie qu&#39;il y a 80% de chances de détecter un effet réel. Une puissance plus élevée réduit les faux négatifs, mais nécessite plus de trafic ou une exécution plus longue."

>[!CONTEXTUALHELP]
>id="target_sample_size_traffic_mode"
>title="Mode de trafic"
>abstract="Comment les utilisateurs rejoignent votre expérience. Continu : les utilisateurs saisissent une valeur quotidienne pendant la durée de l’expérience. Le trafic se déplace automatiquement vers des variantes plus performantes au fur et à mesure des résultats."

>[!CONTEXTUALHELP]
>id="target_sample_size_metric_type"
>title="Type de mesure"
>abstract="Quel type de mesure mesurez-vous ? Pourcentage : utilisez-le pour les résultats binaires tels que les clics ou les conversions, où chaque utilisateur fait ou ne fait pas quelque chose. Nombre : utilisez-le pour des mesures telles que le chiffre d’affaires ou les pages vues, où la valeur peut varier considérablement d’un utilisateur à l’autre."

>[!CONTEXTUALHELP]
>id="target_sample_size_auto_daily_traffic"
>title="Trafic quotidien"
>abstract="Nombre d’utilisateurs participant à votre expérience chaque jour. Utilisé pour des expériences continues s’étendant sur plusieurs jours, avec un trafic automatiquement réorienté vers des variantes plus performantes au fur et à mesure des résultats."

>[!CONTEXTUALHELP]
>id="target_sample_size_baseline_metric_rate"
>title="Taux de mesure de référence"
>abstract="Votre performance actuelle avant le début de l’expérience, moyenne du bras de contrôle. Toujours requis. Pour les mesures en pourcentage, saisissez un pourcentage : si 5 % des visiteurs cliquent sur Acheter aujourd’hui, saisissez un pourcentage de 5. Pour les mesures de comptage, saisissez la valeur décimale brute."

>[!CONTEXTUALHELP]
>id="target_ai_insights_primary_metric"
>title="Mesure principale"
>abstract="La mesure principale est automatiquement extraite des paramètres de création de rapports. Pour apporter des modifications, modifiez la mesure d’objectif sous Objectifs et paramètres."

>[!CONTEXTUALHELP]
>id="target_ai_insights_hypothesis"
>title="Hypothèse"
>abstract="L’hypothèse est une instruction que vous définissez et qui explique le résultat attendu de l’expérience. Incluez une description de ce qui est modifié et où, puis indiquez quelle mesure vous prévoyez de modifier et comment."

>[!CONTEXTUALHELP]
>id="target_ai_insights_insights"
>title="Statistiques"
>abstract="Les informations d’expérience sont les enseignements tirés par l’IA lorsque les données d’expérience ont atteint une signification statistique."

>[!CONTEXTUALHELP]
>id="target_ai_insights_opportunities"
>title="Opportunités"
>abstract="Les opportunités d’expérience sont des idées de traitement suggérées par l’IA basées sur des modèles que l’IA trouve dans vos captures d’écran et résultats d’expérience."

>[!CONTEXTUALHELP]
>id="target_ai_insights_treatment_details"
>title="Détails du traitement"
>abstract="Les détails du traitement affichent des images de ce à quoi ressemble un traitement lorsqu’un utilisateur y est qualifié. Vous pouvez consulter ces images pour toutes les expériences. Certaines expériences peuvent vous demander de confirmer l’image ou de la remplacer si nécessaire."
