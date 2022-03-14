---
keywords: test multivarié;mvt;factoriel complet;mvt ou a/b;a/b multivarié;estimateur de trafic;quand utiliser mvt;considérations sur mvt;multivarié;factoriel partiel;factoriel partiel;factoriel complet
description: Découvrez comment utiliser Multivariate Testing (MVT) dans Adobe [!DNL Target] pour comparer des combinaisons d’offres dans des éléments d’une page afin de déterminer la combinaison offrant les meilleures performances.
title: Qu’est-ce qu’un test multivarié ?
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1460'
ht-degree: 88%

---

# Présentation du test multivarié

Le [!UICONTROL test multivarié] (MVT) dans [!DNL Adobe Target]compare des combinaisons d’offres d’éléments sur une page afin de déterminer la combinaison offrant les meilleures performances pour une audience spécifique. Il identifie l’élément qui impacte le plus le succès de l’activité.

## Présentation des MVT {#section_C73A2D1409EC42C9B0EDD4B976651C5E}

Les tests multivariés vous permettent de découvrir l’influence relative que les éléments spécifiques ont sur la conversion, par rapport à d’autres éléments sur la page. Cela peut également vous aider à affiner la combinaison d’éléments présentés comme étant efficaces.

Un avantage que le test multivarié présente par rapport au test A/B est la possibilité de vous montrer les éléments de la page qui ont la plus grande influence sur la conversion. Cet effet est également connu sous le nom « d’effet principal ». Ces informations sont utiles, par exemple en vous aidant à déterminer où placer du contenu pour lequel vous souhaitez recevoir le plus d’attention.

Les tests multivariés vous aident également à trouver des effets composés entre plusieurs éléments d’une page. Par exemple, une publicité spécifique peut produire plus de conversions lorsqu’elle est combinée avec une bannière spécifique ou l’image d’un héros. Cet effet est également connu sous le nom « d’effet d’interaction ».

[!DNL Target] utilise des tests multivariés factoriels complets pour vous permettre d’optimiser le contenu. Un test multivarié factoriel complet teste toutes les combinaisons possibles de contenu avec une probabilité égale. Par exemple, en présence de deux éléments de page comportant trois offres chacun, vous obtenez neuf combinaisons possibles (3x3). Trois éléments, dont deux contiennent trois offres possibles et un deux offres, fournissent 18 options (3x3x2).

Dans Target, chaque combinaison est une expérience. Le test multivarié compare chaque expérience afin que vous puissiez découvrir les combinaisons qui sont les plus réussies. En même temps, les données sont collectées et analysées afin de comprendre comment chaque emplacement et les offres influencent la mesure de succès.

![](assets/multivariate.png)

En raison du nombre de combinaisons qui peut être généré, un test multivarié nécessite plus de temps et de trafic qu’un test A/B. La page doit recevoir un volume suffisant de trafic pour produire des résultats statistiquement significatifs pour chaque expérience. Pour obtenir des résultats utiles, vous devez comprendre le volume de trafic que votre page reçoit et tester le nombre optimal de combinaisons pendant la durée appropriée pour obtenir les résultats requis. L’[estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) de Target peut vous aider à concevoir un test qui fonctionne avec votre trafic. Avant d’utiliser l’estimateur de trafic, vous devez être en possession de statistiques fiables présentant le nombre d’impressions et de conversions que votre site reçoit normalement. Examinez les niveaux de trafic par jour. Plus une activité comporte d’expériences, plus l’activité doit inclure de trafic ou plus sa durée d’exécution doit être longue. Si le trafic n’est pas très élevé, vous devez tester un petit nombre de combinaisons. Sinon, la durée requise pour produire des résultats de test significatifs sera peut-être trop longue pour être utile.

## Terminologie des MVT {#section_DF475CA7F34B4CFDB7BE7363761D64AE}

Lors de la configuration d’un test multivarié, il est utile de comprendre la terminologie de base.

Dans l’industrie, il existe plusieurs termes utilisés de manière différente. Cette section définit les termes utilisés par [!DNL Target].

**Combinaison :** variations de contenu créées lorsque vous testez plusieurs options de contenu à plusieurs emplacements. Par exemple, si vous testez trois emplacements, chacun avec trois options de contenu, il existe alors 27 combinaisons possibles (3x3x3). Un visiteur de votre site verra une combinaison, également référencée en tant qu’expérience.

**Contenu :** texte ou image comprenant une variation de test dans un emplacement. Dans un test multivarié, un certain nombre d’options de contenu dans plusieurs emplacements sont comparées. Dans la méthodologie du test multivarié, le contenu est parfois référencé en tant que *niveau*.

**Élément :** élément DOM contenant des variations de contenu à tester dans le test multivarié. Voir aussi *Emplacement*.

**Emplacement :** zone de contenu spécifique sur une page, souvent contenue par un seul élément DOM. Dans la méthodologie du test multivarié, un emplacement est parfois référencé en tant que *facteur*. Un test multivarié factoriel complet compare toutes les combinaisons possibles d’offres dans vos emplacements.

## Quand utiliser le test multivarié et le test A/B {#section_3D2B966B6671406C861A1843EA41D28C}

