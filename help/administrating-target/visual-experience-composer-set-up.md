---
keywords: visual experience composer;vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css selectors
description: Configurez le compositeur d’expérience visuelle Adobe Target en spécifiant ses paramètres généraux, la configuration de la fenêtre d’affichage mobile et les sélecteurs CSS.
title: Configuration du compositeur d’expérience visuelle Adobe Target
feature: administration general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 52%

---


# Configuration du compositeur d’expérience visuelle

Configurez le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience visuelle] (VEC) en spécifiant ses paramètres généraux, sa configuration de fenêtre d’affichage mobile et ses sélecteurs CSS.

Pour accéder à la page de configuration du [!UICONTROL compositeur d’expérience visuelle], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL compositeur d’expérience visuelle].**

>[!NOTE]
>
>Notez que les paramètres de cette page s&#39;appliquent à l&#39;ensemble du compte [!DNL Target].

![Page de configuration du compositeur d’expérience visuelle](/help/administrating-target/assets/vec.png)

## Paramètres généraux

Vous pouvez définir des paramètres généraux pour le compositeur d’expérience visuelle.

![Section Paramètres généraux](/help/administrating-target/assets/general-settings.png)

Les méthodes suivantes sont disponibles :

### URL par défaut

Définissez l’URL par défaut utilisée par le [!UICONTROL compositeur d’expérience visuelle]. Il s’agit de la page par défaut, par exemple votre page d’accueil, utilisée lorsque vous configurez une expérience pour chaque nouvelle activité. Si vous ne définissez pas d’URL par défaut, vous devez saisir une URL pour chaque activité lors de sa création.

### Activer le compositeur d’expérience avancé {#eec}

Autorise la modification des sites avec des iFrames ou avec un contenu mixte. Certains sites peuvent ne pas être compatibles avec la version améliorée. Désélectionnez cette option pour revenir au compositeur d’expérience visuelle [!UICONTROL d’origine]. La répartition des activités sur les sites n’est pas affectée par ce choix.

Pour plus d’informations, voir [Résolution des problèmes du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

Vous pouvez également activer le [!UICONTROL compositeur d’expérience amélioré] au niveau de l’activité.

### Chargement du contenu mixte

Activez le contenu mixte lors de l’ouverture d’un site Web à l’aide du [!UICONTROL compositeur d’expérience amélioré] (CEE). L&#39;activation de cette option permet d&#39;éviter les surcharges supplémentaires liées au chargement de ressources statiques via des serveurs proxy [!DNL Target].

Cette option est utile si, par exemple :

* Vos en-têtes CSP (Content Security Policy) permettent le chargement de contenu mixte sans l’utilisation de serveurs proxy pour lesquels la norme CEE est activée.
* Le temps de chargement de votre site Web HTTP augmente dans la CEE, où le chargement de JavaScript, d’images, etc. prend plus de temps par proxy.

### Générer des instantanés d’expérience dans le diagramme de flux d’activité

L’activation des instantanés d’expérience génère des miniatures pour vos expériences dans le diagramme de processus de l’activité. Pour certains utilisateurs, la désactivation des instantanés peut permettre d’obtenir des performances plus rapides.

## ![Configuration Premium ](/help/assets/premium.png) badgeMobile Viewport

Vous pouvez ajouter des périphériques à utiliser lors de la prévisualisation d’expériences. Chaque périphérique est associé à une audience.

![Section Configuration de la fenêtre d’affichage mobile](/help/administrating-target/assets/mobile-viewport-configuration.png)

Cliquez sur **[!UICONTROL Ajouter]**, indiquez un nom descriptif pour la fenêtre d’affichage mobile, indiquez la largeur et la hauteur, sélectionnez le système d’exploitation de votre choix, puis cliquez sur [!UICONTROL Enregistrer].

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
>Le remplacement du paramètre par activité n’est pas disponible dans les activités [!UICONTROL Automated Personalization] et [!UICONTROL Multivariate Testing].  Voir [Sélecteurs d’éléments utilisés dans le compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) pour plus d’informations sur les sélecteurs.

## Vidéo de formation : Préférences de compte (7:33) ![badge Aperçu](/help/assets/overview.png)

Cette vidéo comporte des informations sur les préférences de compte.

* Description des paramètres du compte disponibles dans [!DNL Target Standard]

>[!NOTE]
>
>L&#39;interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Setup]) a été repensée afin d&#39;améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d&#39;améliorer l&#39;expérience de l&#39;utilisateur sur l&#39;ensemble du produit. Les informations de la vidéo suivante sont généralement correctes ; toutefois, les options peuvent se trouver à des emplacements légèrement différents. Les vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
