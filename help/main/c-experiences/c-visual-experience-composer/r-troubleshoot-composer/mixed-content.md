---
keywords: contenu mixte;sécurisé;non sécurisé;chrome;dépannage;vec;compositeur d’expérience visuelle;non sécurisé;http;https;firefox;internet explorer
description: Découvrez comment activer le contenu mixte dans  [!DNL Chrome],  [!DNL Firefox] et  [!DNL Edge].
title: Comment activer le contenu mixte dans mon navigateur ?
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
TQID: https://experienceleague.adobe.com/6Q1UvNmU-vSr9sp3pe2JN-wkjFUMWFxtPkgQegArrVw
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 566
ht-degree: 85%

---

# Activation du contenu mixte dans votre navigateur

Le contenu mixte se produit si la demande initiale est sécurisée via HTTPS, mais le contenu HTTPS *et* HTTP est chargé pour afficher la page web. Le contenu HTTPS est sécurisé. Le contenu HTTP n’est pas sécurisé.

Les navigateurs modernes peuvent bloquer l’affichage d’une page ou afficher des messages d’avertissement si le contenu sécurisé est mélangé à du contenu non sécurisé.

Un message d’avertissement s’affiche si le [!UICONTROL compositeur d’expérience visuelle] (VEC) d’[!DNL Adobe Target] tente d’ouvrir une page au contenu mixte. Ce message vous explique comment désactiver le blocage dans votre navigateur. La désactivation du blocage permet d’ouvrir un site HTTP ou un site comportant du contenu mixte (HTTPS et HTTP).

![Avertissement de contenu mixte](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Auparavant, lorsque le contenu mixte n’était pas autorisé, vous pouviez toujours effectuer certaines actions de l’étape 1 du processus assisté en trois étapes lors de la création d’activités. [!DNL Target] bloque désormais les actions de l’étape 1. Lorsque le message ci-dessus s’affiche, vous devez activer le contenu mixte avant de continuer la création de l’activité.

Les paramètres de sécurité du navigateur peuvent bloquer le chargement du contenu mixte ou du contenu non sécurisé (HTTP) sur une page sécurisée (HTTPS) ou une trame sécurisée (par exemple le compositeur d’expérience visuelle). Si vous ne souhaitez pas désactiver les paramètres de sécurité du navigateur, vous devez disposer d’un site web HTTPS.

Si votre site web s’exécute sur un domaine non sécurisé (HTTP), vous devez autoriser le compositeur d’expérience visuelle à charger du contenu mixte actif.

>[!IMPORTANT]
>
>L’autorisation du contenu mixte affecte uniquement le compositeur d’expérience visuelle et non votre site web actif.

Pour plus d’informations, consultez la page [Mixed Content (Contenu mixte)](https://developer.mozilla.org/fr/docs/Web/Security/Mixed_content) sur le site web *Mozilla Developer Network* (MDN).

## Activation du contenu mixte dans [!DNL Google Chrome] {#task_FF297A08F66E47A588C14FD67C037B3A}

Si vous visitez un site au moyen d’une connexion sécurisée, [!DNL Chrome] vérifie que le contenu de la page web a été transmis en toute sécurité.

Consultez « [Gérer les avertissements concernant les sites dangereux](https://support.google.com/chrome/answer/99020?hl=fr) » dans l’aide de Google Chrome.

Si vous utilisez le VEC avec la dernière version de [!DNL Chrome] (version 79.0.3945.117 ou ultérieure), vous devez mettre à jour les paramètres de votre site. Les visiteurs et visiteuses de votre site n’ont pas besoin d’effectuer ces étapes.

1. Cliquez sur l’icône de verrouillage (mise en garde), puis sur **[!UICONTROL Paramètres du site]**.

   ![Paramètres du site](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Faites défiler jusqu’à **[!UICONTROL Contenu non sécurisé]**, puis utilisez la liste déroulante pour remplacer « Bloquer (par défaut) » par « Autoriser ».

   ![Contenu non sécurisé](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Chargez à nouveau la page du compositeur d’expérience visuelle.

## Activation du contenu mixte dans [!DNL Mozilla Firefox] {#task_5448763B8DC941FD80F84041AEF0A14D}

Par défaut, [!DNL Firebox] bloque les pages qui contiennent du contenu sécurisé et non sécurisé. Vous devez modifier définitivement ce paramètre pour utiliser [!DNL Target]. Les visiteurs et visiteuses de votre site n’ont pas besoin d’effectuer ces étapes.

1. Dans Firefox, saisissez `about:config` dans la barre d’adresse.
1. Acceptez le message d’avertissement affiché par [!DNL Firefox].

   ![Avertissement de Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Dans la barre de recherche, entrez `block_active`.

   ![Paramètre block_principal de Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Double-cliquez sur ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   La valeur true se transforme en false. Lorsque la valeur devient false, l’opération est terminée.

   ![Sécurité de Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. Redémarrez votre ordinateur après avoir modifié ce paramètre.

## Activation du contenu mixte dans [!DNL Microsoft Edge]

Si vous visitez un site au moyen d’une connexion sécurisée, [!DNL Edge] vérifie que le contenu de la page web a été transmis en toute sécurité.

Si vous utilisez le VEC avec la dernière version de [!DNL Edge], vous devez mettre à jour les paramètres de votre site. Les visiteurs et visiteuses de votre site n’ont pas besoin d’effectuer ces étapes.

1. Dans [!DNL Edge], cliquez sur **[!DNL Microsoft Edge]** dans la barre de menus, **[!UICONTROL Paramètres]**, puis sur **Cookies et autorisations de site**.

1. Faites défiler jusqu’à **[!UICONTROL Contenu non sécurisé]**.

1. Cliquez sur **[!UICONTROL Contenu non sécurisé]**, puis sur **[!UICONTROL Ajouter]** en regard de **[!UICONTROL Autoriser]**, ajoutez le site sur lequel autoriser le contenu non sécurisé, puis cliquez sur **[!UICONTROL Ajouter]**.

1. Chargez à nouveau la page du compositeur d’expérience visuelle.
