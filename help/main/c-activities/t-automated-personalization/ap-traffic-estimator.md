---
keywords: estimateur de trafic;automated personalization;ap;estimer le trafic
description: Utilisez l’[!UICONTROL Estimateur de trafic] pour déterminer si vous disposez d’un trafic suffisant pour qu’une activité [!UICONTROL Automated Personalization] réussisse.
title: Quelle quantité de trafic est nécessaire pour réussir une activité  ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 794
ht-degree: 8%

---

# Estimation du trafic requis pour réussir un test

L’[!DNL Adobe Target] [!UICONTROL Estimateur de trafic] fournit des commentaires qui vous permettent de savoir si vous disposez d’un trafic suffisant pour que votre activité [!UICONTROL Automated Personalization] (AP) réussisse.

Comme les activités  utilisent plusieurs combinaisons d’offres, il est important de connaître le trafic requis pour obtenir des résultats significatifs. L’[!UICONTROL estimateur de trafic] utilise des statistiques sur votre page et le nombre d’expériences testées afin d’estimer la quantité de trafic et la durée de test nécessaires pour que l’activité réussisse.

L’[!UICONTROL estimateur de trafic] détermine s’il y a suffisamment de trafic pour générer des modèles personnalisés en comparant l’estimation des impressions de page et le taux de conversion type pour les pages. Idéalement, pour une activité réussie, la taille d’échantillon appropriée garantit que le contenu personnalisé est prêt au bout de 50 % de la durée de l’activité ou 14 jours, selon la durée la plus courte. Ce processus laisse suffisamment de temps pour obtenir du contenu personnalisé et apprendre quel contenu diffuser.

N’oubliez pas que [!DNL Target] diffuse les expériences de manière aléatoire jusqu’à ce que les algorithmes de personnalisation soient créés. L’icône en forme de coche en regard de chaque offre s’affiche lorsque le modèle de cette offre est prêt et que [!DNL Target] peut commencer à diffuser du contenu personnalisé. Comme l’effet élévateur n’est attendu qu’une fois les modèles prêts, l’indication visuelle vous permet de définir l’attente appropriée. Utilisez l’[!UICONTROL Estimateur de trafic] dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour obtenir des instructions sur le moment où les modèles sont prêts.

## Utilisation de l’estimateur de trafic

1. Sur la page [!UICONTROL Expériences] du [!UICONTROL Compositeur d’expérience visuelle] d’une activité [!UICONTROL Automated Personalization], cliquez sur l’icône **[!UICONTROL Trafic]** ( ![icône d’estimateur de trafic](/help/main/assets/icons/Gauge2.svg) ) dans le coin supérieur gauche de la page [!UICONTROL Expériences].

   L’[!UICONTROL Estimateur de trafic] s’ouvre.

   ![&#x200B; Interface utilisateur de l’estimateur de trafic &#x200B;](assets/ap-est.png)

   Vous pouvez de nouveau cliquer sur l’icône pour masquer l’[!UICONTROL Estimateur de trafic].

1. Spécifiez le taux de conversion type (ou le taux de conversion attendu de cette activité), les impressions d’activité estimées par jour et la durée du test.

   | Mesure | Description |
   | --- | --- |
   | **[!UICONTROL Nombre d’offres]** | Cette mesure est calculée automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité, après les exclusions. |
   | **[!UICONTROL Taux de conversion standard]** | Cette mesure est exprimée en pourcentage, en fonction de votre estimation ou des données antérieures de votre système d’analyse. |
   | **[!UICONTROL Estimation Des Visites Par Jour]** | Cette mesure correspond au nombre de visites par jour des visiteurs et visiteuses qui peuvent visualiser l’activité, en fonction des critères de ciblage. Cette mesure peut être basée sur vos données d’analyse. Ce nombre doit être celui des visites, et non des visiteurs uniques. |
   | **[!UICONTROL Durée du test]** | Nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute. |

   L’[!UICONTROL estimateur de trafic] utilise ces mesures pour déterminer les ajustements nécessaires à l’exécution réussie d’un test.

   Dans la partie supérieure de l’[!UICONTROL Estimateur de trafic], les valeurs saisies sont calculées et les résultats affichés.

   ![Estimation du trafic avec les valeurs et les résultats affichés](assets/ap-est-no.png)

   Lorsque vous modifiez les valeurs, l’estimation change. Par exemple, si vous testez de nombreuses combinaisons et que votre taux de conversion et vos impressions sont trop faibles, l’[!UICONTROL Estimateur de trafic] indique la durée pendant laquelle le test doit s’exécuter pour réussir. Ou, si votre trafic est faible, l’[!UICONTROL Estimateur de trafic] peut suggérer un nombre inférieur de combinaisons d’offres afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   Si le trafic est insuffisant, tenez compte des points suivants :

   * Envisagez d’utiliser une activité de [[!UICONTROL ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) au lieu de [!UICONTROL Automated Personalization] pour créer des expériences avec plusieurs modifications d’offre dans une variation d’expérience.
   * Réduisez le nombre de combinaisons d’offres dans votre activité .
   * Augmentez la durée de l’activité.

   Ajustez les nombres jusqu’à ce que l’[!UICONTROL Estimateur de trafic] indique que vous disposez d’un trafic suffisant, puis concevez votre test en conséquence.

   ![Estimateur de trafic affichant un message de trafic suffisant](assets/ap-est-yes.png)

   Si le trafic est suffisant, l’icône [!UICONTROL Trafic] affiche une vérification verte. S’il est insuffisant, l’icône affiche une étiquette d’avertissement rouge.

## Questions fréquentes sur l’estimateur de trafic

Tenez compte des questions fréquentes suivantes lorsque vous utilisez l’[!UICONTROL estimateur de trafic] :

### Pourquoi les modèles personnalisés ne sont-ils pas créés même si mon activité AP a suffisamment de trafic ?

Dans certains cas, votre trafic est suffisamment important pour qu’un modèle personnalisé soit créé, mais ce trafic peut [!DNL Target] informer qu’il n’existe aucune différence significative entre le modèle personnalisé et le aléatoire. Bien que le modèle soit créé et testé en [!DNL Target], il n’est pas déployé, car il n’est pas meilleur que aléatoire.

Une raison possible pour laquelle le modèle n’est pas meilleur que aléatoire peut être que les offres ne sont pas suffisamment différentes les unes des autres. Si tel est le cas, vous pouvez essayer de rendre les offres plus visuellement différentes si le message est similaire, ou vous pouvez essayer de modifier le message lui-même.
