---
keywords: faq;questions fréquentes;forum aux questions;analytics pour target;a4T;mesure;définitions de mesures
description: Trouvez des réponses aux questions relatives aux définitions de mesures et à l’utilisation d’Analytics pour la Cible (A4T). A4T vous permet d’utiliser le rapports Analytics avec les activités Adobe Target.
title: Où puis-je trouver des informations sur les définitions de mesure avec A4T ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 58%

---


# FAQ sur les définitions de mesures - A4T

Cette rubrique contient des réponses aux questions fréquentes sur le partage de mesures, d’audiences et de rapports lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Quelle est l’expiration de l’appartenance à une activité ? Pendant combien de temps après le début de leur participation à l’activité les actions des visiteurs seront-elles comptées dans l’activité s’ils ne la revoient pas ? {#section_41B4958F33534E4B96DEE0C981227A79}

L’expiration par défaut pour l’activité est de 90 jours après la dernière interaction du visiteur avec l’activité. Cela peut être ajusté par le service à la clientèle si nécessaire. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ? {#adv-settings}

Les options [!UICONTROL Paramètres avancés] ne sont pas disponibles pour les activités qui utilisent [!DNL Analytics] comme source de rapports (A4T).

Pour les activités qui utilisent A4T, la mesure d’objectif utilisera toujours les paramètres &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur en Activité]&quot; et &quot;[!UICONTROL Sur chaque impression]&quot;. *non* configurable.

Pour les activités autres que A4T, vous pouvez utiliser les [options Paramètres avancés](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) pour gérer la façon dont vous mesurez la réussite. Les options incluent l’ajout de dépendances, la sélection de l’option permettant de conserver ou de supprimer l’utilisateur dans l’activité et la comptabilisation de la mesure une fois par participant ou sur chaque impression. Vous accédez aux options [!UICONTROL Paramètres avancés] dans une activité non A4T en cliquant sur les ellipses verticales > [!UICONTROL Paramètres avancés], comme indiqué ci-dessous :

![Paramètres avancés](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## Que sont les mesures calculées et comment remplacent-elles la mbox SiteCatalyst:Event que j’utilisais ?  {#section_D59F4719E6B94758A2187427C17F8EF3}

Les mesures calculées vous permettent de créer des mesures personnalisées dérivées des calculs de segments ou mathématiques. Auparavant, vous utilisiez la mbox `SiteCatlayst:Event` où `evar27=shoes` et l’événement est `purchase`. Vous devez maintenant créer un segment où `evar27=shoes` puis créer une mesure calculée où l’événement est `purchase` avec le segment appliqué. Ces mesures représentent un avantage car elles peuvent être créées à tout moment, même après que l’activité a commencé. Elles peuvent alors être utilisées sur tous les rapports dans Analytics.

## A4T attribue-t-il des conversions à plusieurs campagnes ?  {#section_7F15C727206440CD86B3A8CE77087DF9}

Oui. Cela se fait à l’aide du paramètre « Affectation intégrale ».
