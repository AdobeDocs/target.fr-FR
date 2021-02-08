---
keywords: contenu mixte;sécurisé;non sécurisé;chrome;dépannage;vec;compositeur d’expérience visuelle;non sécurisé;http;https;firefox;internet explorer
description: Certains navigateurs bloquent l’affichage d’une page si elle comporte du contenu sécurisé et non sécurisé. Découvrez comment activer le contenu mixte dans Chrome, Firefox et Edge.
title: Comment activer le contenu mixte dans mon navigateur ?
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Activation du contenu mixte dans votre navigateur

Le contenu mixte se produit si le contenu HTTP (sécurisé) *et* HTTP (non sécurisé) est chargé pour afficher la même page Web et que la requête initiale était sécurisée par HTTPS.

Les navigateurs modernes peuvent bloquer l’affichage d’une page ou afficher des messages d’avertissement si le contenu sécurisé est mélangé à du contenu non sécurisé.

Si le [!UICONTROL compositeur d’expérience visuelle] (compositeur d’expérience visuelle) de [!DNL Target] tente d’ouvrir une page contenant du contenu mixte, un message s’affiche indiquant comment désactiver le blocage dans votre navigateur afin que vous puissiez ouvrir un site HTTP ou un site qui comporte des appels mixtes (HTTPS et HTTP).

![avertissement de contenu mixte](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Auparavant, lorsque le contenu mixte n’était pas autorisé, vous pouviez toujours effectuer certaines actions de l’étape 1 du processus assisté en trois étapes lors de la création d’activités. [!DNL Target] bloque désormais les actions de l’étape 1. Lorsque ce message s’affiche, vous devez activer le contenu mixte avant de continuer à créer l’activité.

Les paramètres de sécurité du navigateur peuvent bloquer le chargement du contenu mixte ou du contenu non sécurisé (HTTP) sur une page sécurisée (HTTPS) ou une trame sécurisée (par exemple le compositeur d’expérience visuelle). Si vous ne souhaitez pas désactiver les paramètres de sécurité du navigateur, vous devez disposer d’un site web HTTPS.

Si votre site web s’exécute sur un domaine non sécurisé (HTTP), vous devez autoriser le compositeur d’expérience visuelle à charger du contenu mixte actif.

>[!NOTE]
>
>L’autorisation du contenu mixte affecte uniquement le compositeur d’expérience visuelle et non votre site Web actif.

Pour plus d’informations, voir [Mixed Content (Contenu mixte)](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) sur le site web *Mozilla Developer Network* (MDN).

## Activation du contenu mixte dans Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Si vous visitez un site via une connexion sécurisée, Chrome vérifie que le contenu de la page Web a été transmis en toute sécurité.

Voir [Cette page comporte du contenu non sécurisé](https://support.google.com/chrome/answer/1342714?hl=en) dans l’aide Google Chrome.

Si vous utilisez le compositeur d’expérience visuelle avec la dernière version de Chrome (version 79.0.3945.117 ou ultérieure), vous devez mettre à jour les paramètres de votre site. Les visiteurs de votre site n’ont pas besoin de suivre ces étapes.

1. Cliquez sur l’icône de verrouillage ou d’avertissement, puis sur **[!UICONTROL Paramètres du site]**.

   ![Paramètres du site](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Accédez à **[!UICONTROL Contenu non sécurisé]**, puis utilisez la liste déroulante pour remplacer &quot;Bloc (par défaut)&quot; par &quot;Autoriser&quot;.

   ![Contenu non sécurisé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Rechargez la page du compositeur d’expérience visuelle.

## Activation du contenu mixte dans Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

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

1. Cliquez sur l’icône de verrouillage ou d’avertissement, puis sur **[!UICONTROL Autorisations du site]**.

   ![Autorisations de site dans Microsoft Edge](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Accédez à **[!UICONTROL Contenu non sécurisé]**, puis utilisez la liste déroulante pour remplacer &quot;Bloc (par défaut)&quot; par &quot;Autoriser&quot;.

   ![Contenu non sécurisé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Rechargez la page du compositeur d’expérience visuelle.