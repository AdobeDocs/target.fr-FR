---
keywords: a/b;a/a;aa;
description: Découvrez ce qu’est un test A/A, pourquoi vous souhaitez peut-être exécuter un test A/A, combien de temps vous devez exécuter le test et comment interpréter les résultats.
title: Qu’est-ce que le test A/A ?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 4f0ebdd06287a438e519d9bccb677ab1a9093396
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 1%

---

# Test A/A

Avant d’exécuter un test A/A sur votre site à l’aide de [!DNL Adobe Target], il est important de comprendre ce qu’est un test A/A, pourquoi vous souhaitez peut-être exécuter un test A/A, combien de temps vous devez exécuter le test et comment interpréter les résultats.

## Qu’est-ce que le test A/A ?

Avant d’expliquer les tests A/A, il est conseillé de passer en revue les tests A/B afin de pouvoir discuter des différences.

Dans un test A/B standard, le trafic est affecté à plusieurs expériences différentes. Une expérience correspond généralement au &quot;contrôle&quot; et des variantes de l’expérience sont testées par rapport au contrôle afin de déterminer l’expérience qui crée le plus d’effet élévateur dans une mesure donnée.

Le test A/A implique toutefois d’affecter le trafic à deux expériences identiques, généralement avec une répartition 50/50 de trafic. Avec un test A/B standard, vous souhaitez généralement découvrir un effet élévateur en conversion. Cela diffère d’un test A/A dont l’objectif est généralement de déterminer qu’il existe *aucune* différence d’effet élévateur entre les expériences identiques.

## Pourquoi voudrais-tu tester deux expériences identiques et qu’est-ce que cela accomplit ?

Certaines organisations effectuent des tests A/A lors de l’implémentation d’un nouvel outil de test, tel que [!DNL Target], pour déterminer si :

* L’activité a été correctement configurée.
* Le code a été correctement implémenté.
* Les rapports sont précis

Bien que peu d’entreprises exécutent des tests A/A, il est recommandé de les exécuter en tant qu’expériences de &quot;santé mentale&quot; afin de créer de la confiance après la mise en oeuvre de l’outil ou avant d’effectuer des tests A/B susceptibles d’avoir un impact sur la conversion et les recettes.

## Pourquoi l’effet élévateur d’une expérience s’affiche-t-il lorsque les expériences sont identiques ?

Il existe de nombreuses raisons pour lesquelles vous pouvez voir un effet élévateur dans une expérience par rapport à une autre expérience (identique) :

### Le test A/A a été surveillé en permanence.

Un problème courant lors de l’exécution de tout type de test, y compris un test A/A, consiste à examiner les résultats en permanence, et à arrêter prématurément un test lorsque vous constatez une signification statistique, puis à déclarer une expérience gagnante. Les analystes font souvent ce qu&#39;on appelle la &quot;recherche de données&quot;. La recherche de données implique d’examiner les données de test de manière précoce et fréquente tout en essayant de déterminer l’expérience la plus performante. Le risque est d&#39;arrêter le test de manière prématurée, ce qui pourrait invalider les résultats.

Dans un test A/A, la recherche de données peut souvent amener les analystes à voir l’effet élévateur dans une expérience, alors qu’en fait il ne devrait y avoir aucune différence, car les deux expériences sont identiques. En fait, avec un contrôle continu, les tests A/A sont *garantis* pour montrer une &quot;signification statistique&quot; (à savoir, un degré de confiance supérieur à un certain seuil, comme 95 %) à un moment donné pendant le test.

Pour éviter cela, et comme pour un test A/B classique, vous devez donc décider à l’avance quelle taille d’échantillon utiliser, en fonction de la taille d’effet minimale (l’effet élévateur minimal en dessous duquel un effet n’est pas important pour votre entreprise), de la puissance et des niveaux de pertinence que vous trouvez acceptables.

Dans un test A/A, l’objectif serait alors de *ne pas* voir un résultat statistiquement significatif une fois que votre test aura atteint la taille d’échantillon souhaitée.

[!UICONTROL Adobe Target Sample Size Calculator] est un outil important pour vous aider à déterminer la taille d’échantillon à cibler et la durée d’exécution du test.

* [Calculateur de taille Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

En outre, consultez les articles suivants pour plus d’informations sur la durée d’exécution d’une activité, ainsi que d’autres conseils et astuces utiles :

* [Quelle doit être la durée d’exécution d’un test A/B ?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Dix écueils A/B courants et comment les éviter](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### La signification statistique a un impact sur les résultats du test.

Le niveau de pertinence d’un test détermine la probabilité que le test signale une différence significative de taux de conversion entre deux offres différentes alors qu’en fait, il n’y a aucune différence réelle. On parle alors de faux positif ou d’erreur de type I. Le niveau de pertinence est un seuil spécifié par l’utilisateur et il existe un compromis entre la tolérance pour les faux positifs et le nombre de visiteurs qui doivent être inclus dans le test pour choisir le niveau de pertinence approprié.

Le degré de pertinence le plus souvent utilisé dans les tests A/A et A/B est de 5 %, ce qui correspond à un degré de confiance de 95 % (degré de confiance = 100 % - niveau de pertinence). Un degré de confiance de 95 % signifie que chaque fois que vous effectuez un test, il existe une probabilité de 5 % de détecter un effet élévateur statistiquement significatif, même s’il n’y a aucune différence entre les expériences.

Supposons que vous souhaitiez atteindre un degré de confiance de 95 % avec votre test A/A. Avec un degré de confiance de 95 %, 1 test A/A sur 20 peut présenter un effet élévateur statistiquement significatif dans les conversions. Avec un degré de confiance de 90 %, 1 test sur 10 peut afficher un effet élévateur dans les conversions lors du test d’expériences identiques.

## Bonne pratique

Si vous décidez qu’un test A/A est nécessaire dans votre entreprise, sachez que les expériences identiques peuvent temporairement montrer une différence par rapport au contrôle. Cela peut être normal, en fonction de la période d’exécution du test. La différence devrait diminuer au fur et à mesure que les visiteurs et le temps passeront.

La bonne pratique consiste à utiliser une méthodologie de test A/B standard : choisissez la taille de l’échantillon à l’avance en fonction d’une taille d’effet minimale, de la puissance souhaitée et de la signification en utilisant le [calculateur de taille Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Accordez ensuite un temps suffisant et aux visiteurs avant d’arriver à une conclusion. N’oubliez pas que selon le niveau de pertinence de votre test, il est possible qu’une expérience montre une différence d’effet élévateur, voire qu’elle soit déclarée gagnante.
