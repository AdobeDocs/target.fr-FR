---
keywords: AB;A/B;AB...n;comparer des expériences;Ciblage;comparer du contenu;ciblage automatique;affectation automatique
description: Explorez les activités de test A/B dans  [!DNL Target] - [!UICONTROL Manuel], [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique].
title: Découvrez les activités de test A/B disponibles dans  [!DNL Target].
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
TQID: https://experienceleague.adobe.com/wcflYDj0VB7dJODNO6XjFHB0PPIhN4aUrBJxbKPoNdg
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 757
ht-degree: 19%

---

# Présentation du test A/B

Une activité manuelle [!UICONTROL Test A/B] (parfois appelée test A/B...N) compare plusieurs versions du contenu de votre site web afin de déterminer la version qui génère le plus de conversions, de ventes ou d’autres mesures que vous identifiez. Utilisez un test A/B pour comparer les modifications apportées à votre page par rapport à la conception de la page par défaut afin de déterminer l’expérience qui produit les meilleurs résultats.

>[!TIP]
>
>Outre l’activité [!UICONTROL Manuel] (par défaut) [!UICONTROL Test A/B] (abordée dans cet article), [!DNL Target] fournit deux types supplémentaires d’activités [!UICONTROL Test A/B] : [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]. Consultez [Types d’activités de test A/B](#types) ci-dessous pour plus d’informations.

Les tests A/B manuels sont utiles lorsque vous avez une hypothèse claire sur les moyens d’améliorer les performances de votre page en fonction des mesures de succès ou d’une diffusion de contenu alternative.

Les tests A/B manuels sont adaptés aux modifications importantes qui peuvent impliquer de nouvelles dispositions ou des traitements radicalement différents des éléments. Si votre conception de test n’est pas facilement divisée en éléments de page individuels, vous devez exécuter un test A/B avant d’exécuter un [test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Lorsque vous configurez votre test A/B, vous pouvez déterminer le pourcentage de visiteurs qui voient chaque expérience. Par exemple, vous pouvez répartir le trafic de manière égale entre le contrôle et une deuxième expérience, ou vous pouvez tester une nouvelle expérience plus risquée en la montrant à seulement 5 % de votre audience.

>[!NOTE]
>
>Pour plus d’informations sur la détermination de la taille optimale d’échantillon pour un test A/B, consultez [Planification de votre test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Lorsque le nombre d’expériences différentes dépasse cinq et s’étend sur plusieurs emplacements, il est préférable d’envisager un [&#x200B; test MVT &#x200B;](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) avant d’exécuter vos tests A/B. Le test multivarié indique les zones de la page qui sont les plus susceptibles d’améliorer la conversion. Il s’agit des emplacements sur lesquels un spécialiste marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’emplacement le plus important pour atteindre vos objectifs. Après avoir déterminé les emplacements et le contenu les plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner davantage les résultats. Par exemple, pour tester deux images spécifiques l’une par rapport à l’autre ou pour comparer le libellé ou les couleurs d’un call to action. En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Types d’activités de test A/B {#types}

Outre l’activité manuelle [!UICONTROL Test A/B], [!DNL Target] propose deux types supplémentaires d’activités [!UICONTROL Test A/B] : [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique].

| Type d’activité | Description |
| --- | --- |
| [!UICONTROL Test A/B Manuel] | Compare au moins deux expériences afin de déterminer celle qui améliore le mieux les conversions tout au long d’une période de test prédéfinie.<P>Cette section décrit comment configurer une activité manuelle [!UICONTROL Test A/B], mais les étapes pour les autres types d’activités [!UICONTROL Test A/B] sont similaires. |
| [!UICONTROL Affectation automatique] | Identifie un gagnant parmi plusieurs expériences, puis redirige le trafic vers le gagnant, ce qui augmente la conversion à mesure que le test s’exécute et apprend.<P>Pour en savoir plus sur les avantages de l’utilisation d’une activité [!UICONTROL Affectation automatique], consultez [Affectation automatique](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) dans *Quelle durée devez-vous exécuter un test A/B* et [Présentation de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Badge Premium](/help/main/assets/premium.png) [!UICONTROL Ciblage automatique] | Utilise le machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing. L’expérience la plus adaptée est ensuite proposée aux visiteurs et visiteuses en fonction de leur profil client individuel et du comportement passé de visiteurs et visiteuses similaires.<P>Pour plus d’informations, voir [&#x200B; Ciblage automatique &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Pour plus d’informations sur les activités de [!UICONTROL Test A/B] qui vous conviennent, consultez le PDF interactif du [Guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md).

Les étapes de création des trois types d’activités [!UICONTROL Test A/B] sont similaires. Pour créer une activité [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique] :

1. Commencez par [créer une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).
1. Lorsque vous accédez à la page [!UICONTROL Ciblage], cliquez sur le contrôle [!UICONTROL Affectation du trafic], puis choisissez la méthode d&#39;affectation du trafic souhaitée dans le volet de droite, comme illustré ci-dessous :

   * [!UICONTROL &#x200B; Affectation automatique à la meilleure expérience &#x200B;]
   * [!UICONTROL &#x200B; Ciblage automatique pour une expérience personnalisée &#x200B;]

   ![Paramètres de la méthode d’affectation du trafic](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

## Inclure des recommandations dans les activités A/B

Vous pouvez inclure des recommandations dans les activités [!UICONTROL Test A/B], [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] (et [!UICONTROL Ciblage d’expérience] (XT)). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

Cette fonctionnalité requiert une [licence Target Premium](/help/main/c-intro/intro.md#premium).
