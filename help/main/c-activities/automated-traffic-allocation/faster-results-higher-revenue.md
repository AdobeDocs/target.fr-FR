---
keywords: affectation automatique du trafic;ciblage;affectation automatique;affectation automatique
description: Découvrez comment une activité [!UICONTROL Affectation automatique] dans [!DNL Adobe Target] identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement davantage de trafic au gagnant.
title: Les activités d’[!UICONTROL affectation automatique] peuvent-elles obtenir des résultats plus rapides et un chiffre d’affaires plus élevé ?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: 'https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%
---
# Comment l’affectation automatique  surpasse un test manuel {#faster-results-higher-revenue}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez pourquoi une activité d’**[!UICONTROL affectation automatique]** peut fournir des résultats plus rapides et un chiffre d’affaires plus élevé qu’un test A/B manuel, comment elle fonctionne et quand l’affectation manuelle du trafic reste le meilleur choix.

>[!ENDSHADEBOX]

Avec une activité A/B manuelle, vous risquez de perdre des conversions, car vous ne pouvez pas diffuser l’expérience gagnante à l’ensemble de votre audience tant que l’activité n’est pas terminée. Votre distribution du trafic reste fixe même après avoir reconnu que certaines expériences sont plus performantes que d’autres, et l’activité doit exécuter l’intégralité de son cours avant que vous puissiez agir sur une expérience gagnante.

## Affectation automatique du trafic {#auto-allocating-traffic}

L’**[!UICONTROL affectation automatique]** est la meilleure option si vous souhaitez diffuser l’expérience gagnante plus souvent et plus tôt dans l’activité, tout en supprimant ou en réduisant les coûts de configuration et de calcul liés au choix de la taille des échantillons, des niveaux de confiance et d’autres concepts statistiques.

## Comment fonctionne l’[!UICONTROL affectation automatique] ? {#how-it-works}

**[!UICONTROL L’affectation automatique]** utilise le principe du bandit manchot. Un bandit manchot est un terme familier pour une machine à sous. Considérez l’affectation automatique du trafic comme un ensemble de machines à sous, dans ce cas des variations de test, dont les poignées sont tirées de manière égale au début. Au fil du temps, une ou plusieurs machines, ou variantes de test, peuvent payer plus que d’autres. Lorsque cette situation se produit, un joueur commence naturellement à tirer les poignées des machines qui gagnent plus souvent. En termes d’affectation du trafic, [!DNL Target] offre à davantage de visiteurs l’expérience ou les expériences qui gagnent le plus.

L’illustration suivante présente une activité A/B de deux semaines. Avec l’affectation automatique **[!UICONTROL 1&rbrace;, à mesure qu’une expérience gagnante se présente, [!DNL Target] détourne une plus grande partie du trafic vers cette expérience gagnante au début du test.]**

![Illustration de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Comment l’[!UICONTROL affectation automatique] fournit-elle des résultats plus rapides ? {#faster-results}

Plus de visiteurs voient les variations les plus performantes. Lorsqu’une seule variation prend de l’avance, encore plus de visiteurs sont redirigés vers cette expérience gagnante pendant que le test est toujours en cours d’exécution. Cette méthode s’avère particulièrement utile si l’activité A/B s’exécute à un moment clé de l’activité, comme un jour férié, le lancement d’un produit ou un événement lié à l’actualité mondiale.

## Comment l’[!UICONTROL affectation automatique] peut-elle augmenter le chiffre d’affaires ? {#higher-revenue}

**[!UICONTROL L’affectation automatique]** trouve le gagnant plus rapidement qu’une division A/B manuelle et vous permet d’exploiter immédiatement ce gagnant, en capturant les revenus à la hausse qui auraient été perdus dans une approche traditionnelle ou manuelle. L’**[!UICONTROL affectation automatique]** dirige davantage de trafic vers l’expérience présentant le taux de conversion le plus élevé, afin qu’elle puisse augmenter votre chiffre d’affaires pendant que l’activité s’exécute et apprend.

Dans l’exemple suivant, l’affectation automatique **[!UICONTROL 1&rbrace; a gagné davantage de chiffre d’affaires au cours du test en poussant plus de trafic (40 %) vers l’expérience D, qui avait le taux de conversion le plus élevé.]**

![L’affectation automatique fournit une illustration de chiffre d’affaires plus élevé](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Dans quels cas dois-je m’en tenir à l’affectation manuelle du trafic ? {#manual-allocation}

Un test A/B manuel est l’option la plus applicable lorsque vous devez classer les performances de chaque expérience par rapport aux autres. L’affectation automatique **[!UICONTROL 1&rbrace; trouve et exploite les meilleures performances, mais ne garantit pas la différenciation entre les expériences les moins performantes.]** Utilisez l’affectation manuelle du trafic pour contrôler entièrement la proportion de votre trafic visiteur qui voit chaque variante de test et pour personnaliser les seuils statistiques pertinents pour votre entreprise.

## Prise en main {#get-started}

Prêt à lancer votre première activité d’**[!UICONTROL affectation automatique]** ? Voir [Création d’une activité d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) et la [présentation de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
