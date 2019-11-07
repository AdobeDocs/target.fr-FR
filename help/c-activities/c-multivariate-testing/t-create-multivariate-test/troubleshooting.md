---
keywords: Éditeur d’expérience web mobile
description: Cette rubrique comporte des suggestions pour résoudre des problèmes qui peuvent se produire lors de la conception d’un test multivarié.
title: Résolution de problèmes liés aux tests multivariés
subtopic: Fenêtres d’affichage mobiles
topic: Standard
uuid: 4de03e03-cbbd-4e8f-a1b9-19ba8b2e6951
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Résolution de problèmes liés aux tests multivariés{#troubleshoot-multivariate-tests}

Cette rubrique comporte des suggestions pour résoudre des problèmes qui peuvent se produire lors de la conception d’un test multivarié.

* Lors de la modification d’une activité, si vous avez utilisé des mesures basées sur Analytics et que la suite de rapports ne se charge pas (le compteur s’affiche), basculez les mesures sur des mesures Target, puis basculez à nouveau sur une mesure basée sur Analytics. La suite de rapports devrait maintenant se charger.
* Si vous apportez des modifications à un test déjà en cours d’exécution, vous devez réinitialiser le test et ses données.

   Target vous autorise à modifier une activité réelle. Gardez à l’esprit que la modification d’une activité en cours d’avancement peut réinitialiser le test. De ce fait, les rapports peuvent ne pas reconnaître certaines des modifications.

   Il est prudent d’apporter de petites modifications, telles que la modification d’offres de texte ou HTML existantes.

   Les actions spécifiques qui réinitialisent les noms et rapports des expériences sont :

   * Ajout d’un nouvel emplacement
   * Suppression d’un emplacement
   * Ajout de nouvelles offres ou suppression d’offres d’un emplacement existant

