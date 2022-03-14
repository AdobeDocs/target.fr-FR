---
keywords: contenu mixte;sécurisé;non sécurisé;chrome;dépannage;vec;compositeur d’expérience visuelle;non sécurisé;http;https;firefox;internet explorer
description: Certains navigateurs bloquent l’affichage d’une page si elle comporte du contenu sécurisé et non sécurisé. Découvrez comment activer le contenu mixte dans Chrome, Firefox et Edge.
title: Comment activer le contenu mixte dans mon navigateur ?
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 26%

---

# Activation du contenu mixte dans votre navigateur

Le contenu mixte se produit si la demande initiale est sécurisée via HTTPS, mais HTTPS. *et* Le contenu HTTP est chargé pour afficher la page web. Le contenu HTTPS est sécurisé. Le contenu HTTP n’est pas sécurisé.

Les navigateurs modernes peuvent bloquer l’affichage d’une page ou afficher des messages d’avertissement si le contenu sécurisé est mélangé à du contenu non sécurisé.

Un message d’avertissement s’affiche si la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC) dans [!DNL Target] tente d’ouvrir une page contenant du contenu mixte. Ce message vous explique comment désactiver le blocage dans votre navigateur. La désactivation du blocage permet d&#39;ouvrir un site HTTP ou un site comportant des appels mixtes (HTTPS et HTTP).

![Avertissement de contenu mixte](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Auparavant, lorsque le contenu mixte n’était pas autorisé, vous pouviez toujours effectuer certaines actions de l’étape 1 du processus assisté en trois étapes lors de la création d’activités. [!DNL Target] bloque désormais les actions de l’étape 1. Lorsque ce message s’affiche, vous devez activer le contenu mixte avant de poursuivre la création de l’activité.

Les paramètres de sécurité du navigateur peuvent bloquer le chargement du contenu mixte ou du contenu non sécurisé (HTTP) sur une page sécurisée (HTTPS) ou une trame sécurisée (par exemple le compositeur d’expérience visuelle). Si vous ne souhaitez pas désactiver les paramètres de sécurité de votre navigateur, vous devez disposer d’un site web HTTPS.

Si votre site web s’exécute sur un domaine non sécurisé (HTTP), vous devez autoriser le VEC à charger du contenu principal mixte.

>[!NOTE]
>
>L’autorisation du contenu mixte affecte uniquement le compositeur d’expérience visuelle et non votre site Web actif.

Pour plus d’informations, voir [Mixed Content (Contenu mixte)](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) sur le site web *Mozilla Developer Network* (MDN).

## Activation du contenu mixte dans Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Si vous visitez un site au moyen d’une connexion sécurisée, Chrome vérifie que le contenu de la page web a été transmis en toute sécurité.

Voir &quot;[Cette page comporte du contenu non sécurisé](https://support.google.com/chrome/answer/1342714?hl=en)&quot; dans l’aide de Google Chrome.

Si vous utilisez le VEC avec la dernière version de Chrome (version 79.0.3945.117 ou ultérieure), vous devez mettre à jour les paramètres de votre site. Les visiteurs de votre site n’ont pas besoin d’effectuer ces étapes.

1. Cliquez sur l’icône de verrouillage (mise en garde), puis sur **[!UICONTROL Paramètres du site]**.

   ![Paramètres du site](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Faites défiler jusqu’à **[!UICONTROL Contenu non sécurisé]**, puis utilisez la liste déroulante pour remplacer &quot;Bloc (par défaut)&quot; par &quot;Autoriser&quot;.

   ![Contenu non sécurisé](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Rechargez la page du VEC.

## Activation du contenu mixte dans Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Par défaut, Firefox bloque les pages qui contiennent du contenu sécurisé et non sécurisé. Pour utiliser [!DNL Target], il est conseillé de modifier définitivement ce paramètre. Les visiteurs de votre site n’ont pas besoin d’effectuer ces étapes.

1. Dans Firefox, saisissez `about:config` dans la barre d’adresse.
1. Acceptez le message d’avertissement affiché par Firefox.

   ![Avertissement Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Dans la barre de recherche, entrez `block_active`.

   ![Paramètre block_principal Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Double-cliquez sur ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   La valeur true se transforme en false. Lorsque la valeur devient false, l’opération est terminée. 

   ![Sécurité Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Redémarrez votre ordinateur après avoir modifié ce paramètre.

## Activation du contenu mixte dans Microsoft Edge

Si vous visitez un site au moyen d’une connexion sécurisée, Edge vérifie que le contenu de la page web a été transmis en toute sécurité.

Si vous utilisez le VEC avec la dernière version d’Edge, vous devez mettre à jour les paramètres de votre site. Les visiteurs de votre site n’ont pas besoin d’effectuer ces étapes.

1. Cliquez sur l’icône de verrouillage (mise en garde), puis sur **[!UICONTROL Autorisations du site]**.

   ![Autorisations de site dans Microsoft Edge](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Faites défiler jusqu’à **[!UICONTROL Contenu non sécurisé]**, puis utilisez la liste déroulante pour remplacer &quot;Bloc (par défaut)&quot; par &quot;Autoriser&quot;.

   ![Contenu non sécurisé](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Rechargez la page du VEC.
