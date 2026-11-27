---
keywords: contenu mixte;sécurisé;non sécurisé;chrome;dépannage;vec;compositeur d’expérience visuelle;non sécurisé;http;https;firefox;internet explorer
description: Découvrez comment activer le contenu mixte dans [!DNL Chrome], [!DNL Firefox] et [!DNL Edge].
title: Comment activer le contenu mixte dans mon navigateur ?
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
TQID: 'https://experienceleague.adobe.com/6Q1UvNmU-vSr9sp3pe2JN-wkjFUMWFxtPkgQegArrVw'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 11%
---
# Activation du contenu mixte dans le navigateur {#mixed-content}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment activer le contenu mixte dans [!DNL Google Chrome], [!DNL Mozilla Firefox] et [!DNL Microsoft Edge], de sorte que le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) puisse ouvrir les sites HTTP et les sites contenant du contenu mixte.

>[!ENDSHADEBOX]

Une page contient du contenu mixte lorsqu’elle est demandée en toute sécurité via HTTPS, mais charge le contenu HTTPS et HTTP. Le contenu HTTPS est sécurisé, contrairement au contenu HTTP, de sorte que les navigateurs modernes peuvent bloquer cette page ou afficher un message d’avertissement.

Lorsque le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) de [!DNL Adobe Target] tente d’ouvrir une page au contenu mixte, un message d’avertissement s’affiche avec des instructions pour désactiver le blocage dans le navigateur. La désactivation du blocage permet d’ouvrir un site HTTP ou un site à contenu mixte (HTTPS et HTTP).

![Page de création d’activité avec un message indiquant que le chargement des scripts du navigateur doit être autorisé pour créer des activités, à côté d’une illustration de l’invite de rechargement du navigateur](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Auparavant, certaines actions de l’étape 1 du workflow guidé en trois étapes restaient disponibles lorsque le contenu mixte n’était pas autorisé. [!DNL Target] bloque désormais toutes les actions de l’étape 1. Le contenu mixte doit donc être activé pour que la création de l’activité puisse continuer.

Les paramètres de sécurité du navigateur peuvent bloquer le contenu non sécurisé (HTTP) chargé dans une page ou une trame sécurisée (HTTPS), telle que le compositeur d’expérience visuelle. L’alternative à la modification de ces paramètres est un site web HTTPS. Si le site web s’exécute sur un domaine non sécurisé (HTTP), le compositeur d’expérience visuelle doit être autorisé à charger du contenu mixte actif.

>[!IMPORTANT]
>
>L’autorisation du contenu mixte affecte uniquement le compositeur d’expérience visuelle et non le site web actif.

Pour plus d’informations, consultez la page [Mixed Content (Contenu mixte)](https://developer.mozilla.org/fr/docs/Web/Security/Mixed_content) sur le site web *Mozilla Developer Network* (MDN).

## Activer le contenu mixte dans [!DNL Google Chrome]

[!DNL Chrome] vérifie que le contenu d&#39;une page demandée via une connexion sécurisée a été transmis en toute sécurité. Consultez « [Gérer les avertissements concernant les sites dangereux](https://support.google.com/chrome/answer/99020?hl=fr) » dans l’aide de Google Chrome.

Pour utiliser le compositeur d’expérience visuelle avec la dernière version de [!DNL Chrome] (version 79.0.3945.117 ou ultérieure), mettez à jour les paramètres du site comme suit. Les visiteurs et visiteuses du site n’ont pas besoin d’effectuer ces étapes.

1. Cliquez sur l&#39;icône de verrouillage (mise en garde), puis sur **[!UICONTROL Paramètres du site]**.

   ![Barre d&#39;adresse Chrome avec le menu de connexion ouvert et les paramètres du site mis en surbrillance](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Dans **[!UICONTROL Contenu non sécurisé]**, remplacez « Bloquer (par défaut) » par « Autoriser » dans la liste déroulante.

   ![Paramètres du site Chrome avec le menu déroulant Contenu non sécurisé ouvert et Autoriser sélectionné](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Chargez à nouveau la page du compositeur d’expérience visuelle.

## Activer le contenu mixte dans [!DNL Mozilla Firefox]

Par défaut, [!DNL Firefox] bloque les pages qui mélangent du contenu sécurisé et non sécurisé. Ce paramètre doit donc être modifié définitivement pour utiliser [!DNL Target]. Les visiteurs et visiteuses du site n’ont pas besoin d’effectuer ces étapes.

1. Dans [!DNL Firefox], saisissez `about:config` dans la barre d’adresse.
1. Accepte le message d&#39;avertissement que [!DNL Firefox] affiche.

   ![Firefox Poursuivez avec la page d&#39;avertissement Attention pour environ:config avec le bouton Accepter le risque et continuer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Dans la barre de recherche, saisissez `block_active`.

   ![Firefox à propos de:config recherchez block_active en affichant security.xed_content.block_active_content défini sur true](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Double-cliquez sur `security.mixed_content.block_active_content`.

   La valeur passe de « True » à « False ». Lorsque la valeur affiche « False », la modification est terminée.

   ![Firefox à propos de:config affichant security.xed_content.block_active_content défini sur false](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. Redémarrez l&#39;ordinateur après avoir modifié ce paramètre.

## Activer le contenu mixte dans [!DNL Microsoft Edge]

[!DNL Edge] vérifie que le contenu d&#39;une page demandée via une connexion sécurisée a été transmis en toute sécurité. Pour utiliser le compositeur d’expérience visuelle avec la dernière version de [!DNL Edge], mettez à jour les paramètres du site comme suit. Les visiteurs et visiteuses du site n’ont pas besoin d’effectuer ces étapes.

1. Dans [!DNL Edge], cliquez sur **[!DNL Microsoft Edge]** dans la barre de menus, cliquez sur **[!UICONTROL Paramètres]**, puis sur **Cookies et autorisations de site**.
1. Faites défiler jusqu’à **[!UICONTROL Contenu non sécurisé]** et cliquez dessus.
1. En regard de **[!UICONTROL Autoriser]**, cliquez sur **[!UICONTROL Ajouter]**, saisissez le site sur lequel autoriser le contenu non sécurisé, puis cliquez sur **[!UICONTROL Ajouter]**.
1. Chargez à nouveau la page du compositeur d’expérience visuelle.
