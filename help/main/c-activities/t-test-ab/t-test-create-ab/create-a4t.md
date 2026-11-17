---
keywords: Ciblage;analytics;serveur de suivi;analytics for target;a4t
description: Découvrez comment configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source de création de rapports (A4T).
title: Comment puis-je utiliser les données [!DNL Analytics] dans [!DNL Target] ?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: 'https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%
---
# Utilisation des données [!DNL Adobe Analytics] {#create-a4t}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment configurer une activité pour utiliser [!DNL Adobe Analytics] comme source de création de rapports (A4T), que préparer avant de commencer et comment choisir l’objectif de l’activité.

>[!ENDSHADEBOX]

Analytics for Target (A4T) mesure les résultats d’une activité [!DNL Adobe Target] avec les données et mesures de [!DNL Adobe Analytics]. Pour utiliser A4T, configurez l’activité de sorte que [!DNL Analytics] soit sa source de création de rapports. Pour plus d’informations sur la configuration de [!DNL Analytics] en tant que source de données pour [!DNL Target], consultez [Adobe Analytics en tant que Source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Avant de commencer {#before-you-begin}

>[!NOTE]
>
>L’option **[!UICONTROL Adobe Analytics]** est disponible lorsque votre compte [!DNL Adobe Experience Cloud] est lié à la fois à [!DNL Analytics] et à [!DNL Target], même si l’intégration entre [!DNL Target] et [!DNL Analytics] n’a pas été configurée pour votre compte.

Avant de créer l’activité, établissez son objectif, par exemple en améliorant le chiffre d’affaires par visiteur (RPV) ou en augmentant le nombre de clics sur votre panier. Sélectionnez ensuite la mesure de succès finale qui mesure cet objectif. D&#39;autres mesures peuvent être sélectionnées à tout moment dans [!DNL Analytics], mais vous devez toujours spécifier la mesure que ce test est censé affecter.

## Sélectionner Analytics comme source de création de rapports {#select-reporting-source}

>[!NOTE]
>
>Si vous utilisez la version 0.9.1 ou ultérieure d’at.js, il n’est pas nécessaire de spécifier de serveur de suivi lorsque vous créez une activité qui utilise [!DNL Adobe Analytics] comme source de création de rapports. La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Le champ **[!UICONTROL Serveur de suivi]** de la page **[!UICONTROL Objectifs et paramètres]** peut rester vide.

La source de création de rapports est sélectionnée sur la page **[!UICONTROL Objectifs et paramètres]** de l’activité. Sur cette page, vous choisissez une société [!DNL Analytics] et la suite de rapports qui reçoit les données d’activité [!DNL Target], et vous vérifiez le serveur de suivi.

➡️ Pour connaître les étapes, les exigences relatives aux suites de rapports et les détails du serveur de suivi, consultez [Reporting Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source).

Lorsque [!DNL Analytics] est la source de création de rapports, l’activité ne propose pas d’option permettant de configurer des audiences pour la création de rapports. [!DNL Analytics] segments sont disponibles à la place dans le rapport [!DNL Target] **[!UICONTROL Activités]**.

## Définir l’objectif de l’activité {#set-goal}

Chaque activité nécessite une mesure de succès comme objectif. L’objectif est l’activité de conversion qui signale une activité réussie. Toute mesure disponible dans le sélecteur de mesures [!DNL Analytics] peut être utilisée. Il est recommandé de ne jamais exécuter un test sans objectif d’amélioration spécifique.

Définir un objectif ne vous empêche pas d’utiliser d’autres mesures pour évaluer les résultats du test. L’objectif identifie toutefois la seule chose que vous souhaitez améliorer avec le test.

Une fois qu’un visiteur a terminé votre objectif, il n’est plus inclus dans l’activité. Si le visiteur entre à nouveau dans l’activité après l’avoir terminée, il est comptabilisé comme un nouveau visiteur.
