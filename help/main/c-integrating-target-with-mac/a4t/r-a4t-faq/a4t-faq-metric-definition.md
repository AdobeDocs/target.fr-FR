---
keywords: faq;questions fréquentes;forum aux questions;analytics pour target;a4T;mesure;définitions de mesures
description: Trouvez des réponses aux questions sur les définitions de mesures et l’utilisation d’Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser la création de rapports Analytics avec des activités Adobe [!DNL Target] .
title: Où puis-je trouver des informations sur les définitions de mesures avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 36%

---

# FAQ sur les définitions de mesures - A4T

Cette rubrique contient les réponses aux questions fréquentes sur les définitions de mesures et l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Quelle est l’expiration de l’appartenance à une activité ? Combien de temps après l’entrée des visiteurs dans l’activité leurs actions sont-elles comptabilisées dans l’activité s’ils ne la voient plus ? {#section_41B4958F33534E4B96DEE0C981227A79}

+++Réponse
L’expiration par défaut pour l’activité est de 90 jours après la dernière interaction du visiteur avec l’activité. Ce paramètre peut être ajusté par le service clientèle si nécessaire. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

+++

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options des Paramètres avancés ? {#adv-settings}

+++Réponse
Les options [!UICONTROL Advanced Settings] ne sont pas disponibles pour les activités qui utilisent [!DNL Analytics] comme source de création de rapports (A4T).

Pour les activités qui utilisent A4T, la mesure d’objectif utilise toujours les paramètres « [!UICONTROL Increment Count & Keep User in Activity] » et « [!UICONTROL On Every Impression] ». Ces paramètres ne sont *pas configurables*

Pour les activités hors A4T, vous pouvez utiliser les options [Paramètres avancés](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) pour gérer la manière dont vous mesurez la réussite. Les options incluent l’ajout de dépendances, le choix de conserver l’utilisateur dans l’activité ou de le supprimer, et le comptage de la mesure une fois par participant ou à chaque impression. Pour accéder aux options de [!UICONTROL Advanced Settings] d’une activité hors A4T, cliquez sur les points de suspension verticaux > [!UICONTROL Advanced Settings], comme illustré ci-dessous :

![Paramètres avancés](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## Que sont les mesures calculées et comment remplacent-elles la mbox SiteCatalyst:Event que j’utilisais auparavant ? {#section_D59F4719E6B94758A2187427C17F8EF3}

+++Réponse
Les mesures calculées vous permettent de créer des mesures personnalisées dérivées des calculs de segments ou mathématiques. Auparavant, vous utilisiez la mbox `SiteCatlayst:Event` où `evar27=shoes` et l’événement est `purchase`. Vous devez maintenant créer un segment où `evar27=shoes` puis créer une mesure calculée où l’événement est `purchase` avec le segment appliqué. Ces mesures peuvent être créées à tout moment, même après le début de l’activité. Elles peuvent alors être utilisées sur tous les rapports dans Analytics.

+++

## A4T attribue-t-il des conversions à plusieurs campagnes ? {#section_7F15C727206440CD86B3A8CE77087DF9}

+++Réponse
Oui, en utilisant le paramètre « Affectation complète ».

+++
