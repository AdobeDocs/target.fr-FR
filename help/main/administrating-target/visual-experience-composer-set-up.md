---
keywords: compositeur d’expérience visuelle;vec;url par défaut;compositeur d’expérience amélioré;eec;contenu mixte;instantanés d’expérience;fenêtre d’affichage mobile;css;sélecteurs css
description: Découvrez comment configurer le compositeur d’expérience visuelle (VEC) d’Adobe [!DNL Target] en spécifiant ses paramètres généraux, la configuration des fenêtres d’affichage mobiles et les sélecteurs CSS.
title: Comment configurer le compositeur d’expérience visuelle (VEC) ?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 49%

---

# Configuration du [!UICONTROL Visual Experience Composer]

Configurez le [!DNL Adobe Target] d’[!UICONTROL Visual Experience Composer] (VEC) en spécifiant ses paramètres généraux, la configuration de la fenêtre d’affichage mobile et les sélecteurs CSS.

Pour accéder à la page de configuration des [!UICONTROL Visual Experience Composer], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer].**

{{permissions-update}}

>[!NOTE]
>
>Gardez à l’esprit que les paramètres de cette page s’appliquent à l’ensemble du compte [!DNL Target].

## Paramètres généraux

Vous pouvez spécifier des paramètres généraux pour la [!UICONTROL Visual Experience Composer].

![Section Paramètres généraux](/help/main/administrating-target/assets/general-settings.png)

Les méthodes suivantes sont disponibles :

### URL par défaut

Définissez l’URL par défaut utilisée par le [!UICONTROL Visual Experience Composer]. Il s’agit de la page par défaut, par exemple votre page d’accueil, utilisée lorsque vous configurez une expérience pour chaque nouvelle activité. Si vous ne définissez pas d’URL par défaut, vous devez saisir une URL pour chaque activité lors de sa création.

### Activer le compositeur d’expérience avancé {#eec}

Autorise la modification des sites avec des iFrames ou avec un contenu mixte. Certains sites peuvent ne pas être compatibles avec la version améliorée. Désélectionnez cette option pour revenir au [!UICONTROL Visual Experience Composer] d’origine. La répartition des activités sur les sites n’est pas affectée par ce choix.

Pour plus d’informations, voir [Résolution des problèmes du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

Vous pouvez également activer le [!UICONTROL Enhanced Experience Composer] au niveau de l&#39;activité.

### Chargement du contenu mixte

Activez le contenu mixte lors de l’ouverture d’un site web à l’aide du [!UICONTROL Enhanced Experience Composer] (EEC). L’activation de cette option évite la surcharge supplémentaire liée au chargement de ressources statiques via des serveurs proxy [!DNL Target].

Cette option s’avère utile si, par exemple :

* Les en-têtes de votre politique de sécurité du contenu (CSP) permettent de charger du contenu mixte sans utiliser de serveurs proxy avec le compositeur d’expérience amélioré activé.
* Votre site web HTTP est confronté à un temps de chargement accru dans l’EEC, où le chargement de JavaScript, d’images, etc. prend plus de temps via proxy.

### Générer des instantanés d’expérience dans le diagramme de flux d’activités

L’activation des instantanés d’expérience génère des miniatures pour vos expériences dans le diagramme de processus de l’activité. Pour certains utilisateurs, la désactivation des instantanés peut permettre d’obtenir des performances plus rapides.

## Configuration des fenêtres d’affichage mobiles 

>[!NOTE]
>
>Les paramètres [!UICONTROL Mobile Viewport Configuration] sont une fonctionnalité de [Target Premium](/help/main/c-intro/intro.md#premium).


Vous pouvez ajouter des périphériques à utiliser lors de la prévisualisation d’expériences. Chaque périphérique est associé à une audience.

![Section Configuration de la fenêtre d’affichage mobile](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

Cliquez sur **[!UICONTROL Add]**, spécifiez un nom explicite pour la fenêtre d’affichage mobile, spécifiez la largeur et la hauteur, sélectionnez le système d’exploitation souhaité, puis cliquez sur [!UICONTROL Save].

Pour obtenir des informations sur l’ajout d’une fenêtre d’affichage mobile, voir [Configuration de fenêtre d’affichage mobile](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Sélecteurs CSS {#css}

Spécifiez comment [!DNL Target] génère des sélecteurs CSS.

![Section Sélecteurs CSS](/help/main/administrating-target/assets/css-selectors.png)

Ces options aident [!DNL Target] à comprendre la structure de votre site afin de générer de meilleurs sélecteurs CSS pour la distribution de contenu. Par défaut, [!DNL Target] génère les sélecteurs selon les identifiants d’élément de la page. Si votre site utilise peu d’ID, ou des ID en double sur la même page, l’utilisation de classes peut être une meilleure option.

Vous pouvez sélectionner une des options suivantes ou les deux :

### Utiliser les ID d’élément

Désélectionnez cette option si le même ID est utilisé pour plusieurs éléments ou si l’ID d’élément peut changer au chargement de la page.

### Utiliser les classes d’éléments

Par défaut, [!DNL Target] utilise uniquement les identifiants d’élément. Cependant, si votre page est conçue pour utiliser des classes pour identifier des éléments, comme une page créée avec [!DNL Adobe Experience Manager], vous devez également sélectionner [!UICONTROL Use element classes].

>[!NOTE]
>
>Bien que tout ait été fait pour assurer la précision, sachez que l’utilisation des classes peut entraîner des erreurs. Si vous ne sélectionnez aucune des deux options, la précision est également affectée. L’ordre de précision est ID > classes > aucune des options. Assurez-vous de systématiquement tester votre page pour garantir que les sélecteurs sont corrects.

Vous pouvez remplacer ce paramètre par activité (cliquez sur l’icône d’engrenage [!UICONTROL Settings], puis sélectionnez [!UICONTROL CSS Selectors]). Cette fonctionnalité est particulièrement utile si vous avez plusieurs sites qui sont configurés différemment.

>[!NOTE]
>
>Le remplacement du paramètre par activité n’est pas disponible dans les activités [!UICONTROL Automated Personalization] et [!UICONTROL Multivariate Testing].  Voir [Sélecteurs d’éléments utilisés dans le compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md) pour plus d’informations sur les sélecteurs.

## Vidéo de formation : Préférences du compte (7:33) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo comporte des informations sur les préférences de compte.

* Description des paramètres du compte disponibles dans [!DNL Target Standard]

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Setup]) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur. Les informations de la vidéo suivante sont généralement correctes. Toutefois, les options peuvent se trouver à des emplacements légèrement différents. Des vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
