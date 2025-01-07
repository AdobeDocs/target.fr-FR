---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer les offres de code et d’images à l’aide de la bibliothèque des offres dans Adobe Target.
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# Offres

Utilisez la bibliothèque [!UICONTROL Offers] dans [!DNL Adobe Target] pour gérer votre offre de code et le contenu de votre offre d’image.

1. Cliquez sur **[!UICONTROL Offers]** pour ouvrir la bibliothèque.

   La bibliothèque contient les offres qui ont été configurées par l’intermédiaire de [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et les API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

   La page [!UICONTROL Offers] comporte deux onglets sur le côté droit : [!UICONTROL Code Offers] et [!UICONTROL Image Offers] qui permettent d&#39;afficher les offres par type.

   ![Page Offres affichant les onglets Offres de code et Offres d’image](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Facultatif) Cliquez sur la liste déroulante **[!UICONTROL Type]** pour filtrer les offres par type (Offre d’HTML, [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md) et [Dossiers](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![image offer_filter](assets/offers_filter.png)

1. (Facultatif) Cliquez sur la liste déroulante **[!UICONTROL Source]** pour filtrer les offres par source (Adobe Target, Adobe Target Classic et Adobe Experience Manager).

1. (Facultatif) Effectuez des tâches supplémentaires en pointant sur l’offre ou le dossier souhaité dans l’onglet [!UICONTROL Code Offers] , puis en cliquant sur l’icône souhaitée.

   ![Options des offres de code](assets/offer-picker-large.png)

   Les options incluent :

   * Afficher (pour plus d&#39;informations, voir [Affichage des définitions d&#39;offre](#section_6B059DD121434E6292CAB393507D010E) ci-dessous.)
   * Modifier
   * Copier
   * Déplacer (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur l’icône **[!UICONTROL Move]** de l’élément souhaité, cliquez sur le dossier souhaité, puis sur **[!UICONTROL Drop]**).
   * Supprimer

   Selon vos autorisations, il se peut que vous ne voyiez pas d’icônes pour toutes les options. Par exemple, un utilisateur disposant d’autorisations [!UICONTROL Observer] ne dispose pas des droits d’utilisation de l’option [!UICONTROL Copy].

   Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [ Utilisation de contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Facultatif) Effectuez des tâches supplémentaires en pointant sur l’offre d’image ou le dossier de votre choix sur l’onglet [!UICONTROL Image Offers] , puis en cliquant sur l’icône de votre choix.

   ![Options d’offres Image](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Les options incluent :

   * Sélectionner
   * Télécharger
   * Afficher les propriétés
   * Modifier
   * Annoter
   * Copier

   Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [ Utilisation de contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >Les offres d’image ne font pas partie du modèle [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).


## Affichage des définitions d&#39;offre {#section_6B059DD121434E6292CAB393507D010E}

Vous pouvez afficher les détails de la définition de l’offre sur une carte pop-up dans la bibliothèque de [!UICONTROL Offers] sans ouvrir l’offre.

Par exemple, la carte de définition d’offre ci-dessous pour une offre HTML est accessible en cliquant sur l’icône d’information :

![image offer-card-html](assets/offer-card-html-new.png)

Les informations suivantes sont disponibles :

* Nom
* ID d’offre
* Type
* Dernière modification

Cliquez sur le lien [!UICONTROL View Full Details] pour afficher le contenu de l’offre et les activités qui font référence à une offre de code. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Les informations comprennent les [!UICONTROL Live Activities] et les [!UICONTROL Inactive Activities].

Les informations disponibles sur chaque carte varient en fonction du type d’offre : Offre d’HTML, [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offre à distance](/help/main/c-experiences/c-manage-content/about-remote-offers.md) ou [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

La fonctionnalité Détails de l’offre ne s’applique pas aux offres d’image.

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
