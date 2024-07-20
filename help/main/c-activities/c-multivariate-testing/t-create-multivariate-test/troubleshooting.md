---
keywords: Tests multivariés;dépannage;dépannage;mvt
description: Explorez les défis potentiels auxquels vous pourriez être confronté lors de l’utilisation des activités [!UICONTROL Multivariate Test] (MVT) dans  [!DNL Adobe Target], ainsi que les solutions suggérées.
title: Comment résoudre un [!UICONTROL Multivariate Test] ?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 22%

---

# Résolution des problèmes liés aux activités [!UICONTROL Multivariate Test]

Cet article contient des suggestions pour résoudre certains problèmes qui peuvent se produire lors de la conception d’un [!UICONTROL Multivariate Test] (MVT) dans [!DNL Adobe Target].

* Lors de la modification d’une activité, si vous avez utilisé des mesures basées sur [!DNL Analytics] et que la suite de rapports ne se charge pas (le compteur s’affiche), basculez les mesures sur [!DNL Target], puis basculez à nouveau sur une mesure basée sur [!DNL Analytics]. La suite de rapports devrait maintenant se charger.
* Si vous apportez des modifications à un test déjà en cours d’exécution, vous pouvez réinitialiser le test et ses données.

  [!DNL Target] permet de modifier une activité en direct. La modification d’une activité en cours peut réinitialiser le test, de sorte que les rapports peuvent ne pas reconnaître certaines des modifications.

  Il est prudent d’apporter de petites modifications, telles que la modification d’offres de texte ou HTML existantes.

  Les actions spécifiques qui réinitialisent les noms et les rapports d’expérience incluent :

   * Ajout d’un nouvel emplacement
   * Suppression d’un emplacement
   * Ajout de nouvelles offres ou suppression d’offres d’un emplacement existant
