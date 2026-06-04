---
keywords: AB;A/B;AB...n;comparer des expériences;Ciblage;comparer du contenu;ciblage automatique;affectation automatique
description: Découvrez les différents types d’activités de test A/B dans  [!DNL Target] - Manuel, Affectation automatique et Ciblage automatique. Choisissez celui qui vous convient.
title: Quels types d’activités A/B sont disponibles dans Target ?
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 22%

---

# Présentation du test A/B

Une activité manuelle [!UICONTROL Test A/B] compare plusieurs versions du contenu de votre site web afin de déterminer la version qui améliore le mieux vos conversions au cours d’une période de test prédéfinie.

>[!NOTE]
>
>Outre l’activité Manuel (par défaut) [!UICONTROL Test A/B] (traitée dans cette section), [!DNL Target] fournit deux types supplémentaires d’activités [!UICONTROL Test A/B] : [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]. Consultez [Types d’activités de test A/B](#types) ci-dessous pour plus d’informations.

Une activité manuelle [!UICONTROL Test A/B] (parfois appelée test A/B...N) compare plusieurs versions du contenu de votre site web afin de déterminer la version qui génère le plus de conversions, de ventes ou d’autres mesures que vous identifiez. Utilisez un test A/B pour comparer les modifications apportées à votre page par rapport à la conception de la page par défaut afin de déterminer l’expérience qui produit les meilleurs résultats.

Les tests A/B manuels sont utiles lorsque vous avez une hypothèse claire sur les moyens d’améliorer les performances de votre page en fonction des mesures de succès ou d’une diffusion de contenu alternative.

Les tests A/B manuels sont adaptés aux modifications importantes qui peuvent impliquer de nouvelles dispositions ou des traitements radicalement différents des éléments. Si votre conception de test n’est pas facilement divisée en éléments de page individuels, vous devez exécuter un test A/B avant un [test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Lorsque vous configurez votre test A/B, vous pouvez déterminer le pourcentage de visiteurs qui voient chaque expérience. Par exemple, vous pouvez fractionner le trafic uniformément entre l’expérience de contrôle et la deuxième expérience ou vous pouvez tester une nouvelle expérience, plus risquée, en ne l’affichant qu’à 5 % de votre audience.

>[!NOTE]
>
>Pour plus d’informations sur la détermination de la taille optimale d’échantillon pour un test A/B, consultez [Planification de votre test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Lorsque le nombre d’expériences différentes dépasse cinq et s’étend sur plusieurs emplacements, il est préférable d’envisager un [ test MVT ](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) avant d’exécuter vos tests A/B. Le test multivarié indique les zones de la page qui sont les plus susceptibles d’améliorer la conversion. Il s’agit des emplacements sur lesquels un spécialiste marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’emplacement le plus important pour atteindre vos objectifs. Après avoir déterminé les emplacements et le contenu les plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner davantage les résultats. Par exemple, pour tester deux images spécifiques l’une par rapport à l’autre ou pour comparer le libellé ou les couleurs d’un call to action. En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Types d’activités de test A/B {#types}

Outre l’activité manuelle [!UICONTROL Test A/B] (traitée dans cette section), [!DNL Target] fournit deux types supplémentaires d’activités de test A/B : [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique].

| Type d’activité | Description |
| --- | --- |
| [!UICONTROL Test A/B Manuel] | Compare plusieurs expériences afin de déterminer la meilleure expérience qui améliore les conversions tout au long d’une période de test prédéfinie.<P>Cette section décrit comment configurer une activité manuelle [!UICONTROL Test A/B], mais les étapes pour les autres types d’activités [!UICONTROL Test A/B] sont similaires. |
| [!UICONTROL Affectation automatique] | Identifie un gagnant parmi plusieurs expériences, puis redirige le trafic vers le gagnant, ce qui augmente la conversion à mesure que le test s’exécute et apprend.<P>Pour en savoir plus sur les avantages de l’utilisation d’une activité [!UICONTROL Affectation automatique], consultez [Affectation automatique](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) dans *Quelle durée devez-vous exécuter un test A/B* et [Présentation de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Badge Premium](/help/main/assets/premium.png) [!UICONTROL Ciblage automatique] | Utilise le machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing. L’expérience la plus adaptée est ensuite proposée aux visiteurs et visiteuses en fonction de leur profil client individuel et du comportement passé de visiteurs et visiteuses similaires.<P>Pour plus d’informations, voir [ Ciblage automatique ](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Pour plus d’informations sur les activités de [!UICONTROL Test A/B] qui vous conviennent, consultez le PDF interactif du [Guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md).

Les étapes de création des trois types d’activités [!UICONTROL Test A/B] sont similaires. Pour créer une activité [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique], commencez par [créer une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), mais lorsque vous accédez à la page [!UICONTROL Ciblage], choisissez la méthode d’affectation de trafic souhaitée, comme illustré ci-dessous :

* [!UICONTROL  Affectation automatique à la meilleure expérience ]
* [!UICONTROL  Ciblage automatique pour une expérience personnalisée ]

![Paramètres de la méthode d’affectation du trafic](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Inclure des recommandations dans les activités A/B

Vous pouvez inclure des recommandations dans les activités [!UICONTROL Test A/B], [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] (et [!UICONTROL Ciblage d’expérience] (XT)). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

Cette fonctionnalité nécessite que vous ayez une licence [](/help/main/c-intro/intro.md#premium)

## Vidéo de formation : Types d’activités (9:03) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium].

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)
