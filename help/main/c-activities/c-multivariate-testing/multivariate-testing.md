---
keywords: test multivarié;mvt;factoriel complet;mvt ou a/b;multivarié a/b;estimateur de trafic;quand utiliser mvt;considérations mvt;multivarié;factoriel partiel;factoriel partiel;factoriel complet
description: Découvrez comment utiliser une [!UICONTROL Multivariate Test] (MVT) dans  [!DNL Adobe Target]  comparer des combinaisons d’offres dans des éléments d’une page afin de déterminer la combinaison la plus performante.
title: Qu'est-ce qu'un [!UICONTROL Multivariate Test] ?
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 47%

---

# Vue d’ensemble des [!UICONTROL Multivariate Test]

Une activité [!UICONTROL Multivariate Test] (MVT) dans [!DNL Adobe Target] compare les combinaisons d’offres dans les éléments d’une page afin de déterminer la combinaison la plus performante pour une audience spécifique. Une activité [!UICONTROL Multivariate Test] permet également d’identifier l’élément qui impacte le plus le succès de l’activité.

Le test multivarié vous permet de découvrir l’influence relative de certains éléments sur la conversion par rapport à d’autres éléments de la page. Les tests multivariés peuvent également vous aider à affiner une combinaison d’éléments qui se sont avérés efficaces.

Par rapport à un test A/B, un [!UICONTROL Multivariate Test] offre la possibilité de montrer les éléments de votre page qui ont la plus grande influence sur la conversion. Cet avantage est également connu sous le nom d’« effet principal ». Ces informations sont utiles, par exemple, pour vous aider à déterminer où placer le contenu qui doit recevoir le plus d’attention.

Les activités [!UICONTROL Multivariate Test] vous aident également à trouver des effets composés entre plusieurs éléments d’une page. Par exemple, une publicité spécifique peut produire plus de conversions lorsqu’elle est combinée avec une bannière spécifique ou l’image d’un héros. Cet effet est également connu sous le nom « d’effet d’interaction ».

[!DNL Target] utilise des tests multivariés factoriels complets pour vous permettre d’optimiser le contenu. Un test multivarié full-factoriel examine toutes les combinaisons possibles de contenu avec une probabilité égale. Par exemple, en présence de deux éléments de page comportant trois offres chacun, vous obtenez neuf combinaisons possibles (3x3). Trois éléments, dont deux contiennent trois offres possibles et un deux offres, fournissent 18 options (3x3x2).

En [!DNL Target], chaque combinaison est une expérience. Le [!UICONTROL Multivariate Test] compare chaque expérience afin que vous puissiez identifier les combinaisons les plus réussies. En même temps, les données sont collectées et analysées afin de comprendre comment chaque emplacement et les offres influencent la mesure de succès.

![image multivariée](assets/multivariate.png)

En raison du nombre de combinaisons pouvant être générées, un [!UICONTROL Multivariate Test] nécessite plus de temps et de trafic qu’un test A/B. La page doit recevoir un volume suffisant de trafic pour produire des résultats statistiquement significatifs pour chaque expérience. Pour obtenir des résultats utiles, vous devez comprendre la quantité de trafic que votre page reçoit et tester le nombre optimal de combinaisons pendant le temps approprié pour obtenir les résultats requis.

L’[estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) de Target peut vous aider à concevoir un test qui fonctionne avec votre trafic. Avant d’utiliser l’estimateur de trafic, vous devez être en possession de statistiques fiables présentant le nombre d’impressions et de conversions que votre site reçoit normalement. Examinez les niveaux de trafic par jour. Plus une activité comporte d’expériences, plus elle doit inclure de trafic ou son exécution doit durer. Si le volume de trafic n’est pas élevé, vous devez tester quelques combinaisons, sinon le temps nécessaire pour obtenir des résultats de test significatifs pourrait être trop long pour être utile.

## Terminologie MVT {#section_DF475CA7F34B4CFDB7BE7363761D64AE}

Lors de la configuration d’un test multivarié, il est utile de comprendre la terminologie de base.

Dans l’industrie, il existe plusieurs termes utilisés de manière différente. Cette section définit les termes utilisés par [!DNL Target].

**Combinaison :** variations de contenu créées lorsque vous testez plusieurs options de contenu à plusieurs emplacements. Par exemple, si vous testez trois emplacements, chacun avec trois options de contenu, il existe alors 27 combinaisons possibles (3x3x3). Un visiteur ou une visiteuse de votre site voit une combinaison, également appelée expérience.

**Contenu :** texte ou image comprenant une variation de test dans un emplacement. Dans un test multivarié, plusieurs options de contenu à plusieurs emplacements sont comparées. Dans la méthodologie du test multivarié, le contenu est parfois référencé en tant que *niveau*.

**Élément :** élément DOM contenant des variations de contenu à tester dans le test multivarié. Voir aussi *Emplacement*.

**Emplacement :** zone de contenu spécifique sur une page, souvent contenue par un seul élément DOM. Dans la méthodologie du test multivarié, un emplacement est parfois référencé en tant que *facteur*. Un test multivarié factoriel complet compare toutes les combinaisons possibles d’offres dans vos emplacements.

