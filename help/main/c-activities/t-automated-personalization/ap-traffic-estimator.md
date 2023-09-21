---
keywords: estimateur de trafic;personnalisation automatisée;ap;estimation du trafic
description: Utilisez la variable [!DNL Adobe Target] [!UICONTROL estimateur de trafic] pour déterminer si le trafic de votre [!UICONTROL Automated Personalization] pour réussir.
title: Quantité de trafic requise pour une réussite [!UICONTROL Automated Personalization] Activité ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 11%

---

# Estimation du trafic requis pour réussir un test

La variable [!DNL Adobe Target] [!UICONTROL estimateur de trafic] fournit des commentaires qui vous permettent de savoir si votre trafic est suffisant pour votre [!UICONTROL Automated Personalization] (AP) pour réussir.

Parce que [!UICONTROL Automated Personalization] Les activités utilisent plusieurs combinaisons d’offres. Il est important de connaître le volume de trafic requis pour fournir des résultats significatifs. La variable [!UICONTROL estimateur de trafic] utilise des statistiques sur votre page et le nombre d’expériences en cours de test afin d’estimer le volume de trafic et la durée du test nécessaires au succès de l’activité.

La variable [!UICONTROL estimateur de trafic] détermine si le trafic est suffisant pour générer des modèles personnalisés en comparant l’estimation des impressions de page et le taux de conversion type des pages. Idéalement, pour une activité réussie, la taille d’échantillon appropriée garantit que le contenu personnalisé est prêt au bout de 50 % de la durée de l’activité ou 14 jours, selon la durée la plus courte. Ce processus laisse suffisamment de temps pour obtenir du contenu personnalisé et apprendre quel contenu diffuser.

N’oubliez pas que [!DNL Target] diffuse de manière aléatoire des expériences jusqu’à ce que les algorithmes de personnalisation soient créés. L’icône en forme de coche en regard de chaque offre indique le moment où le modèle de cette offre est prêt et [!DNL Target] peut commencer à diffuser du contenu personnalisé. Comme l’effet élévateur n’est attendu qu’une fois les modèles prêts, l’indication visuelle vous permet de définir les attentes appropriées. Utilisez la variable [!UICONTROL estimateur de trafic] dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour obtenir une indication du moment où les modèles sont prêts.

## Utilisation de l’estimateur de trafic

1. Dans la [!UICONTROL Expériences] de la page [!UICONTROL Compositeur d’expérience visuelle] dans un [!UICONTROL Automated Personalization] , cliquez sur l’activité  **[!UICONTROL Trafic]** Icône

   ![Icône de trafic](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   La variable [!UICONTROL estimateur de trafic] s’ouvre. Vous pouvez à nouveau cliquer sur **[!UICONTROL Trafic]**[!UICONTROL  pour masquer l’estimateur de trafic].

   ![Interface utilisateur de l’estimateur de trafic](assets/ap_est.png)

1. Indiquez le taux de conversion type (ou le taux de conversion escompté pour cette activité), l’estimation des impressions de l’activité par jour et la durée du test.

   | Mesure | Description |
   | --- | --- |
   | **[!UICONTROL Nombre d’offres]** | Cette mesure est calculée automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité, après toute exclusion. |
   | **[!UICONTROL Taux de conversion type]** | Cette mesure est exprimée en pourcentage, selon votre estimation ou les données antérieures provenant de votre système d’analyse. |
   | **[!UICONTROL Estimation du nombre de visites par jour]** | Cette mesure correspond au nombre de visites par jour effectuées par des visiteurs qui peuvent visualiser l’activité, selon les critères de ciblage. Cette mesure peut être basée sur vos données d’analyse. Ce nombre doit être constitué de visites, et non de visiteurs uniques. |
   | **[!UICONTROL Durée du test]** | Nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute. |

   La variable [!UICONTROL estimateur de trafic] utilise ces mesures pour déterminer les ajustements nécessaires pour exécuter un test réussi.

   Près de la partie supérieure de la [!UICONTROL estimateur de trafic], les valeurs que vous avez saisies sont calculées et les résultats s&#39;affichent.

   ![Estimation de trafic avec valeurs et résultats affichés](assets/ap_est_no.png)

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez de nombreuses combinaisons et que le taux de conversion et les impressions sont trop faibles, la variable [!UICONTROL estimateur de trafic] indique la durée pendant laquelle le test doit s’exécuter pour réussir. Ou, si votre trafic est faible, la variable [!UICONTROL estimateur de trafic] pourrait suggérer un nombre inférieur de combinaisons d’offres afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si vous ne disposez pas d’un trafic suffisant, tenez compte des points suivants :

   * Envisagez d’utiliser une [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) activité au lieu de [!UICONTROL Automated Personalization] pour créer des expériences avec plusieurs modifications d’offre dans une variation d’expérience.
   * Réduisez le nombre de combinaisons d’offres au sein de vos [!UICONTROL Automated Personalization] activité.
   * Augmentez la durée de l’activité.

   Ajustez les nombres jusqu’à ce que la fonction [!UICONTROL estimateur de trafic] indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.

   ![estimateur de trafic présentant un message de trafic suffisant](assets/ap_est_yes.png)

   Si le trafic est suffisant, la variable [!UICONTROL Trafic] affiche une coche verte. S’il est insuffisant, l’icône affiche une étiquette d’avertissement rouge.

## Questions fréquentes sur l’estimateur de trafic

Tenez compte des questions fréquentes suivantes lorsque vous utilisez le [!UICONTROL estimateur de trafic]:

### Pourquoi les modèles personnalisés ne sont-ils pas créés même si mon activité AP a suffisamment de trafic ?

Dans certains cas, votre trafic est suffisamment important pour qu’un modèle personnalisé soit créé, mais il peut informer le trafic. [!DNL Target] qu’il n’y a pas de différence significative entre le modèle personnalisé et le aléatoire. Bien que le modèle soit intégré [!DNL Target] et testé, il n’est pas déployé, car le modèle n’est pas meilleur que aléatoire.

Une raison possible pour que le modèle ne soit pas meilleur que aléatoire est que les offres ne sont pas assez différentes les unes des autres. Si tel est le cas, vous pouvez essayer de rendre les offres plus visuellement différentes si la messagerie est similaire, ou vous pouvez essayer de modifier la messagerie elle-même.
