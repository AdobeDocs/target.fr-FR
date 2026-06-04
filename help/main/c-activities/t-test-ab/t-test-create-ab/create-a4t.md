---
keywords: Ciblage;analytics;serveur de suivi;analytics for target;a4t
description: Découvrez comment configurer une activité dans pour l [!DNL Adobe Target] utiliser  [!DNL Adobe Analytics]  tant que source de création de rapports (A4T).
title: Comment puis-je utiliser  [!DNL Analytics]  données dans  [!DNL Target] ?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 492
ht-degree: 21%

---

# Utilisation des données [!DNL Adobe Analytics]

Vous pouvez configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source de création de rapports (A4T).

Pour plus d’informations sur la configuration de [!DNL Analytics] comme source de données pour [!DNL Target], voir [Adobe Analytics comme Source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Avant de configurer une activité qui utilise [!DNL Analytics] comme source de création de rapports, définissez l’objectif de l’activité, tel que l’amélioration du chiffre d’affaires par visiteur (RPV) ou l’augmentation du nombre de clics dans votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner des mesures supplémentaires à tout moment dans [!DNL Analytics], vous devez toujours spécifier une mesure spécifique que ce test affectera.

>[!NOTE]
>
>L’option [!DNL Adobe Analytics] est disponible si vous avez lié votre compte [!DNL Adobe Experience Cloud] à la fois à [!DNL Analytics] et à [!DNL Target], même si l’intégration entre [!DNL Target] et [!DNL Analytics] n’a pas été configurée pour votre compte.

Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour les [!DNL Target], vous sélectionnez une suite de rapports [!DNL Analytics] pour recevoir des données d’activité [!DNL Target]. Pour spécifier une source de création de rapports, choisissez d’abord l’une des [!DNL Analytics] sociétés auxquelles votre compte est lié, puis sélectionnez la suite de rapports appropriée pour l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Adobe Target] peuvent être sélectionnées. Si la suite de rapports attendue ne s’affiche pas, essayez d’abord de vous déconnecter puis de vous reconnecter à la [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports est toujours absente de la liste, contactez l’assistance clientèle.

[!UICONTROL Analytics for Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s’affiche dans le champ [!UICONTROL Serveur de suivi]. Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le bon serveur de suivi dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] comme source de création de rapports pour votre activité, il n’est pas nécessaire de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

Lors de la configuration d’une activité après avoir configuré [!DNL Analytics] comme source de création de rapports, il n’est pas possible de configurer des audiences pour les rapports. [!DNL Analytics] segments sont disponibles dans le rapport [!DNL Target] [!UICONTROL Activités].

Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez choisir n’importe quelle mesure [!DNL Analytics] disponible dans le sélecteur de mesures [!DNL Analytics].

La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que vous voulez améliorer avec le test.

Une fois qu’un visiteur a terminé votre objectif, il n’est plus inclus dans l’activité. Si le visiteur rejoint à nouveau votre activité après avoir terminé une activité, il est comptabilisé comme un nouveau visiteur.
