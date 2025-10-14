---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Découvrez comment utiliser l’estimateur de trafic qui vous permet de déterminer si vous disposez d’un trafic suffisant pour que votre activité  [!DNL Adobe Target] [!UICONTROL Multivariate Test] réussisse.
title: Quelle quantité de trafic est nécessaire pour une activité [!UICONTROL Multivariate Test] (MVT) ?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 21%

---

# Estimation du trafic requis pour la réussite d’une activité [!UICONTROL Multivariate Test]

Un test multivarié comparant plusieurs expériences, il est important de connaître le volume de trafic requis pour fournir des résultats significatifs. Le [!UICONTROL Traffic Estimator] utilise des statistiques sur votre page et le nombre d’expériences testées pour estimer la quantité de trafic et la durée de test nécessaires pour réussir le test.

Le [!UICONTROL Traffic Estimator] prédit la taille d’échantillon nécessaire pour garantir les éléments suivants :

* Confiance à 95 %. Cette statistique signifie que la probabilité de signaler un faux positif en l’absence d’effet élévateur réel est de 5 % (100 % - niveau de confiance).
* 80 % de puissance statistique. Cette statistique signifie que le test a une probabilité de 80 % de détecter une portance réelle de 25 % ou plus.
* 25 % minimum d’ascenseur détectable de manière fiable. [!DNL Target] calcule la quantité de trafic requise pour avoir 80 % de chances de détecter une augmentation réelle de 25 % ou plus.

Le test utilise la correction de Bonferroni pour effectuer des corrections pour plusieurs comparaisons. Cette méthode est connue pour être conservative, ce qui est équilibré par l’application d’un effet élévateur minimal détectable de manière fiable relativement important.

Le [!UICONTROL Traffic Estimator] fournit également des commentaires qui vous permettent de savoir si vous disposez d’un trafic suffisant pour que le test que vous avez conçu réussisse.

1. Dans la page [!UICONTROL Experiences] de l’[!UICONTROL Visual Experience Composer] dans une activité [!UICONTROL Multivariate], cliquez sur l’icône **[!UICONTROL Traffic]** ( ![icône de l’estimateur de trafic](/help/main/assets/icons/Gauge2.svg) ) dans le coin supérieur gauche de la page [!UICONTROL Experiences].

   La [!UICONTROL Traffic Estimator] s’ouvre.

   ![&#x200B; Interface utilisateur de l’estimateur de trafic &#x200B;](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Vous pouvez de nouveau cliquer sur l’icône pour masquer le [!UICONTROL Traffic Estimator].

   Près de la partie supérieure du [!UICONTROL Traffic Estimator], les valeurs que vous avez saisies sont calculées et les résultats sont affichés.

1. (Conditionnel) Fournissez le taux de conversion type, le nombre estimé de visiteurs par jour et la durée du test.

   * **[!UICONTROL Number of Content Combinations]** : calculé automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité après chaque exclusion.
   * **[!UICONTROL Typical Conversion Rate]** : le taux de conversion est exprimé en pourcentage, en fonction de votre estimation ou des données antérieures de votre système d’analyse.
   * **[!UICONTROL Estimated Visitors Per Day]** : il s’agit du nombre de visiteurs et visiteuses susceptibles d’afficher cette page en fonction des critères de ciblage. Cela peut être basé sur vos données d’analyse.
   * **[!UICONTROL Test Duration]** : nombre de jours pendant lesquels l’activité doit s’exécuter.

   Le [!UICONTROL Traffic Estimator] utilise ces statistiques pour déterminer les ajustements nécessaires à l’exécution d’un test réussi.

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez de nombreuses expériences et que votre taux de conversion et vos impressions sont trop faibles, la [!UICONTROL Traffic Estimator] indique combien de temps l’exécution du test doit durer pour réussir. Si votre trafic est faible, le [!UICONTROL Traffic Estimator] peut suggérer un nombre d’expériences inférieur afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous n’avez pas suffisamment de trafic, vous pouvez effectuer une ou les deux opérations suivantes :

   * Réduire le nombre de combinaisons d’offres et le nombre d’emplacements.
   * Augmenter la durée du test.

   Ajustez les nombres jusqu’à ce que le [!UICONTROL Traffic Estimator] indique que vous disposez d’un trafic suffisant, puis concevez votre test en conséquence.
