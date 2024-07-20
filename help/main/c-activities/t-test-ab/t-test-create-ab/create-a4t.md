---
keywords: ciblage;analytics;serveur de suivi;analytics for target;a4t
description: Découvrez comment configurer une activité dans  [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source des rapports (A4T).
title: Comment puis-je utiliser les  [!DNL Analytics] données dans [!DNL Target] ?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 18%

---

# Utilisation des données [!DNL Adobe Analytics]

Vous pouvez configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source des rapports (A4T).

Pour plus d’informations sur la configuration de [!DNL Analytics] en tant que source de données pour [!DNL Target], voir [Adobe Analytics as a Reporting Source for Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Avant de configurer une activité qui utilise [!DNL Analytics] comme source de création de rapports, définissez l’objectif de l’activité, par exemple améliorer les recettes par visiteur (RPV) ou augmenter les clics sur votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner des mesures supplémentaires à tout moment dans [!DNL Analytics], vous devez tout de même spécifier une mesure particulière que vous prévoyez d’affecter à ce test.

>[!NOTE]
>
>L’option [!DNL Adobe Analytics] est disponible si vous avez lié votre compte [!DNL Adobe Experience Cloud] avec [!DNL Analytics] et [!DNL Target], même si l’intégration entre [!DNL Target] et [!DNL Analytics] n’a pas été configurée pour votre compte.

Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous sélectionnez une suite de rapports [!DNL Analytics] pour recevoir les données d’activité [!DNL Target]. Pour spécifier une source de création de rapports, faites d’abord votre choix parmi les [!DNL Analytics] sociétés auxquelles votre compte est lié, puis sélectionnez la suite de rapports appropriée pour l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Adobe Target] peuvent être sélectionnées. Si vous ne voyez pas la suite de rapports attendue, essayez d’abord de vous déconnecter et de vous reconnecter à [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports n’apparaît toujours pas dans la liste, contactez l’assistance clientèle.

[!UICONTROL Analytics for Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s’affiche dans le champ [!UICONTROL Tracking Server] . Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le serveur de suivi approprié dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] comme source des rapports de votre activité, vous n’avez pas besoin de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Tracking Server] vide sur la page [!UICONTROL Goals & Settings].

Lors de la configuration d’une activité après avoir configuré [!DNL Analytics] comme source de création de rapports, il n’existe pas d’option pour configurer des audiences pour la création de rapports. [!DNL Analytics] segments sont disponibles dans le rapport [!DNL Target] [!UICONTROL Activities].

Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez choisir n’importe quelle mesure [!DNL Analytics] disponible dans le sélecteur de mesures [!DNL Analytics].

La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que vous voulez améliorer avec le test.

Une fois qu’un visiteur a atteint votre objectif, il n’est plus inclus dans l’activité. Si le visiteur entre à nouveau dans l’activité après avoir terminé une activité, il est comptabilisé comme un nouveau visiteur.
