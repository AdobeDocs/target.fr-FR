---
keywords: a/b;a/a;aa;
description: Avant d’effectuer un test A/A sur votre site à l’aide d’Adobe Target, il est important de comprendre ce qu’est un test A/A, pourquoi vous souhaitez peut-être effectuer un test A/A, combien de temps vous devez exécuter le test et comment interpréter les résultats.
title: Test A/A
feature: A/B Tests
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 1%

---


# Test A/A

Avant d’exécuter un test A/A sur votre site à l’aide de [!DNL Adobe Target], il est important de comprendre ce qu’est un test A/A, pourquoi vous souhaitez peut-être effectuer un test A/A, combien de temps vous devez exécuter le test et comment interpréter les résultats.

## Qu’est-ce que le test A/A ?

Avant d’expliquer les tests A/A, il est bon de passer en revue les tests A/B afin que nous puissions discuter des différences.

Dans un test A/B standard, le trafic est affecté à plusieurs expériences différentes. Une expérience est généralement le &quot;contrôle&quot; et les variations de l’expérience sont testées par rapport au contrôle afin de déterminer l’expérience qui crée le plus d’effet élévateur dans une mesure donnée.

Le test A/A, cependant, implique l’affectation du trafic à deux expériences identiques, généralement avec une répartition 50/50 de l’affectation du trafic. Avec un test A/B standard, vous souhaitez généralement découvrir un effet élévateur dans la conversion. Ceci diffère d’un test A/A dans lequel votre objectif est généralement de déterminer qu’il y a *aucune* différence d’effet élévateur entre les expériences identiques.

## Pourquoi voudriez-vous tester deux expériences identiques et qu’est-ce que cela accomplit ?

Certaines organisations effectuent des tests A/A lors de la mise en oeuvre d&#39;un nouvel outil de test, tel que [!DNL Target], pour déterminer si :

* L&#39;activité a été correctement configurée.
* Le code a été implémenté correctement.
* Le rapports est précis

Bien que peu d’entreprises exécutent des tests A/A, il est en fait recommandé de les exécuter comme des expériences de &quot;santé mentale&quot; afin de créer de la confiance après la mise en oeuvre de l’outil ou avant d’effectuer des tests A/B qui pourraient avoir un impact sur la conversion et les recettes.

## Pourquoi l’effet élévateur d’une expérience est-il visible lorsque les expériences sont identiques ?

Il existe de nombreuses raisons pour lesquelles l’effet élévateur peut s’afficher dans une expérience par rapport à une autre expérience (identique) :

### Le test A/A n&#39;a pas été autorisé à s&#39;exécuter suffisamment longtemps.

L’arrêt prématuré d’un test et la déclaration d’une expérience gagnante constituent un problème courant lors de l’exécution de tout type de test, y compris d’un test A/A. Les analystes font souvent ce qu&#39;on appelle &quot;l&#39;examen des données&quot;. L’analyse des données implique de consulter les données de test de manière précoce et fréquente tout en essayant de déterminer quelle expérience est la plus performante. Le risque est de stopper prématurément le test, ce qui pourrait invalider les résultats.

Dans un test A/A, l’observation des données peut souvent amener les analystes à voir l’effet élévateur dans une expérience, lorsqu’ils supposent qu’il ne devrait y avoir aucune différence, car les deux expériences sont identiques. Compte tenu du temps et des visites suffisantes, la différence d’effet élévateur devrait diminuer.

Comme dans le cas d’un test A/B classique, vous devez donc décider à l’avance de la taille de l’échantillon à utiliser, en fonction de la taille minimale de l’effet, de la puissance et des niveaux de signification que vous jugez acceptables. Dans un test A/A, l’objectif serait alors de *ne pas* voir un résultat statistiquement significatif une fois que votre test aura atteint la taille d’échantillon souhaitée.

Le [!UICONTROL calculateur de taille d’échantillon d’Adobe Target] est un outil important pour vous aider à déterminer la taille d’échantillon à cibler et la durée d’exécution du test.

* [Calculatrice de taille Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

En outre, consultez les articles suivants pour en savoir plus sur la durée d’exécution d’une activité, ainsi que d’autres conseils et astuces utiles :

* [Quelle doit être la durée d’exécution d’un test A/B ?](/help/c-activities/t-test-ab/sample-size-determination.md)
* [Dix pièges A/B courants et comment les éviter](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### La signification statistique a un impact sur les résultats du test.

Le degré de signification d&#39;un test détermine la probabilité que le test signale une différence significative de taux de conversion entre deux offres différentes alors qu&#39;en fait il n&#39;y a pas de différence réelle. Il s’agit d’un faux positif ou d’une erreur de type I. Le niveau de signification est un seuil spécifié par l’utilisateur et il existe un compromis entre la tolérance pour les faux positifs et le nombre de visiteurs qui doivent être inclus dans le test pour choisir le niveau de signification approprié.

Un niveau de signification couramment utilisé dans les tests A/A et A/B est de 5 %, ce qui correspond à un niveau de confiance de 95 % (niveau de confiance = 100 % - degré de signification). Un degré de confiance de 95 % signifie que chaque fois que vous effectuez un test, il y a une probabilité de 5 % de détecter un effet élévateur statistiquement significatif, même s’il n’y a aucune différence entre les expériences.

Supposons que vous souhaitiez atteindre un niveau de confiance de 95 % avec votre test A/A. Avec un niveau de confiance de 95 %, 1 test A/A sur 20 peut présenter un effet élévateur statistiquement significatif sur les conversions. Avec un degré de confiance de 90 %, 1 test sur 10 peut afficher un effet élévateur des conversions lors du test d’expériences identiques.

## Bonne pratique

Si vous décidez qu’un test A/A est nécessaire dans votre entreprise, sachez que les expériences identiques peuvent temporairement montrer une différence par rapport au contrôle. Cela peut être normal, selon le moment où le test est autorisé à s’exécuter. La différence devrait diminuer avec plus de temps et de visiteurs.

Il est recommandé d’utiliser une méthodologie de test A/B standard : déterminez la taille de l’échantillon à l’avance en fonction d’une taille d’effet minimale, de la puissance et de la signification souhaitées à l’aide du [calculateur de taille d’Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Ensuite, prévoyez suffisamment de temps et de visiteurs avant d’en arriver à une conclusion. N’oubliez pas que, selon le niveau de signification de votre test, il est possible qu’une expérience montre une différence d’effet élévateur et soit même déclarée gagnante.
