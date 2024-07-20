---
keywords: estimateur de trafic;personnalisation automatisée;ap;estimation du trafic
description: Utilisez le  [!DNL Adobe Target] [!UICONTROL Traffic Estimator] pour déterminer si votre activité [!UICONTROL Automated Personalization] a suffisamment de trafic pour réussir.
title: Combien de trafic est nécessaire pour une activité [!UICONTROL Automated Personalization] réussie ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 10%

---

# Estimation du trafic requis pour réussir un test

[!DNL Adobe Target] [!UICONTROL Traffic Estimator] fournit des commentaires qui vous permettent de savoir si vous disposez d’un trafic suffisant pour que votre activité [!UICONTROL Automated Personalization] (AP) réussisse.

Comme les activités [!UICONTROL Automated Personalization] utilisent plusieurs combinaisons d’offres, il est important de connaître le volume de trafic requis pour fournir des résultats significatifs. Le [!UICONTROL Traffic Estimator] utilise des statistiques sur votre page et le nombre d’expériences en cours de test pour estimer le volume de trafic et la durée du test nécessaires pour que l’activité soit réussie.

[!UICONTROL Traffic Estimator] détermine s’il existe suffisamment de trafic pour générer des modèles personnalisés en comparant l’estimation des impressions de page et le taux de conversion type pour les pages. Idéalement, pour une activité réussie, la taille d’échantillon appropriée garantit que le contenu personnalisé est prêt au bout de 50 % de la durée de l’activité ou 14 jours, selon la durée la plus courte. Ce processus laisse suffisamment de temps pour obtenir du contenu personnalisé et apprendre quel contenu diffuser.

N’oubliez pas que [!DNL Target] diffuse les expériences de manière aléatoire jusqu’à ce que les algorithmes de personnalisation soient créés. L’icône en forme de coche en regard de chaque offre indique quand le modèle de cette offre est prêt et que [!DNL Target] peut commencer à diffuser du contenu personnalisé. Comme l’effet élévateur n’est attendu qu’une fois les modèles prêts, l’indication visuelle vous permet de définir les attentes appropriées. Utilisez le [!UICONTROL Traffic Estimator] dans le [!UICONTROL Visual Experience Composer] (VEC) pour obtenir une indication du moment où les modèles sont prêts.

## Utilisation de l’estimateur de trafic

1. Sur la page [!UICONTROL Experiences] de l’activité [!UICONTROL Visual Experience Composer] d’une activité [!UICONTROL Automated Personalization], cliquez sur l’icône **[!UICONTROL Traffic]**.

   ![Icône de trafic](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   Le [!UICONTROL Traffic Estimator] s’ouvre. Vous pouvez à nouveau cliquer sur **[!UICONTROL Traffic]** pour masquer le [!UICONTROL Traffic Estimator].

   ![Interface utilisateur de l’estimateur de trafic](assets/ap_est.png)

1. Indiquez le taux de conversion type (ou le taux de conversion escompté pour cette activité), l’estimation des impressions de l’activité par jour et la durée du test.

   | Mesure | Description |
   | --- | --- |
   | **[!UICONTROL Number of Offers]** | Cette mesure est calculée automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité, après toute exclusion. |
   | **[!UICONTROL Typical Conversion Rate]** | Cette mesure est exprimée en pourcentage, selon votre estimation ou les données antérieures provenant de votre système d’analyse. |
   | **[!UICONTROL Estimated Visits Per Day]** | Cette mesure correspond au nombre de visites par jour effectuées par des visiteurs qui peuvent visualiser l’activité, selon les critères de ciblage. Cette mesure peut être basée sur vos données d’analyse. Ce nombre doit être constitué de visites, et non de visiteurs uniques. |
   | **[!UICONTROL Test Duration]** | Nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute. |

   [!UICONTROL Traffic Estimator] utilise ces mesures pour déterminer les ajustements nécessaires pour exécuter un test réussi.

   Près de la partie supérieure de [!UICONTROL Traffic Estimator], les valeurs que vous avez saisies sont calculées et les résultats s’affichent.

   ![ Estimation de trafic avec valeurs et résultats affichés](assets/ap_est_no.png)

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez de nombreuses combinaisons et que votre taux de conversion et vos impressions sont trop faibles, la [!UICONTROL Traffic Estimator] indique la durée pendant laquelle le test doit s’exécuter pour réussir. Ou, si votre trafic est faible, le [!UICONTROL Traffic Estimator] peut suggérer un nombre inférieur de combinaisons d’offres afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous ne disposez pas d’un trafic suffisant, tenez compte des points suivants :

   * Pensez à utiliser une activité de [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) au lieu de [!UICONTROL Automated Personalization] pour créer des expériences avec plusieurs changements d’offres dans une variation d’expérience.
   * Réduisez le nombre de combinaisons d’offres dans votre activité [!UICONTROL Automated Personalization].
   * Augmentez la durée de l’activité.

   Ajustez les nombres jusqu&#39;à ce que le [!UICONTROL Traffic Estimator] indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.

   ![Estimateur de trafic présentant un message de trafic suffisant](assets/ap_est_yes.png)

   Si le trafic est suffisant, l’icône [!UICONTROL Traffic] affiche une coche verte. S’il est insuffisant, l’icône affiche une étiquette d’avertissement rouge.

## Questions fréquentes sur l’estimateur de trafic

Tenez compte des questions fréquentes suivantes lorsque vous utilisez [!UICONTROL Traffic Estimator] :

### Pourquoi les modèles personnalisés ne sont-ils pas créés même si mon activité AP a suffisamment de trafic ?

Dans certaines circonstances, votre trafic est suffisamment important pour qu’un modèle personnalisé soit créé, mais ce trafic peut informer [!DNL Target] qu’il n’existe aucune différence significative entre le modèle personnalisé et le modèle aléatoire. Bien que le modèle soit créé dans [!DNL Target] et testé, il n’est pas déployé, car il n’est pas meilleur que aléatoire.

Une raison possible pour que le modèle ne soit pas meilleur que aléatoire est que les offres ne sont pas assez différentes les unes des autres. Si tel est le cas, vous pouvez essayer de rendre les offres plus visuellement différentes si la messagerie est similaire, ou vous pouvez essayer de modifier la messagerie elle-même.
