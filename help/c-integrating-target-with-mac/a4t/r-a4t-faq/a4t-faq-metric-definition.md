---
description: Cette rubrique contient des réponses aux questions fréquentes sur le partage de mesures, d’audiences et de rapports lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).
keywords: faq;questions fréquentes;forum aux questions;analytics pour target;a4T;mesure;définitions de mesures
seo-description: Cette rubrique contient des réponses aux questions fréquentes sur le partage de mesures, d’audiences et de rapports lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).
seo-title: FAQ sur les définitions de mesures - A4T
solution: Target
title: FAQ sur les définitions de mesures - A4T
topic: Standard
uuid: 41d41665-9057-479d-b0a8-7cffb90ca843
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# FAQ sur les définitions de mesures - A4T{#metric-definitions-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur le partage de mesures, d’audiences et de rapports lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Quelle est l’expiration de l’appartenance à une activité ? Pendant combien de temps après le début de leur participation à l’activité les actions des visiteurs seront-elles comptées dans l’activité s’ils ne la revoient pas ?  {#section_41B4958F33534E4B96DEE0C981227A79}

L’expiration par défaut pour l’activité est de 90 jours après la dernière interaction du visiteur avec l’activité. Cela peut être ajusté par le service à la clientèle si nécessaire. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

## Les options avancées des mesures de succès dans Target sont-elles compatibles avec A4T ?  {#section_F060E3438F4144258BB95813EDEABDAA}

Actuellement, ces options ne sont pas compatibles avec A4T.

## Que sont les mesures calculées et comment remplacent-elles la mbox SiteCatalyst:Event que j’utilisais ?  {#section_D59F4719E6B94758A2187427C17F8EF3}

Les mesures calculées vous permettent de créer des mesures personnalisées dérivées des calculs de segments ou mathématiques. Auparavant, vous utilisiez la mbox `SiteCatlayst:Event` où `evar27=shoes` et l’événement est `purchase`. Vous devez maintenant créer un segment où `evar27=shoes` puis créer une mesure calculée où l’événement est `purchase` avec le segment appliqué. Ces mesures représentent un avantage car elles peuvent être créées à tout moment, même après que l’activité a commencé. Elles peuvent alors être utilisées sur tous les rapports dans Analytics.

## A4T attribue-t-il des conversions à plusieurs campagnes ?  {#section_7F15C727206440CD86B3A8CE77087DF9}

Oui. Cela se fait à l’aide du paramètre « Affectation intégrale ».