Vous pouvez utiliser les tests multivariés avec les tests A/B afin d’optimiser votre page. Vous trouverez ci-dessous des exemples d’utilisation conjointe :

* Utilisez un test A/B pour optimiser la disposition de la page suivi par un test multivarié pour déterminer le meilleur contenu dans chaque élément de la page..

   Un test A/B peut fournir des commentaires importants sur la disposition et un test multivarié excelle lors du test du contenu dans les éléments de conception de la page. L’exécution d’un test A/B sur la disposition avant de tester plusieurs options de contenu peut vous aider à déterminer la meilleure disposition et le contenu ayant le plus d’impact.

* Utilisez un test multivarié pour déterminer l’élément qui est le plus important, puis exécutez un test A/B plus ciblé sur cet élément.

   Lorsque le nombre d’expériences différentes dépasse cinq et qu’elles couvrent plusieurs éléments, il est préférable d’envisager un test multivarié avant d’exécuter vos tests A/B. Le test MVT indique les zones de la page qui sont les plus susceptibles d’améliorer la conversion. Il s’agit des éléments sur lesquels un spécialiste du marketing doit se concentrer. Par exemple, le test multivarié peut indiquer que l’incitation à l’action est l’élément le plus important pour atteindre vos objectifs. Une fois que vous avez déterminé les éléments et le contenu qui sont le plus utiles pour permettre d’atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner encore plus les résultats, par exemple pour tester deux images spécifiques l’une par rapport à l’autre ou pour comparer les termes ou les couleurs d’une incitation à l’action. En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

## Considérations  {#section_979FE3F398654C1EA1C86E7DBC9A8DAD}

* Utilisez un test multivarié lorsque vous avez au moins trois éléments à tester. Si vous n’en n’avez pas autant, exécutez une série de Tests A/B.
* Sélectionnez les éléments de page qui, selon vous, auront le plus gros impact sur les résultats.
* N’incluez pas un trop grand nombre d’éléments ou d’emplacements dans un test. Plus le nombre est élevé, plus la durée du test est longue.
* Planifiez la conception du test à l’avance. Il n’est pas conseillé de modifier un test une fois qu’il est actif et que les données commencent à être collectées et analysées.
* Il est préférable que les éléments soient indépendants les uns des autres.

   Par exemple, ne vérifiez pas la disposition et le contenu dans le même test.

* Prévoyez du temps supplémentaire pour le contrôle qualité en raison de l’augmentation du nombre d’expériences. Vous pouvez également utiliser des tests factoriels partiels pour réduire le volume de trafic nécessaire à un test multivarié. Pour plus d’informations, voir Tests factoriels partiels ci-dessous :

## Test factoriel partiel

[!DNL Target] propose des tests multivariés factoriels complets comme option d’activité intégrée. Dans les statistiques, le design d’expériences propose de nombreuses approches, ou conceptions, qui permettent de déterminer les facteurs influençant les résultats. L&#39;une de ces approches est la suivante : [Méthode Taguchi](https://en.wikipedia.org/wiki/Taguchi_methods) pour les tests factoriels partiels. Cette méthode permet aux marketeurs d’élaborer un ensemble d’hypothèses réduisant le nombre de permutations d’expériences qui doivent être traitées, diminuant ainsi les conditions de trafic requises pour un test multivarié. Cette fonctionnalité et approche de test peut être utilisée dans [!DNL Target] en utilisant cette [feuille de calcul hors ligne](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Si votre équipe utilise d’autres approches de design d’expériences, vous pouvez utiliser cette feuille de calcul comme implémentation de référence pour des designs d’expériences personnalisés.

Lorsque vous utilisez la feuille de calcul hors ligne, tenez compte des conseils suivants :

* Choisissez les éléments que vous voulez modifier et le nombre de versions de chaque élément (3 x 2, 4 x 3 et ainsi de suite).
* Gardez une numérotation cohérente. Par exemple, si le bouton est l’élément 1 et que les options sont Bleu, Vert et Jaune, le bouton bleu correspond à 1-1, le bouton vert à 1-2 et le bouton jaune à 1-3.
* La feuille de calcul hors ligne propose le nombre approprié d’expériences nécessaires (quatre pour un 3 x 2, neuf pour un 4 x 3, etc.).
* Créez les expériences dans le workflow A/B avec le [Compositeur d’expérience visuelle (VEC)](/help/main/c-experiences/experiences.md). Vous pouvez utiliser du code personnalisé, modifier du HTML, WYSIWYG ou toute combinaison.
* Une fois l’activité terminée (en fonction du calculateur de taille d’échantillon), exécutez les résultats à l’aide de la feuille de calcul pour obtenir d’autres détails.

Pour d’autres considérations ainsi que des bonnes pratiques, voir [Bonnes pratiques du test multivarié](/help/main/c-activities/c-multivariate-testing/best-practices.md#reference_53635817FFB741EF8C4E56CC70688EDD).

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Types d’activité (9:03) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo de présentation explique les types d’activité disponibles dans Target Standard/Premium. Les tests multivariés sont abordés dans la vidéo à partir de 4:20.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment comprendre, planifier et créer un test multivarié à l’aide du flux de travaux Target à trois étapes.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)
