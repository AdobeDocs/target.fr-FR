---
keywords: Administration, rôle d’approbateur, approbateur
description: Effectuez les premières tâches que les  [!DNL Adobe Target]  doivent effectuer après avoir reçu l’invitation par e-mail à  [!DNL Adobe Experience Cloud].
title: Où Puis-Je Commencer À Administrer  [!DNL Target] ?
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: 614fd89c9746ce55f502debd5b689c34de400ae5
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 32%

---

# Premières étapes de l’administrateur

Cet article décrit les premières étapes que [!DNL Adobe Target] administrateurs doivent suivre après avoir reçu l’invitation par e-mail envoyée au [!DNL Adobe Experience Cloud].

## Être invité à [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

Un administrateur système dans l’[!DNL Adobe Admin Console] doit vous ajouter en tant qu’utilisateur dans [!DNL Target] en vous invitant à rejoindre l’application. L’administrateur système doit ensuite vous ajouter à un ou plusieurs profils de produit spécifiques au rôle (groupes d’utilisateurs). Ces deux tâches sont effectuées dans [Adobe Admin Console](https://adminconsole.adobe.com).

Pour plus d’informations, voir [Gestion des groupes d’utilisateurs](https://helpx.adobe.com/enterprise/using/users.html).

Vous recevrez un e-mail d’invitation une fois que l’administrateur système aura effectué ces étapes.

## Acceptation de l’invitation {#task_24FE66659E634B24AB61DB8497772E17}

Après avoir reçu l’invitation à rejoindre le [!DNL Adobe Experience Cloud], acceptez l’invitation, connectez-vous et acceptez le [!UICONTROL End User License Agreement] (CLUF).

1. Acceptez l’invitation à rejoindre [!DNL Adobe Experience Cloud].
1. Si vous ne possédez pas déjà un Adobe ID, vous êtes invité à en créer un.

   Si vous disposez d’une Adobe ID, votre Adobe ID est reconnue et vous êtes invité à vous connecter.
1. Acceptez la [!UICONTROL Terms of Use].
1. Passez en revue le résumé de ce que vous avez fait jusqu’à présent, puis cliquez sur **[!UICONTROL Continue to Experience Cloud]**.
1. Connectez-vous à l’[!DNL Adobe Experience Cloud] et cliquez sur **[!UICONTROL Link Account]**.

   >[!NOTE]
   >
   >Si vous ne liez pas votre compte, vous ne pourrez pas accéder à [!DNL Target].

   Tous les produits [!UICONTROL Experience Cloud] apparaissent sur la page de liaison. Cliquez sur `Link Target` et saisissez vos nom d’utilisateur et mot de passe [!DNL Target] pour accéder à [!DNL Target].
1. Cliquez sur **[!UICONTROL Continue to Experience Cloud]**.

   À ce stade, aucun groupe n’est configuré pour que vous puissiez le lier.
1. Si vous le souhaitez, visionnez la vidéo qui vous présente [!DNL Adobe Experience Cloud].
1. Pour connaître vos nouveaux privilèges et accéder au produit, déconnectez-vous d’[!DNL Adobe Experience Cloud], puis reconnectez-vous.
1. Passez à l’étape suivante, en [vous attribuant le rôle d’approbateur](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Attribution à vous-même du rôle d’approbateur {#task_15CAA437A71444E2932B333D5E66A3C7}

Après avoir accepté l’invitation à rejoindre l’[!DNL Adobe Experience Cloud] et vous être connecté, vérifiez que [!DNL Target] a été ajouté à votre compte [!DNL Experience Cloud], puis attribuez-vous le rôle [!UICONTROL Approver] pour [!DNL Target].

Si votre organisation dispose d’une licence [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), voir [Spécification des rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*.

Si votre organisation dispose d’une licence [Target Premium](/help/main/c-intro/intro.md#premium), voir [Étape 6 : Spécification des rôles et autorisations](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) dans *Configuration des autorisations d’Entreprise*.

L’étape suivante doit consister à configurer les utilisateurs dans [!DNL Target Standard] et [!DNL Target Premium]. Pour plus d’informations, voir [Gestion des utilisateurs](/help/main/administrating-target/c-user-management/user-management.md).

## Autorisations requises pour la modification des paramètres de [!UICONTROL Administration] {#admin-permissions}

**Avant le 22 avril 2025** : les utilisateurs disposant de droits d’[!UICONTROL Approvers] dans le [!DNL Adobe Admin Console] peuvent modifier tous les paramètres de la [[!UICONTROL Administration] page ](/help/main/administrating-target/administrating-target.md) page de [!DNL Target], quel que soit leur rôle de [!DNL Target].

**À compter du 22 avril 2025** : seuls les administrateurs [!UICONTROL Product] et [!UICONTROL Solutions] pourront mettre à jour les paramètres des sections [[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md), quels que soient leurs rôles dans les espaces de travail [!DNL Target]. Les utilisateurs ne disposant pas de cette autorisation auront un accès en lecture seule aux sections [!UICONTROL Administration].

Cette mise à jour améliore le contrôle organisationnel sur les configurations d’instance de [!DNL Target], empêchant les mises à jour accidentelles qui pourraient affecter la diffusion des activités entre différentes équipes de test et de personnalisation.
