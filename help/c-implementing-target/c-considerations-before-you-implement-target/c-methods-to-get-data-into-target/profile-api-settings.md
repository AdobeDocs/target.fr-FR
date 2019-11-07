---
keywords: implémentation;api;profil;paramètres de l’API de profil
description: Activez ou désactivez l’authentification pour la mise à jour des lots via l’API et générez un jeton d’authentification de profil.
title: Paramètres de l’API de profil
subtopic: Prise en main
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Paramètres de l’API de profil{#profile-api-settings}

Activez ou désactivez l’authentification pour la mise à jour des lots via l’API et générez un jeton d’authentification de profil.

Adobe Target crée et gère un profil pour chaque utilisateur. Ce profil est stocké dans le cluster Target Edge et est mis à jour en temps réel après chaque visite. Cependant, vous pouvez mettre à jour un profil individuellement ou en masse via l’API.

Pour plus de sécurité, vous pouvez exiger que l’appel de l’API de mise à jour en masse requiert qu’un jeton d’accès valide soit transmis dans l’en-tête de la demande. Les utilisateurs disposant d’autorisations Approbateur peuvent générer et activer des jetons d’authentification d’API de profil.

**Pour exiger une authentification et générer un jeton d’accès à l’aide de l’interface utilisateur de Target :**

1. Cliquez sur **[!UICONTROL Configuration]** &gt; **[!UICONTROL Implémentation]**.
1. Sous **[!UICONTROL Paramètres de l’API de profil]**, utilisez la liste déroulante **[!UICONTROL Identification requise]** pour activer ou désactiver les exigences d’authentification.

   ![](assets/profile_api_settings.png)

1. (Conditionnel) Si vous avez activé les exigences d’authentification, cliquez sur **[!UICONTROL Générer un jeton d’authentification de profil]**.

   ![](assets/profile_api_settings_2.png)

   Le jeton expire selon l’heure indiquée dans la zone [!UICONTROL Expire dans].

   >[!NOTE]
   >
   >Vous pouvez également générer un jeton d’authentification de profil via l’API. Pour plus d’informations, voir [Profiles](https://developers.adobetarget.com/api/#profiles) sur le [site web Adobe Target Developers](https://developers.adobetarget.com/).

1. Copiez le jeton et insérez-le dans l’en-tête de la demande au format « Autorisation » : « Support ».

Cliquez sur [!UICONTROL Regénérer un jeton d’authentification de profil] pour régénérer le jeton si nécessaire.

>[!IMPORTANT]
>
>La réinitialisation de ce jeton entraîne l’échec des appels d’API utilisant le jeton actuel. Vous devez, de ce fait, mettre à jour tous les scripts ou applications utilisant ce jeton.

