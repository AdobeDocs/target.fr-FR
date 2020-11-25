---
keywords: faq;frequently asked questions;analytics for target;a4T;activity setup
description: Cette rubrique contient des réponses aux questions fréquentes sur l’effet élévateur et le degré de confiance lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).
title: FAQ sur le paramétrage des activités - A4T
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: a12eea60aa3e66cdb54ab284fa3f942be4d56178
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 36%

---


# FAQ sur le paramétrage des activités - A4T

This topic contains answers to questions that are frequently asked about activity setup and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## Quels types d’activités prennent en charge Analytics comme source de création de rapports (A4T) ?{#section_5E4F58CD25A5424E869E6FE0803968EF}

Pour obtenir une liste complète, consultez les « Types d’activité pris en charge » dans [Adobe Analytics en tant que source de création de rapports pour Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux paramètres avancés ?

Pour les activités qui utilisent [!DNL Analytics] comme source de rapports (A4T), la mesure d’objectif utilise toujours les paramètres &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur en Activité]&quot; et &quot;[!UICONTROL Sur chaque impression]&quot;. Ceci *n&#39;est pas* configurable.

Pour plus d’informations, voir &quot;Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ?&quot; in [Metric definitions - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Je viens de créer une activité. Pourquoi n’ai-je accès à aucune donnée ? {#section_9F8092BE4225442896F926540292F221}

When an activity is created, [!DNL Target] sends a classification file to [!DNL Analytics]. Although [!DNL Analytics] is capturing the and processing the data, it does not show in the reports until the classification file has been updated. Cela peut prendre jusqu’à 24 heures. Si vous n’avez pas accès à vos données après 48 heures, veuillez [contacter le service à la clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Sinon, si vous savez que vous allez lancer une activité, vous pouvez créer l’activité quelques jours auparavant et les classifications seront envoyées une fois l’activité sauvegardée. De cette manière, les données apparaissent dans les rapports dès le lancement. Please note that it takes 45-90 minutes for data to be processed in [!DNL Analytics].

## Pourquoi est-ce que je ne parviens pas à sélectionner Analytics comme source de création des rapports lors de la création d’une activité ? {#section_9F4F69C3085F4C2480AF439127EB27CD}

You can change your [!UICONTROL Reporting Settings] options in [!UICONTROL Administration].

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]**.
1. Dans la liste déroulante **[!UICONTROL Solution Experience Cloud utilisée pour la création de rapports]**, cliquez sur **[!UICONTROL Sélection par activité]**.

![](assets/select-per-activity.png)

La liste déroulante **[!UICONTROL Source des rapports]** est activée dans l’écran **[!UICONTROL Objectif et paramètres]** afin de créer et modifier des activités.

To always use [!DNL Analytics] as the reporting source, select **[!UICONTROL Adobe Analytics]** from the drop-down list in [!UICONTROL Administration].

## Un visiteur peut-il basculer entre des expériences ciblées et contrôlées lors de différentes visites dans une activité de Cible automatique qui utilise A4T ?

Ce qui suit est vrai en supposant que le visitorId ne change pas pour un visiteur entre deux visites.

Si le pourcentage d’affectation du trafic est ajusté en activité intermédiaire, il est possible qu’un visiteur puisse passer d’une expérience ciblée à une expérience de contrôle.

Si les pourcentages ne sont pas ajustés en activité moyenne, un visiteur qui voit initialement le contrôle est toujours envoyé au contrôle. Un visiteur envoyé vers des expériences ciblées est toujours envoyé vers des expériences ciblées.

* Après avoir été dans le &quot;compartiment&quot; ciblé du trafic, le visiteur peut être envoyé vers une expérience différente, de la visite à la visite, si les modèles d’apprentissage automatique déterminent qu’une expérience différente est pertinente pour la nouvelle visite.
* Après avoir été affecté au &quot;compartiment&quot; de contrôle du trafic, un visiteur verra toujours la même expérience car l’affectation de l’expérience est basée sur un hachage pseudo-aléatoire déterministe du visitorId du visiteur.
