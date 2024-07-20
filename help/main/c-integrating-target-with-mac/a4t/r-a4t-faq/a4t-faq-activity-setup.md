---
keywords: faq;questions fréquentes;analytics pour target;a4T;configuration des activités
description: Trouvez des réponses aux questions sur la configuration de l’activité lors de l’utilisation d’Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser les rapports Analytics pour les activités  [!DNL Target] .
title: Où puis-je trouver des questions fréquentes sur les paramètres d’activité avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 6%

---

# FAQ sur le paramétrage des activités - A4T

Cette rubrique contient des réponses aux questions fréquentes sur la configuration des activités et l’utilisation de [!DNL Analytics] comme source des rapports pour [!DNL Target] (A4T).

## Quels types d’activité prennent en charge [!DNL Analytics] comme source de création de rapports (A4T) ? {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++Réponse
Pour obtenir une liste complète, voir &quot;Types d’activité pris en charge&quot; dans [Adobe Analytics as the Reporting Source for Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## Puis-je utiliser le même nom d’activité pour deux activités d’espaces de travail distincts lors de l’utilisation de rapports A4T ?

+++Réponse

N’utilisez pas le même nom d’activité pour deux activités des [espaces de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) distincts qui utilisent les rapports A4T.

Bien que cela soit pris en charge lors de l’utilisation de [!DNL Target] comme source de création de rapports, l’utilisation du même nom d’activité pour deux activités n’est pas prise en charge lors de l’utilisation de [!UICONTROL Analytics for Target] comme source de création de rapports.

+++

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux paramètres avancés ?

+++Réponse
Pour les activités utilisant [!DNL Analytics] comme source des rapports (A4T), la mesure d’objectif utilise les paramètres &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; et &quot;[!UICONTROL On Every Impression]&quot;. Ces paramètres sont *non* configurables.

Pour plus d’informations, voir &quot;Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ?&quot; dans [FAQ sur les définitions de mesures - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Je viens de créer une activité. Pourquoi aucunes données n’y sont-elles importées ? {#section_9F8092BE4225442896F926540292F221}


+++Réponse
Lors de la création d’une activité, [!DNL Target] envoie un fichier de classification à [!DNL Analytics]. Bien que [!DNL Analytics] capture et traite les données, il n’affiche pas cela dans les rapports tant que le fichier de classification n’a pas été mis à jour. Ce processus peut prendre entre 24 et 72 heures. Si, après 72 heures, vos données ne s’affichent pas, [contactez le service à la clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Si vous savez que vous lancez une activité, vous pouvez également créer l’activité quelques jours à l’avance et les classifications sont envoyées lors de l’enregistrement de l’activité. De cette manière, les données apparaissent dans les rapports dès le lancement. Veuillez noter que le traitement des données dans [!DNL Analytics] prend entre 45 et 90 minutes.

+++

## Pourquoi ne puis-je pas sélectionner Analytics comme source de création de rapports lorsque je crée une activité ? {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++Réponse
Vous pouvez modifier vos options [!UICONTROL Reporting Settings] dans [!UICONTROL Administration].

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]**.
1. Dans la liste déroulante **[!UICONTROL Experience Cloud solution used for reporting]**, cliquez sur **[!UICONTROL Select per Activity]**.

![image de sélection par activité](assets/select-per-activity.png)

La liste déroulante **[!UICONTROL Reporting Source]** est activée dans l’écran **[!UICONTROL Goal & Settings]** pour la création et la modification d’activités.

Pour toujours utiliser [!DNL Analytics] comme source de création de rapports, sélectionnez **[!UICONTROL Adobe Analytics]** dans la liste déroulante de [!UICONTROL Administration].

+++

## Un visiteur peut-il passer d’une expérience ciblée à une expérience contrôlée au cours de différentes visites dans une activité de ciblage automatique qui utilise A4T ?

+++Réponse
Ce qui suit est vrai, en supposant que le visitorId ne change pas pour un visiteur entre les visites.

Si le pourcentage d’affectation du trafic est ajusté en milieu d’activité, il est possible qu’un visiteur puisse passer d’une expérience ciblée à une expérience de contrôle.

Si les pourcentages ne sont pas ajustés en milieu d’activité, un visiteur qui voit initialement le contrôle est toujours envoyé au contrôle. Un visiteur envoyé aux expériences ciblées est toujours envoyé aux expériences ciblées.

* Après s’être trouvé dans le &quot;compartiment&quot; ciblé du trafic, le visiteur peut être envoyé vers une expérience différente, de la visite à la visite, si les modèles d’apprentissage automatique déterminent qu’une expérience différente est pertinente pour la nouvelle visite.
* Après avoir été affecté au &quot;compartiment&quot; de contrôle du trafic, un visiteur verra toujours la même expérience, car l’affectation d’expérience est basée sur un hachage pseudo-aléatoire déterministe de l’identifiant visiteur du visiteur.

+++

## Puis-je utiliser une mesure [!DNL Analytics] binaire avec un segment appliqué comme objectif d’optimisation dans une activité [!UICONTROL Auto-Allocate] ? {#binomial}

+++Réponse
Vous ne pouvez pas utiliser une mesure [!DNL Analytics] avec un segment appliqué comme objectif d’optimisation dans une activité [!UICONTROL Auto-Allocate]. Pour contourner ce problème, vous pouvez définir un événement personnalisé qui atteigne le même objectif et l’utiliser comme mesure d’objectif d’optimisation.

+++