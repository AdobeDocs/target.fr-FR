---
keywords: Tests multivariés;dépannage;dépannage;mvt
description: Explorez les défis potentiels auxquels vous pourriez être confronté lors de l’utilisation des activités de test multivarié (MVT) dans Adobe Target, ainsi que les solutions suggérées.
title: Comment résoudre les problèmes liés aux tests multivariés ?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---

# Résolution de problèmes liés aux tests multivariés

Cette rubrique contient des suggestions pour résoudre certains problèmes qui peuvent se produire lors de la conception d’une [!UICONTROL Multivariate] Test (MVT) dans [!DNL Adobe Target].

* Lors de la modification d’une activité, si vous avez utilisé [!DNL Analytics]mesures basées sur et que la suite de rapports ne se charge pas (s’affiche avec un compteur), basculez les mesures sur [!DNL Target] mesures, puis passez de nouveau à [!DNL Analytics]mesure basée sur . La suite de rapports devrait maintenant se charger.
* Si vous apportez des modifications à un test déjà en cours d’exécution, vous pouvez réinitialiser le test et ses données.

   [!DNL Target] permet de modifier une activité active. Gardez à l’esprit que la modification d’une activité en cours d’avancement peut réinitialiser le test. De ce fait, les rapports peuvent ne pas reconnaître certaines des modifications.

   Il est prudent d’apporter de petites modifications, telles que la modification d’offres de texte ou HTML existantes.

   Les actions spécifiques qui réinitialisent les noms et rapports des expériences sont :

   * Ajout d’un nouvel emplacement
   * Suppression d’un emplacement
   * Ajout de nouvelles offres ou suppression d’offres d’un emplacement existant
