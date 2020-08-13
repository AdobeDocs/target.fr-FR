---
keywords: visual experience composer;vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css selectors
description: Configurez le compositeur d’expérience visuelle Adobe Target en spécifiant ses paramètres généraux, la configuration de la fenêtre d’affichage mobile et les sélecteurs CSS.
title: Configuration du compositeur d’expérience visuelle Adobe Target
feature: administration general
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 52%

---


# Configuration du compositeur d’expérience visuelle

Configurez le compositeur d’expérience [!DNL Adobe Target]  visuelle en spécifiant ses paramètres généraux, la configuration de la fenêtre d’affichage mobile et les sélecteurs CSS.

Pour accéder à la page de configuration du compositeur d’expérience [!UICONTROL visuelle] , cliquez sur **[!UICONTROL Administration]** > Compositeur d’expérience **[!UICONTROL visuelle].**

>[!NOTE]
>
>Notez que les paramètres de cette page s’appliquent à l’ensemble du [!DNL Target] compte.

![Page de configuration du compositeur d’expérience visuelle](/help/administrating-target/assets/vec.png)

## Paramètres généraux

Vous pouvez définir des paramètres généraux pour le compositeur d’expérience visuelle.

![Section Paramètres généraux](/help/administrating-target/assets/general-settings.png)

Les méthodes suivantes sont disponibles :

### URL par défaut

Définissez l’URL par défaut utilisée par le [!UICONTROL compositeur d’expérience visuelle]. Il s’agit de la page par défaut, par exemple votre page d’accueil, utilisée lorsque vous configurez une expérience pour chaque nouvelle activité. Si vous ne définissez pas d’URL par défaut, vous devez saisir une URL pour chaque activité lors de sa création.

### Activer le compositeur d’expérience avancé

Autorise la modification des sites avec des iFrames ou avec un contenu mixte. Certains sites peuvent ne pas être compatibles avec la version améliorée. Deselect this option to revert to the original [!UICONTROL Visual Experience Composer]. La répartition des activités sur les sites n’est pas affectée par ce choix.

Pour plus d’informations, voir [Résolution des problèmes du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

You can also enable the [!UICONTROL Enhanced Experience Composer] at the activity level.

### Chargement du contenu mixte

Enable mixed content while opening a website using the [!UICONTROL Enhanced Experience Composer] (EEC). Enabling this option avoids the extra overhead of loading static resources via [!DNL Target] proxy servers.

Cette option est utile si, par exemple :

* Vos en-têtes CSP (Content Security Policy) permettent le chargement de contenu mixte sans l’utilisation de serveurs proxy pour lesquels la norme CEE est activée.
* Le temps de chargement de votre site Web HTTP augmente dans la CEE, où le chargement de JavaScript, d’images, etc. prend plus de temps par proxy.

### Générer des instantanés d’expérience dans le diagramme de flux d’activité

L’activation des instantanés d’expérience génère des miniatures pour vos expériences dans le diagramme de processus de l’activité. Pour certains utilisateurs, la désactivation des instantanés peut permettre d’obtenir des performances plus rapides.

## ![Configuration du badge](/help/assets/premium.png) Premium pour les fenêtres d’affichage mobiles

Vous pouvez ajouter des périphériques à utiliser lors de la prévisualisation d’expériences. Chaque périphérique est associé à une audience.

![Section Configuration de la fenêtre d’affichage mobile](/help/administrating-target/assets/mobile-viewport-configuration.png)

Click **[!UICONTROL Add]**, specify a descriptive name for the mobile viewport, specify the width and height, select the desired operating system, then click [!UICONTROL Save].

Pour obtenir des informations sur l’ajout d’une fenêtre d’affichage mobile, voir [Configuration de fenêtre d’affichage mobile](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Sélecteurs CSS {#css}

Spécifiez comment [!DNL Target] génère des sélecteurs CSS.

![Section Sélecteurs CSS](/help/administrating-target/assets/css-selectors.png)

Ces options aident [!DNL Target] à comprendre la structure de votre site afin de générer de meilleurs sélecteurs CSS pour la distribution de contenu. Par défaut, [!DNL Target] génère les sélecteurs selon les identifiants d’élément de la page. Si votre site utilise peu d’ID, ou des ID en double sur la même page, l’utilisation de classes peut être une meilleure option.

Vous pouvez sélectionner une des options suivantes ou les deux :

### Utiliser les ID d’élément

Désélectionnez cette option si le même ID est utilisé pour plusieurs éléments ou si l’ID d’élément peut changer au chargement de la page.

### Utiliser les classes d’éléments

Par défaut, [!DNL Target] utilise uniquement les identifiants d’élément. Néanmoins, si votre page est conçue pour utiliser des classes pour identifier les éléments, par exemple une page créée avec [!DNL Adobe Experience Manager], vous devez également sélectionner [!UICONTROL Utiliser les classes d’éléments].

>[!NOTE]
>
>Bien que tout ait été fait pour garantir la précision, sachez que l&#39;utilisation de classes peut entraîner des erreurs. Si vous ne sélectionnez aucune des deux options, la précision est également affectée. L’ordre de précision est ID > classes > aucune des options. Assurez-vous de systématiquement tester votre page pour garantir que les sélecteurs sont corrects.

Vous pouvez remplacer ce paramètre par activité (cliquez sur l’icône en forme d’engrenage [!UICONTROL Paramètres], puis sélectionnez [!UICONTROL Sélecteurs CSS]). Cette fonctionnalité est particulièrement utile si vous avez plusieurs sites qui sont configurés différemment.

>[!NOTE]
>
>Overriding the setting per activity is not available in [!UICONTROL Automated Personalization] and [!UICONTROL Multivariate Testing] activities.  Voir [Sélecteurs d’éléments utilisés dans le compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) pour plus d’informations sur les sélecteurs.

## Vidéo de formation : Balise ![Aperçu des préférences du compte (7:33)](/help/assets/overview.png)

Cette vidéo comporte des informations sur les préférences de compte.

* Description des paramètres du compte disponibles dans [!DNL Target Standard]

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] Administration [!UICONTROL (anciennement] Configuration ) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur sur l’ensemble du produit. Les informations de la vidéo suivante sont généralement correctes ; toutefois, les options peuvent se trouver à des emplacements légèrement différents. Les vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
