---
keywords: implementation;api;profile;profile api settings;authentication token
description: Activez ou désactivez l’authentification pour la mise à jour des lots via l’API et générez un jeton d’authentification de profil.
title: Paramètres de l’API de profil
feature: api
subtopic: Getting Started
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 64%

---


# Paramètres de l’API de profil{#profile-api-settings}

Activez ou désactivez l’authentification pour la mise à jour des lots via l’API et générez un jeton d’authentification de profil.

[!DNL Adobe Target] crée et gère un profil pour chaque utilisateur. This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit, however, you can update a profile individually or in bulk via API.

Pour plus de sécurité, vous pouvez exiger que l’appel de l’API de mise à jour en masse requiert qu’un jeton d’accès valide soit transmis dans l’en-tête de la demande. Users with [!UICONTROL Approver] permissions can generate and enable profile API authentication tokens.

**Pour exiger une authentification et générer un jeton d’accès à l’aide de l’interface utilisateur de Target :**

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.
1. Sous API **[!UICONTROL de]** Profil, faites glisser la bascule **[!UICONTROL Exiger l’authentification]** pour passer à la position activée ou désactivée.

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Pfofile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   Le jeton expire selon l’heure indiquée dans la zone [!UICONTROL Expire dans].

   >[!NOTE]
   >
   >Vous pouvez également générer un jeton d’authentification de profil via l’API. Pour plus d’informations, voir [Profiles](https://developers.adobetarget.com/api/#profiles) sur le [site web Adobe Target Developers](https://developers.adobetarget.com/).

1. Copiez le jeton et insérez-le dans l’en-tête de la demande au format « Autorisation » : « Support ».

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>La réinitialisation de ce jeton entraîne l’échec des appels d’API utilisant le jeton actuel. Vous devez, de ce fait, mettre à jour tous les scripts ou applications utilisant ce jeton.
