---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer les offres de code et d’image à l’aide de la bibliothèque d’offres dans Adobe Target.
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: be59e8ccbf12f7b3cc42becc36a8b3c7474f2f9e
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 36%

---

# Offres

Utilisez la variable [!UICONTROL Offres] bibliothèque dans [!DNL Adobe Target] pour gérer le contenu de l’offre de code et de l’offre d’image.

1. Pour ouvrir la bibliothèque, cliquez sur **[!UICONTROL Offres.]**

   La bibliothèque contient les offres qui ont été configurées par l’intermédiaire de [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et les API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

   La variable [!UICONTROL Offres] La page comporte deux onglets sur le côté droit : [!UICONTROL Offres de code] et [!UICONTROL Offres d’image] qui vous permettent d’afficher les offres par type.

   ![Page Offres affichant les onglets Offres (code) et Offres (images)](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Facultatif) Cliquez sur le **[!UICONTROL Type]** liste déroulante pour filtrer les offres par type (offre par HTML, [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), et [Dossiers](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![image offer_filter](assets/offers_filter.png)

1. (Facultatif) Cliquez sur le **[!UICONTROL Source]** liste déroulante pour filtrer les offres par source (Adobe Target, Adobe Target Classic et Adobe Experience Manager).

1. (Facultatif) Effectuez des tâches supplémentaires en survolant l’offre ou le dossier de votre choix sur la page [!UICONTROL Offres de code] puis en cliquant sur l’icône de votre choix.

   ![Options d’offres de code](assets/offer-picker-large.png)

   Les options incluent :

   * Afficher (pour plus d’informations, voir [Affichage des définitions d’offre](#section_6B059DD121434E6292CAB393507D010E) ci-dessous.)
   * Modifier
   * Copier
   * Déplacer (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur le bouton **[!UICONTROL Déplacer]** pour l’élément de votre choix, cliquez sur le dossier de votre choix, puis sur **[!UICONTROL Déposer]**.)
   * Supprimer

   Selon vos autorisations, il se peut que les icônes de toutes les options ne s’affichent pas. Par exemple, un utilisateur avec [!UICONTROL Observateur] Les autorisations ne disposent pas des droits permettant d’utiliser la variable [!UICONTROL Copier] .

   Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu de la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Facultatif) Effectuez des tâches supplémentaires en survolant l’offre ou le dossier d’image de votre choix sur la page [!UICONTROL Offres d’image] puis en cliquant sur l’icône de votre choix.

   ![Options d’offres d’images](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Les options incluent :

   * Select
   * Télécharger
   * Afficher les propriétés
   * Modifier
   * Annoter
   * Copier

   Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu de la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >Les offres d’images ne font pas partie de la [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) modèle.


## Affichage des définitions d’offre {#section_6B059DD121434E6292CAB393507D010E}

Vous pouvez afficher les détails de la définition de l’offre sur une carte contextuelle dans le [!UICONTROL Offres] sans ouvrir l’offre.

Par exemple, la carte de définition d’offre suivante pour une offre de HTML est accessible en pointant la souris sur une offre de la fonction [!UICONTROL Contenu] , puis cliquez sur l’icône d’informations :

![image offer-card-html](assets/offer-card-html.png)

Les informations suivantes sont disponibles :

* Nom
* Source
* Type
* ID d’offre
* Chemin de l’offre
* Dernière modification

Cliquez sur l’onglet [!UICONTROL Utilisation de l’offre] pour afficher les activités qui référencent une offre de code dans la carte contextuelle de définition de chaque offre. Cette fonctionnalité ne s’applique pas aux offres d’image. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Informations incluses [!UICONTROL Activités en direct] et [!UICONTROL Activités inactives].

![image d’utilisation de carte-offre](assets/offer-card-usage.png)

L’illustration ci-dessous présente une carte de définition d’offre pour une offre de redirection :

![image de redirection par carte-offre](assets/offer-card-redirect.png)

Les informations suivantes sont disponibles :

* Nom
* Source
* Type
* ID d’offre
* Chemin de l’offre
* Dernière modification
* URL de redirection
* Inclure tous les paramètres d’URL (Activé ou Désactivé)
* Transmettre l’ID de session de mbox (activé ou désactivé)

L’illustration ci-dessous présente une carte de définition d’offre pour une offre distante :

![image-carte-offre-distante](assets/offer-card-remote.png)

Les informations suivantes sont disponibles :

* Nom
* Source
* Type
* ID d’offre
* Chemin de l’offre
* Dernière modification
* Type d’URL de redirection
* URL absolue ou relative

## Vidéo de formation : Le Référentiel de contenu ![Badge de présentation](/help/main/assets/overview.png)

Cette vidéo fournit des informations sur la gestion des offres.

* Connexion entre la [bibliothèque des ressources Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) et la bibliothèque de contenu Target
* Offres HTML personnalisées
* Offre HTML personnalisée dans le compositeur d’expérience visuelle

>[!VIDEO](https://video.tv.adobe.com/v/17387)
