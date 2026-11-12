---
keywords: Administration, rôle d’approbateur, approbateur
description: Effectuez les premières tâches que les administrateurs d’Adobe Target doivent effectuer après avoir reçu l’invitation par e-mail à Adobe Experience Cloud.
title: Par Où Commencer L'Administration De [!DNL Target] ?
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
TQID: 'https://experienceleague.adobe.com/GfadY-knTwzXCB-n1AZ9u3PtoAyJokn1OXu3elRhgXk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 9%
---
# Premières étapes de l’administrateur

Effectuez ces étapes après avoir reçu une invitation à rejoindre [!DNL Adobe Target] via le [!DNL Adobe Experience Cloud]. Lorsque vous êtes prêt à configurer les valeurs par défaut du compte, consultez [Comment administrer Target ?](/help/main/administrating-target/administrating-target.md). Pour obtenir de l’aide sur la recherche de **[!UICONTROL Administration]** dans l’interface utilisateur, consultez [Comprendre l’ [!DNL Target] interface utilisateur](/help/main/c-intro/understand-the-target-ui.md).

**Présentation des workflows**

1. [Être invité à rejoindre Target](#task_3E0817630774431983FAA3D2CB2E75BD) : un administrateur système vous ajoute dans le [!DNL Adobe Admin Console].
1. [Accepter l&#39;invitation](#task_24FE66659E634B24AB61DB8497772E17) : connectez-vous à [!DNL Experience Cloud] et liez votre compte [!DNL Target].
1. [Attribuez-vous le rôle d’approbateur](#task_15CAA437A71444E2932B333D5E66A3C7) : confirmez l’accès et les autorisations pour votre type de licence.
1. [Gestion des utilisateurs](/help/main/administrating-target/c-user-management/user-management.md) : ajoutez des utilisateurs et attribuez des rôles pour [!DNL Target Standard] ou [!DNL Target Premium].

## Être invité à [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

Un administrateur système dans [!DNL Adobe Admin Console] doit vous ajouter en tant qu’utilisateur dans [!DNL Target] en vous invitant à rejoindre. L’administrateur doit également vous ajouter à un ou plusieurs profils de produit spécifiques au rôle (groupes d’utilisateurs). Les deux tâches sont effectuées dans le [Adobe Admin Console](https://adminconsole.adobe.com).

Pour obtenir des conseils détaillés, consultez [Découvrez comment gérer les utilisateurs et les profils de produit](https://helpx.adobe.com/enterprise/using/users.html) dans la documentation Adobe Enterprise.

Une fois que l’administrateur a effectué ces étapes, vous recevez un e-mail d’invitation.

## Acceptation de l’invitation {#task_24FE66659E634B24AB61DB8497772E17}

Après avoir reçu l&#39;invitation à rejoindre le [!DNL Adobe Experience Cloud], acceptez-le, connectez-vous et acceptez le [!UICONTROL Contrat de licence de l&#39;utilisateur final] (CLUF).

Procédez comme suit pour accepter l’invitation et lier [!DNL Target] à votre compte [!DNL Experience Cloud] :

1. Acceptez l’invitation à rejoindre [!DNL Adobe Experience Cloud].
1. Si vous ne possédez pas déjà un Adobe ID, vous êtes invité à en créer un.

   Si vous disposez déjà d’une Adobe ID, connectez-vous lorsque vous y êtes invité.

1. Acceptez les [!UICONTROL conditions d&#39;utilisation].

1. Vérifiez le résumé de ce que vous avez fait jusqu’à présent, puis cliquez sur **[!UICONTROL Continuer vers Experience Cloud]**.

1. Connectez-vous à [!DNL Adobe Experience Cloud] et cliquez sur **[!UICONTROL Lier le compte]**.

   >[!NOTE]
   >
   >Si vous ne liez pas votre compte, vous ne pouvez pas accéder à [!DNL Target].

   Tous les [!UICONTROL produits Experience Cloud] apparaissent sur la page de liaison. Cliquez sur **[!UICONTROL Lier Target]**, puis entrez votre nom d&#39;utilisateur et votre mot de passe [!DNL Target].
1. Cliquez sur **[!UICONTROL Continuer vers Experience Cloud]**.

   À ce stade, vous ne disposez peut-être pas encore de profils de produit avec des droits à lier ; votre administrateur système peut les attribuer dans le [!DNL Adobe Admin Console].
1. Si vous le souhaitez, regardez la vidéo qui présente le [!DNL Adobe Experience Cloud].
1. Pour actualiser vos privilèges et ouvrir le produit, déconnectez-vous de [!DNL Adobe Experience Cloud], puis reconnectez-vous.
1. Continuer vers [Attribuez-vous le rôle d&#39;approbateur](#task_15CAA437A71444E2932B333D5E66A3C7).

## Attribution à vous-même du rôle d’approbateur {#task_15CAA437A71444E2932B333D5E66A3C7}

Après avoir accepté l’invitation et vous être connecté, confirmez que [!DNL Target] apparaît dans votre compte [!DNL Experience Cloud], puis attribuez-vous le rôle [!UICONTROL Approbateur] pour [!DNL Target].

Sélectionnez les conseils correspondant à votre licence :

* Si votre organisation dispose d’une licence [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consultez [Découvrez comment spécifier des rôles et des autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*.
* Si votre organisation dispose d’une licence [Target Premium](/help/main/c-intro/intro.md#premium), voir [Étape 6 : Spécification des rôles et autorisations](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) dans *Configuration des autorisations d’Entreprise*.

Vous pouvez ensuite configurer des utilisateurs pour [!DNL Target Standard] ou [!DNL Target Premium]. Consultez [Gestion des utilisateurs](/help/main/administrating-target/c-user-management/user-management.md) pour obtenir un aperçu et des liens vers le workflow approprié pour votre licence.

## Autorisations requises pour la modification des paramètres de [!UICONTROL Administration] {#admin-permissions}

**Avant le 22 avril 2025** : les utilisateurs disposant de [!UICONTROL droits d’approbateur] dans [!DNL Adobe Admin Console] pouvaient modifier ou changer tous les paramètres des pages [[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md) dans [!DNL Target], quel que soit leur rôle [!DNL Target].

**À compter du 22 avril 2025** : seuls les administrateurs [!UICONTROL Produit] et [!UICONTROL Solutions] peuvent mettre à jour les paramètres des sections [[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md), quels que soient leurs rôles dans [!DNL Target] espaces de travail. Les utilisateurs ne disposant pas de cette autorisation ont un accès en lecture seule aux sections [!UICONTROL Administration].

Cette modification améliore le contrôle organisationnel sur la configuration de l’instance [!DNL Target] et permet d’éviter les mises à jour accidentelles qui pourraient affecter la diffusion des activités entre les équipes de test et de personnalisation.
