---
description: L’estimateur de trafic fournit des commentaires qui vous permettent de savoir si votre volume de trafic est suffisant pour que votre activité réussisse.
title: Estimation du trafic requis pour réussir un test
feature: ap
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 100%

---


# ![PREMIUM](/help/assets/premium.png) Estimation du trafic requis pour réussir un test{#estimate-the-traffic-required-for-success}

L’estimateur de trafic fournit des commentaires qui vous permettent de savoir si votre volume de trafic est suffisant pour que votre activité réussisse.

L’activité d’Automated Personalization utilisant plusieurs combinaisons d’offres, il est important de connaître le volume de trafic requis pour fournir des résultats significatifs. L’estimateur de trafic utilise des statistiques relatives à votre page ainsi que le nombre d’expériences en cours de test afin d’estimer le volume de trafic et la durée du test requis pour assurer le succès de l’activité.

L’estimateur de trafic détermine si le volume de trafic est suffisant pour générer des modèles personnalisés, en comparant le nombre estimé d’impressions de page et le taux de conversion type des pages. Idéalement, pour une activité réussie, la taille d’échantillon appropriée garantit que le contenu personnalisé est prêt au bout de 50 % de la durée de l’activité ou 14 jours, selon la durée la plus courte. Il s’agit d’un délai suffisant pour obtenir un contenu personnalisé et savoir quel contenu diffuser.

Pour rappel, Target diffuse les expériences de façon aléatoire jusqu’à ce que les algorithmes de personnalisation soient compilés. L’icône en forme de coche en regard de chaque offre indique le moment où le modèle correspondant à cette offre est prêt et où Target est en mesure de commencer à diffuser du contenu personnalisé. L’effet élévateur n’étant attendu qu’une fois que les modèles sont prêts, l’indication visuelle vous permet de définir l’attente appropriée. Utilisez l’estimateur de trafic dans le compositeur d’expérience visuelle (VEC) pour obtenir une indication du moment où les modèles seront prêts.

1. Dans le compositeur d’expérience, cliquez sur **[!UICONTROL Trafic]**.

   ![Icône de trafic](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   L’estimateur de trafic s’ouvre. Vous pouvez à nouveau cliquer sur **[!UICONTROL Trafic]** pour masquer l’estimateur de trafic.

   ![](assets/ap_est.png)

1. Fournissez le taux de conversion type (ou le taux de conversion escompté pour cette activité), l’estimation des impressions de l’activité par jour et la durée du test.

   * Nombre de combinaison de contenus : calculé automatiquement selon le nombre d’expériences créées dans le cadre de votre activité, après toute exclusion.
   * Taux de conversion typique : le taux de conversion est exprimé sous la forme d’un pourcentage basé sur votre estimation ou les données antérieures provenant de votre système d’analyse.
   * Nombre estimé de visites par jour : il s’agit du nombre de visites par jour effectuées par des visiteurs qui peuvent voir l’activité selon les critères de ciblage. Cela peut être basé sur vos données d’analyse. Il est à noter que ce nombre doit être celui des visites, et non des visiteurs uniques.
   * Durée du test : nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute.

   L’estimateur de trafic utilise ces statistiques pour déterminer les ajustements requis pour exécuter un test réussi.

   Près de la partie supérieure de l’estimateur de trafic, les valeurs que vous avez saisies sont calculées et les résultats s’affichent.

   ![](assets/ap_est_no.png)

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez un grand nombre de combinaisons et que votre taux de conversion et vos impressions sont trop faibles, l’estimateur de trafic indique la durée pendant laquelle le test doit s’exécuter pour être réussi. Ou, si votre trafic est faible, l’estimateur de trafic peut suggérer un nombre de combinaisons d’offres plus faible afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous n’avez pas suffisamment de trafic, vous pouvez effectuer l’une ou plusieurs des opérations suivantes :

   * Envisagez d’utiliser le ciblage automatique au lieu d’Automated Personalization pour créer des expériences comportant plusieurs modifications d’offres au sein d’une variation d’expérience unique.
   * Réduisez le nombre de combinaisons d’offres dans votre activité Automated Personalization.
   * Augmentez la durée de l’activité.

   Ajustez les chiffres jusqu’à ce que l’estimateur de trafic indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.

   ![](assets/ap_est_yes.png)

   Si le trafic est suffisant, l’icône de trafic affiche une coche verte. S’il est insuffisant, l’icône affiche une étiquette d’avertissement rouge.
