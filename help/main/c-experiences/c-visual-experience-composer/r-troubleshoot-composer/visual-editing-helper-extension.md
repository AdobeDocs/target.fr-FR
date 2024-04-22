---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur;faq
description: Découvrez pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le [!UICONTROL Visual Experience Composer] (VEC). La variable [!UICONTROL Visual Editing Helper] l’extension de navigateur vous permet de charger des sites web de manière fiable dans le VEC.
title: Comment utiliser la variable [!UICONTROL Visual Editing Helper] Extension ?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 8edae6a197a3ac82b85fcce4d99c8b0d5f45c712
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 64%

---

# [!UICONTROL Visual Editing Helper] extension

La variable [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extension de navigateur pour [!DNL Google Chrome] permet de charger des sites web de manière fiable dans la variable [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) pour créer rapidement des expériences web et une assurance qualité.

>[!IMPORTANT]
>
>Cette nouvelle extension remplace la précédente [extension de navigateur Assistant du compositeur d’expérience visuelle de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md). Voir la remarque importante en haut de cet article. En raison des améliorations de sécurité apportées à Manifest v3, [!DNL Adobe] nécessite le téléchargement de cette nouvelle extension pour continuer à créer visuellement vos sites web dans [!DNL Target].

## Raisons pour lesquelles certains sites web peuvent ne pas s’ouvrir de manière fiable dans le VEC :

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* Le site d’assurance qualité et/ou d’étape du client n’est pas disponible pour le grand public (site interne).

La variable [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] l’extension de navigateur pour résout les problèmes de chargement du site pour lesquels les clients dépendent désormais de la variable [!DNL Target] [Compositeur d’expérience avancé](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou des extensions tierces, telles que Requestly.

## Avantages de l’utilisation de [!UICONTROL Visual Editing Helper] extension

* Tous les en-têtes qui démolissent un iframe, comme `X-Frame-Options` et `Content-Security-Policy`, sont implicitement supprimés du site web. Il n’est pas nécessaire de créer des règles complexes avec Requestly.
* Si une page Web ne contient pas encore la bibliothèque at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.

  Notez qu’en utilisant le [Compositeur d’expérience améliorée](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), l’extension n’injecte pas at.js, mais la fonctionnalité Cookies SameSite est toujours présente. Pour injecter at.js sur la page web, désactivez l’Enhanced Experience Composer.

* [Fenêtres d’affichage mobiles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) sont prises en charge même sans les [!UICONTROL Enhanced Experience Composer] (Compositeur d’expérience avancé).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Procurez-vous et installez le [!UICONTROL Visual Editing Helper] extension de navigateur

1. Accédez au [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extension de navigateur dans Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Cliquez sur **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. Ouvrez le VEC dans [!DNL Target].
1. Pour utiliser l’extension, cliquez sur le bouton [!UICONTROL Visual Editing Helper] icône d’extension de navigateur ( ![Icône de l’extension d’édition visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou AQ.

   La variable [!UICONTROL Visual Editing Helper] est automatiquement activé lorsqu’un site web est ouvert dans la variable [!UICONTROL Target] VEC pour alimenter la création. L’extension ne comporte aucun paramètre conditionnel. L’extension gère automatiquement tous les paramètres, y compris les paramètres des cookies SameSite.

   Pour plus d’informations sur le correctif de navigateur d’attribut `SameSite=None`, consultez la section « Comment les politiques d’application des cookies SameSite récemment annoncées par Google Chrome influencent-elles le VEC et l’EEC ? » dans [Résolution des problèmes liés au Compositeur d’expérience visuelle et au Compositeur d’expérience améliorée](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Remarques

* Pour [!DNL Target], l’extension charge la dernière version d’at.js disponible dans la fonction [!DNL Target] Interface utilisateur dans [!UICONTROL Administration] > [!UICONTROL Implementation] et at.js télécharge les bibliothèques de création.
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans la même organisation [!DNL Adobe Experience Cloud] que celle dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site web à l’aide du VEC dont le chargement échoue, un message s’affiche et vous suggère d’installer le [!UICONTROL Visual Editing Helper] extension de navigateur.
   * Si at.js n’est pas encore implémenté sur le site Web, un message s’affiche dans le VEC pour suggérer d’installer l’extension.
* Si vous essayez d’utiliser la nouvelle extension, revenez à l’[ancienne extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) et que [!DNL Target] ne parvient pas à charger votre site web, effacez toutes les données du navigateur et désactivez la nouvelle extension.

## Questions fréquentes

### L’extension, lorsqu’elle est active, fait-elle n’importe quoi lorsqu’elle est utilisée en dehors de [!DNL Adobe Target] ou [!UICONTROL Adobe Journey Optimizer] (AJO) ?

L’extension s’active uniquement lorsque le site web en question est chargé dans un iFrame dans les produits [!DNL Adobe] ([!DNL Target], [!DNL AJO]). En dehors de ce flux, l’extension ne tente pas d’ajouter, de supprimer ou de modifier des en-têtes et l’extension ne tente pas d’injecter du code dans le site web.

### Que fait l’extension lorsqu’elle est active dans le compositeur d’expérience visuelle (VEC) [!DNL Adobe Target] ?

Lorsqu’un site web est chargé dans un iFrame dans des produits [!DNL Adobe] ([!DNL Target], [!DNL AJO]), l’extension injecte du code (fourni avec l’extension) sur le site web et télécharge les fichiers d’assistance à partir du réseau CDN [!DNL Adobe] pour activer la création visuelle.
