---
keywords: estimation du trafic;estimateur de trafic;estimation;trafic;confiance;puissance statistique;effet élévateur;bonferroni;taux de conversion;visiteurs par jour;durée
description: Découvrez comment utiliser l’estimateur de trafic qui vous permet de savoir si vous disposez d’un trafic suffisant pour que votre activité de [!DNL Adobe Target] [!UICONTROL test multivarié] réussisse.
title: Quelle quantité de trafic est nécessaire pour une activité de [!UICONTROL test multivarié] (MVT) ?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: 'https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 8%
---
# Estimation du trafic requis pour une activité de [!UICONTROL test multivarié] réussie {#traffic-estimator}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser l’**[!UICONTROL estimateur de trafic]** pour vérifier si votre activité de **[!UICONTROL test multivarié]** dispose d’un trafic suffisant pour réussir.

>[!ENDSHADEBOX]

Un test multivarié compare plusieurs expériences. Il est donc important de connaître la quantité de trafic requise pour fournir des résultats significatifs. L’**[!UICONTROL estimateur de trafic]** utilise des statistiques sur votre page et le nombre d’expériences testées afin d’estimer la quantité de trafic et la durée de test nécessaires pour réussir le test. Il fournit également des commentaires qui vous permettent de savoir si vous disposez d’un trafic suffisant pour le test que vous avez conçu pour réussir.

L’estimateur de trafic **&#x200B;**&#x200B;prédit la taille d’échantillon nécessaire pour garantir les éléments suivants :

* **Confiance à 95 %.** Cette statistique signifie que la probabilité de signaler un faux positif en l’absence d’effet élévateur réel est de 5 % (100 % - niveau de confiance).
* **80 % de puissance statistique.** Cette statistique signifie que le test a une probabilité de 80 % de détecter une portance réelle de 25 % ou plus.
* **25 % minimum d&#39;effet élévateur détectable de manière fiable.** [!DNL Target] calcule la quantité de trafic requise pour avoir une probabilité de 80 % de détecter une augmentation réelle de 25 % ou plus.

Le test utilise la correction de Bonferroni pour effectuer des corrections pour plusieurs comparaisons. Cette méthode est connue pour être conservative, ce qui est équilibré par l’application d’un effet élévateur minimal détectable de manière fiable relativement important.

## Utilisation de l’estimateur de trafic {#use-traffic-estimator}

Lors de la conception d’un **[!UICONTROL test multivarié]**, l’**[!UICONTROL estimateur de trafic]** vous permet de vérifier si le trafic sur votre page est suffisant pour le nombre d’expériences que vous prévoyez de tester. L’exécution de cette vérification avant le lancement du test vous permet d’éviter un test qui ne peut pas atteindre un nombre suffisant de visiteurs pour produire des résultats significatifs. Elle vous montre également comment ajuster le nombre de combinaisons ou la durée du test si le trafic n’est pas suffisant.

1. Dans la page **[!UICONTROL Expériences]** du **[!UICONTROL Compositeur d’expérience visuelle]** d’une activité **[!UICONTROL Multivarié]**, cliquez sur l’icône **[!UICONTROL Trafic]** (icône ![Estimateur de trafic](/help/main/assets/icons/Gauge2.svg)) dans le coin supérieur gauche de la page.

   L&#39;estimateur de trafic **[!UICONTROL 0]** s&#39;ouvre. Pour le masquer, cliquez de nouveau sur l’icône .

   ![Interface utilisateur de l’estimateur de trafic](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Près de la partie supérieure de l’**[!UICONTROL estimateur de trafic]**, les valeurs que vous avez saisies sont calculées et les résultats s’affichent.

1. (Facultatif) Fournissez le taux de conversion type, le nombre estimé de visiteurs par jour et la durée du test.

   L&#39;**[!UICONTROL estimateur de trafic]** utilise ces statistiques pour déterminer les ajustements nécessaires à l&#39;exécution réussie d&#39;un test.

   | Mesure | Description |
   | --- | --- |
   | **[!UICONTROL Nombre de combinaisons de contenu]** | Cette mesure est calculée automatiquement, en fonction du nombre d’expériences créées dans le cadre de votre activité, après les exclusions. |
   | **[!UICONTROL Taux De Conversion Standard]** | Cette mesure est exprimée en pourcentage, en fonction de votre estimation ou des données antérieures de votre système d’analyse. |
   | **[!UICONTROL Estimation Du Nombre De Visiteurs Par Jour]** | Cette mesure correspond au nombre de visiteurs et visiteuses susceptibles d’afficher cette page, en fonction des critères de ciblage. Ce nombre peut être basé sur vos données d’analyse. |
   | **[!UICONTROL Durée Du Test]** | Nombre de jours pendant lesquels vous souhaitez que l’activité s’exécute. |

1. Passez en revue les résultats. Lorsque vous modifiez les valeurs, l’estimation change.

   Par exemple, si vous testez de nombreuses expériences et que votre taux de conversion et vos impressions sont trop faibles, l’**[!UICONTROL estimateur de trafic]** indique combien de temps l’exécution du test doit durer pour réussir. Si votre trafic est faible, l’**[!UICONTROL estimateur de trafic]** peut suggérer un nombre d’expériences inférieur afin que vous puissiez exécuter le test pendant le nombre de jours souhaité.

1. Si vous ne disposez pas d’un trafic suffisant, effectuez l’une ou l’autre des opérations suivantes, ou les deux :

   * Réduire le nombre de combinaisons d’offres et le nombre d’emplacements.
   * Augmenter la durée du test.

1. Ajustez les nombres jusqu&#39;à ce que l&#39;**[!UICONTROL estimateur de trafic]** indique que vous avez suffisamment de trafic, puis concevez votre test en conséquence.
