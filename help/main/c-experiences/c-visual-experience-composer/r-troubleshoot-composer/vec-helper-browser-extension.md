---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur
description: Découvrez pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le [!UICONTROL Visual Experience Composer] (VEC). L’extension de navigateur VEC Helper vous permet de charger des sites web de manière fiable dans le compositeur d’expérience visuelle.
title: Comment utiliser l’extension d’assistance [!UICONTROL Visual Experience Composer] (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 6c702ab7d787c266d90162ef894f780770a69e37
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 53%

---

# [!UICONTROL Visual Experience Composer] Helper extension

L’extension d’assistance de navigateur [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) pour [!DNL Google Chrome] vous permet de charger des sites web de manière fiable dans le VEC afin de créer rapidement des expériences web et d’en contrôler la qualité.

Le navigateur d’assistance de VEC est une extension [!DNL Chrome]. Cette extension n&#39;est pas nécessaire lors de l&#39;utilisation de [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>* L’ancienne extension d’assistance VEC [!DNL Target] documentée dans cet article a été créée à l’aide du manifeste V2. [!DNL Google] a annoncé qu’il n’autoriserait plus les extensions créées à l’aide de Manifest V2 à compter de juin 2024. Pour plus d’informations, voir l’ [ annonce de la chronologie de la prise en charge de Manifest V2](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} à partir de [!DNL Google] sur le site *Chrome for Developers*.
>
>* À compter de juin 2024, [!DNL Google] commencera à désactiver les extensions créées à l’aide du manifeste V2, y compris l’extension documentée dans cette rubrique. [!DNL Adobe] recommande à la clientèle de passer à la version la plus récente de l’[extension Assistant d’édition visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) dès que possible.
>
>* Les clients qui utilisent des magasins web Chrome privés doivent continuer à utiliser cette version de l’extension jusqu’à ce que la prise en charge de ce cas d’utilisation soit implémentée dans la [nouvelle extension [!UICONTROL Visual Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) d’ici la fin janvier 2025.

## Raisons pour lesquelles certains sites web peuvent ne pas s’ouvrir de manière fiable dans le VEC :

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* La bibliothèque at.js n’est pas encore instaurée sur le site Web.
* Le site d’assurance qualité et/ou d’étape du client n’est pas disponible pour le grand public (site interne).
* Il existe actuellement certaines limites lors de la tentative d’utilisation du compositeur d’expérience visuelle pour ouvrir un site web qui utilise [Service Workers](https://developer.mozilla.org/fr/docs/Web/API/Service_Worker_API){target=_blank} (SW).

Un SW est une technologie web qui peut être utilisée pour intercepter les requêtes du domaine sur lequel il est installé par une page web. Le SW survit à la visite de la page et s’active lors de visites ultérieures. Le SW décide quelles requêtes passent et lesquelles sont interceptées puis diffusées à partir d’un cache.

Le SW peut contrôler le caching. Il peut mettre en cache la page web elle-même, les ressources statiques telles que les requêtes JS, CSS, IMG, AJAX, leur contenu et leurs en-têtes de réponse, y compris les éléments que notre [extension d’assistance du VEC de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) tente de supprimer, comme X-Frame-Options : SAMEORIGIN, CSP (Content-Security-Policy) ou Set-Cookie.

Malheureusement, les API de l’extension Chrome qui interceptent les requêtes web ne reçoivent pas les requêtes qui ont été interceptées et gérées par un serveur de logiciels. Par conséquent, l’extension ne peut pas corriger les en-têtes et les cookies si la demande de page web a été diffusée à partir d’un cache par un serveur d’applications web (SW), car la page web ne se charge pas dans le VEC en raison des en-têtes X-Frame-Options ou CSP qui ont également été mis en cache.

Pour pallier ce problème, vous pouvez désactiver Service Workers dans l’onglet Outils de développement Chrome > Application , puis activer la case à cocher &quot;Contournement pour le réseau&quot; sous la section Service Workers.

* Vous utilisez Google Chrome 80+ avec des stratégies améliorées d’application des cookies SameSite. Pour plus d’informations, voir [Quel est l’impact des stratégies d’application des cookies SameSite de Google Chrome récemment annoncées sur le compositeur d’expérience visuelle et le compositeur d’expérience avancé ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite) ?

L’extension de navigateur VEC Helper pour Chrome résout les problèmes de chargement de site pour lesquels les clients se fient désormais au [!DNL Target] [Compositeur d’expérience avancé](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou à des extensions tierces, telles que Requestly.

## Avantages de l’extension d’assistance du compositeur d’expérience visuelle

* Tous les en-têtes qui démolissent un iframe, comme X-Frame-Options et Content-Security-Policy, sont implicitement supprimés du site web. Il n’est plus nécessaire de créer des règles complexes avec Requestly.
* Si une page Web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.

  Notez que l’utilisation du compositeur d’expérience avancé (EEC) ne permet pas d’injecter at.js, mais la fonctionnalité SameSite Cookie est toujours présente. Pour injecter at.js sur la page web, désactivez le Compositeur d’expérience visuelle.

* Les [fenêtres d’affichage mobiles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) sont prises en charge même sans le [!UICONTROL Enhanced Experience Composer] (EEC).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Obtenir et installer l’extension d’assistance du compositeur d’expérience visuelle

1. Accédez à l’extension de navigateur [Adobe Target VEC Helper dans le magasin Web Chrome](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Cliquez sur **[!UICONTROL Add to Chrome > Add Extension]**.
1. Ouvrez le VEC dans [!DNL Target].
1. Pour utiliser l’extension, cliquez sur l’icône de l’extension du navigateur d’assistance de VEC (![icône de l’assistant de VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md).
1. (Conditionnel) Faites glisser la bascule **[!UICONTROL Inject Target Libraries]** vers la position &quot;activée&quot; si la page web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target].

   L’illustration suivante présente l’assistant de VEC avec le paramètre [!UICONTROL Inject Target Libraries] activé :

   ![Assistant de VEC 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   L’illustration suivante présente l’assistant de VEC vous demandant si vous souhaitez qu’il injecte des bibliothèques [!DNL Target] dans la page pour activer la création :

   ![Assistant de VEC 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Conditionnel) Faites glisser la bascule **[!UICONTROL Cookies]** vers la position &quot;activée&quot; pour ajouter automatiquement le correctif du navigateur d’attributs `SameSite=None`.

   ![Bascule des cookies dans l’extension d’assistance de VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Pour plus d’informations sur le correctif de navigateur d’attribut `SameSite=None`, consultez la section « Comment les politiques d’application des cookies SameSite récemment annoncées par Google Chrome influencent-elles le VEC et l’EEC ? » dans [Résolution des problèmes liés au Compositeur d’expérience visuelle et au Compositeur d’expérience améliorée](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Remarques

* L’indicateur [!UICONTROL Inject Target libraries] de l’extension est désactivé par défaut. Vous pouvez activer cet balise si vous souhaitez utiliser le VEC sur un site qui n’a pas encore été mis en œuvre pour [!DNL Target].

  Cet indicateur est un paramètre global. La balise est activée ou désactivée pour tous les sites Web ouverts dans le VEC. Ainsi, par exemple, si vous activez cet indicateur et ouvrez un site web déjà mis en oeuvre avec at.js, vous recevez un message vous informant que at.js est déjà chargé. Adobe prévoit que la plupart des clients ont déjà mis en oeuvre at.js sur leurs pages et utilisent le paramètre par défaut &quot;désactivé&quot;.

* L’extension charge la dernière version d’at.js disponible à partir de [!DNL Target UI] dans [!UICONTROL Administration > Implementation].
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans la même [!DNL Adobe Experience Cloud] organisation que celle dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site Web à l’aide du VEC et que le chargement échoue, un message s’affiche pour vous suggérer d’installer l’extension de navigateur VEC Helper.
   * Si at.js n’est pas encore mis en œuvre sur le site Web, un message s’affiche dans le VEC pour suggérer d’installer l’extension.
   * Si l’extension est activée et alimente le chargement, des messages s’affichent lorsque l’extension injecte la bibliothèque at.js (si nécessaire) ou aide à ouvrir le site Web de manière fiable dans le VEC.
