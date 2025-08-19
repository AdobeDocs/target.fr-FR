---
keywords: Tests multivariés;dépannage;dépannage;mvt
description: Explorez les défis potentiels que vous pouvez rencontrer lors de l’utilisation d’activités [!UICONTROL Multivariate Test] (MVT) dans [!DNL Adobe Target], ainsi que les solutions suggérées.
title: Comment résoudre les problèmes liés à un [!UICONTROL Multivariate Test] ?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 22%

---

# Résolution des problèmes liés aux activités [!UICONTROL Multivariate Test]

Cet article contient des suggestions pour résoudre certains problèmes qui peuvent se produire lors de la conception d’un [!UICONTROL Multivariate Test] (MVT) dans [!DNL Adobe Target].

* Lors de la modification d’une activité, si vous avez utilisé des mesures basées sur [!DNL Analytics] et que la suite de rapports ne se charge pas (affichage à double flèche), basculez les mesures vers des mesures [!DNL Target], puis revenez à la mesure basée sur [!DNL Analytics]. La suite de rapports devrait maintenant se charger.
* Si vous apportez des modifications à un test en cours d’exécution, vous pouvez réinitialiser le test et ses données.

  [!DNL Target] permet de modifier une activité active. La modification d’une activité en cours peut réinitialiser le test et les rapports peuvent ne pas reconnaître certaines des modifications.

  Il est prudent d’apporter de petites modifications, telles que la modification d’offres de texte ou HTML existantes.

  Les actions spécifiques qui réinitialisent les noms d’expérience et les rapports incluent :

   * Ajout d’un nouvel emplacement
   * Suppression d’un emplacement
   * Ajout de nouvelles offres ou suppression d’offres d’un emplacement existant
