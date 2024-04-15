---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer les offres de code et d’image à l’aide de la bibliothèque d’offres.
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 646472f35ef4623666545f9945255d61bfe16073
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 29%

---

# Offres

Utilisez la variable [!UICONTROL Offers] bibliothèque dans [!DNL Adobe Target] pour gérer le contenu de l’offre de code et de l’offre d’image.

>[!NOTE]
>
>Cet article contient des informations sur les mises à jour apportées à la variable [!DNL Target] interface utilisateur qui fait actuellement partie d’un programme bêta. La variable [!DNL Adobe Target] L’équipe active souvent de nouvelles fonctionnalités pour certains clients à des fins de test et de commentaire. Une fois la période de test terminée, ces fonctionnalités seront activées pour tous les clients à l’avenir. [!DNL Target Standard/Premium] versions et annoncées dans les notes de mise à jour.

1. Cliquez sur **[!UICONTROL Offers]** pour ouvrir la bibliothèque.

   La bibliothèque contient les offres qui ont été configurées par l’intermédiaire de [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et les API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

   La variable [!UICONTROL Offers] La page comporte deux onglets sur le côté droit : [!UICONTROL Code Offers] et [!UICONTROL Image Offers] qui vous permettent d’afficher les offres par type.

   ![Page Offres affichant les onglets Offres (code) et Offres (images)](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Facultatif) Cliquez sur le **[!UICONTROL Type]** liste déroulante pour filtrer les offres par type (offre par HTML, [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), et [Dossiers](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![image offer_filter](assets/offers_filter.png)

1. (Facultatif) Cliquez sur le **[!UICONTROL Source]** liste déroulante pour filtrer les offres par source (Adobe Target, Adobe Target Classic et Adobe Experience Manager).

1. (Facultatif) Effectuez des tâches supplémentaires en survolant l’offre ou le dossier de votre choix sur la page [!UICONTROL Code Offers] puis en cliquant sur l’icône de votre choix.

   ![Options Offres de code](assets/offer-picker-large.png)

   Les options incluent :

   * Afficher (pour plus d’informations, voir [Affichage des définitions d’offre](#section_6B059DD121434E6292CAB393507D010E) ci-dessous.)
   * Modifier
   * Copier
   * Déplacer (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur le bouton **[!UICONTROL Move]** pour l’élément de votre choix, cliquez sur le dossier de votre choix, puis sur **[!UICONTROL Drop]**.)
   * Supprimer

   Selon vos autorisations, il se peut que les icônes de toutes les options ne s’affichent pas. Par exemple, un utilisateur avec [!UICONTROL Observer] Les autorisations ne disposent pas des droits permettant d’utiliser la variable [!UICONTROL Copy] .

   Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu de la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Facultatif) Effectuez des tâches supplémentaires en survolant l’offre ou le dossier d’image de votre choix sur la page [!UICONTROL Image Offers] puis en cliquant sur l’icône de votre choix.

   ![Options d’offres d’images](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Les options incluent :

   * Sélectionner
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

Vous pouvez afficher les détails de la définition de l’offre sur une carte contextuelle dans le [!UICONTROL Offers] sans ouvrir l’offre.

Par exemple, la carte de définition d’offre suivante pour une offre de HTML est accessible en pointant la souris sur une offre de la fonction [!UICONTROL Content] , puis cliquez sur l’icône d’informations :

![image offer-card-html](assets/offer-card-html.png)

Les informations suivantes sont disponibles :

* Nom
* Source
* Type
* ID d’offre
* Chemin de l’offre
* Dernière modification

Cliquez sur le bouton [!UICONTROL Offer Usage] pour afficher les activités qui référencent une offre de code dans la carte contextuelle de définition de chaque offre. Cette fonctionnalité ne s’applique pas aux offres d’image. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Informations incluses [!UICONTROL Live Activities] et [!UICONTROL Inactive Activities].

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

## Vidéo de formation : le référentiel de contenu ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo fournit des informations sur la gestion des offres.

* Connexion entre la [bibliothèque des ressources Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) et la bibliothèque de contenu Target
* Offres HTML personnalisées
* Offre HTML personnalisée dans le compositeur d’expérience visuelle

>[!VIDEO](https://video.tv.adobe.com/v/17387)
