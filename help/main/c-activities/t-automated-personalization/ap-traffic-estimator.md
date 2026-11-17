---
keywords: estimateur de trafic;automated personalization;ap;estimer le trafic
description: Utilisez l’[!UICONTROL estimateur de trafic] pour évaluer si vous avez suffisamment de trafic pour qu’une activité [!UICONTROL Automated Personalization] réussisse.
title: Quelle est la quantité de trafic nécessaire pour réussir une activité [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: 'https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 8%
---
# Estimation du trafic requis pour réussir un test {#traffic-estimator}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser l’**[!UICONTROL estimateur de trafic]** pour vérifier si votre activité **[!UICONTROL Automated Personalization]** dispose d’un trafic suffisant pour réussir.

>[!ENDSHADEBOX]

L’[!DNL Adobe Target]**[!UICONTROL estimateur de trafic]** fournit des commentaires qui vous permettent de savoir si vous disposez d’un trafic suffisant pour que votre activité **[!UICONTROL Automated Personalization]** (AP) réussisse. Les activités AP utilisent plusieurs combinaisons d’offres. Il est donc important de connaître la quantité de trafic requise pour fournir des résultats significatifs. L’**[!UICONTROL estimateur de trafic]** utilise des statistiques sur votre page et le nombre d’expériences testées afin d’estimer la quantité de trafic et la durée de test nécessaires pour que l’activité réussisse.

L’**[!UICONTROL estimateur de trafic]** détermine s’il y a suffisamment de trafic pour générer des modèles personnalisés en comparant l’estimation des impressions de page et le taux de conversion type des pages. Idéalement, pour une activité réussie, la taille d’échantillon appropriée garantit que le contenu personnalisé est prêt au bout de 50 % de la durée de l’activité ou 14 jours, selon la durée la plus courte. Ce processus laisse suffisamment de temps pour obtenir du contenu personnalisé et apprendre quel contenu diffuser.

[!DNL Target] diffuse aléatoirement des expériences jusqu’à ce que les algorithmes de personnalisation soient créés. L’icône en forme de coche en regard de chaque offre s’affiche lorsque le modèle de cette offre est prêt et que [!DNL Target] peut commencer à diffuser du contenu personnalisé. L’effet élévateur n’est attendu qu’une fois les modèles prêts. L’indication visuelle vous permet donc de définir l’attente appropriée. Utilisez l’**[!UICONTROL estimateur de trafic]** dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) pour savoir quand les modèles sont prêts.

>[!NOTE]
>
>Un modèle personnalisé n’est pas toujours déployé, même si votre trafic est suffisant. [!DNL Target] crée et teste le modèle, mais il ne le déploie que s’il est plus performant qu’une sélection aléatoire d’expériences. Si le modèle n’est pas meilleur que aléatoire, les offres ne sont probablement pas suffisamment différentes les unes des autres. Dans ce cas, rendez les offres plus visuellement différentes si le message est similaire ou modifiez le message lui-même.

## Utilisation de l’estimateur de trafic {#use-traffic-estimator}

Lorsque vous créez une activité **[!UICONTROL Automated Personalization]**, l’**[!UICONTROL estimateur de trafic]** vous permet de vérifier si le trafic sur votre page est suffisant pour que les modèles personnalisés soient prêts à temps. L’exécution de cette vérification avant le lancement de l’activité vous permet d’éviter un test qui ne peut pas atteindre suffisamment de visiteurs pour diffuser du contenu personnalisé et vous montre comment ajuster le nombre de combinaisons d’offres ou la durée de l’activité si le trafic n’est pas suffisant.

1. À partir de votre activité **[!UICONTROL Automated Personalization]**, accédez à la page **[!UICONTROL Expériences]** du **[!UICONTROL Compositeur d’expérience visuelle].

1. Cliquez sur l’icône **[!UICONTROL Trafic]** (![icône de l’estimateur de trafic](/help/main/assets/icons/Gauge2.svg)).

   L&#39;estimateur de trafic **[!UICONTROL 0]** s&#39;ouvre. Pour fermer la fenêtre, cliquez de nouveau sur l’icône.

   ![Interface utilisateur de l’estimateur de trafic](assets/ap-est.png)

1. Spécifiez le taux de conversion type (ou le taux de conversion attendu de cette activité), les impressions d’activité estimées par jour et la durée du test.

   L’estimateur de trafic **** utilise ces mesures pour déterminer les ajustements nécessaires à l’exécution réussie d’un test.

   | Mesure | Description |
   | --- | --- |
   | **[!UICONTROL Nombre d’offres]** | Cette mesure est calculée automatiquement en fonction du nombre d’expériences créées dans le cadre de votre activité, après les exclusions. |
   | **[!UICONTROL Taux De Conversion Standard]** | Cette mesure est exprimée en pourcentage, en fonction de votre estimation ou des données antérieures de votre système d’analyse. |
   | **[!UICONTROL Estimation Des Visites Par Jour]** | Cette mesure correspond au nombre de visites par jour des visiteurs et visiteuses qui peuvent visualiser l’activité, en fonction des critères de ciblage. Cette mesure peut être basée sur vos données d’analyse. Ce nombre doit être celui des visites, et non des visiteurs uniques. |
   | **[!UICONTROL Durée Du Test]** | Nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute. |



1. Passez en revue les résultats. Lorsque vous modifiez les valeurs, l’estimation change.

   Par exemple, si vous testez de nombreuses combinaisons et que votre taux de conversion et vos impressions sont trop faibles, l’**[!UICONTROL estimateur de trafic]** indique la durée pendant laquelle le test doit s’exécuter pour réussir. Ou, si votre trafic est faible, l’**[!UICONTROL estimateur de trafic]** peut suggérer un nombre inférieur de combinaisons d’offres afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

   ![Estimation du trafic avec affichage des valeurs et des résultats](assets/ap-est-no.png)

1. Si le trafic est insuffisant, tenez compte des options suivantes :

   * Utilisez une activité de [**[!UICONTROL ciblage automatique]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) au lieu de **[!UICONTROL Automated Personalization]** pour créer des expériences avec plusieurs modifications d’offre dans une variation d’expérience.
   * Réduisez le nombre de combinaisons d’offres dans votre activité **[!UICONTROL Automated Personalization]**.
   * Augmentez la durée de l’activité.

1. Ajustez les nombres jusqu&#39;à ce que l&#39;**[!UICONTROL estimateur de trafic]** indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.

   Si le trafic est suffisant, l’icône **[!UICONTROL Trafic]** affiche une vérification verte. S’il est insuffisant, l’icône affiche une étiquette d’avertissement rouge.

   ![Estimateur de trafic affichant un message de trafic suffisant](assets/ap-est-yes.png)
