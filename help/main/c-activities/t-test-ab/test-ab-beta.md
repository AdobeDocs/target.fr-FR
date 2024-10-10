---
keywords: AB;A/B;AB...n;comparer des expériences;ciblage;comparer du contenu;ciblage automatique;affectation automatique
description: Explorez les activités de test A/B dans  [!DNL Target] - [!UICONTROL Manual], [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].
title: Découvrez les activités de test A/B disponibles dans  [!DNL Target].
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 36cc6486a95b977589aced55168a93ffd300d78f
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 21%

---

# Présentation des tests A/B

Une activité [!UICONTROL A/B Test] manuelle (parfois appelée test A/B...N) compare plusieurs versions du contenu de votre site Web afin de déterminer la version qui génère le plus de conversions, de ventes ou d’autres mesures que vous identifiez. Utilisez un test A/B pour comparer les modifications apportées à votre page par rapport à la conception de la page par défaut afin de déterminer l’expérience qui produit les meilleurs résultats.

>[!TIP]
>
>Outre l&#39;activité [!UICONTROL Manual] (par défaut) [!UICONTROL A/B Test] (discutée dans cet article), [!DNL Target] fournit deux types supplémentaires d&#39;activités [!UICONTROL A/B Test] : [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]. Pour plus d’informations, voir [Types des activités de test A/B](#types) ci-dessous.

Les tests A/B manuels sont utiles lorsque vous disposez d’une hypothèse claire sur les moyens d’améliorer les performances de votre page en fonction de mesures de succès ou d’une autre diffusion de contenu.

Les tests A/B manuels sont bien adaptés aux modifications importantes qui peuvent impliquer de nouvelles mises en page ou des traitements radicalement différents des éléments. Si votre conception de test ne se décompose pas facilement en éléments de page individuels, vous devez exécuter un test A/B avant d’exécuter un [test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Lorsque vous configurez votre test A/B, vous pouvez déterminer le pourcentage de visiteurs qui visualisent chaque expérience. Par exemple, vous pouvez répartir le trafic uniformément entre l’expérience de contrôle et une seconde expérience, ou vous pouvez tester une nouvelle expérience plus risquée en l’affichant à seulement 5 % de votre audience.

>[!NOTE]
>
>Pour plus d’informations sur la détermination de la taille optimale d’échantillon pour un test A/B, consultez [Planification de votre test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Lorsque le nombre d’expériences différentes dépasse cinq et qu’elles couvrent plusieurs emplacements, il est préférable d’envisager un [test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) avant d’exécuter vos tests A/B. Le test multivarié indique les zones de la page qui sont les plus susceptibles d’améliorer la conversion. Ces zones sont les emplacements sur lesquels un spécialiste du marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’emplacement le plus important pour atteindre vos objectifs. Une fois que vous avez déterminé les emplacements et le contenu les plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner davantage les résultats. Par exemple, pour tester deux images spécifiques l’une par rapport à l’autre, ou pour comparer la formulation ou les couleurs d’un appel à l’action. En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Types d’activités de test A/B {#types}

Outre l&#39;activité [!UICONTROL A/B Test] manuelle, [!DNL Target] fournit deux types d&#39;activités [!UICONTROL A/B Testing] supplémentaires : [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].

| Type d’activité | Description |
| --- | --- |
| [!UICONTROL Manual A/B Test] | Compare au moins deux expériences afin de déterminer celle qui améliore le mieux les conversions tout au long d’une période de test prédéfinie.<P>Cette section décrit comment configurer une activité [!UICONTROL A/B Test] manuelle, mais les étapes des autres types d’activités [!UICONTROL A/B Test] sont similaires. |
| [!UICONTROL Auto-Allocate] | Identifie un gagnant parmi plusieurs expériences, puis redirige le trafic vers le gagnant, en augmentant la conversion au fur et à mesure que le test s’exécute et apprend.<P>Pour en savoir plus sur les avantages de l’utilisation d’une activité [!UICONTROL Auto-Allocate], voir [Affectation automatique](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) dans *Quelle doit être la durée d’exécution d’un test A/B* et [Présentation de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Badge Premium](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | Utilise l’apprentissage automatique avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par les marketeurs. L’expérience la plus personnalisée est ensuite proposée aux visiteurs en fonction de leurs profils client individuels et des comportements antérieurs de visiteurs similaires.<P>Pour plus d’informations, voir [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Pour plus d’informations sur l’une de ces activités [!UICONTROL A/B Test] qui vous convient, consultez le [PDF de guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md) interactif.

Les étapes de création des trois types d’activités [!UICONTROL A/B Test] sont similaires. Pour créer une activité [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target] :

1. Commencez par [créer une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).
1. Lorsque vous accédez à la page [!UICONTROL Targeting], cliquez sur la commande [!UICONTROL Traffic Allocation], puis sélectionnez la méthode d’affectation du trafic souhaitée dans le volet de droite, comme illustré ci-dessous :

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experience]

   ![ Paramètres de méthode d’affectation du trafic ](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

## Inclure des recommandations dans les activités A/B

Vous pouvez inclure des recommandations dans les activités [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] (et les activités [!UICONTROL Experience Targeting] (XT)). Pour plus d’informations, consultez [Recommendations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

Cette fonctionnalité requiert une [licence Target Premium](/help/main/c-intro/intro.md#premium).