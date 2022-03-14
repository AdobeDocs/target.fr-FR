---
keywords: faq;questions fréquentes;forum aux questions;analytics pour target;a4T;mesure;définitions de mesures
description: Trouver des réponses aux questions sur les définitions de mesures et l’utilisation d’Analytics pour [!DNL Target] (A4T). A4T vous permet d’utiliser les rapports Analytics avec Adobe [!DNL Target] activités.
title: Où puis-je trouver des informations sur les définitions de mesures avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 38%

---

# FAQ sur les définitions de mesures - A4T

Cette rubrique contient des réponses aux questions fréquentes sur les définitions de mesures et sur l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Quelle est l’expiration de l’appartenance à une activité ? Combien de temps après que les visiteurs ont rejoint l’activité leurs actions sont-elles comptabilisées dans l’activité s’ils ne la revoient pas ? {#section_41B4958F33534E4B96DEE0C981227A79}

L’expiration par défaut pour l’activité est de 90 jours après la dernière interaction du visiteur avec l’activité. Si nécessaire, ce paramètre peut être ajusté par le service à la clientèle. Cependant, ce paramètre est global pour toutes les activités. Il ne doit donc pas être ajusté pour un seul cas.

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ? {#adv-settings}

Le [!UICONTROL Paramètres avancés] Les options ne sont pas disponibles pour les activités qui utilisent [!DNL Analytics] comme source des rapports (A4T).

Pour les activités utilisant A4T, la mesure d’objectif utilise toujours le paramètre &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité]&quot; et &quot;[!UICONTROL À chaque impression]&quot;. Ces paramètres sont les suivants : *not* configurable.

Pour les activités autres que A4T, vous pouvez utiliser la variable [Options des paramètres avancés](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) pour gérer la manière dont vous mesurez le succès. Les options incluent l’ajout de dépendances, le choix de garder l’utilisateur dans l’activité ou de le supprimer, ainsi que la comptabilisation de la mesure une fois par participant ou à chaque impression. Vous accédez au [!UICONTROL Paramètres avancés] options d’une activité autre qu’A4T en cliquant sur les points alignés verticalement > [!UICONTROL Paramètres avancés], comme illustré ci-dessous :

![Paramètres avancés](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

## Que sont les mesures calculées et comment remplacent-elles la mbox SiteCatalyst:Event que j’utilisais ? {#section_D59F4719E6B94758A2187427C17F8EF3}

Les mesures calculées vous permettent de créer des mesures personnalisées dérivées des calculs de segments ou mathématiques. Auparavant, vous utilisiez la mbox `SiteCatlayst:Event` où `evar27=shoes` et l’événement est `purchase`. Vous devez maintenant créer un segment où `evar27=shoes` puis créer une mesure calculée où l’événement est `purchase` avec le segment appliqué. Ces mesures peuvent être créées à tout moment, même après le lancement de l’activité. Elles peuvent alors être utilisées sur tous les rapports dans Analytics.

## A4T attribue-t-il des conversions à plusieurs campagnes ? {#section_7F15C727206440CD86B3A8CE77087DF9}

Oui, à l’aide du paramètre &quot;Affectation complète&quot;.
