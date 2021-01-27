---
keywords: content;assets;manage content;offers;manage assets;enter selection mode;selection mode
description: Comment gérer les offres de code et d’image ?
title: Offres
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 70547a05155aa2909b0e66a1f26b0fd2cc730dd9
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 40%

---


# Offres

Utilisez la bibliothèque [!UICONTROL Offres] de [!DNL Adobe Target] pour gérer le contenu de votre offre de code et de votre offre d’images.

1. Pour ouvrir la bibliothèque, cliquez sur **[!UICONTROL Offres.]**

   La bibliothèque contient les offres qui ont été configurées par l’intermédiaire de [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et les API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

   La page [!UICONTROL Offres] comporte deux onglets sur le côté droit : [!UICONTROL Offres de code] et [!UICONTROL Offres d’image] qui vous permettent de vue des offres par type.

   ![Page Offres présentant les onglets Offres de code et Offres d’image](/help/c-experiences/c-manage-content/assets/offers-page.png)

1. (Facultatif) Cliquez sur la liste déroulante **[!UICONTROL Type]** pour filtrer les offres par type (Offre HTML, [Fragments d’expérience](/help/c-experiences/c-manage-content/aem-experience-fragments.md), [Offre de redirection](/help/c-experiences/c-manage-content/offer-redirect.md), [Offre distante](/help/c-experiences/c-manage-content/about-remote-offers.md), [Offres JSON](/help/c-experiences/c-manage-content/create-json-offer.md), et &lt;a 10/>Dossiers](/help/c-experiences/c-manage-content/create-content-folder.md)).[

   ![](assets/offers_filter.png)

1. (Facultatif) Cliquez sur la liste déroulante **[!UICONTROL Source]** pour filtrer les offres par source (Adobe Target, Adobe Target Classic et Adobe Experience Manager).

1. (Facultatif) Effectuez d’autres tâches en passant la souris sur l’offre ou le dossier de votre choix dans l’onglet [!UICONTROL Offres de code], puis en cliquant sur l’icône de votre choix.

   ![Options d’offres de code](assets/offer-picker-large.png)

   Les options incluent :

   * Vue (Pour plus d’informations, voir [Affichage des définitions d’offre](#section_6B059DD121434E6292CAB393507D010E) ci-dessous.)
   * Modifier
   * Copier
   * Déplacer (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur l’icône **[!UICONTROL Déplacer]** de l’élément souhaité, cliquez sur le dossier de votre choix, puis sur **[!UICONTROL Déposer]**.)
   * Supprimer

   Selon vos autorisations, il se peut que les icônes de toutes les options ne s’affichent pas. Par exemple, un utilisateur disposant des autorisations [!UICONTROL Observer] ne dispose pas des droits d’utilisation de l’option [!UICONTROL Copier].

1. (Facultatif) Effectuez d’autres tâches en passant la souris sur l’offre ou le dossier d’image de votre choix sur l’onglet [!UICONTROL Offres d’image], puis en cliquant sur l’icône de votre choix.

   ![Options d’offres d’images](/help/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Les options incluent :

   * Select
   * Télécharger
   * Afficher les propriétés
   * Modifier
   * Annoter
   * Copier

## Affichage des définitions d&#39;offre {#section_6B059DD121434E6292CAB393507D010E}

Vous pouvez vue les détails de la définition d&#39;offre sur une carte contextuelle de la bibliothèque [!UICONTROL Offres] sans ouvrir l&#39;offre.

Par exemple, la carte de définition d&#39;offre suivante pour une offre HTML est accessible en passant la souris sur une offre de la liste [!UICONTROL Contenu], puis en cliquant sur l&#39;icône d&#39;information :

![](assets/offer-card-html.png)

Les informations suivantes sont disponibles :

* Nom
* Source
* Type
* ID d’offre
* Chemin de l’offre
* Dernière modification

Cliquez sur l’onglet [!UICONTROL Utilisation de l’offre] pour afficher les activités qui référencent une offre de code dans la carte contextuelle de définition de chaque offre. Cette fonctionnalité ne s’applique pas aux offres d’image. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Les informations incluent [!UICONTROL Activités actives] et [!UICONTROL Activités inactives].

![](assets/offer-card-usage.png)

L’illustration ci-dessous présente une carte de définition d’offre pour une offre de redirection :

![](assets/offer-card-redirect.png)

Les informations suivantes sont disponibles :

* Nom
* Source
* Type
* ID d’offre
* Chemin de l’offre
* Dernière modification
* URL de redirection
* Inclure tous les paramètres d’URL (Activé ou Désactivé)
* Transmettre l’ID de session de la mbox (Activé ou Désactivé)

L’illustration ci-dessous présente une carte de définition d’offre pour une offre distante :

![](assets/offer-card-remote.png)

Les informations suivantes sont disponibles :

* Nom
* Source
* Type
* ID d’offre
* Chemin de l’offre
* Dernière modification
* Type d’URL de redirection
* URL absolue ou relative

## Vidéo de formation : Le Référentiel de contenu  ![badge Aperçu](/help/assets/overview.png)

Cette vidéo fournit des informations sur la gestion des offres.

* Connexion entre la [bibliothèque des ressources Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) et la bibliothèque de contenu Target
* Offres HTML personnalisées
* Offre HTML personnalisée dans le compositeur d’expérience visuelle

>[!VIDEO](https://video.tv.adobe.com/v/17387)