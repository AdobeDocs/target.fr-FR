---
description: Cette rubrique contient des réponses aux questions fréquentes sur l’effet élévateur et le degré de confiance lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).
keywords: faq;questions fréquentes;analytics pour target;a4T;configuration des activités
seo-description: Cette rubrique contient des réponses aux questions fréquentes sur l’effet élévateur et le degré de confiance lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).
seo-title: FAQ sur le paramétrage des activités - A4T
solution: Target
title: FAQ sur le paramétrage des activités - A4T
topic: Standard
uuid: 3472ab3c-908b-40f8-81a6-512dccde64a6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# FAQ sur le paramétrage des activités - A4T{#activity-settings-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur l’effet élévateur et le degré de confiance lors de l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Quels types d’activités prennent en charge Analytics comme source de création de rapports (A4T) ?{#section_5E4F58CD25A5424E869E6FE0803968EF}

Pour obtenir une liste complète, consultez les « Types d’activité pris en charge » dans [Adobe Analytics en tant que source de création de rapports pour Adobe Target (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Je viens de créer une activité. Pourquoi n’ai-je accès à aucune donnée ? {#section_9F8092BE4225442896F926540292F221}

Lors de la création d’une activité, Target envoie un fichier de classification à Analytics. Bien qu’Analytics capture et traite les données, il n’affiche pas les rapports avant que le fichier de classification n’ait été mis à jour. Cela peut prendre jusqu’à 24 heures. Si vous n’avez pas accès à vos données après 48 heures, veuillez [contacter le service à la clientèle](https://marketing.adobe.com/resources/help/en_US/target/target/r_problem.html). Sinon, si vous savez que vous allez lancer une activité, vous pouvez créer l’activité quelques jours auparavant et les classifications seront envoyées une fois l’activité sauvegardée. De cette manière, les données apparaissent dans les rapports dès le lancement. Veuillez noter que le traitement des données dans Analytics prend 45 à 90 minutes.

## Pourquoi est-ce que je ne parviens pas à sélectionner Analytics comme source de création des rapports lors de la création d’une activité ?  {#section_9F4F69C3085F4C2480AF439127EB27CD}

Vous pouvez modifier les paramètres de création de rapports dans Configuration.

1. Dans Adobe Target, cliquez sur **[!UICONTROL Configuration]**.
1. Dans la liste déroulante **[!UICONTROL Solution Experience Cloud utilisée pour la création de rapports]**, cliquez sur **[!UICONTROL Sélection par activité]**.

![](assets/select-per-activity.png)

La liste déroulante **[!UICONTROL Source des rapports]** est activée dans l’écran **[!UICONTROL Objectif et paramètres]** afin de créer et modifier des activités.

Pour toujours utiliser Analytics comme source de rapports, sélectionnez **[!UICONTROL Adobe Analytics]** dans la liste déroulante dans Configuration.
