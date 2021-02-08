---
keywords: vec;compositeur d’expérience visuelle;vec;iframe;extension;navigateur
description: Découvrez pourquoi certains sites Web ne s’ouvrent pas de manière fiable dans le compositeur d’expérience visuelle. L’extension de navigateur de l’assistance du compositeur d’expérience visuelle vous permet de charger des sites Web de manière fiable au sein du compositeur d’expérience visuelle.
title: Comment utiliser l’extension d’assistance du compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 50%

---


# Extension d’assistance du Compositeur d’Expérience Visuelle

L’extension de navigateur d’assistance [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) pour Google Chrome vous permet de charger des sites Web de manière fiable au sein du compositeur d’expérience visuelle pour créer rapidement des expériences Web et effectuer un contrôle qualité.

>[!NOTE]
>
>Le navigateur d’assistance du compositeur d’expérience visuelle est une extension Chrome. Cette extension n&#39;est pas nécessaire lors de l&#39;utilisation de Mozilla Firefox.

## Raisons pour lesquelles certains sites Web pourraient ne pas s’ouvrir de manière fiable dans le compositeur d’expérience visuelle

* Le site Web possède des politiques strictes en matière de sécurité.
* Le site Web se trouve dans un iframe.
* La bibliothèque at.js n’est pas encore instaurée sur le site Web.
* Le site d’assurance qualité et/ou d’étape du client n’est pas disponible pour le grand public (site interne).
* Vous utilisez Google Chrome 80+ avec des règles améliorées d’application des cookies de SameSite. Pour plus d’informations, voir [Quel est l’impact des politiques d’application des cookies récemment annoncées dans Google Chrome SameSite sur le compositeur d’expérience visuelle et sur le site EEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite) ?

