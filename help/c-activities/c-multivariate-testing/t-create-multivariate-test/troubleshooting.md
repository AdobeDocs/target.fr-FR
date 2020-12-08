---
keywords: Mobile Web Experience Editor
description: Cette rubrique contient des suggestions pour résoudre certains problèmes qui peuvent se produire lors de la conception d’un test multivarié en Adobe Target.
title: Résolution de problèmes liés aux tests multivariés
feature: mvt
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 77%

---


# Résolution de problèmes liés aux tests multivariés{#troubleshoot-multivariate-tests}

Cette rubrique contient des suggestions pour résoudre certains problèmes qui peuvent se produire lors de la conception d’un test multivarié en Adobe Target.

* Lors de la modification d’une activité, si vous avez utilisé des mesures basées sur Analytics et que la suite de rapports ne se charge pas (le compteur s’affiche), basculez les mesures sur des mesures Target, puis basculez à nouveau sur une mesure basée sur Analytics. La suite de rapports devrait maintenant se charger.
* Si vous apportez des modifications à un test déjà en cours d’exécution, vous devez réinitialiser le test et ses données.

   Target vous autorise à modifier une activité réelle. Gardez à l’esprit que la modification d’une activité en cours d’avancement peut réinitialiser le test. De ce fait, les rapports peuvent ne pas reconnaître certaines des modifications.

   Il est prudent d’apporter de petites modifications, telles que la modification d’offres de texte ou HTML existantes.

   Les actions spécifiques qui réinitialisent les noms et rapports des expériences sont :

   * Ajout d’un nouvel emplacement
   * Suppression d’un emplacement
   * Ajout de nouvelles offres ou suppression d’offres d’un emplacement existant

