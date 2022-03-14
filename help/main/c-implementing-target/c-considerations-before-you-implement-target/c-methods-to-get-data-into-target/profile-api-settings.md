---
keywords: implémentation;api;profil;paramètres de l’api de profil;jeton d’authentification
description: Découvrez comment configurer l’authentification pour les mises à jour par lots via Adobe [!DNL Target] API et générer un jeton d’authentification de profil.
title: Comment utiliser les paramètres de l’API de profil pour activer ou désactiver les mises à jour par lots ?
feature: APIs/SDKs
role: Developer
exl-id: 6346e11b-0853-47f1-9706-69e8635a6f25
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 61%

---

# Paramètres de l’API de profil

Activation ou désactivation de l’authentification pour les mises à jour par lots via [!DNL Adobe Target] API et générer un jeton d’authentification de profil.

[!DNL Adobe Target] crée et gère un profil pour chaque utilisateur. Ce profil est stocké dans la variable [!DNL Target] grappe Edge et est mise à jour en temps réel après chaque visite ; toutefois, vous pouvez mettre à jour un profil individuellement ou en bloc via l’API.

Pour plus de sécurité, vous pouvez exiger que l’appel de l’API de mise à jour en masse requiert qu’un jeton d’accès valide soit transmis dans l’en-tête de la demande.

**Pour exiger une authentification et générer un jeton d’accès à l’aide de l’interface utilisateur de Target :**

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.
1. Sous **[!UICONTROL API de profil]** faire glisser **[!UICONTROL Authentification requise]** basculez sur la position activée ou désactivée.

   ![](assets/profile_api_settings.png)

1. (Conditionnel) Si vous avez activé les exigences d’authentification, cliquez sur **[!UICONTROL Générer un nouveau jeton d’authentification de profil]**.

   ![](assets/profile_api_settings_2.png)

   Le jeton expire selon l’heure indiquée dans la zone [!UICONTROL Expire dans].

   Vous devez disposer de l’une des autorisations utilisateur suivantes pour générer un jeton d’authentification :

   * Au minimum l’autorisation [!UICONTROL Éditeur] (ou [!UICONTROL Approbateur])

      Pour plus d’informations concernant les clients [!DNL Target Standard], consultez [Spécifier les rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*. Pour plus d’informations concernant les clients [!DNL Target Premium], consultez [Configuration des autorisations d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Rôle d’administrateur au niveau de l’espace de travail/du profil de produit

      Les espaces de travail sont disponibles uniquement pour les clients [!DNL Target Premium]. Pour plus d’informations, consultez [Configuration des autorisations d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Droits d’administrateur (autorisation Sysadmin) au niveau du produit [!DNL Adobe Target]
   >[!NOTE]
   >
   >Vous pouvez également générer un jeton d’authentification de profil via l’API. Pour plus d’informations, voir [Profiles](https://developers.adobetarget.com/api/#profiles) sur le [site web Adobe Target Developers](https://developers.adobetarget.com/).

1. Copiez le jeton et insérez-le dans l’en-tête de la demande au format « Autorisation » : « Support ».

Cliquez sur [!UICONTROL Générer un nouveau jeton d’authentification de profil] pour régénérer le jeton selon les besoins.

>[!IMPORTANT]
>
>La réinitialisation de ce jeton entraîne l’échec des appels d’API utilisant le jeton actuel. Vous devez, de ce fait, mettre à jour tous les scripts ou applications utilisant ce jeton.