## Quand utiliser [!UICONTROL Multivariate Test] ou A/B {#section_3D2B966B6671406C861A1843EA41D28C}

Vous pouvez utiliser les tests multivariés avec les tests A/B afin d’optimiser votre page. Vous trouverez ci-dessous des exemples d’utilisation conjointe :

* Utilisez un test A/B pour optimiser la mise en page, suivi d’un test MVT pour déterminer le meilleur contenu dans chaque élément de la page.

  Un test A/B peut fournir des commentaires importants sur la disposition et un test multivarié excelle lors du test du contenu dans les éléments de conception de la page. L’exécution d’un test A/B sur la mise en page avant de tester plusieurs options de contenu peut vous aider à déterminer la meilleure mise en page et le contenu le plus pertinent.

* Utilisez un test multivarié pour déterminer l’élément qui est le plus important, puis exécutez un test A/B plus ciblé sur cet élément.

  Lorsque le nombre d’expériences différentes dépasse cinq et s’étend sur deux éléments ou plus, il est préférable d’envisager de réaliser un test MVT avant d’exécuter vos tests A/B. Le test MVT indique les zones de la page qui sont les plus susceptibles d’améliorer la conversion. Il s’agit des éléments sur lesquels un spécialiste du marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’élément le plus important pour atteindre vos objectifs. Une fois que vous avez déterminé les éléments et le contenu les plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner davantage les résultats. Par exemple, vous pouvez tester deux images spécifiques l’une par rapport à l’autre ou comparer le libellé ou les couleurs d’un call to action. En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Considérations  {#section_979FE3F398654C1EA1C86E7DBC9A8DAD}

* Utilisez un test multivarié lorsque vous avez au moins trois éléments à tester. Si vous en avez moins, exécutez une série de tests A/B.
* Sélectionnez les éléments de page qui, selon vous, ont le plus d’impact sur les résultats.
* N’incluez pas un trop grand nombre d’éléments ou d’emplacements dans un test. Plus le nombre est élevé, plus la durée du test est longue.
* Planifiez la conception du test à l’avance. Ne modifiez pas un test une fois qu’il est en ligne et que les données commencent à être collectées et analysées.
* Les éléments doivent être indépendants les uns des autres.

  Par exemple, ne vérifiez pas la disposition et le contenu dans le même test.

* Prévoyez du temps supplémentaire pour l’assurance qualité en raison de l’augmentation du nombre d’expériences. Vous pouvez également utiliser le test factoriel partiel pour réduire la quantité de trafic nécessaire à un test multivarié. Pour plus d’informations, voir Test factoriel partiel ci-dessous :

## Test factoriel partiel

[!DNL Target] propose des tests multivariés factoriels complets comme option d’activité intégrée. Dans les statistiques,
La « conception d’expériences » propose de nombreuses approches, ou conceptions, pour déterminer les facteurs qui influencent les résultats. Une telle approche est la [méthode de Taguchi](https://en.wikipedia.org/wiki/Taguchi_methods) pour les tests partiels factoriels. Taguchi permet aux professionnels du marketing de formuler un ensemble d’hypothèses qui réduisent le nombre de permutations d’expériences à tester et, par conséquent, réduisent les exigences de trafic pour un test multivarié. Cette fonctionnalité et cette approche de test peuvent être appliquées dans [!DNL Target] à l’aide de cette feuille de calcul [ hors ligne ](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Si votre équipe utilise d’autres approches de design d’expériences, vous pouvez utiliser cette feuille de calcul comme implémentation de référence pour des designs d’expériences personnalisés.

Lorsque vous utilisez la feuille de calcul hors ligne, tenez compte des conseils suivants :

* Sélectionnez les éléments à modifier et le nombre de versions de chaque élément (3x2, 4x3, etc.).
* Gardez une numérotation cohérente. Par exemple, si le bouton est l’élément 1 et que les options sont Bleu, Vert et Jaune, le bouton bleu correspond à 1-1, le bouton vert à 1-2 et le bouton jaune à 1-3.
* La feuille de calcul hors ligne propose le nombre approprié d’expériences nécessaires (quatre pour un 3 x 2, neuf pour un 4 x 3, etc.).
* Créez les expériences dans le workflow A/B avec le [Compositeur d’expérience visuelle (VEC)](/help/main/c-experiences/experiences.md). Vous pouvez utiliser du code personnalisé, modifier du HTML, WYSIWYG ou toute combinaison.
* Une fois l’activité terminée (en fonction du calculateur de taille d’échantillon), exécutez les résultats dans la feuille de calcul pour obtenir les autres détails.

Pour d’autres considérations ainsi que des bonnes pratiques, voir [Bonnes pratiques du test multivarié](/help/main/c-activities/c-multivariate-testing/best-practices.md#reference_53635817FFB741EF8C4E56CC70688EDD).

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Types d’activités (9:03) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo de présentation explique les types d’activités disponibles dans [!DNL Target]. Le test multivarié est discuté à partir de 4:20.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Création de tests multivariés (9:25) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment comprendre, planifier et créer un test multivarié à l’aide du workflow guidé en trois étapes Target.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)
