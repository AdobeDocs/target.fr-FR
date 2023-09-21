---
keywords: priorité;création d’expérience;priorité;expérience;audience;expérience;changer d’expérience;compositeur d’expérience visuelle
description: Découvrez comment les visiteurs peuvent passer d’une expérience à une autre [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] (XT) à mesure que leurs profils évoluent.
title: Les visiteurs peuvent-ils changer d’expérience dans une [!UICONTROL Ciblage d’expérience] Activité ?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 44%

---

# Changement d’expérience dans [!UICONTROL Ciblage d’expérience]

Avec [!UICONTROL Ciblage d’expérience], vous pouvez contrôler l’expérience que les visiteurs voient au fur et à mesure de l’évolution de leurs profils.

La liste suivante présente quelques scénarios dans lesquels les profils des visiteurs peuvent évoluer et vous pouvez présenter un contenu différent en fonction de ces modifications :

| Scénario | Détails |
|--- |--- |
| Emplacement géographique | Quand des visiteurs voyagent, pour affaires ou pour leurs loisirs, ils peuvent se rendre sur votre site web ou application mobile depuis différents emplacements géographiques. |
| État du client | Les visiteurs peuvent être considérés comme des prospects avant de créer un compte ou d’acheter un produit. |
| Affinité catégorielle | L’ [affinité catégorielle](/help/main/c-target/c-visitor-profile/category-affinity.md) fonctionnalité dans [!DNL Target] capture automatiquement les catégories vues par les visiteurs, puis calcule l’affinité des visiteurs avec la catégorie à des fins de ciblage. Par exemple, les visiteurs qui ont consulté plusieurs articles sur votre site web concernant un sujet particulier se voient présenter du contenu en rapport avec ce sujet. |
| Jour de la semaine | Tandis que le week-end approche, vous pouvez présenter aux visiteurs du contenu sur des films, des restaurants ou d’autres formes de divertissement. |

Pour utiliser ces fonctionnalités dans [!DNL Target], il est important de comprendre les informations suivantes lorsque vous utilisez [!UICONTROL Ciblage d’expérience] activités :

* **La priorité est régie par l’ordre des expériences, du haut vers le bas.** Si un visiteur est admissible pour plus de deux audiences, il reçoit du contenu de l’expérience de priorité supérieure.
* **Les visiteurs passent d’une expérience à une autre [!UICONTROL Ciblage d’expérience] activité s’ils commencent à se qualifier pour l’audience d’une expérience de priorité supérieure.**

  Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en Allemagne, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web en Allemagne, ce visiteur est passé à l’expérience B (Visiteurs d’Allemagne).

  ![Priorité États-Unis > Allemagne](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Les visiteurs passent également d’une expérience à l’autre s’ils ne se qualifient plus pour leur audience actuelle, mais commencent à se qualifier pour une expérience de priorité inférieure.**
* **Si les visiteurs cessent de se qualifier pour leur expérience actuelle et ne remplissent pas les critères d’une autre expérience, ils voient le contenu par défaut.**

  Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en France, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web depuis la France, ce visiteur reste dans l’expérience d’origine.

  ![Priorité États-Unis > Allemagne](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Une expérience ciblée sur &quot;Tous les visiteurs&quot; peut être utilisée comme dernière expérience dans la variable [!UICONTROL Ciblage d’expérience] pour &quot;attraper&quot; les visiteurs qui ne sont qualifiés pour aucune autre expérience. Si une expérience ciblée sur &quot;Tous les visiteurs&quot; n’est pas la dernière dans l’ordre, les autres expériences ciblées répertoriées en dessous de cette expérience sont toujours évaluées.**

  Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en Allemagne, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web depuis l’Allemagne, ce visiteur reste dans l’expérience A (Visiteurs des États-Unis).

  ![Priorité États-Unis > Tous les visiteurs](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  Si cela n’est pas souhaitable, vous pouvez créer une audience explicitement définie comme l’inverse de l’audience ciblée, comme indiqué dans l’exemple suivant :

  ![Priorité États-Unis > Non-États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Avec une seule expérience [!UICONTROL Ciblage d’expérience] , les visiteurs restent dans une expérience même s’ils ne remplissent plus les critères de l’audience qui les a placés dans cette expérience.**

  Si cela n’est pas souhaitable, vous pouvez créer une autre expérience ciblée sur l’audience inverse (par exemple, « Hors États-Unis » contrairement à « États-Unis »).

  Vous pouvez également créer une [!UICONTROL Test A/B] activité ciblée sur l’audience souhaitée avec une affectation de trafic à 100 %, comme illustré ci-dessous :

  ![Priorité d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **[!DNL Target]La priorité des expériences est définie par leur ordre (de haut en bas), de la même façon qu’elles s’affichent dans l’interface utilisateur de .**

  Cela est important dans les cas où un visiteur peut remplir les critères de plusieurs de vos audiences. Si, par exemple, vous avez deux expériences : l’une ciblée sur &quot;États-Unis&quot; et l’autre sur &quot;New York&quot;, un visiteur situé à New York est admissible pour les deux audiences. Par conséquent, vous devez vous assurer que l’expérience &quot;New York&quot; est définie avant l’expérience &quot;États-Unis&quot; dans la variable [!DNL Target] Interface utilisateur. Cette pratique garantit que l’expérience &quot;New York&quot; la plus ciblée a la priorité la plus élevée, comme illustré dans l’exemple suivant :

  ![Priorité New York > États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
