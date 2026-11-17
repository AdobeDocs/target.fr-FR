---
keywords: priorité;création d’expérience;priorité;expérience;audience;expérience;changer d’expérience;compositeur d’expérience visuelle
description: Découvrez comment les visiteurs peuvent basculer entre les expériences dans une activité de [!DNL Adobe Target] [!UICONTROL Ciblage d’expérience] (XT) au fur et à mesure de l’évolution de leurs profils.
title: Les visiteurs peuvent-ils changer d’expérience dans une activité de [!UICONTROL ciblage d’expérience] ?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
TQID: 'https://experienceleague.adobe.com/4bBukCristluFUClhewMcSsNMTPjLjXEqM1QyyropKU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: b6f5758b-84f7-4943-8b05-1297a046943c
    internal-label: Experience target
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aaa094f4f36b6088ca180637d8054b6d5ff59d60
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 20%
---
# Changement d’expérience dans le [!UICONTROL ciblage d’expérience] {#switching-experiences}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez le fonctionnement de la priorité dans une activité de **[!UICONTROL Ciblage d’expérience]** et le moment où les visiteurs passent d’une expérience à l’autre au fur et à mesure de l’évolution de leurs profils.

>[!ENDSHADEBOX]

Avec le **[!UICONTROL ciblage d’expérience]**, vous pouvez contrôler l’expérience que les visiteurs voient au fur et à mesure de l’évolution de leurs profils. Le profil d’un visiteur ou d’une visiteuse peut changer de plusieurs façons et vous souhaiterez peut-être présenter différents contenus en fonction de ces modifications. Le tableau suivant en fournit quelques exemples :

| Scénario | Détails |
|--- |--- |
| Emplacement géographique | Quand des visiteurs voyagent, pour affaires ou pour leurs loisirs, ils peuvent se rendre sur votre site web ou application mobile depuis différents emplacements géographiques. |
| État du client | Les visiteurs peuvent être considérés comme des prospects avant de créer un compte ou d’acheter un produit. |
| Affinité catégorielle | La fonctionnalité [affinité catégorielle](/help/main/c-target/c-visitor-profile/category-affinity.md) de [!DNL Target] capture automatiquement les catégories affichées par les visiteurs, puis calcule l’affinité des visiteurs pour chaque catégorie à des fins de ciblage. Par exemple, les visiteurs et visiteuses qui ont consulté plusieurs articles sur un sujet particulier sur votre site web reçoivent du contenu associé à ce sujet. |
| Jour de la semaine | Tandis que le week-end approche, vous pouvez présenter aux visiteurs du contenu sur des films, des restaurants ou d’autres formes de divertissement. |

Pour utiliser ces fonctionnalités dans [!DNL Target], il est important de comprendre les informations suivantes lorsque vous utilisez les activités de **[!UICONTROL ciblage d’expérience]**.

## Comment sont servis les visiteurs {#how-visitors-are-served}

L’ordre des expériences dans l’interface utilisateur [!DNL Target], de haut en bas, contrôle leur priorité. Définissez donc l’expérience la plus ciblée avant la plus large. Le tableau suivant résume ce que les visiteurs voient dans chaque situation.

| Situation | Ce que le visiteur voit |
|--- |--- |
| Le visiteur se qualifie pour plusieurs audiences. | Contenu de l’expérience dont la priorité est la plus élevée. |
| Le visiteur commence à se qualifier pour l’audience d’une expérience à priorité plus élevée. | Le visiteur passe à l’expérience avec une priorité plus élevée. |
| Le visiteur cesse de se qualifier pour l’audience actuelle, mais commence à se qualifier pour une expérience de priorité inférieure. | Le visiteur passe à l’expérience de priorité inférieure. |
| Le visiteur cesse de se qualifier pour l’expérience actuelle et ne se qualifie plus pour une autre expérience. | Contenu par défaut. |
| Le visiteur ne s’est qualifié pour aucune autre expérience et la dernière expérience est ciblée sur « Tous les visiteurs ». | L’expérience « Tous les visiteurs ». Cette expérience « attrape » les visiteurs qui ne se sont qualifiés pour aucune autre expérience. |
| Une expérience ciblée sur « Tous les visiteurs » n’est pas la dernière dans la commande. | Les expériences ciblées répertoriées en dessous de l’expérience « Tous les visiteurs » sont toujours évaluées. |
| L’activité a une seule expérience et le visiteur ne remplit plus les critères de son audience. | Le visiteur reste dans l’expérience. |

## Exemples {#examples}

Les exemples suivants illustrent ces situations.

### Priorité : New York et États-Unis

Si vous avez deux expériences, l’une ciblée sur « États-Unis » et l’autre sur « New York », un visiteur situé à New York se qualifie pour les deux audiences. Par conséquent, vous devez définir l’expérience « New York » avant l’expérience « États-Unis » dans l’interface utilisateur [!DNL Target]. Cette pratique garantit que l’expérience « New York » plus ciblée a la priorité la plus élevée, comme illustré dans l’exemple suivant :

![Priorité New York > États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-refresh.png)

### Passer à une expérience hautement prioritaire : des États-Unis à l’Allemagne

Dans la configuration d’activité suivante, un visiteur a accédé à votre site web depuis les États-Unis, puis s’est rendu en Allemagne et a visité votre site web une seconde fois. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web en Allemagne, ce visiteur est passé à l’expérience B (Visiteurs d’Allemagne).

![Priorité États-Unis > Allemagne](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### Laisser le public : les États-Unis à la France

Dans la configuration d’activité suivante, un visiteur a accédé à votre site web depuis les États-Unis, puis a voyagé en France et visité votre site web une seconde fois. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web depuis la France, ce visiteur reste dans l’expérience d’origine.

![Priorité US > Allemagne, visiteur de France](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### Expérience ciblée sur tous les visiteurs

Dans la configuration d’activité suivante, un visiteur a accédé à votre site web depuis les États-Unis, puis s’est rendu en Allemagne et a visité votre site web une seconde fois. Durant sa première visite, ce visiteur relevait de l’expérience A (Visiteurs des États-Unis). Après avoir consulté votre site web depuis l’Allemagne, ce visiteur reste dans l’expérience A (visiteurs américains).

![Priorité États-Unis > Tous les visiteurs](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-refresh.png)

Si cela n’est pas souhaitable, vous pouvez créer une audience explicitement définie comme l’inverse de l’audience ciblée, comme indiqué dans l’exemple suivant :

![Priorité États-Unis > Non-États-Unis](/help/main/c-activities/t-experience-target/t-xt-create/assets/not-us.png)

### Activité à expérience unique

Avec une activité de **[!UICONTROL ciblage d’expérience]** à expérience unique, les visiteurs restent dans une expérience même s’ils ne remplissent plus les critères de l’audience qui les a placés dans cette expérience. Si cela n’est pas souhaitable, vous pouvez créer une autre expérience ciblée sur l’audience inverse (par exemple, « Pas aux États-Unis » par opposition à « États-Unis »). Une autre option consiste à créer une activité de **[!UICONTROL test A/B]** ciblée sur l’audience souhaitée avec une affectation de 100 % du trafic, comme illustré dans l’exemple suivant :

![Priorité d’une expérience](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-refresh.png)
