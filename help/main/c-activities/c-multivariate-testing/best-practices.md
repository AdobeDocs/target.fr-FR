---
keywords: mvt;test multivarié;bonnes pratiques de test multivarié;bonnes pratiques mvt;combinaisons mvt;rapports mvt
description: Découvrez comment améliorer les performances, éviter les problèmes et corriger les problèmes connus qui peuvent se produire lors de la création et de l’exécution d’activités de [!UICONTROL test multivarié] dans [!DNL Adobe Target].
title: Quelles sont les bonnes pratiques pour une activité de [!UICONTROL test multivarié] ?
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
TQID: 'https://experienceleague.adobe.com/nQEf5GZ8-zVZakygPtMAYWk-xoJPdcycFbzCNKTqJ-k'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 30%
---
# [!UICONTROL Bonnes pratiques de test multivarié] {#mvt-best-practices}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment planifier, créer, analyser et assurer le suivi d’une activité de **[!UICONTROL test multivarié]** pour obtenir des résultats fiables.

>[!ENDSHADEBOX]

Les conseils suivants vous aident à améliorer les performances, à éviter les problèmes et à corriger les problèmes connus qui peuvent se produire lorsque vous créez et exécutez des activités de **[!UICONTROL test multivarié]** (MVT) dans [!DNL Adobe Target].

## Planifier {#plan}

* **Utilisez au moins trois éléments dans le test.**

  Si vous en avez moins, exécutez une série de tests A/B. Pour plus d&#39;informations, voir [Quand utiliser le test multivarié par rapport à A/B](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#when-to-use-mvt).

* **Tenez compte de la quantité de trafic que vous obtenez généralement, y compris le nombre d’impressions et de conversions.**

  MVT nécessite suffisamment de trafic pour générer des résultats utiles. Ces informations permettent de réduire la probabilité de concevoir un test avec des exigences qui dépassent le trafic de votre site.

* **Tenez compte des emplacements de votre page qui sont susceptibles de produire des résultats significatifs.**

  Une bannière ou une image principale va probablement entraîner plus de conversions qu’un changement de pied de page. L’inclusion d’emplacements ayant moins d’influence dans votre test ne fait qu’augmenter le volume de trafic et le temps requis pour tester les emplacements plus importants de la page.

* **Gardez les éléments indépendants les uns des autres.**

  Par exemple, ne vérifiez pas la disposition et le contenu dans le même test.

* **Examinez le code HTML pour les pages que vous souhaitez tester.**

  Assurez-vous que les éléments HTML de votre site ne comportent pas d’identifiants DOM en double. Les ID en double peuvent avoir pour conséquence la diffusion du même élément de contenu vers plusieurs emplacements.

* **Préparez vos variations de page à l’avance.**

  Repérez les différences de contenu pour chaque offre et créez les offres d’image, de texte et HTML que vous prévoyez d’utiliser dans le test.

* **Planifiez du temps supplémentaire pour l’assurance qualité.**

  Le nombre d’expériences augmente, de sorte que le contrôle qualité prend plus de temps.

## Créer {#create}

* **N&#39;incluez pas plus de combinaisons que nécessaire pour le test.**

  Chaque combinaison testée augmente significativement le volume de trafic et le temps requis pour obtenir des résultats acceptables. Par exemple, en présence de trois emplacements comportant trois offres chacun, vous obtenez 27 combinaisons possibles (3 x 3 x 3). Trois emplacements, dont deux contiennent trois offres possibles et un deux offres, fournissent 18 options (3 x 3 x 2). Les nombres augmentent substantiellement avec chaque emplacement et offre supplémentaires.

* **Nommez les emplacements et les offres.**

  Vous pouvez renommer chaque emplacement et offre de votre test par un nom plus pertinent. Le nombre d’offres à chaque emplacement apparaît dans l’en-tête de l’emplacement. Les noms utiles vous aident à identifier vos offres lors de l’examen des rapports.

* **Tirez parti des fonctionnalités de prévisualisation pour éviter les combinaisons de contenu indésirables.**

  Révisez toutes les expériences générées par votre test avant de passer en réel. Assurez-vous qu’il n’existe aucune combinaison avec des revendications contradictoires (par exemple, 20 % de réduction et 19 $ de réduction dans la même expérience) ou des conceptions incompatibles, telles qu’un arrière-plan et une police de même couleur.

* **Utilisez l’[estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator) pour vous assurer que votre test est conçu en fonction de la quantité de trafic reçue par votre page.**

  Assurez-vous que l’**[!UICONTROL estimateur de trafic]** donne le feu vert à la configuration de test afin d’obtenir les résultats souhaités.

* **Rendre les alternatives de chaque élément significativement différentes les unes des autres.**

  Bien que cela ne soit pas obligatoire, il est recommandé que chaque élément ait le même nombre d’alternatives.

## Analyser {#analyze}

* **Utilisez fréquemment le [rapport Contribution des emplacements](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)** pour surveiller les performances de chaque emplacement et offre.

* **Dans le [rapport Performance de l’expérience](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), basez vos décisions sur les données affichées en utilisant les filtres [!UICONTROL Meilleur 5] et [!UICONTROL Pire 5].**

  Le filtre **[!UICONTROL Tous]** rend difficile l’extraction des informations souhaitées, et toutes les expériences ne peuvent pas s’afficher dans le graphique. Utilisez le filtre **[!UICONTROL Tous]** si vous souhaitez examiner une expérience spécifique qui ne fait pas partie des cinq meilleures ou pires.

## Suivi {#follow-up}

* Bien que [!DNL Target] vous permette de modifier une activité active, **la modification d’une activité en cours peut réinitialiser le test.** Il se peut que les rapports ne reconnaissent pas certaines des modifications. Vous pouvez modifier en toute sécurité les offres HTML dans la bibliothèque des offres uniquement.

  Les actions spécifiques qui réinitialisent les noms d’expérience et les rapports incluent :

  * Ajout d’un nouvel emplacement
  * Suppression d’un emplacement
  * Ajout de nouvelles offres ou suppression d’offres à partir d’un emplacement existant
  * Modification d’offres de texte enrichi
  * Modification d’offres de couleur d’arrière-plan

* **Si la suite de rapports ne se charge pas lorsque vous modifiez une activité qui utilise des mesures basées sur [!DNL Analytics] (une double flèche s’affiche),** basculez les mesures vers [!DNL Target] mesures, puis revenez aux mesures basées sur [!DNL Analytics]. La suite de rapports devrait maintenant se charger.

* **Suivez un test MVT avec un ou plusieurs tests A/B** afin de déterminer le meilleur contenu possible pour les résultats souhaités. Une fois que vous avez déterminé les emplacements et le contenu qui sont le plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner encore plus les résultats. Par exemple, lorsque vous savez quels emplacements sont les plus importants, testez deux images spécifiques l’une par rapport à l’autre ou comparez le libellé ou les couleurs d’un call to action.
