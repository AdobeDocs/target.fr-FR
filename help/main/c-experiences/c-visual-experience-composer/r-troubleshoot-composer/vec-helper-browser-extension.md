---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur
description: Découvrez pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC). L’extension de navigateur Assistant du VEC vous permet de charger des sites web de manière fiable dans le VEC.
title: Comment utiliser l’extension d’assistance du compositeur d’expérience visuelle [!UICONTROL ] (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
TQID: 'https://experienceleague.adobe.com/lqZGGWG1NVtKDzNGPq5k2bDPzxDfNWqPtJ-bYfLCr3Q'
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
source-wordcount: '1119'
ht-degree: 5%
---
# Extension d’assistance du compositeur d’expérience visuelle  {#vec-helper-extension}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment l’extension de navigateur Assistant du compositeur d’expérience visuelle héritée charge les sites web dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC), et comment l’installer et l’utiliser.

>[!ENDSHADEBOX]

L’extension de navigateur d’assistance du compositeur d’expérience visuelle ]**(VEC) [!DNL Adobe Target]**[!UICONTROL  pour [!DNL Google Chrome] charge les sites web de manière fiable dans le VEC, ce qui accélère la création et la vérification d’expériences web. L&#39;extension n&#39;est pas nécessaire dans [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>* L’extension d’assistance du compositeur d’expérience visuelle héritée [!DNL Target] documentée dans cet article a été créée avec Manifest V2. [!DNL Google] a annoncé qu’il arrêterait d’autoriser les extensions créées avec Manifest V2 à partir de juin 2024. Pour plus d’informations, consultez l’annonce de la chronologie de prise en charge de [Manifest V2](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} de [!DNL Google] sur le site *Chrome pour les développeurs*.
>
>* À compter de juin 2024, [!DNL Google] désactive les extensions créées avec Manifest V2, y compris l’extension documentée dans cet article. [!DNL Adobe] recommande de passer à la nouvelle extension [Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) dès que possible.

## Pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le VEC

Un site web peut ne pas s’ouvrir de manière fiable dans le VEC pour les raisons suivantes :

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* La bibliothèque at.js n’est pas encore instaurée sur le site Web.
* Le site d’assurance qualité ou d’évaluation du client est interne et non disponible en dehors du réseau.
* Le site web utilise [Service Workers](https://developer.mozilla.org/fr/docs/Web/API/Service_Worker_API){target=_blank} (SW), que le compositeur d’expérience visuelle prend actuellement en charge uniquement avec des limitations. Voir la section suivante.
* Le site web est ouvert dans [!DNL Chrome] 80 ou une version ultérieure, ce qui applique les politiques de cookies SameSite. Pour plus d’informations, voir [Politiques de cookies SameSite de Google Chrome](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

L’extension de navigateur Assistant du compositeur d’expérience visuelle pour [!DNL Chrome] résout les problèmes de chargement du site pour lesquels les clients se fient autrement au [!DNL Target] [compositeur d’expérience amélioré](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou à des extensions tierces telles que Requestly.

### Ouvrier dans le domaine des services

Un service worker (SW) est une technologie web qu’une page web installe pour intercepter les requêtes concernant son domaine. Le SW survit à la visite de la page et s’active lors de visites ultérieures. Il décide quelles requêtes passent et lesquelles sont interceptées et diffusées à partir d’un cache.

Un SW peut mettre en cache la page web elle-même, les ressources statiques telles que les requêtes JS, CSS, IMG et AJAX, leur contenu et leurs en-têtes de réponse. Ces en-têtes incluent ceux que l’extension d’assistance du VEC de Target [ tente de supprimer ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), tels que `X-Frame-Options: SAMEORIGIN`, CSP (`Content-Security-Policy`) et `Set-Cookie`.

Les API d&#39;extension [!DNL Chrome] qui interceptent les requêtes web ne reçoivent pas les requêtes qu&#39;un SW a interceptées et traitées. Lorsqu’un SW diffuse la requête de page web à partir d’un cache, l’extension ne peut donc pas corriger les en-têtes et les cookies, et la page ne se charge pas dans le VEC en raison des en-têtes `X-Frame-Options` ou CSP mis en cache.

Pour contourner ce problème, désactivez Service Workers dans l’onglet [!DNL Chrome] Outils de développement > **Application**, puis activez la case à cocher « Contourner pour le réseau » dans la section Service Workers.

## Avantages de l’extension VEC Helper

* **En-têtes qui démolissent un iframe supprimés :** l’extension supprime implicitement des en-têtes tels que `X-Frame-Options` et `Content-Security-Policy` du site web. Aucune règle complexes de type Requestly n’est donc nécessaire.
* **injection d’at.js :** lorsqu’une page web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], l’extension peut l’injecter. Vous pouvez ensuite créer des expériences pour le site web et créer et vérifier les activités à l’aide de liens de prévisualisation. Avec le Enhanced Experience Composer (EEC), l’extension n’injecte pas at.js, mais la fonctionnalité de cookie SameSite est conservée. Pour injecter at.js sur la page web, désactivez l’Enhanced Experience Composer.
* **Fenêtres d’affichage mobiles :** [les fenêtres d’affichage mobiles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) sont prises en charge même sans le **[!UICONTROL compositeur d’expérience amélioré]** (EEC).
* **Nouveaux [!DNL Target] clients :** l’extension permet d’expérimenter avec [!DNL Target] même si les développeurs informatiques n’ont pas encore implémenté [!DNL Target] sur le site web.
* **Partenaires :** partenaires qui traitent les sites web et [!DNL Target] comptes de plusieurs clients obtiennent un seul mécanisme pour prendre en charge le chargement du compositeur d’expérience visuelle, au lieu de plusieurs règles dans des outils tiers.

## Obtenir et installer l’extension d’assistance du compositeur d’expérience visuelle

L’installation de l’extension dans [!DNL Chrome] permet de charger des sites web de manière fiable dans le VEC, y compris les sites web qui bloquent les iFrames ou pour lesquels at.js n’est pas encore implémenté.

1. Accédez à l’extension de navigateur [Adobe Target VEC Helper dans le magasin web Chrome](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca).
1. Cliquez sur **[!UICONTROL Ajouter à Chrome]** > **[!UICONTROL Ajouter une extension]**.
1. Ouvrez le VEC dans [!DNL Target].
1. En mode VEC ou [QA](/help/main/c-activities/c-activity-qa/activity-qa.md), cliquez sur l’icône de l’extension de navigateur Assistant du VEC ( ![icône Assistant du VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) dans la barre d’outils de [!DNL Chrome].
1. (Conditionnel) Si la page web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], activez le bouton (bascule) Insérer des **[!UICONTROL bibliothèques cible]** .

   L’illustration suivante présente l’assistant VEC avec le paramètre **[!UICONTROL Injecter des bibliothèques cibles]** activé :

   ![Panneau d’extension d’assistance du VEC avec le bouton (bascule) Insérer des bibliothèques cible activé et le bouton (bascule) Cookies désactivé, montrant que le paramètre Cookies définit les indicateurs SameSite=None et Secure sur tous les cookies pour les requêtes au sein du VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   Le compositeur d’expérience visuelle demande ensuite s’il doit injecter les bibliothèques [!DNL Target] dans la page pour activer la création :

   ![Invite d’injection des bibliothèques Target indiquant que l’extension d’assistance du VEC de Target souhaite injecter des bibliothèques Target dans la page pour activer la création, avec les boutons Annuler et Autoriser](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Conditionnel) Activez le bouton (bascule) **[!UICONTROL Cookies]** pour ajouter automatiquement le correctif de navigateur d’attribut `SameSite=None`.

   ![Panneau d’extension d’assistance du VEC avec le bouton Cookies activé et mis en surbrillance, dans le compositeur d’expérience visuelle affichant un exemple de page](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Pour plus d’informations sur le correctif de navigateur d’attribut `SameSite=None`, voir [Politiques de cookie SameSite de Google Chrome](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Remarques sur l’utilisation

* L’indicateur **[!UICONTROL Injecter des bibliothèques cibles]** dans l’extension est désactivé par défaut. Activez-le pour utiliser le compositeur d’expérience visuelle sur un site sur lequel [!DNL Target] n’est pas encore implémenté.

  L’indicateur est un paramètre global ; il est donc activé ou désactivé pour tous les sites Web ouverts dans le compositeur d’expérience visuelle. Par exemple, lorsque l’indicateur est activé, l’ouverture d’un site web sur lequel at.js est déjà implémenté affiche un message indiquant qu’at.js est déjà chargé. [!DNL Adobe] s’attend à ce que la plupart des clients disposent déjà d’at.js implémenté sur leurs pages et utilisent le paramètre par défaut désactivé.

* L’extension charge la dernière version d’at.js disponible dans l’interface utilisateur [!DNL Target] sous **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.
* Pour utiliser l’extension afin d’injecter at.js en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet doit être authentifié dans la même organisation [!DNL Adobe Experience Cloud] que celle dans laquelle l’activité a été créée.
* Le compositeur d’expérience visuelle affiche des messages dans les cas suivants :

  * Le chargement d’un site web échoue dans le VEC. Le message suggère d’installer l’extension de navigateur Assistant VEC.
  * at.js n’est pas encore implémenté sur le site web. Le message suggère d’installer l’extension.
  * L’extension est activée et alimente le chargement. Les messages s’affichent lorsque l’extension injecte la bibliothèque at.js, si nécessaire, ou permet d’ouvrir le site web de manière fiable dans le VEC.