L’extension de navigateur d’assistance du compositeur d’expérience visuelle pour Chrome résout les problèmes de chargement de site pour lesquels les clients se fient désormais à l’[!DNL Target] [compositeur d’expérience amélioré](/help/administrating-target/visual-experience-composer-set-up.md#eec) ou à des extensions tierces, telles que Requestly.

## Avantages de l’utilisation de l’extension d’assistance du compositeur d’expérience visuelle

* Tous les en-têtes qui démolissent un iframe, comme X-Frame-Options et Content-Security-Policy, sont implicitement supprimés du site web. Il n’est plus nécessaire de créer des règles complexes avec Requestly pour ce faire.
* Si une page Web ne contient pas encore la bibliothèque JavaScript at.js [!DNL Target], vous pouvez utiliser l’extension pour injecter la bibliothèque afin de pouvoir créer des expériences pour le site Web. Vous pouvez ensuite créer des activités et leur faire passer les tests d’assurance qualité en utilisant des liens d’aperçu.

   Notez que lors de l’utilisation du compositeur d’expérience amélioré (EEC), l’extension n’injecte pas at.js, mais la fonctionnalité Cookie même site est toujours présente. Pour injecter at.js sur la page Web, désactivez la CEE.

* [Les ](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) visionneuses mobiles sont prises en charge, même sans le compositeur [!UICONTROL  d’expérience ] amélioré (CEE).
* Les clients qui débutent avec [!DNL Target] peuvent se servir de l’extension pour expérimenter [!DNL Target] même si leurs développeurs informatiques n’ont pas encore mis en œuvre [!DNL Target] sur leurs sites Web.
* Les partenaires qui gèrent les sites Web et les comptes [!DNL Target] de plusieurs clients disposent désormais d’un mécanisme simple pour prendre en charge le chargement du compositeur d’expérience visuelle, plutôt que de gérer plusieurs règles dans des outils tiers.

## Obtenir et installer l’extension d’assistance du compositeur d’expérience visuelle

1. Accédez à l’[extension de navigateur Adobe Target VEC Helper dans Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Cliquez sur **[!UICONTROL Ajouter à Chrome > Ajouter une extension]**.
1. Ouvrez le compositeur d’expérience visuelle dans [!DNL Target].
1. Pour utiliser l’extension, cliquez sur l’icône de l’extension du navigateur d’assistance de VEC (![icône de l’assistant de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) dans la barre d’outils du navigateur Chrome lorsque vous êtes en mode VEC ou en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md).
1. (Conditionnel) Faites glisser la bascule **[!UICONTROL Injecter les bibliothèques de Cibles]** vers la position &quot;on&quot; si la page Web ne contient pas encore la bibliothèque JavaScript [!DNL Target] at.js.

   L’illustration suivante présente l’assistant de VEC avec le paramètre d’[!UICONTROL injection des bibliothèques Target] activé :

   ![Assistant de VEC 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   L’illustration suivante présente l’assistant de VEC vous demandant si vous souhaitez qu’il injecte des bibliothèques [!DNL Target] dans la page pour activer la création :

   ![Assistant de VEC 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Conditionnel) Faites glisser la bascule **[!UICONTROL Cookies]** vers la position &quot;on&quot; pour ajouter automatiquement le correctif du navigateur d’attributs SameSite=None, puis spécifiez le nom et le domaine du cookie.

   ![Basculement des cookies dans l’extension d’assistance du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Les liens suivants fournissent des informations supplémentaires :

   * Pour plus d’informations sur le correctif du navigateur d’attributs SameSite=None, voir &quot;Comment les politiques d’application des cookies récemment annoncées dans Google Chrome SameSite affectent-elles le compositeur d’expérience visuelle et la CEE ?&quot; dans [Problèmes de dépannage liés au compositeur d’expérience visuelle et au compositeur d’expérience amélioré](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * Le nom du cookie est &quot;mbox&quot; et le domaine du cookie est le deuxième niveau et le niveau supérieur des domaines à partir desquels vous servez la mbox. Il s’agit d’un cookie propriétaire, puisqu’il est diffusé à partir du domaine de votre société. Exemple: `mycompany.com`. Pour plus d’informations, voir [Cookies Adobe Target](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) dans le *Guide de l’utilisateur de l’interface Experience Cloud*.

## Remarques

* Votre implémentation doit utiliser la [!DNL Target]bibliothèque at.js. Vous ne pouvez pas utiliser une implémentation de mbox.js avec l’extension.
* L’indicateur d’[!UICONTROL Injection de bibliothèques Target] dans l’extension est désactivé par défaut. Vous pouvez activer cet balise si vous souhaitez utiliser le VEC sur un site qui n’a pas encore été mis en œuvre pour [!DNL Target].

   Notez que cette balise est un paramètre global. La balise est activée ou désactivée pour tous les sites Web ouverts dans le VEC. Par exemple, si vous définissez cet indicateur sur &quot;on&quot; et ouvrez un site Web qui est déjà implémenté avec at.js, vous recevrez un message vous informant qu’at.js est déjà chargé. Nous prévoyons que la plupart des clients auront déjà mis en oeuvre at.js sur leurs pages et utiliseront le paramètre par défaut &quot;off&quot;.

* L’extension charge la dernière version d’at.js disponible à partir de [!DNL Target UI] dans [!UICONTROL Administration > Implémentation].
* Lorsque vous utilisez l’extension pour injecter at.js en [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md), un autre onglet Chrome doit être ouvert. Cet onglet Chrome doit être authentifié dans la même [!DNL Adobe Experience Cloud] organisation que celle dans laquelle vous avez créé l’activité.
* Les messages suivants vous permettent de rester informé :

   * Si vous tentez de charger un site Web à l’aide du VEC et que le chargement échoue, un message s’affiche pour vous suggérer d’installer l’extension de navigateur VEC Helper.
   * Si at.js n’est pas encore mis en œuvre sur le site Web, un message s’affiche dans le VEC pour suggérer d’installer l’extension.
   * Si l’extension est activée et alimente le chargement, des messages s’affichent lorsque l’extension injecte la bibliothèque at.js (si nécessaire) ou aide à ouvrir le site Web de manière fiable dans le VEC.

