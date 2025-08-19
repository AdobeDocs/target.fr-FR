---
keywords: a/b;a/a;aa;
description: Découvrez ce qu’est un test A/A, pourquoi vous souhaitez peut-être en effectuer un, combien de temps vous devez l’exécuter et comment interpréter les résultats.
title: Qu’est-ce que le test A/A ?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 4f0ebdd06287a438e519d9bccb677ab1a9093396
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 1%

---

# Test A/A

Avant d’effectuer un test A/A sur votre site à l’aide de [!DNL Adobe Target], il est important de comprendre ce qu’est un test A/A, pourquoi vous souhaitez peut-être effectuer un test A/A, combien de temps vous devez exécuter le test et comment interpréter les résultats.

## Qu’est-ce que le test A/A ?

Avant d’expliquer les tests A/A, il est préférable de passer en revue les tests A/B afin de pouvoir ensuite discuter des différences.

Dans un test A/B standard, le trafic est affecté à deux expériences différentes ou plus. Une expérience est généralement le « contrôle » et des variations de l’expérience sont testées par rapport au contrôle afin de déterminer quelle expérience crée le plus d’effet élévateur dans une mesure donnée.

Les tests A/A, cependant, impliquent d’allouer le trafic à deux expériences identiques, normalement avec une répartition d’affectation du trafic 50/50. Avec un test A/B standard, vous souhaitez généralement découvrir un effet élévateur lors de la conversion. Cela diffère d’un test A/A dans lequel l’objectif est généralement de déterminer qu’il n’y a *aucune différence*’effet élévateur entre des expériences identiques.

## Pourquoi voudriez-vous tester deux expériences identiques et qu’est-ce que cela accomplit ?

Certaines organisations effectuent des tests A/A lors de la mise en œuvre d’un nouvel outil de test, tel que [!DNL Target], afin de déterminer si :

* L&#39;activité a été correctement paramétrée
* Le code a été correctement implémenté
* Les rapports sont exacts

Bien que peu d’organisations exécutent des tests A/A, il est recommandé de les exécuter en tant qu’expériences « sensées » pour établir la confiance après la mise en œuvre de l’outil ou avant d’effectuer des tests A/B qui pourraient avoir un impact sur la conversion et le chiffre d’affaires.

## Pourquoi un effet élévateur peut-il s’afficher pour une expérience lorsque les expériences sont identiques ?

Il existe de nombreuses raisons pour lesquelles vous pouvez voir l’effet élévateur dans une expérience plutôt que dans une autre (expérience identique) :

### Le test A/A était surveillé en permanence

Un problème courant lors de l’exécution de tout type de test, y compris un test A/A, est d’examiner les résultats en permanence et d’arrêter prématurément un test lorsque vous constatez une signification statistique et que vous déclarez une expérience gagnante. Les analystes font souvent ce qu&#39;on appelle un « examen des données ». La recherche de données consiste à examiner les données de test de manière précoce et fréquente, tout en essayant de déterminer l’expérience la plus performante. Le risque est d’arrêter le test prématurément, ce qui pourrait invalider les résultats.

Dans un test A/A, la recherche de données peut souvent amener les analystes à voir l’effet élévateur dans une expérience, alors qu’en fait il ne devrait y avoir aucune différence, car les deux expériences sont identiques. En fait, avec un aperçu continu, les tests A/A sont *garantis* pour montrer une « signification statistique » (à savoir, un degré de confiance au-dessus d’un certain seuil, tel que 95 %) à un moment donné pendant le test.

Pour éviter cela, et comme pour un test A/B normal, vous devez donc décider à l’avance de la taille de l’échantillon à utiliser, en fonction de la taille minimale de l’effet (l’effet élévateur minimum en dessous duquel un effet n’est pas important pour votre entreprise), de la puissance et des niveaux de signification que vous trouvez acceptables.

Dans un test A/A, l’objectif serait alors de *pas* voir un résultat statistiquement significatif une fois que votre test aurait atteint la taille d’échantillon souhaitée.

Le [!UICONTROL Adobe Target Sample Size Calculator] est un outil important pour vous aider à déterminer la taille d’échantillon à cibler et la durée d’exécution du test.

* [Calculateur de taille d’Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

En outre, consultez les articles suivants pour savoir combien de temps vous devez exécuter une activité et obtenir d’autres conseils et astuces utiles :

* [Quelle doit être la durée d’exécution d’un test A/B ?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Dix pièges courants d’A/B et comment les éviter](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### La signification statistique a un impact sur les résultats de vos tests

Le niveau de pertinence d’un test détermine la probabilité que le test signale une différence significative dans les taux de conversion entre deux offres différentes, alors qu’en fait, il n’y a aucune différence réelle. On parle alors d’erreur de type I ou de faux positif. Le niveau de signification est un seuil spécifié par l’utilisateur. Il existe un compromis entre la tolérance pour les faux positifs et le nombre de visiteurs à inclure dans le test pour choisir le niveau de signification approprié.

Un niveau de signification couramment utilisé dans les tests A/A et A/B est de 5 %, ce qui correspond à un niveau de confiance de 95 % (niveau de confiance = 100 % - niveau de signification). Un niveau de confiance de 95 % signifie que chaque fois que vous effectuez un test, il existe une probabilité de 5 % de détecter une augmentation statistiquement significative, même s’il n’existe aucune différence entre les expériences.

Supposons que vous souhaitiez atteindre un niveau de confiance de 95 % avec votre test A/A. Avec un niveau de confiance de 95 %, 1 test A/A sur 20 pourrait montrer une augmentation statistiquement significative des conversions. Avec un niveau de confiance de 90 %, 1 test sur 10 peut afficher une augmentation des conversions lors du test d’expériences identiques.

## Bonne pratique

Si vous décidez qu’un test A/A est nécessaire dans votre organisation, sachez que des expériences identiques peuvent temporairement montrer une différence par rapport au contrôle. Cela peut être normal, selon la durée d’exécution du test. La différence devrait diminuer avec plus de temps et de visiteurs.

La bonne pratique consiste à utiliser la méthodologie de test A/B régulière : décidez à l’avance de la taille de l’échantillon en fonction de la taille minimale de l’effet pertinent, de la puissance souhaitée et de la signification à l’aide du [Calculateur de taille d’Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Ensuite, prévoyez suffisamment de temps et de visiteurs avant d’arriver à une conclusion, et souvenez-vous que selon le niveau de pertinence de votre test, il est possible qu’une expérience montre une différence d’effet élévateur, et qu’elle soit même déclarée gagnante.
