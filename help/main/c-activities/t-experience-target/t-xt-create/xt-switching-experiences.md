---
keywords: priorité;création d’expérience;priorité;expérience;audience;expérience;changer d’expérience;compositeur d’expérience visuelle
description: Découvrez comment les visiteurs peuvent passer d’une expérience à l’autre dans un Adobe [!DNL Target] l’activité de ciblage d’expérience (XT) à mesure que leurs profils évoluent.
title: Les visiteurs peuvent-ils changer d’expérience dans une activité de ciblage d’expérience ?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: ceae12da7ee3580a943da180e8705fc5d4ab646a
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 96%

---

# Changement d’expérience dans Adobe Experience Targeting

Informations sur la manière dont les visiteurs peuvent passer d’une expérience à une autre, au fur et à mesure de l’évolution de leurs profils, dans une activité de ciblage d’expérience.

Grâce au ciblage d’expérience, vous pouvez contrôler quelle expérience voient les visiteurs au fur et à mesure de l’évolution de leurs profils. La liste ci-après présente quelques scénarios dans lesquels les profils des visiteurs peuvent évoluer et pour lesquels vous pouvez présenter un autre contenu :

| Scénario | Détails |
|--- |--- |
| Emplacement géographique | Quand des visiteurs voyagent, pour affaires ou pour leurs loisirs, ils peuvent se rendre sur votre site web ou application mobile depuis différents emplacements géographiques. |
| État du client | Les visiteurs peuvent être considérés comme des prospects avant de créer un compte ou d’acheter un produit. |
| Affinité catégorielle | L’ [affinité catégorielle](/help/main/c-target/c-visitor-profile/category-affinity.md) de Target capture automatiquement les catégories visitées par un utilisateur, puis calcule l’affinité de ce dernier avec les différentes catégories à des fins de ciblage. Par exemple, les visiteurs qui ont consulté sur votre site web plusieurs articles concernant un sujet particulier peuvent se voir présenter du contenu en rapport avec ce sujet. |
| Jour de la semaine | Tandis que le week-end approche, vous pouvez présenter aux visiteurs du contenu sur des films, des restaurants ou d’autres formes de divertissement. |

Pour profiter de ces fonctionnalités dans [!DNL Target], il est important de comprendre les informations suivantes au sujet des activités de ciblage d’expérience :

* **La priorité est régie par l’ordre des expériences, du haut vers le bas.** Si un visiteur se qualifie pour plus de deux audiences, il reçoit du contenu de l’expérience avec la priorité supérieure.
* **Les visiteurs basculeront entre les expériences dans une activité XT s’ils commencent à se qualifier pour l’audience d’une expérience de qualité supérieure.**

   Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en Allemagne, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web en Allemagne, ce visiteur est passé à l’expérience B (Visiteurs d’Allemagne).

   ![Priorité États-Unis > Allemagne](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Les visiteurs basculeront également entre les expériences s’ils cessent de se qualifier pour l’audience actuelle et commencent à se qualifier pour une expérience de priorité inférieure.**
* **Si les visiteurs cessent de se qualifier pour leur expérience actuelle, sans se qualifier pour une autre expérience, il verront alors le contenu par défaut.**

   Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en France, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web en France, ce visiteur restera dans l’expérience initiale.

   ![Priorité États-Unis > Allemagne](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Une expérience ciblée sur « Tous les visiteurs » peut être utilisée comme dernière expérience de l’activité de ciblage d’expérience pour « rattraper » les visiteurs qui n’ont pas été dirigés vers une autre expérience. Si une expérience ciblée sur « Tous les visiteurs » n’est pas la dernière dans l’ordre des expériences, les autres expériences ciblées figurant plus bas que cette expérience dans la liste seront quand même évaluées.**

   Par exemple, dans la configuration de l’activité suivante, un visiteur a consulté votre site web depuis les États-Unis, puis s’est rendu en Allemagne, d’où il a de nouveau consulté votre site web. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web depuis l’Allemagne, ce visiteur restera dans l’expérience A (Visiteurs des États-Unis).

   ![Priorité États-Unis > Tous les visiteurs](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

   Si cela n’est pas souhaitable, vous pouvez créer une audience explicitement définie comme l’inverse de l’audience ciblée, comme indiqué dans l’exemple suivant :

   ![Priorité États-Unis > Non-États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Dans une activité de ciblage d’une seule expérience, les visiteurs resteront dans une expérience même s’ils ne remplissent plus les critères de l’audience qui les a placés dans cette expérience.**

   Si cela n’est pas souhaitable, vous pouvez créer une autre expérience ciblée sur l’audience inverse (par exemple, « Hors États-Unis » contrairement à « États-Unis »).

   Vous pouvez aussi créer une activité A/B ciblée sur l’audience recherchée avec une affectation de trafic à 100 %, comme indiqué ci-dessous :

   ![Priorité d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **La priorité des expériences est définie par leur ordre (de haut en bas), de la même façon qu’elles s’affichent dans l’interface utilisateur de Target.**

   Cela est important dans les cas où un visiteur peut remplir les critères de plusieurs de vos audiences. Supposons, par exemple, que vous ayez deux expériences : l’une ciblée sur les États-Unis, l’autre sur New York. Un visiteur se trouvant à New York remplirait alors les critères des deux audiences. Vous devez, par conséquent, veiller à ce que l’expérience New York soit définie avant l’expérience États-Unis dans l’interface utilisateur de Target. Ainsi, l’expérience New York la plus ciblée a la priorité la plus élevée, comme illustré dans l’exemple ci-après :

   ![Priorité New York > États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
