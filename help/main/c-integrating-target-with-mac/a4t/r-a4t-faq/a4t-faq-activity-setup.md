---
keywords: faq;questions fréquentes;analytics pour target;a4T;configuration des activités
description: Trouvez des réponses aux questions sur la configuration des activités lors de l’utilisation d’Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser la création de rapports Analytics pour les activités  [!DNL Target] .
title: Où puis-je trouver des questions fréquentes sur les paramètres d’activité avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 10%

---

# FAQ sur le paramétrage des activités - A4T

Cette rubrique contient les réponses aux questions fréquentes sur la configuration des activités et l’utilisation de [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T).

## Quels types d’activités sont pris en charge [!DNL Analytics] tant que source de création de rapports (A4T) ? {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++Réponse
Pour obtenir une liste complète, consultez les « Types d’activité pris en charge » dans [Adobe Analytics en tant que source de création de rapports pour Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## Puis-je utiliser le même nom d’activité pour deux activités à partir d’espaces de travail distincts lors de l’utilisation des rapports A4T ?

+++Réponse

N’utilisez pas le même nom d’activité pour deux activités provenant d’[espaces de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) distincts qui utilisent les rapports A4T.

Bien que cela soit pris en charge lorsque vous utilisez [!DNL Target] comme source de création de rapports, l’utilisation du même nom d’activité pour deux activités n’est pas prise en charge lorsque vous utilisez [!UICONTROL Analytics for Target] comme source de création de rapports.

+++

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux paramètres avancés ?

+++Réponse
Pour les activités utilisant [!DNL Analytics] comme source de création de rapports (A4T), la mesure d’objectif utilise les paramètres « [!UICONTROL Increment Count & Keep User in Activity] » et « [!UICONTROL On Every Impression] ». Ces paramètres ne sont *pas configurables*

Pour plus d’informations, reportez-vous à la rubrique « Lorsque je configure mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ? » dans la [FAQ sur les définitions de mesures - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Je viens de créer une activité. Pourquoi aucunes données n’y sont-elles importées ? {#section_9F8092BE4225442896F926540292F221}


+++Réponse
Lorsqu’une activité est créée, [!DNL Target] envoie un fichier de classification à [!DNL Analytics]. Bien que le [!DNL Analytics] capture et traite les données, il ne l’affiche pas dans les rapports tant que le fichier de classification n’a pas été mis à jour. Ce processus peut prendre entre 24 et 72 heures. Si, après 72 heures, vous ne voyez pas vos données, [contactez le service clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Si vous savez que vous lancez une activité, vous pouvez également créer l’activité quelques jours à l’avance et envoyer les classifications lorsque l’activité est enregistrée. De cette manière, les données apparaissent dans les rapports dès le lancement. Notez que le traitement des données en [!DNL Analytics] prend entre 45 et 90 minutes.

+++

## Pourquoi ne puis-je pas sélectionner Analytics comme source de création de rapports lorsque je crée une activité ? {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++Réponse
Vous pouvez modifier vos options de [!UICONTROL Reporting Settings] dans [!UICONTROL Administration].

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]**.
1. Dans la liste déroulante **[!UICONTROL Experience Cloud solution used for reporting]**, cliquez sur **[!UICONTROL Select per Activity]**.

![sélectionner une image par activité](assets/select-per-activity.png)

La liste déroulante **[!UICONTROL Reporting Source]** est activée dans l’écran **[!UICONTROL Goal & Settings]** pour créer et modifier des activités.

Pour toujours utiliser [!DNL Analytics] comme source de création de rapports, sélectionnez **[!UICONTROL Adobe Analytics]** dans la liste déroulante de [!UICONTROL Administration].

+++

## Un visiteur peut-il basculer entre les expériences ciblées et contrôlées au cours de différentes visites dans une activité de ciblage automatique qui utilise A4T ?

+++Réponse
Ce qui suit est vrai en supposant que l’identifiant visiteur ne change pas pour un visiteur entre les visites.

Si le pourcentage d’affectation du trafic est ajusté en milieu d’activité, il est possible qu’un visiteur puisse passer d’une expérience ciblée à une expérience de contrôle.

Si les pourcentages ne sont pas ajustés en milieu d’activité, un visiteur qui voit initialement le contrôle est toujours envoyé au contrôle. Un visiteur qui est envoyé à des expériences ciblées est toujours envoyé à des expériences ciblées.

* Après s’être trouvé dans le « compartiment » de trafic ciblé, le visiteur peut être envoyé à une expérience différente d’une visite à l’autre si les modèles de machine learning déterminent qu’une expérience différente est pertinente pour la nouvelle visite.
* Après avoir été affecté au « compartiment » de contrôle du trafic, un visiteur verra toujours la même expérience, car l’affectation de l’expérience est basée sur un hachage pseudo-aléatoire déterministe de l’identifiant visiteur du visiteur.

+++

## Puis-je utiliser une mesure de [!DNL Analytics] binomiale avec un segment appliqué comme objectif d’optimisation dans une activité [!UICONTROL Auto-Allocate] ? {#binomial}

+++Réponse
Vous ne pouvez pas utiliser une mesure [!DNL Analytics] avec un segment appliqué comme objectif d’optimisation dans une activité [!UICONTROL Auto-Allocate]. Pour pallier ce problème, vous pouvez définir un événement personnalisé qui atteint le même objectif et l’utiliser comme mesure d’objectif d’optimisation.

+++
