---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Découvrez comment utiliser l’estimateur de trafic qui vous permet de déterminer si vous disposez d’un trafic suffisant pour que votre activité  [!DNL Adobe Target] [!UICONTROL &#x200B; test multivarié &#x200B;] réussisse.
title: Quelle quantité de trafic est nécessaire pour une activité [!UICONTROL test multivarié] (MVT) ?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 19%

---

# Estimation du trafic requis pour la réussite d’une activité de [!UICONTROL test multivarié]

Un test multivarié comparant plusieurs expériences, il est important de connaître le volume de trafic requis pour fournir des résultats significatifs. L’[!UICONTROL estimateur de trafic] utilise des statistiques sur votre page et le nombre d’expériences testées afin d’estimer la quantité de trafic et la durée de test nécessaires pour réussir le test.

L’[!UICONTROL estimateur de trafic] prédit la taille d’échantillon nécessaire pour garantir les éléments suivants :

* Confiance à 95 %. Cette statistique signifie que la probabilité de signaler un faux positif en l’absence d’effet élévateur réel est de 5 % (100 % - niveau de confiance).
* 80 % de puissance statistique. Cette statistique signifie que le test a une probabilité de 80 % de détecter une portance réelle de 25 % ou plus.
* 25 % minimum d’ascenseur détectable de manière fiable. [!DNL Target] calcule la quantité de trafic requise pour avoir 80 % de chances de détecter une augmentation réelle de 25 % ou plus.

Le test utilise la correction de Bonferroni pour effectuer des corrections pour plusieurs comparaisons. Cette méthode est connue pour être conservative, ce qui est équilibré par l’application d’un effet élévateur minimal détectable de manière fiable relativement important.

L’[!UICONTROL Estimateur de trafic] fournit également des commentaires qui vous permettent de savoir si vous disposez d’un trafic suffisant pour le test que vous avez conçu pour réussir.

1. Sur la page [!UICONTROL Expériences] du [!UICONTROL Compositeur d’expérience visuelle] d’une activité [!UICONTROL Multivarié], cliquez sur l’icône **[!UICONTROL Trafic]** ( ![icône d’estimateur de trafic](/help/main/assets/icons/Gauge2.svg) ) dans le coin supérieur gauche de la page [!UICONTROL Expériences].

   L’[!UICONTROL Estimateur de trafic] s’ouvre.

   ![&#x200B; Interface utilisateur de l’estimateur de trafic &#x200B;](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Vous pouvez de nouveau cliquer sur l’icône pour masquer l’[!UICONTROL Estimateur de trafic].

   Dans la partie supérieure de l’[!UICONTROL Estimateur de trafic], les valeurs saisies sont calculées et les résultats affichés.

1. (Conditionnel) Fournissez le taux de conversion type, le nombre estimé de visiteurs par jour et la durée du test.

   * **[!UICONTROL Nombre de combinaisons de contenu]** : calculé automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité après toute exclusion.
   * **[!UICONTROL Taux de conversion standard]** : le taux de conversion est exprimé en pourcentage, en fonction de votre estimation ou des données antérieures de votre système d’analyse.
   * **[!UICONTROL Estimation de visiteurs par jour]** : il s’agit du nombre de visiteurs et visiteuses susceptibles d’afficher cette page en fonction des critères de ciblage. Cela peut être basé sur vos données d’analyse.
   * **[!UICONTROL Durée du test]** : nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute.

   L’[!UICONTROL Estimateur de trafic] utilise ces statistiques pour déterminer les ajustements nécessaires à l’exécution réussie d’un test.

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez de nombreuses expériences et que votre taux de conversion et vos impressions sont trop faibles, l’[!UICONTROL Estimateur de trafic] indique la durée pendant laquelle le test doit s’exécuter pour réussir. Si le trafic est faible, l’[!UICONTROL Estimateur de trafic] peut suggérer un nombre d’expériences inférieur afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous n’avez pas suffisamment de trafic, vous pouvez effectuer une ou les deux opérations suivantes :

   * Réduire le nombre de combinaisons d’offres et le nombre d’emplacements.
   * Augmenter la durée du test.

   Ajustez les nombres jusqu’à ce que l’[!UICONTROL Estimateur de trafic] indique que vous disposez d’un trafic suffisant, puis concevez votre test en conséquence.
