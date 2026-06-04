---
keywords: compositeur d’expérience visuelle;vec;url par défaut;compositeur d’expérience amélioré;eec;contenu mixte;instantanés d’expérience;fenêtre d’affichage mobile;css;sélecteurs css
description: Découvrez comment configurer le compositeur d’expérience visuelle (VEC) d’ [!DNL Target] en spécifiant ses paramètres généraux, la configuration des fenêtres d’affichage mobiles et les sélecteurs CSS.
title: Comment configurer le compositeur d’expérience visuelle (VEC) ?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
TQID: https://experienceleague.adobe.com/E1ck4-aG4txqaFLs3t3-8bN-BQIoY8stRASTRJfhZMY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
subfeature_v2: id: b1d5cd6a-4ed3-43f6-9a52-2721acea1129id: c011fe9c-b94b-4a88-93d8-f2acece55112id: fc9c2184-9102-403f-bd6c-0055021e4bea
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 721
ht-degree: 47%

---

# Configuration du [!UICONTROL compositeur d’expérience visuelle]

Configurez le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience visuelle] (VEC) en spécifiant ses paramètres généraux, la configuration des fenêtres d’affichage mobiles et les sélecteurs CSS.

Pour accéder à la page de configuration du [!UICONTROL compositeur d’expérience visuelle], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL compositeur d’expérience visuelle].**

{{permissions-update}}

>[!NOTE]
>
>Gardez à l’esprit que les paramètres de cette page s’appliquent à l’ensemble du compte [!DNL Target].

## Paramètres généraux

Vous pouvez spécifier des paramètres généraux pour le [!UICONTROL compositeur d’expérience visuelle].

![Section Paramètres généraux](/help/main/administrating-target/assets/general-settings.png)

Les méthodes suivantes sont disponibles :

### URL par défaut

Définissez l’URL par défaut utilisée par le [!UICONTROL compositeur d’expérience visuelle]. Il s’agit de la page par défaut, par exemple votre page d’accueil, utilisée lorsque vous configurez une expérience pour chaque nouvelle activité. Si vous ne définissez pas d’URL par défaut, vous devez saisir une URL pour chaque activité lors de sa création.

### Activer le compositeur d’expérience avancé {#eec}

Autorise la modification des sites avec des iFrames ou avec un contenu mixte. Certains sites peuvent ne pas être compatibles avec la version améliorée. Désélectionnez cette option pour revenir au [!UICONTROL compositeur d’expérience visuelle] d’origine. La répartition des activités sur les sites n’est pas affectée par ce choix.

Pour plus d’informations, voir [Résolution des problèmes du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

Vous pouvez également activer le [!UICONTROL compositeur d’expérience avancé] au niveau de l’activité.

### Chargement du contenu mixte

Activez le contenu mixte lors de l’ouverture d’un site web à l’aide du [!UICONTROL  Enhanced Experience Composer ] (EEC). L’activation de cette option évite la surcharge supplémentaire liée au chargement de ressources statiques via des serveurs proxy [!DNL Target].

Cette option s’avère utile si, par exemple :

* Les en-têtes de votre politique de sécurité du contenu (CSP) permettent de charger du contenu mixte sans utiliser de serveurs proxy avec le compositeur d’expérience amélioré activé.
* Votre site web HTTP est confronté à un temps de chargement accru dans l’EEC, où le chargement de JavaScript, d’images, etc. prend plus de temps via proxy.

### Générer des instantanés d’expérience dans le diagramme de flux d’activités

L’activation des instantanés d’expérience génère des miniatures pour vos expériences dans le diagramme de processus de l’activité. Pour certains utilisateurs, la désactivation des instantanés peut permettre d’obtenir des performances plus rapides.

## Configuration des fenêtres d’affichage mobiles

>[!NOTE]
>
>Les paramètres [!UICONTROL Configuration de la fenêtre d’affichage mobile] sont une fonctionnalité de [Target Premium](/help/main/c-intro/intro.md#premium).


Vous pouvez ajouter des périphériques à utiliser lors de la prévisualisation d’expériences. Chaque périphérique est associé à une audience.

![Section Configuration de la fenêtre d’affichage mobile](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

Cliquez sur **[!UICONTROL Ajouter]**, attribuez un nom explicite à la fenêtre d’affichage mobile, spécifiez la largeur et la hauteur, sélectionnez le système d’exploitation souhaité, puis cliquez sur [!UICONTROL Enregistrer].

Pour obtenir des informations sur l’ajout d’une fenêtre d’affichage mobile, voir [Configuration de fenêtre d’affichage mobile](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Sélecteurs CSS {#css}

Spécifiez comment [!DNL Target] génère des sélecteurs CSS.

![Section Sélecteurs CSS](/help/main/administrating-target/assets/css-selectors.png)

Ces options aident [!DNL Target] à comprendre la structure de votre site afin de générer de meilleurs sélecteurs CSS pour la distribution de contenu. Par défaut, [!DNL Target] génère les sélecteurs selon les identifiants d’élément de la page. Si votre site utilise peu d’ID, ou des ID en double sur la même page, l’utilisation de classes peut être une meilleure option.

Vous pouvez sélectionner une des options suivantes ou les deux :

### Utiliser les ID d’élément

Désélectionnez cette option si le même ID est utilisé pour plusieurs éléments ou si l’ID d’élément peut changer au chargement de la page.

### Utiliser les classes d’éléments

Par défaut, [!DNL Target] utilise uniquement les identifiants d’élément. Cependant, si votre page est conçue pour utiliser des classes pour identifier des éléments, comme une page créée avec des [!DNL Adobe Experience Manager], vous devez également sélectionner [!UICONTROL Utiliser des classes d’éléments].

>[!NOTE]
>
>Bien que tout ait été fait pour assurer la précision, sachez que l’utilisation des classes peut entraîner des erreurs. Si vous ne sélectionnez aucune des deux options, la précision est également affectée. L’ordre de précision est ID > classes > aucune des options. Assurez-vous de systématiquement tester votre page pour garantir que les sélecteurs sont corrects.

Vous pouvez remplacer ce paramètre par activité (cliquez sur l’icône d’engrenage [!UICONTROL Paramètres], puis sélectionnez [!UICONTROL Sélecteurs CSS]). Cette fonctionnalité est particulièrement utile si vous avez plusieurs sites qui sont configurés différemment.

>[!NOTE]
>
>Le remplacement du paramètre par activité n’est pas disponible dans les activités  et [!UICONTROL Multivariate Testing].  Voir [Sélecteurs d’éléments utilisés dans le compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md) pour plus d’informations sur les sélecteurs.

## Vidéo de formation : Préférences du compte (7:33) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo comporte des informations sur les préférences de compte.

* Description des paramètres du compte disponibles dans [!DNL Target Standard]

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Configuration]) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur. Les informations de la vidéo suivante sont généralement correctes. Toutefois, les options peuvent se trouver à des emplacements légèrement différents. Des vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
