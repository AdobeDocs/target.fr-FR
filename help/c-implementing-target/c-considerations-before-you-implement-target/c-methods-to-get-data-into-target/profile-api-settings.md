---
keywords: implementation;api;profile;profile api settings;authentication token
description: Activez ou désactivez l’authentification pour les mises à jour par lots via les API Adobe Target et générez un jeton d’authentification de profil.
title: Paramètres de l'API profil dans Adobe Target
feature: APIs/SDKs
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 40%

---


# Paramètres de l’API de profil

Activez ou désactivez l’authentification pour les mises à jour par lots via les API [!DNL Adobe Target] et générez un jeton d’authentification par profil.

[!DNL Adobe Target] crée et gère un profil pour chaque utilisateur. Ce profil est stocké sur le cluster de serveurs Edge [!DNL Target] et mis à jour en temps réel après chaque visite ; toutefois, vous pouvez mettre à jour un profil individuellement ou en bloc via l’API.

Pour plus de sécurité, vous pouvez exiger que l’appel de l’API de mise à jour en masse requiert qu’un jeton d’accès valide soit transmis dans l’en-tête de la demande.

**Pour exiger une authentification et générer un jeton d’accès à l’aide de l’interface utilisateur de Target :**

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.
1. Sous **[!UICONTROL API de Profil]**, faites glisser la bascule **[!UICONTROL Exiger l&#39;authentification]** vers la position activée ou désactivée.

   ![](assets/profile_api_settings.png)

1. (Conditionnel) Si vous avez activé les exigences d’authentification, cliquez sur **[!UICONTROL Générer un nouveau jeton d’authentification de Profil]**.

   ![](assets/profile_api_settings_2.png)

   Le jeton expire selon l’heure indiquée dans la zone [!UICONTROL Expire dans].

   Vous devez disposer de l’une des autorisations d’utilisateur suivantes pour générer un jeton d’authentification :

   * Au moins [!UICONTROL autorisation de l’éditeur] (ou [!UICONTROL approbateur])

      Pour plus d&#39;informations sur les [!DNL Target Standard] clients, voir [Spécification des rôles et autorisations](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*. Pour plus d’informations sur les clients [!DNL Target Premium], voir [Configuration des autorisations d’entreprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Rôle d’administrateur au niveau de l’espace de travail/du profil de produit

      Les espaces de travail sont disponibles uniquement pour les clients [!DNL Target Premium]. Pour plus d’informations, voir [Configuration des autorisations d’entreprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Droits d’administration (autorisation Sysadmin) au niveau du produit [!DNL Adobe Target]
   >[!NOTE]
   >
   >Vous pouvez également générer un jeton d’authentification de profil via l’API. Pour plus d’informations, voir [Profiles](https://developers.adobetarget.com/api/#profiles) sur le [site web Adobe Target Developers](https://developers.adobetarget.com/).

1. Copiez le jeton et insérez-le dans l’en-tête de la demande au format « Autorisation » : « Support ».

Cliquez sur [!UICONTROL Générer un nouveau jeton d’authentification de Profil] pour régénérer le jeton suivant vos besoins.

>[!IMPORTANT]
>
>La réinitialisation de ce jeton entraîne l’échec des appels d’API utilisant le jeton actuel. Vous devez, de ce fait, mettre à jour tous les scripts ou applications utilisant ce jeton.
