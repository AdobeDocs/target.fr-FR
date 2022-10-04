---
keywords: faq;questions fréquentes;analytics pour target;a4T;configuration des activités
description: Trouver des réponses aux questions sur la configuration des activités lors de l’utilisation d’Analytics pour [!DNL Target] (A4T). A4T vous permet d’utiliser les rapports Analytics pour [!DNL Target] activités.
title: Où puis-je trouver des questions fréquentes sur les paramètres d’activité avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 20%

---

# FAQ sur le paramétrage des activités - A4T

Cette rubrique contient des réponses aux questions fréquentes sur la configuration et l’utilisation des activités [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T).

## Quels types d’activités prennent en charge Analytics comme source de création de rapports (A4T) ? {#section_5E4F58CD25A5424E869E6FE0803968EF}

Pour obtenir une liste complète, consultez les « Types d’activité pris en charge » dans [Adobe Analytics en tant que source de création de rapports pour Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux paramètres avancés ?

Pour les activités utilisant [!DNL Analytics] en tant que source des rapports (A4T), la mesure d’objectif utilise le paramètre &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité]&quot; et &quot;[!UICONTROL À chaque impression]&quot;. Ces paramètres sont les suivants : *not* configurable.

Pour plus d’informations, voir &quot;Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ?&quot; in [FAQ sur les définitions de mesures - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Je viens de créer une activité. Pourquoi aucunes données n’y sont-elles importées ? {#section_9F8092BE4225442896F926540292F221}

Lors de la création d’une activité, [!DNL Target] envoie un fichier de classification à [!DNL Analytics]. Bien que [!DNL Analytics] capture et traite les données. Cela n’apparaît pas dans les rapports tant que le fichier de classification n’a pas été mis à jour. Ce processus peut prendre jusqu’à 24 heures. Si vous n’avez pas accès à vos données après 48 heures, veuillez [contacter le service à la clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Si vous savez que vous lancez une activité, vous pouvez également créer l’activité quelques jours à l’avance et les classifications sont envoyées lors de l’enregistrement de l’activité. De cette manière, les données apparaissent dans les rapports dès le lancement. Veuillez noter que le traitement des données dans prend entre 45 et 90 minutes. [!DNL Analytics].

## Pourquoi ne puis-je pas sélectionner Analytics comme source de création de rapports lorsque je crée une activité ? {#section_9F4F69C3085F4C2480AF439127EB27CD}

Vous pouvez modifier votre [!UICONTROL Paramètres de création de rapports] options dans [!UICONTROL Administration].

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]**.
1. Dans la liste déroulante **[!UICONTROL Solution Experience Cloud utilisée pour la création de rapports]**, cliquez sur **[!UICONTROL Sélection par activité]**.

![image select-per-activity](assets/select-per-activity.png)

La liste déroulante **[!UICONTROL Source des rapports]** est activée dans l’écran **[!UICONTROL Objectif et paramètres]** afin de créer et modifier des activités.

Pour toujours utiliser [!DNL Analytics] comme source de création de rapports, sélectionnez **[!UICONTROL Adobe Analytics]** dans la liste déroulante de [!UICONTROL Administration].

## Un visiteur peut-il passer d’une expérience ciblée à une expérience contrôlée au cours de différentes visites dans une activité de ciblage automatique qui utilise A4T ?

Ce qui suit est vrai, en supposant que le visitorId ne change pas pour un visiteur entre les visites.

Si le pourcentage d’affectation du trafic est ajusté en milieu d’activité, il est possible qu’un visiteur puisse passer d’une expérience ciblée à une expérience de contrôle.

Si les pourcentages ne sont pas ajustés en milieu d’activité, un visiteur qui voit initialement le contrôle est toujours envoyé au contrôle. Un visiteur envoyé aux expériences ciblées est toujours envoyé aux expériences ciblées.

* Après s’être trouvé dans le &quot;compartiment&quot; ciblé du trafic, le visiteur peut être envoyé vers une expérience différente, de la visite à la visite, si les modèles d’apprentissage automatique déterminent qu’une expérience différente est pertinente pour la nouvelle visite.
* Après avoir été affecté au &quot;compartiment&quot; de contrôle du trafic, un visiteur verra toujours la même expérience, car l’affectation d’expérience est basée sur un hachage pseudo-aléatoire déterministe de l’identifiant visiteur du visiteur.


## Puis-je utiliser un fichier binaire ? [!DNL Analytics] mesure avec un segment appliqué comme objectif d’optimisation dans un [!UICONTROL Affectation automatique] activité ? {#binomial}

Vous ne pouvez pas utiliser un [!DNL Analytics] mesure avec un segment appliqué comme objectif d’optimisation dans un [!UICONTROL Affectation automatique] activité. Pour contourner ce problème, vous pouvez définir un événement personnalisé qui atteigne le même objectif et l’utiliser comme mesure d’objectif d’optimisation.