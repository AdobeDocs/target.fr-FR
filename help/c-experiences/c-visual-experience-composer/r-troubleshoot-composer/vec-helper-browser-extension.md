---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur
description: Découvrez pourquoi certains sites web ne s’ouvrent pas de manière fiable dans le compositeur d’expérience visuelle (VEC). L’extension de navigateur VEC Helper vous permet de charger des sites web de manière fiable dans le compositeur d’expérience visuelle.
title: Comment utiliser l’extension d’assistance du compositeur d’expérience visuelle (VEC) ?
feature: 'Compositeur d’expérience visuelle (VEC) '
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 50%

---

# Extension d’assistance du Compositeur d’Expérience Visuelle

L’ [!DNL Adobe Target] [!UICONTROL extension d’assistance du compositeur d’expérience visuelle] (VEC) pour Google Chrome vous permet de charger des sites web de manière fiable dans le compositeur d’expérience visuelle afin de créer rapidement des expériences web et d’en contrôler la qualité.

>[!NOTE]
>
>Le navigateur d’assistance de VEC est une extension Chrome. Cette extension n’est pas nécessaire lors de l’utilisation de Mozilla Firefox.

## Raisons pour lesquelles certains sites web peuvent ne pas s’ouvrir de manière fiable dans le compositeur d’expérience visuelle

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* La bibliothèque at.js n’est pas encore instaurée sur le site Web.
* Le site d’assurance qualité et/ou d’étape du client n’est pas disponible pour le grand public (site interne).
* Vous utilisez Google Chrome 80+ avec des stratégies améliorées d’application des cookies SameSite. Pour plus d’informations, reportez-vous à la section [Comment les stratégies d’application des cookies SameSite de Google Chrome récemment annoncées affectent-elles le compositeur d’expérience visuelle et le compositeur d’expérience avancé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite) ?

L’extension de navigateur VEC Helper pour Chrome résout les problèmes de chargement de site pour lesquels les clients se fient désormais à [!DNL Target] [Compositeur d’expérience avancé](/help/administrating-target/visual-experience-composer-set-up.md#eec) ou à des extensions tierces, telles que Requestly.

## Avantages de l’extension d’assistance du compositeur d’expérience visuelle

* Tous les en-têtes qui démolissent un iframe, comme X-Frame-Options et Content-Security-Policy, sont implicitement supprimés du site web. Il n’est plus nécessaire de créer des règles complexes avec Requestly.
* Si une page Web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.

   Notez que l’utilisation du compositeur d’expérience avancé (EEC) ne permet pas d’injecter at.js, mais la fonctionnalité SameSite Cookie est toujours présente. Pour injecter at.js sur la page web, désactivez le compositeur d’expérience avancé.

* [Les ](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) fenêtres d’affichage mobiles sont prises en charge même sans le compositeur d’expérience  [!UICONTROL avancé]  (EEC).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Obtenir et installer l’extension d’assistance du compositeur d’expérience visuelle

1. Accédez à l’[extension de navigateur Adobe Target VEC Helper dans Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Cliquez sur **[!UICONTROL Ajouter à Chrome > Ajouter une extension]**.
1. Ouvrez le VEC dans [!DNL Target].
1. Pour utiliser l’extension, cliquez sur l’icône de l’extension du navigateur d’assistance de VEC (![icône de l’assistant de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md).
1. (Conditionnel) Faites glisser le bouton d’activation/désactivation **[!UICONTROL Inject Target Libraries]** vers la position &quot;on&quot; si la page web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target].

   L’illustration suivante présente l’assistant de VEC avec le paramètre d’[!UICONTROL injection des bibliothèques Target] activé :

   ![Assistant de VEC 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   L’illustration suivante présente l’assistant de VEC vous demandant si vous souhaitez qu’il injecte des bibliothèques [!DNL Target] dans la page pour activer la création :

   ![Assistant de VEC 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Conditionnel) Faites glisser le bouton **[!UICONTROL Cookies]** vers la position &quot;activée&quot; pour ajouter automatiquement le correctif du navigateur d’attributs SameSite=None , puis spécifiez le nom et le domaine du cookie.

   ![Bascule des cookies dans l’extension d’assistance de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Les liens suivants fournissent des informations supplémentaires :

   * Pour plus d’informations sur le correctif du navigateur d’attributs SameSite=None, voir &quot;Comment les politiques d’application des cookies SameSite de Google Chrome récemment annoncées affectent-elles le compositeur d’expérience visuelle et le compositeur d’expérience avancé ?&quot; dans [Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * Le nom du cookie est &quot;mbox&quot; et le domaine du cookie correspond aux deuxième et dernier niveaux des domaines à partir desquels vous diffusez la mbox. Il s’agit d’un cookie propriétaire, puisqu’il est diffusé à partir du domaine de votre société. Exemple: `mycompany.com`. Pour plus d’informations, voir [Cookies Adobe Target](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html?lang=fr) dans le *Guide de l’utilisateur de l’interface Experience Cloud*.

## Remarques

* L’indicateur d’[!UICONTROL Injection de bibliothèques Target] dans l’extension est désactivé par défaut. Vous pouvez activer cet balise si vous souhaitez utiliser le VEC sur un site qui n’a pas encore été mis en œuvre pour [!DNL Target].

   Cet indicateur est un paramètre global. La balise est activée ou désactivée pour tous les sites Web ouverts dans le VEC. Ainsi, par exemple, si vous activez cet indicateur et ouvrez un site web déjà mis en oeuvre avec at.js, vous recevez un message vous informant que at.js est déjà chargé. Adobe prévoit que la plupart des clients ont déjà mis en oeuvre at.js sur leurs pages et utilisent le paramètre par défaut &quot;désactivé&quot;.

* L’extension charge la dernière version d’at.js disponible à partir de [!DNL Target UI] dans [!UICONTROL Administration > Implémentation].
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans la même [!DNL Adobe Experience Cloud] organisation que celle dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site Web à l’aide du VEC et que le chargement échoue, un message s’affiche pour vous suggérer d’installer l’extension de navigateur VEC Helper.
   * Si at.js n’est pas encore mis en œuvre sur le site Web, un message s’affiche dans le VEC pour suggérer d’installer l’extension.
   * Si l’extension est activée et alimente le chargement, des messages s’affichent lorsque l’extension injecte la bibliothèque at.js (si nécessaire) ou aide à ouvrir le site Web de manière fiable dans le VEC.
