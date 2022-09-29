---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur
description: Découvrez pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC). Le [!UICONTROL Assistant d’édition visuelle] l’extension de navigateur vous permet de charger des sites web de manière fiable dans VEC.
title: Comment utiliser la variable [!UICONTROL Assistant d’édition visuelle] Extension ?
feature: Visual Experience Composer (VEC)
source-git-commit: 0c6d2df47a9115bcbd3c0d8a5ea7d401df29d6c8
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 25%

---

# [!UICONTROL Assistant d’édition visuelle] extension

Le [!DNL Adobe Experience Cloud] [!UICONTROL Assistant d’édition visuelle] l’extension de navigateur pour Google Chrome vous permet de charger des sites web de manière fiable dans [!UICONTROL Adobe Target] [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour créer rapidement des expériences web et une assurance qualité.

>[!IMPORTANT]
>
>Cette nouvelle extension remplace la précédente [Extension de navigateur Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## Raisons pour lesquelles certains sites web peuvent ne pas s’ouvrir de manière fiable dans le compositeur d’expérience visuelle

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* Le site d’assurance qualité ou d’évaluation du client n’est pas disponible pour le monde extérieur (le site est interne).

Le [!DNL Adobe Experience Cloud] [!UICONTROL Assistant d’édition visuelle] l’extension de navigateur pour Chrome résout les problèmes de chargement de site pour lesquels les clients dépendent désormais de la variable [!DNL Target] [Compositeur d’expérience avancé](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou des extensions tierces, telles que Requestly.

## Avantages de l’utilisation de la variable [!UICONTROL Assistant d’édition visuelle] extension

* Tous les en-têtes d’iframe, tels que `X-Frame-Options` et `Content-Security-Policy`, sont implicitement supprimés du site web. Il n’est pas nécessaire de créer des règles complexes avec Requestly.
* Si une page Web ne contient pas encore la bibliothèque at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.

Notez que l’utilisation de la variable [Compositeur d’expérience avancé](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), l’extension n’injecte pas at.js, mais la fonctionnalité Cookie samesite est toujours présente. Pour injecter at.js sur la page web, désactivez le compositeur d’expérience avancé.

* [Fenêtres d’affichage mobiles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) sont prises en charge même sans les [!UICONTROL Compositeur d’expérience avancé] (Compositeur d’expérience avancé).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Procurez-vous et installez le [!UICONTROL Assistant d’édition visuelle] extension de navigateur

1. Accédez au [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extension de navigateur dans Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Cliquez sur **[!UICONTROL Ajouter à Chrome]** > **[!UICONTROL Ajouter une extension]**.
1. Ouvrez le VEC dans [!DNL Target].
1. Pour utiliser l’extension, cliquez sur le bouton [!UICONTROL Assistant d’édition visuelle] icône d’extension de navigateur ( ![Icône de l’extension d’édition visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou AQ.

   Le [!UICONTROL Assistant d’édition visuelle] est automatiquement activé lorsqu’un site web est ouvert dans la variable [!UICONTROL Cible] VEC pour alimenter la création. L’extension ne comporte aucun paramètre conditionnel. L’extension gère automatiquement tous les paramètres, y compris les paramètres des cookies SameSite.

   Pour plus d’informations sur la variable `SameSite=None` correction du navigateur d’attributs, voir &quot;Comment les stratégies d’application des cookies SameSite de Google Chrome récemment annoncées affectent-elles le compositeur d’expérience visuelle et le compositeur d’expérience avancé ?&quot; dans [Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Remarques

* Pour [!DNL Target], l’extension charge la dernière version d’at.js disponible dans la fonction [!DNL Target] Interface utilisateur dans [!UICONTROL Administration] > [!UICONTROL Implémentation] et at.js télécharge les bibliothèques de création.
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans le même [!DNL Adobe Experience Cloud] organisation dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site web à l’aide du VEC dont le chargement échoue, un message s’affiche et vous suggère d’installer le [!UICONTROL Assistant d’édition visuelle] extension de navigateur.
   * Si at.js ou alloy.js n’est pas encore mis en oeuvre sur le site web, un message s’affiche dans le VEC suggérant que vous installez l’extension.



