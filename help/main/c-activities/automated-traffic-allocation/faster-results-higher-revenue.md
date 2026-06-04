---
keywords: affectation automatique du trafic;ciblage;affectation automatique;affectation automatique
description: Découvrez comment une activité [!UICONTROL Affectation automatique] dans  [!DNL Adobe Target]  identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement davantage de trafic au gagnant.
title: Les activités [!UICONTROL  Affectation automatique ] peuvent-elles obtenir des résultats plus rapides et un chiffre d’affaires plus élevé ?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 560
ht-degree: 0%

---

# L’[!UICONTROL  Affectation automatique] vous donne des résultats de test plus rapides et un chiffre d’affaires plus élevé qu’un test manuel

Avec une activité A/B manuelle, vous risquez de perdre des conversions, car vous ne pouvez pas diffuser l’expérience gagnante à l’ensemble de votre audience tant que l’activité n’est pas terminée. Votre distribution du trafic reste fixe même après avoir reconnu que certaines expériences sont plus performantes que d’autres, et l’activité doit exécuter l’intégralité de son cours avant que vous puissiez agir sur une expérience gagnante.

## Affectation automatique du trafic

Si vous souhaitez qu’une option soit utilisée plus souvent et plus tôt dans l’activité pour l’expérience gagnante, tout en supprimant ou en réduisant simultanément le coût de configuration et de calcul du prélèvement de tailles d’échantillon, de niveaux de confiance et d’autres concepts statistiques, l’[!UICONTROL  Affectation automatique ] est votre meilleure option.

## Comment fonctionne l’[!UICONTROL affectation automatique] ?

[!UICONTROL Affectation automatique] utilise le principe du bandit manchot. Si le terme n&#39;est pas familier, un bandit manchot est un terme familier pour une machine à sous (pensez : Las Vegas). Visualisez l’affectation automatique du trafic comme ayant plusieurs machines à sous, dans ce cas, des variations de test, et en tirant d’abord toutes les poignées de manière égale. Au fil du temps, une ou plusieurs machines, ou variantes de test, peuvent payer plus que d’autres. Lorsque cette situation se produit, un joueur commencerait naturellement à tirer les poignées de ceux qui gagnent plus souvent. En termes d’affectation du trafic, [!DNL Target] offre à davantage de visiteurs l’expérience ou les expériences qui en valent davantage.

Examinons l’illustration suivante d’une activité A/B de deux semaines. Grâce à l’[!UICONTROL affectation automatique], au fur et à mesure que l’expérience gagnante se présente, [!UICONTROL Target] détourne une plus grande partie du trafic vers ce gagnant dès le début du test.

![illustration de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Comment l’[!UICONTROL affectation automatique] offre-t-elle des résultats plus rapides ?

L’avantage est clair : davantage de visiteurs voient les variations qui ont les meilleures performances. Et lorsqu’une seule variation prend de l’avance, encore plus de visiteurs sont détournés vers cette expérience gagnante, pendant que le test était toujours en cours. Cette méthode s’avère particulièrement utile si l’activité A/B en cours d’exécution se produit pendant un moment clé de l’activité, tel qu’un jour férié, le lancement d’un produit ou un événement d’actualité mondiale.

## Comment l’[!UICONTROL affectation automatique] peut-elle générer des recettes plus élevées ?

L’[!UICONTROL Affectation automatique] identifie le gagnant plus rapidement qu’une répartition A/B manuelle et vous permet également d’exploiter ce gagnant en capturant immédiatement les revenus à la hausse qui auraient été perdus dans une approche traditionnelle ou manuelle. Comme l’[!UICONTROL affectation automatique] dirige davantage de trafic vers l’expérience avec le taux de conversion le plus élevé, elle peut augmenter votre chiffre d’affaires pendant que l’activité s’exécute et apprend.

Dans l’exemple suivant, l’[!UICONTROL  Affectation automatique ] a généré plus de chiffre d’affaires pendant le test en poussant plus de trafic (40 %) vers l’expérience D, qui avait le taux de conversion le plus élevé.

![ L’affectation automatique fournit une illustration de chiffre d’affaires plus élevé](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Dans quels cas dois-je m’en tenir à l’affectation manuelle du trafic ?

Lorsque vous devez classer les performances de chaque expérience par rapport aux autres, un test A/B manuel est le plus approprié. L’[!UICONTROL affectation automatique] trouve et exploite les meilleures performances, mais ne garantit pas la différenciation entre les expériences les moins performantes. Utilisez l’affectation manuelle du trafic pour contrôler entièrement la proportion de votre trafic visiteur qui voit chaque variante de test et pour personnaliser les seuils statistiques pertinents pour votre entreprise.

## Prise en main

Prêt à lancer votre première activité [!UICONTROL  Affectation automatique ] ? [Découvrez comment ici](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
