---
keywords: AB;A/B;AB...n;comparer des expériences;Ciblage;comparer du contenu;ciblage automatique;affectation automatique
description: Explorez les activités de test A/B dans [!DNL Target] - [!UICONTROL Manuel], [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique].
title: Découvrez les activités de test A/B disponibles dans [!DNL Target].
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
TQID: 'https://experienceleague.adobe.com/wcflYDj0VB7dJODNO6XjFHB0PPIhN4aUrBJxbKPoNdg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: d887712962ad4e3cecd6b3b86ee33a4bcb99f2a8
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 19%
---
# Présentation du test A/B {#test-ab}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez ce qu’est un test A/B manuel, quand l’utiliser au lieu d’un test multivarié et comment il se rapporte aux types d’activité Affectation automatique et Ciblage automatique .

>[!ENDSHADEBOX]

Une activité manuelle **[!UICONTROL Test A/B]** (parfois appelée test A/B...N) compare plusieurs versions du contenu de votre site web afin de déterminer celle qui génère le mieux vos conversions, vos ventes ou d’autres mesures que vous identifiez. Utilisez un test A/B pour comparer les modifications apportées à votre page par rapport à la conception de la page par défaut afin de déterminer l’expérience qui produit les meilleurs résultats.

## Quand utiliser un test A/B manuel {#when-to-use}

Utiliser un test A/B manuel lorsque :

* Vous avez une hypothèse claire sur les moyens d’améliorer les performances de vos pages, en fonction des mesures de succès ou d’une autre diffusion de contenu.
* Vous souhaitez tester des modifications importantes, telles que de nouvelles dispositions ou des traitements radicalement différents des éléments. Si votre conception de test n’est pas facilement divisée en éléments de page individuels, vous devez exécuter un test A/B avant d’exécuter un [test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).
* Vous souhaitez décider du pourcentage de visiteurs et visiteuses qui voient chaque expérience. Par exemple, vous pouvez répartir le trafic de manière égale entre le contrôle et une deuxième expérience, ou vous pouvez tester une nouvelle expérience plus risquée en la montrant à seulement 5 % de votre audience.

Pour plus d’informations sur la détermination de la taille optimale d’échantillon pour un test A/B, consultez [Planification de votre test A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

### Combiner un test multivarié et des tests A/B

Lorsque le nombre d’expériences différentes dépasse cinq et s’étend sur plusieurs emplacements, il est préférable d’envisager un [test MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) avant d’exécuter vos tests A/B :

1. **Exécutez un test multivarié** pour identifier les zones de la page les plus susceptibles d’améliorer la conversion. Il s’agit des emplacements sur lesquels un spécialiste marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’emplacement le plus important pour atteindre vos objectifs.

1. **Exécutez un ou plusieurs tests A/B** sur ces emplacements pour affiner davantage les résultats. Par exemple, pour tester deux images spécifiques l’une par rapport à l’autre ou pour comparer le libellé ou les couleurs d’un call to action.

En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Types d’activités de test A/B {#types}

Outre l’activité manuelle **[!UICONTROL Test A/B]**, [!DNL Target] fournit deux types supplémentaires d’**[!UICONTROL activités de test A/B]** : **[!UICONTROL Affectation automatique]** et **[!UICONTROL Ciblage automatique]**.

| Type d’activité | Description |
| --- | --- |
| **[!UICONTROL Test A/B Manuel]** | Compare au moins deux expériences afin de déterminer celle qui améliore le mieux les conversions tout au long d’une période de test prédéfinie.<P>Cette section décrit comment configurer une activité **[!UICONTROL Test A/B]** manuelle, mais les étapes pour les autres types d’activités **[!UICONTROL Test A/B]** sont similaires. |
| **[!UICONTROL Affectation automatique]** | Identifie un gagnant parmi plusieurs expériences, puis redirige le trafic vers le gagnant, ce qui augmente la conversion à mesure que le test s’exécute et apprend.<P>Pour en savoir plus sur les avantages de l’utilisation d’une activité d’**[!UICONTROL affectation automatique]**, consultez [Affectation automatique](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) dans *Combien de temps devez-vous exécuter un test A/B* et [Présentation de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Badge Premium](/help/main/assets/premium.png) **[!UICONTROL Ciblage automatique]** | Utilise le machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing. L’expérience la plus adaptée est ensuite proposée aux visiteurs et visiteuses en fonction de leur profil client individuel et du comportement passé de visiteurs et visiteuses similaires.<P>Pour plus d&#39;informations, consultez [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Pour plus d’informations sur les **[!UICONTROL activités de test A/B]** qui vous conviennent, consultez le [Guide des activités Adobe Target interactif PDF](/help/main/c-activities/target-activities-guide.md).

>[!NOTE]
>
>Vous pouvez inclure des recommandations dans les activités de **[!UICONTROL test A/B]**, de **[!UICONTROL affectation automatique]** et de **[!UICONTROL ciblage automatique]** (et les activités de **[!UICONTROL ciblage d’expérience]** (XT)). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une [licence Target Premium](/help/main/c-intro/intro.md#premium).
