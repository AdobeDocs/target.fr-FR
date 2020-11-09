---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: Une activité de test A/B manuel compare plusieurs versions du contenu de votre site Web afin de déterminer la version qui améliore le mieux vos conversions au cours d’une période de test prédéfinie.
title: Présentation des tests A/B
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# Présentation des tests A/B

A manual [!UICONTROL A/B Test] activity compares two or more versions of your website content to see which version best improves your conversions during a pre-specified test period.

>[!NOTE]
>
>Outre l&#39;activité de test  A/B (par défaut) du manuel (présentée dans la présente section), [!DNL Target] deux autres types d&#39;activités de test  A/B sont disponibles : [!UICONTROL Affectation] automatique et Cible automatique.
>
>Pour plus d’informations, voir [Types d’activités](#types) de test A/B ci-dessous.

A manual [!UICONTROL A/B Test] activity (sometimes referred to as an A/B...N test) compares two or more versions of your Web site content to see which best lifts your conversions, sales, or other metrics you identify. Utilisez un test A/B pour comparer les modifications apportées à votre page par rapport à la conception de la page par défaut afin de déterminer l’expérience qui produit les meilleurs résultats.

Les tests A/B manuels sont particulièrement utiles lorsque vous disposez d’une hypothèse claire des moyens d’améliorer les performances de votre page en fonction des mesures de réussite ou d’une autre diffusion de contenu.

Les tests A/B manuels sont adaptés aux modifications importantes qui peuvent impliquer de nouvelles mises en page ou des traitements radicalement différents des éléments. If your test design does not easily break down into individual page elements, you should run an A/B test before a [multivariate test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

Lorsque vous configurez votre test A/B, vous pouvez déterminer le pourcentage de visiteurs qui voient chaque expérience. Par exemple, vous pouvez fractionner le trafic uniformément entre l’expérience de contrôle et la deuxième expérience ou vous pouvez tester une nouvelle expérience, plus risquée, en ne l’affichant qu’à 5 % de votre audience.

>[!NOTE]
>
>Pour plus d’informations sur la détermination de la taille optimale d’échantillon pour un test A/B, consultez [Planification de votre test A/B](/help/c-activities/t-test-ab/sample-size-determination.md).

Lorsque le nombre d’expériences différentes dépasse cinq et qu’elles couvrent plusieurs emplacements, il est préférable d’envisager un [test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) avant d’exécuter vos tests A/B. Le test multivarié indique les zones de la page qui sont les plus susceptibles d’améliorer la conversion. Il s’agit des emplacements sur lesquels un spécialiste du marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’emplacement le plus important pour atteindre vos objectifs. Une fois que vous avez déterminé les emplacements et le contenu les plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner davantage les résultats, par exemple pour tester deux images spécifiques les unes par rapport aux autres, ou pour comparer le libellé ou les couleurs d’un appel à l’action. En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Types d’activités de test A/B {#types}

Outre l’activité de test  A/B manuelle (présentée dans cette section), [!DNL Target] fournit deux types supplémentaires d’activités de test A/B : [!UICONTROL Affectation] automatique et Cible automatique.

| Type d’activité | Description |
| --- | --- |
| [!UICONTROL Test A/B manuel] | Compare plusieurs expériences afin de déterminer celle qui améliore le mieux les conversions tout au long d’une période de test prédéfinie. <br>Cette section décrit comment configurer une activité de test  A/B manuelle, mais les étapes des autres types d’activités de test  A/B sont similaires. |
| [!UICONTROL Affectation automatique] | Identifie un gagnant parmi plusieurs expériences, puis redirige le trafic vers le gagnant, en augmentant la conversion au fur et à mesure que le test s’exécute et apprend. <br>Pour en savoir plus sur les avantages de l’utilisation d’une activité d’affectation automatique, voir Attribution [](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) automatique dans *Quelle est la durée d’exécution d’un test* A/B et d’une présentation [de l’affectation](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)automatique. |
| ![Balise](/help/assets/premium.png) Premium [!UICONTROL Auto Cible] | Utilise l’apprentissage automatique avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par le responsable du marketing, puis en diffusant l’expérience la plus personnalisée aux visiteurs en fonction de leurs profils client individuels et des comportements antérieurs de visiteurs similaires. <br>Pour plus d’informations, voir Cible [](/help/c-activities/auto-target/auto-target-to-optimize.md)automatique. |

Pour plus d’informations sur l’une de ces activités de test  A/B qui vous convient, consultez le Guide PDF [interactif des Activités de](/help/c-activities/target-activities-guide.md)Adobe Target.

Les étapes de création des trois types d’activités de test  A/B sont similaires. Pour créer une activité d’affectation  automatique ou de Cible  automatique, début en [créant une activité](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)de test A/B, mais lorsque vous accédez à la page [!UICONTROL Ciblage, choisissez la méthode d’affectation du trafic de votre choix, comme illustré ci-dessous :]

* [!UICONTROL Affectation automatique à la meilleure expérience]
* [!UICONTROL Cible automatique pour une expérience personnalisée]

![Paramètres de méthode d’affectation du trafic](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vidéo de formation : Balise ![Aperçu des types d&#39;Activité (9:03)](/help/assets/overview.png)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium].

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)
