---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Informations permettant d’utiliser l’extension d’assistance de navigateur du Compositeur d’Expérience Visuelle (VEC) d’Adobe Target pour charger de manière fiable des sites Web dans le VEC afin de créer rapidement des expériences d’auteur et d’assurance qualité.
title: Extension d’assistance du Compositeur d’Expérience Visuelle d’Adobe Target (VEC)
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 54%

---


# Extension d’assistance du Compositeur d’Expérience Visuelle

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper browser extension for Google Chrome lets you load websites reliably within the VEC to rapidly author and QA web experiences.

>[!NOTE]
>
>Le navigateur d’assistance du compositeur d’expérience visuelle est une extension Chrome. Cette extension n&#39;est pas nécessaire lors de l&#39;utilisation de Mozilla Firefox.

## Raisons pour lesquelles certains sites Web pourraient ne pas s’ouvrir de manière fiable dans le compositeur d’expérience visuelle

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* La bibliothèque at.js n’est pas encore instaurée sur le site Web.
* Le site d’assurance qualité et/ou d’étape du client n’est pas disponible pour le grand public (site interne).
* Vous utilisez Google Chrome 80+ avec des règles améliorées d’application des cookies de SameSite. Pour plus d’informations, voir [Quel est l’impact des politiques d’application des cookies récemment annoncées dans Google Chrome SameSite sur le compositeur d’expérience visuelle et la CEE](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

The VEC Helper browser extension for Chrome solves site-loading issues for which customers now rely on the [!DNL Target] [Enhanced Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md#eec) or third-party extensions, such as Requestly.

## Avantages de l’utilisation de l’extension d’assistance du compositeur d’expérience visuelle

* Tous les en-têtes qui démolissent un iframe, comme X-Frame-Options et Content-Security-Policy, sont implicitement supprimés du site web. Il n’est plus nécessaire de créer des règles complexes avec Requestly pour ce faire.
* Si une page Web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.

   Notez que lors de l’utilisation du compositeur d’expérience amélioré (EEC), l’extension n’injecte pas at.js, mais la fonctionnalité Cookie même site est toujours présente. Pour injecter at.js sur la page Web, désactivez la CEE.

* [Les fenêtres d’affichage](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) mobiles sont prises en charge même sans le compositeur [!UICONTROL d’expérience] amélioré (CEE).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Obtenir et installer l’extension d’assistance du compositeur d’expérience visuelle

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Cliquez sur **[!UICONTROL Ajouter à Chrome > Ajouter une extension]**.
1. Ouvrez le compositeur d’expérience visuelle dans [!DNL Target].
1. Pour utiliser l’extension, cliquez sur l’icône de l’extension du navigateur d’assistance de VEC (![icône de l’assistant de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md).
1. (Conditionnel) Faites glisser la bascule Bibliothèques **[!UICONTROL de Cibles d’]** [!DNL Target] injection vers la position &quot;Activé&quot; si la page Web ne contient pas encore la bibliothèque JavaScript at.js.

   L’illustration suivante présente l’assistant de VEC avec le paramètre d’[!UICONTROL injection des bibliothèques Target] activé :

   ![Assistant de VEC 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   L’illustration suivante présente l’assistant de VEC vous demandant si vous souhaitez qu’il injecte des bibliothèques [!DNL Target] dans la page pour activer la création :

   ![Assistant de VEC 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Conditionnel) Faites glisser la bascule **[!UICONTROL Cookies]** vers la position &quot;activé&quot; pour ajouter automatiquement le correctif du navigateur d’attributs SameSite=None, puis spécifiez le nom et le domaine du cookie.

   ![Basculement des cookies dans l’extension d’assistance du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Les liens suivants fournissent des informations supplémentaires :

   * Pour plus d’informations sur le correctif du navigateur d’attributs SameSite=None, voir &quot;Comment les politiques d’application des cookies récemment annoncées dans Google Chrome SameSite affectent-elles le compositeur d’expérience visuelle et la CEE ?&quot; in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * Le nom du cookie est &quot;mbox&quot; et le domaine du cookie est le deuxième niveau et le niveau supérieur des domaines à partir desquels vous servez la mbox. Il s’agit d’un cookie propriétaire, puisqu’il est diffusé à partir du domaine de votre société. Exemple: `mycompany.com`. Pour plus d’informations, voir Cookies [](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) Adobe Target dans le Guide *de l’interface* Experience Cloud.

## Remarques

* Votre implémentation doit utiliser la [!DNL Target]bibliothèque at.js. Vous ne pouvez pas utiliser une implémentation de mbox.js avec l’extension.
* L’indicateur d’[!UICONTROL Injection de bibliothèques Target] dans l’extension est désactivé par défaut. Vous pouvez activer cet balise si vous souhaitez utiliser le VEC sur un site qui n’a pas encore été mis en œuvre pour [!DNL Target].

   Notez que cette balise est un paramètre global. La balise est activée ou désactivée pour tous les sites Web ouverts dans le VEC. Par exemple, si vous définissez cet indicateur sur &quot;on&quot; et ouvrez un site Web qui est déjà implémenté avec at.js, vous recevrez un message vous informant qu’at.js est déjà chargé. Nous prévoyons que la plupart des clients auront déjà mis en oeuvre at.js sur leurs pages et utiliseront le paramètre par défaut &quot;off&quot;.

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans la même [!DNL Adobe Experience Cloud] organisation que celle dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site Web à l’aide du VEC et que le chargement échoue, un message s’affiche pour vous suggérer d’installer l’extension de navigateur VEC Helper.
   * Si at.js n’est pas encore mis en œuvre sur le site Web, un message s’affiche dans le VEC pour suggérer d’installer l’extension.
   * Si l’extension est activée et alimente le chargement, des messages s’affichent lorsque l’extension injecte la bibliothèque at.js (si nécessaire) ou aide à ouvrir le site Web de manière fiable dans le VEC.

