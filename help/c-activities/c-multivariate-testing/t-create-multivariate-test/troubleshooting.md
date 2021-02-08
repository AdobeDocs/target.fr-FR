---
keywords: Tests multivariés ; résolution des problèmes ; résolution des problèmes ; mvt
description: Explorez les défis potentiels que vous pourriez rencontrer lors de l’utilisation d’activités de test multivarié (MVT) dans Adobe Target, ainsi que les solutions suggérées.
title: Comment résoudre les tests multivariés ?
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Résolution de problèmes liés aux tests multivariés

Cette rubrique contient des suggestions pour résoudre certains problèmes qui peuvent se produire lors de la conception d’un test [!UICONTROL multivarié] (MVT) dans [!DNL Adobe Target].

* Lors de la modification d’une activité, si vous avez utilisé des mesures basées sur [!DNL Analytics] et que la suite de rapports ne se charge pas (l’analyseur s’affiche), basculez les mesures sur des mesures [!DNL Target], puis basculez de nouveau sur une mesure basée sur [!DNL Analytics]. La suite de rapports devrait maintenant se charger.
* Si vous apportez des modifications à un test déjà en cours d’exécution, vous pouvez réinitialiser le test et ses données.

   [!DNL Target] permet de modifier une activité active. Gardez à l’esprit que la modification d’une activité en cours d’avancement peut réinitialiser le test. De ce fait, les rapports peuvent ne pas reconnaître certaines des modifications.

   Il est prudent d’apporter de petites modifications, telles que la modification d’offres de texte ou HTML existantes.

   Les actions spécifiques qui réinitialisent les noms et rapports des expériences sont :

   * Ajout d’un nouvel emplacement
   * Suppression d’un emplacement
   * Ajout de nouvelles offres ou suppression d’offres d’un emplacement existant

