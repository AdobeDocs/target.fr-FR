---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer les offres de code et d’image à l’aide de la bibliothèque d’offres dans Adobe Target.
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f93e33e91fb7be9c0d1772a2014864b46c1dfe47
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# Offres

Utilisez la bibliothèque [!UICONTROL Offers] de [!DNL Adobe Target] pour gérer le contenu de votre offre de code et de votre offre d’image.

1. Cliquez sur **[!UICONTROL Offers]** pour ouvrir la bibliothèque.

   La bibliothèque contient les offres qui ont été configurées par l’intermédiaire de [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et les API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

   La page [!UICONTROL Offers] comporte deux onglets sur le côté droit : [!UICONTROL Code Offers] et [!UICONTROL Image Offers] qui vous permettent d’afficher les offres par type.

   ![ Page Offres affichant les onglets Offres (code) et Offres (images)](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Facultatif) Cliquez sur la liste déroulante **[!UICONTROL Type]** pour filtrer les offres par type (Offre d’HTML, [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md) et [Dossiers](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![ image offer_filter](assets/offers_filter.png)

1. (Facultatif) Cliquez sur la liste déroulante **[!UICONTROL Source]** pour filtrer les offres par source (Adobe Target, Adobe Target Classic et Adobe Experience Manager).

1. (Facultatif) Effectuez d’autres tâches en survolant l’offre ou le dossier de votre choix sur l’onglet [!UICONTROL Code Offers], puis en cliquant sur l’icône de votre choix.

   ![Options d’offres de code](assets/offer-picker-large.png)

   Les options incluent :

   * Vue (Pour plus d’informations, voir [ Affichage des définitions d’offre](#section_6B059DD121434E6292CAB393507D010E) ci-dessous.)
   * Modifier
   * Copier
   * Déplacer (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur l’icône **[!UICONTROL Move]** de l’élément souhaité, cliquez sur le dossier de votre choix, puis sur **[!UICONTROL Drop]**.)
   * Supprimer

   Selon vos autorisations, il se peut que les icônes de toutes les options ne s’affichent pas. Par exemple, un utilisateur disposant d’autorisations [!UICONTROL Observer] n’a pas les droits d’utiliser l’option [!UICONTROL Copy].

   Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Facultatif) Effectuez des tâches supplémentaires en survolant l’offre ou le dossier de l’image de votre choix sur l’onglet [!UICONTROL Image Offers], puis en cliquant sur l’icône de votre choix.

   ![Options d’offres d’images](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Les options incluent :

   * Sélectionner
   * Télécharger
   * Afficher les propriétés
   * Modifier
   * Annoter
   * Copier

   Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >Les offres d’images ne font pas partie du modèle [Autorisations des utilisateurs d’entreprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).


## Affichage des définitions d’offre {#section_6B059DD121434E6292CAB393507D010E}

Vous pouvez afficher les détails de la définition de l’offre sur une carte contextuelle de la bibliothèque [!UICONTROL Offers] sans ouvrir l’offre.

Par exemple, la carte de définition d’offre suivante pour une offre d’HTML est accessible en cliquant sur l’icône d’information :

![offer-card-html image](assets/offer-card-html-new.png)

Les informations suivantes sont disponibles :

* Nom
* ID d’offre
* Type
* Dernière modification

Cliquez sur le lien [!UICONTROL View Full Details] pour afficher le contenu de l’offre et les activités qui référencent une offre de code. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Les informations incluent [!UICONTROL Live Activities] et [!UICONTROL Inactive Activities].

Les informations disponibles sur chaque carte varient en fonction du type d’offre : offre d’HTML, [fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md) ou [offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

La fonctionnalité de détails de l’offre ne s’applique pas aux offres d’image.

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
