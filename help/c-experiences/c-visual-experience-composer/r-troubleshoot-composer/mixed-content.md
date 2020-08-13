---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure;http;https;firefox;internet explorer
description: Certains navigateurs bloquent l’affichage d’une page si elle comporte du contenu sécurisé et non sécurisé.
title: Activation du contenu mixte dans votre navigateur
feature: vec
topic: Advanced,Standard,Classic
uuid: 6944ce97-ff73-4b61-b006-35862ff83ef1
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 35%

---


# Enabling mixed content in your browser{#enabling-mixed-content-in-your-browser}

Le contenu mixte se produit si les contenus HTTPS (sécurisé) ** et HTTP (non sécurisé) sont chargés pour afficher la même page Web et si la demande initiale était sécurisée par HTTPS.

Les navigateurs modernes peuvent bloquer l’affichage d’une page ou afficher des messages d’avertissement si le contenu sécurisé est mélangé à du contenu non sécurisé.

If the [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Target] tries to open a page containing mixed content, a message displays showing how to disable blocking in your browser so you can open an HTTP site or a site that has mixed calls (HTTPS and HTTP).

![avertissement de contenu mixte](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Auparavant, lorsque le contenu mixte n’était pas autorisé, vous pouviez toujours effectuer certaines actions de l’étape 1 du processus assisté en trois étapes lors de la création d’activités. [!DNL Target] bloque désormais les actions de l’étape 1. Lorsque ce message s’affiche, vous devez activer le contenu mixte avant de continuer à créer l’activité.

Les paramètres de sécurité du navigateur peuvent bloquer le chargement du contenu mixte ou du contenu non sécurisé (HTTP) sur une page sécurisée (HTTPS) ou une trame sécurisée (par exemple le compositeur d’expérience visuelle). Si vous ne souhaitez pas désactiver les paramètres de sécurité du navigateur, vous devez disposer d’un site web HTTPS.

Si votre site web s’exécute sur un domaine non sécurisé (HTTP), vous devez autoriser le compositeur d’expérience visuelle à charger du contenu mixte actif.

>[!NOTE]
>
>L’autorisation du contenu mixte affecte uniquement le compositeur d’expérience visuelle et non votre site Web actif.

Pour plus d’informations, voir [Mixed Content (Contenu mixte)](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) sur le site web *Mozilla Developer Network* (MDN).

## Enabling mixed content in Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Si vous visitez un site via une connexion sécurisée, Chrome vérifie que le contenu de la page Web a été transmis en toute sécurité.

Voir [Cette page comporte du contenu non sécurisé](https://support.google.com/chrome/answer/1342714?hl=en) dans l’aide Google Chrome.

Si vous utilisez le compositeur d’expérience visuelle avec la dernière version de Chrome (version 79.0.3945.117 ou ultérieure), vous devez mettre à jour les paramètres de votre site. Les visiteurs de votre site n’ont pas besoin de suivre ces étapes.

1. Cliquez sur l’icône de verrouillage ou d’avertissement, puis sur Paramètres **[!UICONTROL du]** site.

   ![Paramètres du site](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Faites défiler le contenu **** non sécurisé, puis utilisez la liste déroulante pour remplacer &quot;Bloquer (par défaut)&quot; par &quot;Autoriser&quot;.

   ![Contenu non sécurisé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Rechargez la page du compositeur d’expérience visuelle.

## Enabling mixed content in Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Par défaut, Firefox bloque les pages qui contiennent du contenu sécurisé et non sécurisé. Pour utiliser [!DNL Target], il est conseillé de modifier définitivement ce paramètre. Les visiteurs de votre site n’ont pas besoin de suivre ces étapes.

1. Dans Firefox, saisissez `about:config` dans la barre d’adresse.
1. Acceptez le message d’avertissement affiché par Firefox.

   ![Avertissement Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Dans la barre de recherche, entrez `block_active`.

   ![Paramètre principal du bloc Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Double-cliquez sur ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   La valeur true se transforme en false. Lorsque la valeur devient false, l’opération est terminée. 

   ![Sécurité Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Nous vous recommandons de redémarrer votre ordinateur après avoir modifié ce paramètre.

## Activation du contenu mixte dans Microsoft Edge

Si vous visitez un site via une connexion sécurisée, Edge vérifie que le contenu de la page Web a été transmis en toute sécurité.

Si vous utilisez le compositeur d’expérience visuelle avec la dernière version d’Edge, vous devez mettre à jour les paramètres de votre site. Les visiteurs de votre site n’ont pas besoin de suivre ces étapes.

1. Cliquez sur l’icône de verrouillage ou d’avertissement, puis sur Autorisations **[!UICONTROL du]** site.

   ![Autorisations de site dans Microsoft Edge](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Faites défiler le contenu **** non sécurisé, puis utilisez la liste déroulante pour remplacer &quot;Bloquer (par défaut)&quot; par &quot;Autoriser&quot;.

   ![Contenu non sécurisé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Rechargez la page du compositeur d’expérience visuelle.