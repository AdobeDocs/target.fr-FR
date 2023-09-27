---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Découvrez comment utiliser l’estimateur de trafic qui vous permet de savoir si vous disposez d’un trafic suffisant pour votre [!DNL Adobe Target] [!UICONTROL Test multivarié] pour réussir.
title: Quantité de trafic requise pour une [!UICONTROL Test multivarié] (MVT) Activité ?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 73%

---

# Estimation du trafic requis pour une réussite [!UICONTROL Test multivarié] activité

Un test multivarié comparant plusieurs expériences, il est important de connaître le volume de trafic requis pour fournir des résultats significatifs. L’estimateur de trafic utilise des statistiques relatives à votre page ainsi que le nombre d’expériences en cours de test afin d’estimer le volume de trafic et la durée du test requis pour assurer le succès de ce dernier.

L’estimateur de trafic prévoit la taille de l’échantillon requis pour garantir les conditions suivantes :

* Un degré de confiance de 95 %. Cette statistique signifie que la probabilité de signaler un faux positif en l’absence d’effet élévateur réel est de 5 % (100 % - degré de confiance).
* Puissance statistique de 80 %. Cette statistique signifie que le test a une probabilité de 80 % de détecter un véritable effet élévateur de 25 % ou plus.
* Effet élévateur minimal détectable de manière fiable de 25 %. [!DNL Target] calcule le volume de trafic requis pour avoir une chance de 80 % de détecter un véritable effet élévateur de 25 % ou plus.

Le test utilise la correction de Bonferroni pour effectuer des corrections pour plusieurs comparaisons. Cette méthode est connue pour être conservative, ce qui est équilibré par l’application d’un effet élévateur minimal détectable de manière fiable relativement important.

L’estimateur de trafic fournit également des commentaires qui vous permettent de savoir si votre volume de trafic est suffisant pour que le test que vous avez conçu réussisse.

1. Dans la [!UICONTROL Compositeur d’expérience visuelle], cliquez sur le **[!UICONTROL Trafic]** Icône

   L’estimateur de trafic s’ouvre. Vous pouvez à nouveau cliquer sur **[!UICONTROL Trafic pour masquer l’estimateur de trafic.]**

   ![image estimatorempty](assets/estimatorempty.png)

1. Inscrivez le taux de conversion type, l’estimation du nombre de visiteurs par jour et la durée du test.

   * **[!UICONTROL Nombre de combinaison de contenus]** : calculé automatiquement selon le nombre d’expériences créées dans le cadre de votre activité, après toute exclusion.
   * **[!UICONTROL Taux de conversion typique]** : le taux de conversion est exprimé sous la forme d’un pourcentage basé sur votre estimation ou les données antérieures provenant de votre système d’analyse. 
   * **[!UICONTROL Nombre estimé de visiteurs par jour]** : il s’agit du nombre de visiteurs qui sont susceptibles de voir cette page selon les critères de ciblage. Cela peut être basé sur vos données d’analyse.
   * **[!UICONTROL Durée du test]** : nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute.

   L’estimateur de trafic utilise ces statistiques pour déterminer les ajustements requis pour exécuter un test réussi.

   Près de la partie supérieure de l’estimateur de trafic, les valeurs que vous avez saisies sont calculées et les résultats s’affichent.

   ![estimatorimage insuffisante](assets/estimatorinsufficient.png)

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez de nombreuses expériences et que votre taux de conversion et vos impressions sont trop faibles, l’estimateur de trafic indique la durée pendant laquelle le test doit s’exécuter pour réussir. Ou, si votre trafic est faible, l’estimateur de trafic peut suggérer un nombre d’expériences plus faible afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous n’avez pas suffisamment de trafic, vous pouvez effectuer une ou les deux opérations suivantes :

   * Réduire le nombre de combinaisons d’offres et le nombre d’emplacements.
   * Augmenter la durée du test.

   Ajustez les chiffres jusqu’à ce que l’estimateur de trafic indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.

   ![image estimatorok](assets/estimatorok.png)
