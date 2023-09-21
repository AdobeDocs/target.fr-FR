---
keywords: AB;A/B;AB...n;comparer des expériences;ciblage;comparer du contenu;ciblage automatique;affectation automatique
description: Découvrez les différents types d’activités de test A/B dans Adobe [!DNL Target] - Manuel, affectation automatique et ciblage automatique. Choisis celui qui te convient.
title: Quel type d’activités A/B est disponible dans Target ?
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: b5da2f5d41739af39d97e0ce9761006794c04d2b
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 25%

---

# Présentation des tests A/B

Un manuel [!UICONTROL Test A/B] activité compare plusieurs versions du contenu de votre site web afin de déterminer la version qui améliore le mieux vos conversions au cours d’une période de test prédéfinie.

>[!NOTE]
>
>En plus du manuel (par défaut) [!UICONTROL Test A/B] activité (voir cette section), [!DNL Target] fournit deux types supplémentaires de [!UICONTROL Test A/B] activités : [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]. Voir [Types d’activités de test A/B](#types) ci-dessous pour plus d’informations.

Un manuel [!UICONTROL Test A/B] activité (parfois appelée test A/B...N) compare plusieurs versions du contenu de votre site Web afin de déterminer la version qui génère le plus de conversions, de ventes ou d’autres mesures que vous identifiez. Utilisez un test A/B pour comparer les modifications apportées à votre page par rapport à la conception de la page par défaut afin de déterminer l’expérience qui produit les meilleurs résultats.

Les tests A/B manuels sont utiles lorsque vous disposez d’une hypothèse claire sur les moyens d’améliorer les performances de votre page en fonction de mesures de succès ou d’une autre diffusion de contenu.

Les tests A/B manuels sont bien adaptés aux modifications importantes qui peuvent impliquer de nouvelles mises en page ou des traitements radicalement différents des éléments. Si votre conception de test ne se décompose pas facilement en éléments de page individuels, vous devez exécuter un test A/B avant un test [test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Lorsque vous configurez votre test A/B, vous pouvez déterminer le pourcentage de visiteurs qui visualisent chaque expérience. Par exemple, vous pouvez fractionner le trafic uniformément entre l’expérience de contrôle et la deuxième expérience ou vous pouvez tester une nouvelle expérience, plus risquée, en ne l’affichant qu’à 5 % de votre audience.

>[!NOTE]
>
>Pour plus d’informations sur la détermination de la taille optimale d’échantillon pour un test A/B, consultez [Planification de votre test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Lorsque le nombre d’expériences différentes dépasse cinq et s’étend sur deux emplacements ou plus, il est préférable d’envisager une [Test MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) avant d’exécuter vos tests A/B. Le test multivarié indique les zones de la page qui sont les plus susceptibles d’améliorer la conversion. Ces zones sont les emplacements sur lesquels un spécialiste du marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’emplacement le plus important pour atteindre vos objectifs. Une fois que vous avez déterminé les emplacements et le contenu les plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner davantage les résultats. Par exemple, pour tester deux images spécifiques l’une par rapport à l’autre, ou pour comparer la formulation ou les couleurs d’un appel à l’action. En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Types d’activités de test A/B {#types}

En plus du manuel [!UICONTROL Test A/B] activité (voir cette section), [!DNL Target] fournit deux types supplémentaires d’activités de test A/B : [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique].

| Type d’activité | Description |
| --- | --- |
| [!UICONTROL Test A/B manuel] | Compare plusieurs expériences afin de déterminer la meilleure expérience qui améliore les conversions tout au long d’une période de test prédéfinie.<P>Cette section décrit comment configurer un manuel [!UICONTROL Test A/B] , mais les étapes des autres types de [!UICONTROL Test A/B] Les activités sont similaires. |
| [!UICONTROL Affectation automatique] | Identifie un gagnant parmi plusieurs expériences, puis redirige le trafic vers le gagnant, en augmentant la conversion au fur et à mesure que le test s’exécute et apprend.<P>Pour en savoir plus sur les avantages de l’utilisation d’une [!UICONTROL Affectation automatique] activité, voir [Affectation automatique](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) in *Durée d’exécution d’un test A/B* et [Présentation de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Badge Premium](/help/main/assets/premium.png) [!UICONTROL Ciblage automatique] | Utilise l’apprentissage automatique avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par les marketeurs. L’expérience la plus personnalisée est ensuite proposée aux visiteurs en fonction de leurs profils client individuels et des comportements antérieurs de visiteurs similaires.<P>Pour plus d’informations, voir [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Pour plus d’informations sur l’un de ces [!UICONTROL Test A/B] Les activités sont adaptées à vos besoins, voir [PDF du guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md).

Les étapes de création des trois types de [!UICONTROL Test A/B] Les activités sont similaires. Pour créer une [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique] activité, commencez par [création d’une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), mais lorsque vous accédez au [!UICONTROL Ciblage] , choisissez la méthode d’affectation du trafic souhaitée, comme illustré ci-dessous :

* [!UICONTROL Auto affecter à la meilleure expérience]
* [!UICONTROL Ciblage automatique pour une expérience personnalisée]

![Paramètres de méthode d’affectation du trafic](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Inclure des recommandations dans les activités A/B

Vous pouvez inclure des recommandations dans [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], et [!UICONTROL Ciblage automatique] activités (et [!UICONTROL Ciblage d’expérience] (XT). Pour plus d’informations, consultez [Recommendations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

Cette fonctionnalité requiert une licence [Target Premium](/help/main/c-intro/intro.md#premium)

## Vidéo de formation : Types d’activités (9:03) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium].

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)
