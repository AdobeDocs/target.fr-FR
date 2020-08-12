---
keywords: automated traffic allocation;targeting;auto-allocate
description: L’affectation automatique identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement du trafic supplémentaire vers le gagnant afin d’augmenter les conversions pendant que le test se poursuit et apprend.
title: L’affectation automatique peut vous donner des résultats de test plus rapides et des recettes plus élevées qu’un test manuel.
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 5%

---


# L’affectation automatique peut vous donner des résultats de test plus rapides et des recettes plus élevées qu’un test manuel.

Avec une activité A/B manuelle, vous risquez de perdre des conversions, car vous ne pouvez pas diffuser l’expérience gagnante à l’ensemble de votre audience tant que l’activité n’est pas terminée. La répartition du trafic reste fixe même si vous reconnaissez que certaines expériences sont plus performantes que d’autres et que l’activité doit exécuter tout son parcours avant de pouvoir agir sur un gagnant.

## Affectation automatique du trafic

Si vous souhaitez qu’une option serve l’expérience gagnante plus souvent et plus tôt dans l’activité tout en supprimant ou en réduisant simultanément le coût de configuration et de calcul de la sélection des tailles d’échantillon, des niveaux de confiance et d’autres concepts statistiques, l’affectation  automatique est votre meilleure option.

## Comment l’affectation automatique fonctionne-t-elle ?

[!UICONTROL L&#39;affectation] automatique applique le principe du bandit à plusieurs bras. Si le terme n&#39;est pas familier, un bandit à bras unique est un terme familier pour une machine à sous (pensez : Las Vegas). Visualisez l’affectation automatique du trafic comme s’il existe plusieurs machines à sous, dans ce cas, testez les variations et, dans un premier temps, extrayez toutes les poignées de manière égale. Au fil du temps, une ou plusieurs machines, ou des variations de test, pourraient payer plus que d&#39;autres. Quand cela se produit, un joueur début naturellement de tirer les poignées de ceux qui gagnent le plus souvent. En termes d’affectation du trafic, [!DNL Adobe Target] proposera à un plus grand nombre de visiteurs l’expérience ou les expériences qui gagnent le plus.

Examinez l’illustration suivante d’une activité A/B de deux semaines. Avec l’affectation automatique, à mesure qu’une expérience gagnante se dégage, la [!UICONTROL Cible] déplace une plus grande partie du trafic vers ce gagnant dès le début du test.

![Illustration de l’affectation automatique](/help/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Comment l’affectation automatique me donne-t-elle des résultats plus rapides ?

L&#39;avantage est assez clair : davantage de visiteurs voient les variations les plus performantes. Et comme une seule variation avance, encore plus de visiteurs sont détournés vers cette expérience gagnante, alors que le test était encore en cours. Cela s’avère particulièrement utile si l’activité A/B en cours d’exécution survient au cours d’un moment d’activité principal, tel qu’un jour férié, le lancement de produits ou le événement d’actualités mondiales.

## Comment l’affectation automatique peut-elle me rapporter des recettes plus élevées ?

[!UICONTROL L’affectation] automatique identifie le gagnant plus rapidement qu’un fractionnement A/B manuel et vous permet également d’exploiter ce gagnant en capturant immédiatement les recettes à la hausse qui auraient été perdues dans une approche traditionnelle ou manuelle. Comme l’affectation  automatique dirige davantage de trafic vers l’expérience ayant le taux de conversion le plus élevé, elle peut augmenter vos recettes pendant que l’activité s’exécute et s’identifie.

Dans l’exemple suivant, l’affectation  automatique a généré plus de recettes au cours du test en poussant plus de trafic (40 %) vers l’expérience D, qui présentait le plus grand taux de conversion.

![L&#39;affectation automatique fournit une illustration des recettes les plus élevées](/help/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Dans quels cas dois-je m&#39;en tenir à l&#39;affectation manuelle du trafic ?

Lorsque vous devez classer par ordre la façon dont chaque expérience s’est comportée par rapport aux autres, un test A/B manuel est plus approprié. [!UICONTROL L’affectation] automatique permet de rechercher et d’exploiter les expériences les plus performantes, mais ne garantit pas la différenciation entre les expériences les moins performantes. Vous devez utiliser l’affectation manuelle du trafic pour contrôler complètement la quantité de trafic visiteur qui voit chaque variante de test et pour personnaliser les seuils statistiques pertinents pour votre activité.

## Commencer

Prêt à lancer votre première activité d’affectation  automatique ? [Apprenez ici](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

