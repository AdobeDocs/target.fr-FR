---
keywords: faq;questions fréquentes;forum aux questions;analytics pour target;a4T;mesure;définitions de mesures
description: Trouvez des réponses aux questions relatives aux définitions de mesures et à l’utilisation d’Analytics pour  [!DNL Target] (A4T). A4T lets you use Analytics reporting with Adobe [!DNL Target] activités.
title: Où puis-je trouver des informations sur les définitions de mesure avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 40%

---

# FAQ sur les définitions de mesures - A4T

Cette rubrique contient des réponses aux questions fréquemment posées sur les définitions de mesure et l’utilisation de [!DNL Adobe Analytics] comme source de rapports pour [!DNL Adobe Target] (A4T).

## Quelle est l’expiration de l’appartenance à une activité ? Combien de temps après l&#39;entrée des visiteurs dans l&#39;activité leurs actions sont-elles comptabilisées dans l&#39;activité si elles ne le revoient pas ? {#section_41B4958F33534E4B96DEE0C981227A79}

L’expiration par défaut pour l’activité est de 90 jours après la dernière interaction du visiteur avec l’activité. Ce paramètre peut être ajusté par ClientCare si nécessaire. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ? {#adv-settings}

Les options [!UICONTROL Paramètres avancés] ne sont pas disponibles pour les activités qui utilisent [!DNL Analytics] comme source de rapports (A4T).

Pour les activités utilisant A4T, la mesure d’objectif utilise toujours les paramètres &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur en Activité]&quot; et &quot;[!UICONTROL Sur chaque impression]&quot;. Ces paramètres sont *non* configurables.

Pour les activités autres que A4T, vous pouvez utiliser les [options Paramètres avancés](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) pour gérer la façon dont vous mesurez la réussite. Les options incluent l’ajout de dépendances, la sélection de l’option permettant de conserver ou de supprimer l’utilisateur dans l’activité et la comptabilisation de la mesure une fois par participant ou sur chaque impression. Vous accédez aux options [!UICONTROL Paramètres avancés] dans une activité non A4T en cliquant sur les ellipses verticales > [!UICONTROL Paramètres avancés], comme indiqué ci-dessous :

![Paramètres avancés](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## Que sont les mesures calculées et comment remplacent-elles la mbox SiteCatalyst:Event que j’utilisais ? {#section_D59F4719E6B94758A2187427C17F8EF3}

Les mesures calculées vous permettent de créer des mesures personnalisées dérivées des calculs de segments ou mathématiques. Auparavant, vous utilisiez la mbox `SiteCatlayst:Event` où `evar27=shoes` et l’événement est `purchase`. Vous devez maintenant créer un segment où `evar27=shoes` puis créer une mesure calculée où l’événement est `purchase` avec le segment appliqué. Ces mesures peuvent être créées à tout moment, même après l’activité. Elles peuvent alors être utilisées sur tous les rapports dans Analytics.

## A4T attribue-t-il des conversions à plusieurs campagnes ?  {#section_7F15C727206440CD86B3A8CE77087DF9}

Oui, en utilisant le paramètre &quot;Affectation complète&quot;.
