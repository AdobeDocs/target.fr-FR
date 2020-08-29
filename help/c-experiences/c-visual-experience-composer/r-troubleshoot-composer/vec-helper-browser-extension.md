---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Informations permettant d’utiliser l’extension d’assistance de navigateur du Compositeur d’Expérience Visuelle (VEC) d’Adobe Target pour charger de manière fiable des sites Web dans le VEC afin de créer rapidement des expériences d’auteur et d’assurance qualité.
title: Extension d’assistance du Compositeur d’Expérience Visuelle d’Adobe Target (VEC)
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: c77561696c35a5890c10591fc1014d812485f0f8
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 85%

---


# Extension d’assistance du Compositeur d’Expérience Visuelle

L’extension d’assistance du Compositeur d’Expérience Visuelle (VEC) [!DNL Adobe Target] pour Google Chrome vous permet de charger des sites Web de manière fiable dans la CVE pour créer rapidement des expériences Web et une assurance qualité.

Raisons pour lesquelles certains sites web peuvent ne pas s’ouvrir de manière fiable dans le VEC :

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* La bibliothèque at.js n’est pas encore instaurée sur le site Web.
* Le site d’assurance qualité et/ou d’étape du client n’est pas disponible pour le grand public (site interne).
* Vous utilisez Google Chrome 80+ avec des règles améliorées d’application des cookies de SameSite. Pour plus d’informations, voir [Quel est l’impact des politiques d’application des cookies récemment annoncées dans Google Chrome SameSite sur le compositeur d’expérience visuelle et la CEE](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

The VEC Helper browser extension for Chrome solves site-loading issues for which customers now rely on the [!DNL Target] [!UICONTROL Enhanced Experience Composer] or third-party extensions, such as Requestly.

Avantages de l’extension d’assistance du compositeur d’expérience visuelle :

* Tous les en-têtes qui démolissent un iframe, comme X-Frame-Options et Content-Security-Policy, sont implicitement supprimés du site web. Il n’est plus nécessaire de créer des règles complexes avec Requestly pour ce faire.
* Si une page Web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.
* Les fenêtres d’affichage mobiles sont prises en charge même sans [!UICONTROL le compositeur d’expérience amélioré] (EEC).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Obtenir et installer l’extension d’assistance du compositeur d’expérience visuelle

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Cliquez sur [!UICONTROL Ajouter à Chrome > Ajouter une extension].
1. Pour utiliser l’extension, cliquez sur l’icône de l’extension du navigateur d’assistance de VEC (![icône de l’assistant de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md).

L’illustration suivante présente l’assistant de VEC avec le paramètre d’[!UICONTROL injection des bibliothèques Target] activé :

![Assistant de VEC 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

L’illustration suivante présente l’assistant de VEC vous demandant si vous souhaitez qu’il injecte des bibliothèques [!DNL Target] dans la page pour activer la création :

![Assistant de VEC 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

## Remarques

* Votre implémentation doit utiliser la [!DNL Target]bibliothèque at.js. Vous ne pouvez pas utiliser une implémentation de mbox.js avec l’extension.
* L’indicateur d’[!UICONTROL Injection de bibliothèques Target] dans l’extension est désactivé par défaut. Vous pouvez activer cet balise si vous souhaitez utiliser le VEC sur un site qui n’a pas encore été mis en œuvre pour [!DNL Target].

   Notez que cette balise est un paramètre global. La balise est activée ou désactivée pour tous les sites Web ouverts dans le VEC. Ainsi, par exemple, si vous activez cet indicateur et ouvrez un site Web où at.js a déjà été instauré, un message vous informe que at.js est déjà chargé. Nous prévoyons que la plupart des clients auront déjà implémenté at.js sur leurs pages et utiliseront le paramètre par défaut OFF.

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans la même [!DNL Adobe Experience Cloud] organisation que celle dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site Web à l’aide du VEC et que le chargement échoue, un message s’affiche pour vous suggérer d’installer l’extension de navigateur VEC Helper.
   * Si at.js n’est pas encore mis en œuvre sur le site Web, un message s’affiche dans le VEC pour suggérer d’installer l’extension.
   * Si l’extension est activée et alimente le chargement, des messages s’affichent lorsque l’extension injecte la bibliothèque at.js (si nécessaire) ou aide à ouvrir le site Web de manière fiable dans le VEC.