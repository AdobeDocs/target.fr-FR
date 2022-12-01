---
keywords: affectation automatisée du trafic;ciblage;affectation automatique;affectation automatique
description: Découvrez comment une activité d’affectation automatique dans Adobe [!DNL Target] identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement du trafic supplémentaire vers le gagnant.
title: Les activités d’affectation automatique peuvent-elles obtenir des résultats plus rapides et des recettes plus élevées ?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 2%

---

# L’affectation automatique peut vous donner des résultats de test plus rapides et un chiffre d’affaires plus élevé qu’un test manuel

Avec une activité A/B manuelle, vous risquez de perdre des conversions, car vous ne pouvez pas diffuser l’expérience gagnante à l’ensemble de votre audience tant que l’activité n’est pas terminée. La répartition de votre trafic reste fixe même si vous reconnaissez que certaines expériences sont plus performantes que d’autres, et l’activité doit exécuter son cours entier avant de pouvoir agir sur un gagnant.

## Affectation automatique du trafic

Si vous souhaitez qu’une option serve l’expérience gagnante plus souvent et plus tôt dans l’activité tout en supprimant ou en réduisant simultanément le coût de configuration et de calcul du choix des tailles d’échantillon, des niveaux de confiance et d’autres concepts statistiques, [!UICONTROL Affectation automatique] est votre meilleure option.

## Comment fonctionne l’affectation automatique ?

[!UICONTROL Affectation automatique] applique le principe du bandit à plusieurs bras. Si le terme n&#39;est pas familier, un bandit à un bras est un terme familier pour une machine à sous (pensez : Las Vegas). Visualisez l’affectation automatique du trafic comme s’il existe plusieurs machines à sous, dans ce cas, testez des variantes et, dans un premier temps, extrayez toutes les poignées de manière égale. Au fil du temps, une ou plusieurs machines, ou variations de test, pourraient payer plus que d&#39;autres. Quand cela se produit, un joueur commence naturellement à tirer les manches de ceux qui gagnent le plus souvent. En termes d’affectation du trafic, [!DNL Adobe Target] servira plus de visiteurs à l’expérience ou aux expériences qui gagneront plus.

Examinez l’illustration suivante d’une activité A/B de deux semaines. Avec [!UICONTROL Affectation automatique], en cas d’expérience gagnante, [!UICONTROL Cible] redirige une plus grande partie du trafic vers ce gagnant tôt dans le test.

![Illustration de l’affectation automatique](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Comment l’affectation automatique me donne-t-elle des résultats plus rapides ?

L&#39;avantage est assez clair : davantage de visiteurs voient les variations qui présentent les meilleures performances. Et comme une variation unique avance, encore plus de visiteurs sont redirigés vers cette expérience gagnante, alors que le test était encore en cours d’exécution. Cela s’avère particulièrement utile si l’activité A/B en cours d’exécution se produit au cours d’un moment métier clé, tel qu’un jour férié, un lancement de produit ou un événement d’actualité mondiale.

## Comment l’affectation automatique peut-elle me rapporter des recettes plus élevées ?

[!UICONTROL Affectation automatique] identifie le gagnant plus rapidement qu’un partage A/B manuel et vous permet également d’exploiter ce gagnant en capturant immédiatement les recettes à la hausse qui auraient été perdues dans une approche traditionnelle ou manuelle. Parce que [!UICONTROL Affectation automatique] dirige plus de trafic vers l’expérience présentant le taux de conversion le plus élevé ; cela peut augmenter vos recettes pendant que l’activité s’exécute et s’apprend.

Dans l’exemple suivant, [!UICONTROL Affectation automatique] ont généré plus de recettes au cours du test en orientant plus de trafic (40 %) vers l’expérience D, qui avait le taux de conversion le plus élevé.

![L’affectation automatique fournit une illustration des recettes plus élevées](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Dans quels cas dois-je m’en tenir à l’affectation manuelle du trafic ?

Lorsque vous devez classer par ordre de classement la façon dont chaque expérience s’est comportée par rapport aux autres, un test A/B manuel est le plus applicable. [!UICONTROL Affectation automatique] identifie et exploite les meilleurs performants, mais ne garantit pas la différenciation entre les expériences les moins performantes. Utilisez l’affectation manuelle du trafic pour contrôler entièrement la quantité de trafic de vos visiteurs qui voit chaque variante de test et pour personnaliser les seuils statistiques pertinents pour votre entreprise.

## Prise en main

Prêt à lancer votre premier [!UICONTROL Affectation automatique] activité ? [Découvrez comment](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
