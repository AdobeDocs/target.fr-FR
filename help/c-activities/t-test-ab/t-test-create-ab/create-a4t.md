---
keywords: Targeting;analytics;tracking server
description: Vous pouvez configurer une activité dans Target Standard afin d’utiliser Adobe Analytics en tant que source des rapports (A4T).
title: Utilisation des données Analytics
feature: a4t general
uuid: 4ac0c181-030b-4cf5-b138-acf02c7af4f6
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 95%

---


# Utilisation des données Analytics{#using-analytics-data}

Vous pouvez configurer une activité dans Target Standard afin d’utiliser Adobe Analytics en tant que source des rapports (A4T).

For detailed information about setting up Analytics as the data source for Target, see [Adobe Analytics as the Reporting Source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

Avant de configurer une activité qui utilise Analytics en tant que source de création de rapports, définissez l’objectif de l’activité, par exemple améliorer le chiffre d’affaires par visiteur (RPV) ou augmenter les clics sur votre panier. Sélectionnez une mesure de succès finale de la campagne. Bien que vous puissiez sélectionner des mesures supplémentaires à tout moment dans Analytics, vous devez tout de même indiquer une mesure spécifique qui devrait être affectée par ce test.

>[!NOTE]
>
>L’option Adobe Analytics est disponible si vous avez lié votre compte Adobe Experience Cloud avec Analytics et Target, même si l’intégration entre Target et Analytics n’a pas été configurée pour votre compte.

Lors de la sélection d’Analytics en tant que source de création de rapports pour Target, vous sélectionnez une suite de rapports Analytics pour recevoir les données d’activité Target. Pour ce faire, faites d’abord votre choix parmi les sociétés Analytics auxquelles votre compte est lié, puis sélectionnez la suite de rapports adaptée à l’activité. Seules les suites de rapports configurées pour se connecter à Adobe Target pourront être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter et de vous connecter à nouveau à Adobe Experience Cloud. Si la suite de rapports n’apparaît toujours pas dans la liste, veuillez contacter l’assistance clientèle.

Analytics for Target requiert un serveur de suivi pour consigner les résultats de manière appropriée. Un serveur de suivi par défaut apparaîtra dans le champ Serveur de suivi. Si vous utilisez plus d’un serveur de suivi, vous devriez vérifier afin de vous assurer d’avoir ajouté le serveur de suivi approprié dans ce champ. Pour plus d’informations, voir [Utilisation d’un serveur de suivi Analytics](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

>[!NOTE]
>
>Si vous utilisez Adobe Analytics comme source des rapports de votre activité, vous ne devez pas spécifier de serveur de suivi durant la création d’activités si vous utilisez mbox.js version 61 (ou ultérieure) ou at.js version 0.9.1 (ou ultérieure). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

Lors de la configuration d’une activité après avoir configuré Analytics en tant que source de création de rapports, il n’existe pas d’option pour configurer des audiences pour la création de rapports. Les segments Analytics sont disponibles dans le rapport Activités cibles.

Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque test. L’objectif de l’activité est l’activité de conversion qui signale une campagne réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez sélectionner toute mesure Analytics disponible dans le sélecteur de mesure Analytics.

La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que vous voulez améliorer avec le test.

Une fois qu’un visiteur a atteint votre objectif, ce visiteur n’est plus inclus dans la campagne. Si le visiteur entre à nouveau dans la campagne après avoir terminé une activité, il est comptabilisé en tant que nouveau visiteur.
