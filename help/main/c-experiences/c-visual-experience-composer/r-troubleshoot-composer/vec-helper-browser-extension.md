---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur
description: Découvrez pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le [!UICONTROL Visual Experience Composer] (VEC). L’extension de navigateur Assistant du VEC vous permet de charger des sites web de manière fiable dans le VEC.
title: Comment utiliser l’extension d’assistance [!UICONTROL Visual Experience Composer] (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 6f4fd14a46f06c1366c02cfaf5a0cee5edbb00c4
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 55%

---

# Extension d’assistance [!UICONTROL Visual Experience Composer]

L’extension de navigateur d’assistance [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) pour [!DNL Google Chrome] vous permet de charger des sites web de manière fiable dans le VEC pour créer rapidement des expériences web et une assurance qualité.

Le navigateur Assistant du compositeur d’expérience visuelle est une extension [!DNL Chrome]. Cette extension n’est pas nécessaire lors de l’utilisation de [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>* L’extension d’assistance du compositeur d’expérience visuelle héritée [!DNL Target] décrite dans cet article a été créée à l’aide de Manifest V2. [!DNL Google] a annoncé qu’il n’autoriserait plus les extensions créées à l’aide de Manifest V2 à compter de juin 2024. Pour plus d’informations, reportez-vous à l’annonce de la chronologie de prise en charge de [Manifest V2](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} disponible [!DNL Google] sur le site *Chrome for Developers*.
>
>* À partir de juin 2024, [!DNL Google] commencera à désactiver les extensions créées à l’aide de Manifest V2, y compris l’extension documentée dans cette rubrique. [!DNL Adobe] recommande à la clientèle de passer à la version la plus récente de l’[extension Assistant d’édition visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) dès que possible.

## Raisons pour lesquelles certains sites web peuvent ne pas s’ouvrir de manière fiable dans le VEC :

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* La bibliothèque at.js n’est pas encore instaurée sur le site Web.
* Le site d’assurance qualité et/ou d’étape du client n’est pas disponible pour le grand public (site interne).
* Il existe actuellement certaines limitations lorsqu’on essaie d’utiliser le VEC (compositeur d’expérience visuelle) pour ouvrir un site web qui utilise [Service Workers](https://developer.mozilla.org/fr/docs/Web/API/Service_Worker_API){target=_blank} (SW).

Un SW est une technologie web qui peut être utilisée pour intercepter les requêtes du domaine sur lequel il est installé par une page web. Le SW survit à la visite de la page et s’active lors de visites ultérieures. Le SW décide quelles requêtes passent et lesquelles sont interceptées puis diffusées à partir d’un cache.

Le SW peut contrôler le caching. Il peut mettre en cache la page web elle-même, les ressources statiques telles que les requêtes JS, CSS, IMG, AJAX, leur contenu et leurs en-têtes de réponse, y compris les éléments que notre [extension d’assistance du VEC de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) tente de supprimer, comme X-Frame-Options : SAMEORIGIN, CSP (Content-Security-Policy) ou Set-Cookie.

Malheureusement, les API d’extension Chrome qui interceptent les requêtes web ne reçoivent pas les requêtes qui ont été interceptées et traitées par un SW. Par conséquent, l’extension ne peut pas corriger les en-têtes et les cookies si la requête de page web a été diffusée à partir d’un cache par un SW, car la page web ne se charge pas dans le VEC en raison des en-têtes X-Frame-Options ou CSP qui ont également été mis en cache.

Pour contourner ce problème, vous pouvez désactiver Service Workers dans l’onglet Chrome Developer Tools > Application, puis activer la case à cocher « Contourner pour le réseau » sous la section Service Workers.

* Vous utilisez Google Chrome 80+ avec des politiques améliorées d’application des cookies SameSite. Pour plus d’informations, consultez [Comment les politiques d’application des cookies SameSite récemment annoncées par Google Chrome affectent-elles le VEC et l’EEC &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite) ?

L’extension de navigateur VEC Helper pour Chrome résout les problèmes de chargement du site pour lesquels les clients se fient désormais au [!DNL Target] [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou à des extensions tierces, telles que Requestly.

## Avantages de l’utilisation de l’extension VEC Helper

* Tous les en-têtes qui démolissent un iframe, comme X-Frame-Options et Content-Security-Policy, sont implicitement supprimés du site web. Il n’est plus nécessaire de créer des règles complexes avec Requestly.
* Si une page Web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.

  Notez qu’en utilisant le Enhanced Experience Composer (EEC), l’extension n’injecte pas at.js, mais la fonctionnalité Cookies SameSite est toujours présente. Pour injecter at.js sur la page web, désactivez le Compositeur d’expérience visuelle.

* Les [fenêtres d’affichage mobiles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) sont prises en charge même sans le [!UICONTROL Enhanced Experience Composer] (EEC).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Obtenir et installer l’extension d’assistance du compositeur d’expérience visuelle

1. Accédez à l’extension de navigateur [Adobe Target VEC Helper dans la boutique en ligne Chrome](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca).
1. Cliquez sur **[!UICONTROL Add to Chrome > Add Extension]**.
1. Ouvrez le VEC dans [!DNL Target].
1. Pour utiliser l’extension, cliquez sur l’icône de l’extension du navigateur d’assistance de VEC (![icône de l’assistant de VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md).
1. (Conditionnel) Faites glisser le bouton **[!UICONTROL Inject Target Libraries]** vers la position « activé » si la page web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target].

   L’illustration suivante présente l’assistant VEC avec le paramètre [!UICONTROL Inject Target Libraries] activé :

   ![Assistant de VEC 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   L’illustration suivante présente l’assistant de VEC vous demandant si vous souhaitez qu’il injecte des bibliothèques [!DNL Target] dans la page pour activer la création :

   ![Assistant de VEC 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Conditionnel) Faites glisser le bouton (bascule) **[!UICONTROL Cookies]** sur la position « activé » pour ajouter automatiquement le correctif de navigateur d’attribut `SameSite=None`.

   ![Basculement des cookies dans l’extension d’assistance du VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Pour plus d’informations sur le correctif de navigateur d’attribut `SameSite=None`, consultez la section « Comment les politiques d’application des cookies SameSite récemment annoncées par Google Chrome influencent-elles le VEC et l’EEC ? » dans [Résolution des problèmes liés au Compositeur d’expérience visuelle et au Compositeur d’expérience améliorée](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Remarques

* L’indicateur [!UICONTROL Inject Target libraries] dans l’extension est DÉSACTIVÉ par défaut. Vous pouvez activer cet balise si vous souhaitez utiliser le VEC sur un site qui n’a pas encore été mis en œuvre pour [!DNL Target].

  Cet indicateur correspond à un paramètre global. La balise est activée ou désactivée pour tous les sites Web ouverts dans le VEC. Ainsi, par exemple, si vous définissez cet indicateur sur « activé » et que vous ouvrez un site web déjà implémenté avec at.js, vous recevez un message vous informant qu’at.js est déjà chargé. Adobe s’attend à ce que la plupart des clients aient déjà mis en œuvre at.js sur leurs pages et utilisent le paramètre par défaut « désactivé ».

* L’extension charge la dernière version d’at.js disponible à partir du [!DNL Target UI] dans [!UICONTROL Administration > Implementation].
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans la même [!DNL Adobe Experience Cloud] organisation que celle dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site Web à l’aide du VEC et que le chargement échoue, un message s’affiche pour vous suggérer d’installer l’extension de navigateur VEC Helper.
   * Si at.js n’est pas encore mis en œuvre sur le site Web, un message s’affiche dans le VEC pour suggérer d’installer l’extension.
   * Si l’extension est activée et alimente le chargement, des messages s’affichent lorsque l’extension injecte la bibliothèque at.js (si nécessaire) ou aide à ouvrir le site Web de manière fiable dans le VEC.
