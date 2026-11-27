---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur;questions fréquentes
description: Découvrez pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC). L’extension de navigateur [!UICONTROL Visual Editing Helper] vous permet de charger des sites web de manière fiable dans le VEC.
title: Comment utiliser l’extension [!UICONTROL Visual Editing Helper] ?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
TQID: 'https://experienceleague.adobe.com/wUWUT-FvVIAo52PDaBMfmT7vxv8VOR71hSGhxFvylus'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
    internal-label: Web experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 5%
---
# Extension [!UICONTROL Visual Editing Helper] {#visual-editing-helper}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment l’extension de navigateur **[!UICONTROL Visual Editing Helper]** charge les sites web de manière fiable dans le **[!UICONTROL Compositeur d’expérience visuelle]** (VEC), et comment l’installer et l’utiliser.

>[!ENDSHADEBOX]

L’extension de navigateur [!DNL Adobe Experience Cloud] **[!UICONTROL Visual Editing Helper]** pour [!DNL Google Chrome] charge les sites web de manière fiable dans le [!DNL Adobe Target] **[!UICONTROL Compositeur d’expérience visuelle]** (VEC), ce qui accélère la création et la vérification d’expériences web.

>[!IMPORTANT]
>
>Cette extension remplace la précédente [extension de navigateur Assistant du compositeur d’expérience visuelle de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), comme décrit dans la remarque importante en haut de cet article. Le manifeste V3 introduit des améliorations de sécurité. Par conséquent, [!DNL Adobe] nécessite de télécharger cette nouvelle extension pour continuer à créer visuellement des sites web dans [!DNL Target].

## Pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le VEC

Un site web peut ne pas s’ouvrir de manière fiable dans le VEC pour les raisons suivantes :

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* Le site d’assurance qualité ou d’évaluation du client est interne et non disponible en dehors du réseau.

L’extension résout ces problèmes de chargement du site, pour lesquels les clients se fient autrement au [compositeur d’expérience amélioré](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou à des extensions tierces telles que Requestly.

## Avantages de l’extension

* **En-têtes qui démolissent un iframe supprimés :** l’extension supprime implicitement des en-têtes tels que `X-Frame-Options` et `Content-Security-Policy` du site web. Aucune règle complexes de type Requestly n’est donc nécessaire.
* **injection at.js :** lorsqu’une page web ne contient pas encore la bibliothèque at.js [!DNL Target], l’extension peut l’injecter. Vous pouvez ensuite créer des expériences pour le site web et créer et vérifier les activités à l’aide de liens de prévisualisation. Avec le [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) (EEC), l’extension n’injecte pas at.js, mais la fonctionnalité de cookie SameSite est conservée. Pour injecter at.js sur la page web, désactivez l’Enhanced Experience Composer.
* **Fenêtres d’affichage mobiles :** [les fenêtres d’affichage mobiles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) sont prises en charge même sans le **[!UICONTROL compositeur d’expérience amélioré]** (EEC).
* **Nouveaux [!DNL Target] clients :** l’extension permet d’expérimenter avec [!DNL Target] même si les développeurs informatiques n’ont pas encore implémenté [!DNL Target] sur le site web.
* **Partenaires :** partenaires qui traitent les sites web et [!DNL Target] comptes de plusieurs clients obtiennent un seul mécanisme pour prendre en charge le chargement du compositeur d’expérience visuelle, au lieu de plusieurs règles dans des outils tiers.

## Obtention et installation de l’extension

L’installation de l’extension dans [!DNL Chrome] permet de charger des sites web de manière fiable dans le VEC, y compris les sites web qui bloquent les iFrames ou pour lesquels at.js n’est pas encore implémenté.

1. Accédez à l’extension de navigateur [[!DNL Adobe Experience Cloud] **[!UICONTROL Visual Editing Helper &#x200B;]**&#x200B;dans la boutique en ligne Chrome](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Cliquez sur **[!UICONTROL Ajouter à Chrome]** > **[!UICONTROL Ajouter une extension]**.
1. Ouvrez le VEC dans [!DNL Target].
1. En mode VEC ou QA, cliquez sur l’icône d’extension de navigateur **[!UICONTROL Visual Editing Helper]** (![icône Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) dans la barre d’outils de [!DNL Chrome].

   L’extension est activée automatiquement lorsqu’un site web est ouvert dans le compositeur d’expérience visuelle [!DNL Target] pour alimenter la création. Il ne comporte aucun paramètre conditionnel et gère automatiquement tous les paramètres, y compris les paramètres des cookies SameSite. Pour plus d’informations sur le correctif de navigateur d’attribut `SameSite=None`, voir [Politiques de cookie SameSite de Google Chrome](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Remarques sur l’utilisation

* L’extension charge la dernière version d’at.js disponible dans l’interface utilisateur [!DNL Target] sous **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** et at.js télécharge les bibliothèques de création.
* Pour utiliser l’extension afin d’injecter at.js en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet doit être authentifié dans la même organisation [!DNL Adobe Experience Cloud] que celle dans laquelle l’activité a été créée.
* Le compositeur d’expérience visuelle affiche des messages qui suggèrent d’installer l’extension dans les cas suivants :

  * Le chargement d’un site web échoue dans le VEC.
  * at.js ou alloy.js n’est pas encore implémenté sur le site web.

* Si la nouvelle extension a été testée et que l’[ancienne extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) est réutilisée, mais que [!DNL Target] ne parvient pas à charger le site web, effacez toutes les données du navigateur et désactivez la nouvelle extension.

## Dernières modifications apportées à l’extension (17 janvier 2026)

L’extension ajoute une fonctionnalité expérimentale de nettoyage des cookies de démarrage au VEC Helper. La fonctionnalité nettoie les cookies non partitionnés une fois par onglet au début de la création, au lieu de continuellement, ce qui améliore les performances et la fiabilité. Il effectue le suivi de l’historique de chaque onglet pour éviter tout nettoyage redondant et efface cet historique lorsque l’onglet est fermé, de sorte que le nettoyage se comporte correctement lorsque l’onglet est rouvert. Les tests unitaires garantissent un comportement cohérent.

![Options de l’extension d’assistance du VEC, notamment les modes de traitement des cookies, l’option de journalisation avancée et les fonctionnalités expérimentales Retarder le chargement des pages web, le nettoyage des cookies et le nettoyage des cookies de démarrage](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper.png)

## Questions fréquentes

+++ L’extension agit-elle lorsqu’elle est utilisée en dehors de [!DNL Adobe Target] ou de [!UICONTROL Adobe Journey Optimizer] (AJO) ?

L’extension s’active uniquement lorsque le site web est chargé dans un iFrame dans [!DNL Adobe] produits ([!DNL Target], [!DNL AJO]). En dehors de ce flux, l’extension ne tente pas d’ajouter, de supprimer ou de modifier des en-têtes, ni d’injecter du code dans le site web.

+++

+++ Que fait l’extension lorsqu’elle est active dans le compositeur d’expérience visuelle (VEC) [!DNL Adobe Target] ?

Lorsqu’un site web est chargé dans un iFrame dans [!DNL Adobe] produits ([!DNL Target], [!DNL AJO]), l’extension injecte du code fourni avec l’extension dans le site web et télécharge les fichiers d’assistance à partir du réseau CDN [!DNL Adobe] pour activer la création visuelle.

+++
