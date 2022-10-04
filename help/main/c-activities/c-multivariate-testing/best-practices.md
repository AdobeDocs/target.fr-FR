---
keywords: mvt;test multivarié;bonnes pratiques de test multivarié;bonnes pratiques mvt;combinaisons mvt;rapports mvt
description: Découvrez comment améliorer les performances, éviter les problèmes et corriger les problèmes connus qui peuvent se produire lors de la création et de l’exécution d’activités de test multivarié dans Adobe Target.
title: Quelles sont les bonnes pratiques pour les tests multivariés ?
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 100%

---

# Bonnes pratiques pour les tests multivariés

Conseils pour vous aider à améliorer les performances, à éviter les problèmes et à corriger les problèmes connus qui peuvent se produire lors de la création et de l’exécution d’activités de [!UICONTROL test multivarié] dans [!DNL Adobe Target].

## Planifier  {#section_4D4A1F6226F042379BF48DB753608579}

* Repérez les emplacements de votre page qui sont susceptibles de produire des résultats significatifs.

   Par exemple, une bannière ou une image principale va probablement générer plus de conversions qu’une modification du pied de page. L’inclusion d’emplacements ayant moins d’influence dans votre test ne fait qu’augmenter le volume de trafic et le temps requis pour tester les emplacements plus importants de la page.
* Préparez vos variations de page à l’avance.

   Repérez les différences de contenu pour chaque offre et créez les offres d’image, de texte et HTML que vous prévoyez d’utiliser dans le test.

## Créer  {#section_C59C722CA82E48ABA58A4A7FA758F193}

* N’incluez pas plus de combinaisons que nécessaire pour le test.

   Chaque combinaison testée augmente significativement le volume de trafic et le temps requis pour obtenir des résultats acceptables. Par exemple, en présence de trois emplacements comportant trois offres chacun, vous obtenez 27 combinaisons possibles (3 x 3 x 3). Trois emplacements, dont deux contiennent trois offres possibles et un deux offres, fournissent 18 options (3 x 3 x 2). Les nombres augmentent substantiellement avec chaque emplacement et offre supplémentaires.

* Nommez les emplacements et les offres.

   Vous pouvez renommer chaque emplacement et offre de votre test par un nom plus pertinent. Le nombre d’offres à chaque emplacement apparaît dans l’en-tête de l’emplacement. Des noms pertinents vous aident à identifier vos offres lors de l’examen des rapports.

* Tirez parti des fonctionnalités d’aperçu pour éviter des combinaisons non souhaitables de contenu.

   Révisez toutes les expériences générées par votre test avant de passer en réel. Assurez-vous qu’il n’y ait aucune combinaison comportant des instructions contradictoires (par exemple, 20 % de remise et 19 $ de remise dans la même expérience) ou des conceptions incompatibles, par exemple un arrière-plan et une police de la même couleur.

* Utilisez l’[estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) pour vous assurer que le test est conçu pour le volume de trafic que votre page reçoit.

   Assurez-vous que l’estimateur de trafic donne le feu vert à votre configuration de test afin que vous puissiez obtenir les résultats souhaités.
* Il est recommandé de créer des alternatives significativement différentes les unes des autres.

## Analyser  {#section_9A2118CF1039451681C13D9AE79A58AB}

* Utilisez fréquemment le [rapport Contribution des emplacements](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) afin de surveiller les performances de chaque emplacement et chaque offre.
* Dans le [rapport Performance de l’expérience](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), basez vos décisions sur les données affichées en utilisant les filtres 5 meilleurs et 5 pires.

   Le filtre [!UICONTROL Toutes] rend difficile l’extraction des informations souhaitées. En outre, il est impossible d’afficher toutes les expériences dans le graphique. Utilisez le filtre [!UICONTROL Toutes] si vous souhaitez consulter une expérience spécifique qui ne figure pas dans les cinq meilleures ou les cinq pires.

## Effectuer le suivi  {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Même si [!DNL Target] vous autorise à modifier une activité réelle, notez que la modification d’une activité en cours peut réinitialiser le test. Les rapports peuvent donc ne pas reconnaître certaines des modifications. Il est recommandé d’apporter des modifications aux offres HTML uniquement dans la bibliothèque d’offres.

   Les actions spécifiques qui réinitialisent les noms et les rapports d’expérience sont :

   * Ajout d’un nouvel emplacement
   * Suppression d’un emplacement
   * Ajout de nouvelles offres ou suppression d’offres à partir d’un emplacement existant
   * Modification d’offres de texte enrichi
   * Modification d’offres de couleur d’arrière-plan

* En exécutant un ou plusieurs tests A/B après un test multivarié, vous pouvez déterminer le meilleur contenu possible pour les résultats que vous souhaitez.

   Une fois que vous avez déterminé les emplacements et le contenu qui sont le plus utiles pour vous aider à atteindre vos objectifs, vous pouvez exécuter un test A/B pour affiner encore plus les résultats. Par exemple, lorsque vous savez quels emplacements sont les plus importants, testez deux images spécifiques l’une par rapport à l’autre ou comparez les termes ou les couleurs d’une incitation à l’action.
