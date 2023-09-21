---
keywords: ciblage;analytics;serveur de suivi;analytics for target;a4t
description: Découvrez comment configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source des rapports (A4T).
title: Comment utiliser [!DNL Analytics] Données dans [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 20%

---

# Utilisation [!DNL Adobe Analytics] data

Vous pouvez configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source des rapports (A4T).

Pour plus d’informations sur la configuration [!DNL Analytics] comme source de données pour [!DNL Target], voir [Adobe Analytics comme source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Avant de configurer une activité qui utilise [!DNL Analytics] comme source des rapports, définissez l’objectif de l’activité, par exemple améliorer les recettes par visiteur (RPV) ou augmenter les clics sur votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner d’autres mesures à tout moment dans [!DNL Analytics], vous devez toujours spécifier une mesure spécifique que ce test doit affecter.

>[!NOTE]
>
>La variable [!DNL Adobe Analytics] est disponible si vous avez lié votre [!DNL Adobe Experience Cloud] de [!DNL Analytics] et [!DNL Target], même si l’intégration entre [!DNL Target] et [!DNL Analytics] n’a pas été configuré pour votre compte.

Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous sélectionnez une [!DNL Analytics] suite de rapports à recevoir [!DNL Target] données d’activité. Pour spécifier une source de création de rapports, faites d’abord votre choix parmi les options suivantes : [!DNL Analytics] société à laquelle votre compte est lié, puis sélectionnez la suite de rapports appropriée à l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Adobe Target] sont disponibles pour sélection. Si vous ne voyez pas la suite de rapports attendue, essayez d’abord de vous déconnecter et de vous reconnecter au [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports n’apparaît toujours pas dans la liste, contactez l’assistance clientèle.

[!UICONTROL Analytics pour Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s’affiche dans la variable [!UICONTROL Serveur de suivi] champ . Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le serveur de suivi approprié dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de création de rapports de votre activité, vous n’avez pas besoin de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

Lors de la configuration d’une activité après la configuration [!DNL Analytics] en tant que source de création de rapports, il n’existe pas d’option pour configurer des audiences pour la création de rapports. [!DNL Analytics] sont disponibles dans la variable [!DNL Target] [!UICONTROL Activités] rapport.

Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez choisir n’importe lequel [!DNL Analytics] mesure disponible dans la variable [!DNL Analytics] sélecteur de mesures.

La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que vous voulez améliorer avec le test.

Une fois qu’un visiteur a atteint votre objectif, il n’est plus inclus dans l’activité. Si le visiteur entre à nouveau dans l’activité après avoir terminé une activité, il est comptabilisé comme un nouveau visiteur.
