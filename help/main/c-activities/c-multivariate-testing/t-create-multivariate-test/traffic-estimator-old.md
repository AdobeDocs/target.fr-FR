---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Découvrez comment utiliser l’estimateur de trafic qui vous permet de déterminer si vous disposez d’un trafic suffisant pour que votre activité  [!DNL Adobe Target] [!UICONTROL Multivariate Test] réussisse.
title: Quelle quantité de trafic est nécessaire pour une activité [!UICONTROL Multivariate Test] (MVT) ?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 53%

---

# Estimation du trafic requis pour la réussite d’une activité [!UICONTROL Multivariate Test]

Un test multivarié comparant plusieurs expériences, il est important de connaître le volume de trafic requis pour fournir des résultats significatifs. L’estimateur de trafic utilise des statistiques relatives à votre page ainsi que le nombre d’expériences en cours de test afin d’estimer le volume de trafic et la durée du test requis pour assurer le succès de ce dernier.

L’estimateur de trafic prévoit la taille de l’échantillon requis pour garantir les conditions suivantes :

* Confiance à 95 %. Cette statistique signifie que la probabilité de signaler un faux positif en l’absence d’effet élévateur réel est de 5 % (100 % - niveau de confiance).
* 80 % de puissance statistique. Cette statistique signifie que le test a une probabilité de 80 % de détecter une portance réelle de 25 % ou plus.
* 25 % minimum d’ascenseur détectable de manière fiable. [!DNL Target] calcule la quantité de trafic requise pour avoir 80 % de chances de détecter une augmentation réelle de 25 % ou plus.

Le test utilise la correction de Bonferroni pour effectuer des corrections pour plusieurs comparaisons. Cette méthode est connue pour être conservative, ce qui est équilibré par l’application d’un effet élévateur minimal détectable de manière fiable relativement important.

L’estimateur de trafic fournit également des commentaires qui vous permettent de savoir si votre volume de trafic est suffisant pour que le test que vous avez conçu réussisse.

1. Dans la [!UICONTROL Visual Experience Composer], cliquez sur l’icône **[!UICONTROL Traffic]** .

   L’estimateur de trafic s’ouvre. Vous pouvez de nouveau cliquer sur l’icône **[!UICONTROL Traffic]** pour masquer l’estimateur de trafic.

   ![image estimatorempty](assets/estimatorempty.png)

1. Inscrivez le taux de conversion type, l’estimation du nombre de visiteurs par jour et la durée du test.

   * **[!UICONTROL Number of Content Combinations]** : calculé automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité après chaque exclusion.
   * **[!UICONTROL Typical Conversion Rate]** : le taux de conversion est exprimé en pourcentage, en fonction de votre estimation ou des données antérieures de votre système d’analyse.
   * **[!UICONTROL Estimated Visitors Per Day]** : il s’agit du nombre de visiteurs et visiteuses susceptibles d’afficher cette page en fonction des critères de ciblage. Cela peut être basé sur vos données d’analyse.
   * **[!UICONTROL Test Duration]** : nombre de jours pendant lesquels l’activité doit s’exécuter.

   L’estimateur de trafic utilise ces statistiques pour déterminer les ajustements requis pour exécuter un test réussi.

   Près de la partie supérieure de l’estimateur de trafic, les valeurs que vous avez saisies sont calculées et les résultats s’affichent.

   ![estimatorinsuffisance de l’image](assets/estimatorinsufficient.png)

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez de nombreuses expériences et que votre taux de conversion et vos impressions sont trop faibles, l’estimateur de trafic indique la durée pendant laquelle le test doit s’exécuter pour réussir. Ou, si votre trafic est faible, l’estimateur de trafic peut suggérer un nombre d’expériences plus faible afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous n’avez pas suffisamment de trafic, vous pouvez effectuer une ou les deux opérations suivantes :

   * Réduire le nombre de combinaisons d’offres et le nombre d’emplacements.
   * Augmenter la durée du test.

   Ajustez les chiffres jusqu’à ce que l’estimateur de trafic indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.

   ![image estimatorok](assets/estimatorok.png)
