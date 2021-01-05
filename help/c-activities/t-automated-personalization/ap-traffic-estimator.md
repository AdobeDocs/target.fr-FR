---
keywords: traffic estimator;automated personalization;ap;estimate traffic
description: L’estimateur de trafic fournit des commentaires qui vous permettent de savoir si votre activité Adobe Target dispose d’un trafic suffisant pour réussir.
title: Estimation du trafic requis pour réussir un test
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 24%

---


# ![PREMIUM](/help/assets/premium.png) Estimation du trafic requis pour réussir un test

L&#39;[!UICONTROL estimateur de trafic] fournit des commentaires qui vous permettent de savoir si votre activité [!DNL Adobe Target] a suffisamment de trafic pour réussir.

Une activité [!UICONTROL Automated Personalization] utilisant plusieurs combinaisons d’offres, il est important de connaître le volume de trafic requis pour obtenir des résultats significatifs. L’[!UICONTROL estimateur de trafic] utilise des statistiques sur votre page et le nombre d’expériences testées pour estimer la quantité de trafic et la durée du test nécessaires pour que l’activité réussisse.

L’[!UICONTROL estimateur de trafic] détermine si le trafic est suffisant pour générer des modèles personnalisés, en comparant l’estimation des impressions de page et le taux de conversion type des pages. Idéalement, pour une activité réussie, la taille d’échantillon appropriée garantit que le contenu personnalisé est prêt au bout de 50 % de la durée de l’activité ou 14 jours, selon la durée la plus courte. Il s’agit d’un délai suffisant pour obtenir un contenu personnalisé et savoir quel contenu diffuser.

N’oubliez pas que [!DNL Target] diffuse des expériences de manière aléatoire jusqu’à ce que les algorithmes de personnalisation soient créés. L’icône en forme de coche en regard de chaque offre indique quand le modèle de cette offre est prêt et [!DNL Target] peut commencer à diffuser du contenu personnalisé. L’effet élévateur n’étant attendu qu’une fois que les modèles sont prêts, l’indication visuelle vous permet de définir l’attente appropriée. Utilisez l’[!UICONTROL estimateur de trafic] dans le [!UICONTROL compositeur d’expérience visuelle] (compositeur d’expérience visuelle) pour déterminer à quel moment les modèles seront prêts.

## Utilisation de l’estimateur de trafic

1. Dans le [!UICONTROL compositeur d’expérience visuelle], cliquez sur **[!UICONTROL Trafic]**.

   ![Icône de trafic](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   L&#39;[!UICONTROL estimateur de trafic] s&#39;affiche. Vous pouvez à nouveau cliquer sur **[!UICONTROL Trafic]**[!UICONTROL  pour masquer l’estimateur de trafic].

   ![](assets/ap_est.png)

1. Fournissez le taux de conversion type (ou le taux de conversion escompté pour cette activité), l’estimation des impressions de l’activité par jour et la durée du test.

   * **Nombre d&#39;Offres** : Calculé automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité après toute exclusion.
   * **Taux de conversion** type : Le taux de conversion est exprimé en pourcentage, selon votre estimation ou les données antérieures de votre système d’analyse.
   * **Estimation des visites par jour** : Il s’agit du nombre de visites par jour effectuées par des visiteurs qui sont en mesure de vue à l’activité, en fonction des critères de ciblage. Cela peut être basé sur vos données d’analyse. Il est à noter que ce nombre doit être celui des visites, et non des visiteurs uniques.
   * **Durée du test** : nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute.

   L&#39;[!UICONTROL estimato de trafic]r utilise ces statistiques pour déterminer les ajustements nécessaires pour exécuter un test réussi.

   Près du haut de l’[!UICONTROL estimateur de trafic], les valeurs que vous avez entrées sont calculées et les résultats s’affichent.

   ![](assets/ap_est_no.png)

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez un grand nombre de combinaisons et que votre taux de conversion et vos impressions sont trop faibles, l’[!UICONTROL estimateur de trafic] indique la durée d’exécution du test pour réussir. Ou, si votre trafic est faible, l’[!UICONTROL estimateur de trafic] peut suggérer un nombre inférieur de combinaisons d’offres afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous n’avez pas suffisamment de trafic, vous pouvez effectuer l’une ou plusieurs des opérations suivantes :

   * Envisagez d’utiliser une activité [Cible automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) au lieu de [!UICONTROL Automated Personalization] pour créer des expériences avec plusieurs changements d’offre dans une même variation d’expérience.
   * Réduisez le nombre de combinaisons d’offres dans votre activité [!UICONTROL Automated Personalization].
   * Augmentez la durée de l’activité.

   Ajustez les chiffres jusqu’à ce que l’[!UICONTROL estimateur de trafic] indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.

   ![](assets/ap_est_yes.png)

   Si le trafic est suffisant, l&#39;icône [!UICONTROL Trafic] affiche une coche verte. S’il est insuffisant, l’icône affiche une étiquette d’avertissement rouge.

## Questions fréquentes sur l’estimateur de trafic

Tenez compte des questions fréquentes suivantes lorsque vous utilisez l’[!UICONTROL estimateur de trafic] :

### Pourquoi [!DNL Target] ne crée-t-il pas de modèles personnalisés lorsque mon activité AP a assez de trafic ?

Dans certaines circonstances, votre trafic peut être suffisamment important pour qu’un modèle personnalisé soit créé, mais ce trafic peut indiquer [!DNL Target] qu’il n’y a pas de différence significative entre le modèle personnalisé et le modèle aléatoire. Bien que le modèle soit construit dans [!DNL Target] et testé, il ne sera pas déployé car il n&#39;est pas significativement meilleur que aléatoire.

Une des raisons possibles pour lesquelles le modèle n&#39;est pas meilleur que aléatoire pourrait être que les offres ne sont pas significativement différentes les unes des autres. Si tel est le cas, vous pouvez essayer de rendre les offres plus visuellement différentes si le message est similaire, ou vous pouvez essayer de modifier le message lui-même.
