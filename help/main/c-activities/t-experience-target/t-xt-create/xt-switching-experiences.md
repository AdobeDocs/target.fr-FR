---
keywords: priorité;création d’expérience;priorité;expérience;audience;expérience;changer d’expérience;compositeur d’expérience visuelle
description: Découvrez comment les visiteurs peuvent basculer entre les expériences d’une activité  [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) à mesure que leurs profils évoluent.
title: Les visiteurs peuvent-ils changer d’expérience dans une activité [!UICONTROL Experience Targeting] ?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 43%

---

# Changement d’expérience dans [!UICONTROL Experience Targeting]

Avec [!UICONTROL Experience Targeting], vous pouvez contrôler l’expérience que les visiteurs voient évoluer au fur et à mesure de leurs profils.

La liste suivante présente quelques scénarios dans lesquels les profils des visiteurs peuvent évoluer et que vous souhaiterez peut-être présenter différents contenus en fonction de ces modifications :

| Scénario | Détails |
|--- |--- |
| Emplacement géographique | Quand des visiteurs voyagent, pour affaires ou pour leurs loisirs, ils peuvent se rendre sur votre site web ou application mobile depuis différents emplacements géographiques. |
| État du client | Les visiteurs peuvent être considérés comme des prospects avant de créer un compte ou d’acheter un produit. |
| Affinité catégorielle | La fonction [affinité catégorielle](/help/main/c-target/c-visitor-profile/category-affinity.md) de [!DNL Target] capture automatiquement la vue des catégories visiteur, puis calcule l’affinité des visiteurs pour la catégorie à des fins de ciblage. Par exemple, les visiteurs et visiteuses qui ont consulté plusieurs articles sur un sujet particulier sur votre site web reçoivent du contenu associé à ce sujet. |
| Jour de la semaine | Tandis que le week-end approche, vous pouvez présenter aux visiteurs du contenu sur des films, des restaurants ou d’autres formes de divertissement. |

Pour utiliser ces fonctionnalités dans [!DNL Target], il est important de comprendre les informations suivantes lorsque vous travaillez avec des activités [!UICONTROL Experience Targeting] :

* **La priorité est régie par l’ordre des expériences, du haut vers le bas.** Si un visiteur se qualifie pour plus de deux audiences, il reçoit le contenu de l’expérience avec la priorité la plus élevée.
* **Les visiteurs passent d’une expérience à l’autre dans une activité [!UICONTROL Experience Targeting] s’ils commencent à se qualifier pour l’audience d’une expérience à priorité plus élevée.**

  Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en Allemagne, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web en Allemagne, ce visiteur est passé à l’expérience B (Visiteurs d’Allemagne).

  ![Priorité États-Unis > Allemagne](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

* **Les visiteurs changent également d’expérience s’ils cessent de se qualifier pour leur audience actuelle mais commencent à se qualifier pour une expérience de priorité inférieure.**
* **Si les visiteurs cessent de se qualifier pour leur expérience actuelle et ne se qualifient pas pour une autre expérience, ils verront le contenu par défaut.**

  Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en France, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web depuis la France, ce visiteur reste dans l’expérience d’origine.

  ![Priorité États-Unis > Allemagne](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

* **Une expérience ciblée sur « Tous les visiteurs » peut être utilisée comme dernière expérience dans l’activité [!UICONTROL Experience Targeting] pour « attraper » les visiteurs qui ne se qualifient pour aucune autre expérience. Si une expérience ciblée sur « Tous les visiteurs » n’est pas la dernière dans l’ordre, les autres expériences ciblées répertoriées en dessous de cette expérience sont toujours évaluées.**

  Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en Allemagne, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web depuis l’Allemagne, ce visiteur reste dans l’expérience A (visiteurs américains).

  ![Priorité États-Unis > Tous les visiteurs](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-refresh.png)

  Si cela n’est pas souhaitable, vous pouvez créer une audience explicitement définie comme l’inverse de l’audience ciblée, comme indiqué dans l’exemple suivant :

  ![Priorité États-Unis > Non-États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/not-us.png)

* **Avec une activité de [!UICONTROL Experience Targeting] d’expérience unique, les visiteurs restent dans une expérience même s’ils ne remplissent plus les critères de l’audience qui les a placés dans cette expérience.**

  Si cela n’est pas souhaitable, vous pouvez créer une autre expérience ciblée sur l’audience inverse (par exemple, « Hors États-Unis » contrairement à « États-Unis »).

  Vous pouvez également créer une activité [!UICONTROL A/B Test] ciblée sur l’audience souhaitée avec une affectation du trafic de 100 %, comme illustré ci-dessous :

  ![Priorité d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-refresh.png)

* **La priorité des expériences est définie par leur ordre (de haut en bas) telle qu’elles s’affichent dans l’interface utilisateur de [!DNL Target].**

  Cela est important dans les cas où un visiteur peut remplir les critères de plusieurs de vos audiences. Par exemple, si vous avez deux expériences : l’une ciblée sur « États-Unis » et l’autre ciblée sur « New York », un visiteur situé à New York se qualifie pour les deux audiences. Par conséquent, vous devez vous assurer que l’expérience « New York » est définie avant l’expérience « États-Unis » dans l’interface utilisateur de [!DNL Target]. Cette pratique garantit que l’expérience « New York » plus ciblée a la priorité la plus élevée, comme illustré dans l’exemple suivant :

  ![Priorité New York > États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-refresh.png)
