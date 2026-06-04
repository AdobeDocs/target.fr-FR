---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer efficacement les offres de code et d’images à l’aide de la bibliothèque [!UICONTROL Offres].
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
TQID: https://experienceleague.adobe.com/A8ZLHW-FrWHGPJR7P-mhl2pO6SPoDc--LWpFEjtQzBY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 958
ht-degree: 7%

---

# Offres

Découvrez comment gérer efficacement les offres de code et d’images à l’aide de la bibliothèque [!UICONTROL Offres] dans [!DNL Adobe Target].

Pour afficher la bibliothèque [!UICONTROL Offres], cliquez sur l’onglet **[!UICONTROL Offres]** dans la partie supérieure de l’interface utilisateur de [!DNL Target].

![Page Offres](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

La bibliothèque [!UICONTROL Offres] contient des offres qui ont été configurées via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et des API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

La bibliothèque [!UICONTROL Offres] donne un aperçu de toutes les offres de code et d’image et vous permet d’effectuer les actions suivantes :

| Élément | Description |
|--- |--- |
| Rail de navigation de gauche | Basculez entre l’affichage de [!UICONTROL Offres de code] ou [!UICONTROL Offres d’image]. |
| [!UICONTROL Afficher les dossiers] / [!UICONTROL Masquer les dossiers]<P>![Icône Afficher/Masquer les filtres](/help/main/assets/icons/RailLeft.svg) | Cliquez sur l’icône **[!UICONTROL Afficher les dossiers]** ou **[!UICONTROL Masquer les dossiers]** pour afficher ou non la structure des dossiers de vos offres.<P>Pour plus d’informations, voir [Création de dossiers d’offres](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| Icône [!UICONTROL Afficher les filtres]<P>![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) | Cliquez sur l’icône **[!UICONTROL Afficher les filtres]** pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source] et [!UICONTROL Type AEM].<P>Pour plus d’informations, voir [Appliquer des filtres à la liste Offres](#filters) ci-dessous. |
| Champs de recherche | Utilisez les champs **[!UICONTROL Rechercher dans]** pour rechercher rapidement une offre ou pour réduire le nombre d’offres affichées dans la bibliothèque [!UICONTROL Offres]. Vous pouvez effectuer une recherche par [!UICONTROL Nom de l’offre], [!UICONTROL Chemins AEM] ou [!UICONTROL Balises AEM]. Les options de recherche sont persistantes au niveau de la session. |
| [!UICONTROL Créer un dossier] | Cliquez sur **[!UICONTROL Créer un dossier]** pour créer des dossiers dans la bibliothèque [!UICONTROL Offre] afin de contenir les offres de code, les offres d’image, ainsi que d’autres dossiers pour créer une structure de sous-dossiers.<P>Pour plus d’informations, voir [Création de dossiers d’offres](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Création d’une offre]] | Cliquez sur **[!UICONTROL Créer une offre]** pour créer une offre.<P>Pour plus d&#39;informations sur la création des différents types d&#39;offres, voir : <ul><li>Offre HTML</li><li>[ Offre JSON ](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Cases à cocher des opérations en bloc<P>![ Icône Opérations en bloc ](/help/main/assets/icons/Rectangle.svg) | Cliquez sur les cases à cocher [!UICONTROL  Opérations en bloc ] pour effectuer des opérations en bloc sur toutes les offres ou sur les offres sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et du statut de l’offre), consultez [Exécution d’actions rapides](#quick-actions) ci-dessous. |
| [!UICONTROL Nom] | Le nom de chaque offre.<P>Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![icône Quick Info](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte pop-up, y compris l’identifiant de l’offre, le type, la date de la dernière modification de l’offre et par qui, etc.<p>Cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’offre pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité. Les actions suivantes sont disponibles (en fonction de vos autorisations et du statut de l&#39;offre) : [!UICONTROL Modifier], [!UICONTROL Copier], [!UICONTROL Supprimer] et [!UICONTROL Déplacer]. Pour plus d’informations sur chaque action, consultez [Exécution d’actions rapides](#quick-actions) ci-dessous.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL Type] | Le type d’offre : [!UICONTROL Offres ], [[!UICONTROL Offres de redirection]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Offres distantes]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) et [[!UICONTROL Offres JSON]](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
|  | Indique l’emplacement de création de l’offre : [!DNL Adobe Target], [!DNL Adobe Target Classic] et [!DNL Adobe Experience Manager]. |
| [!UICONTROL Dernière mise à jour ] | Affiche la date et l&#39;heure de la dernière modification de l&#39;offre et la personne qui les a effectuées.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre croissant ou décroissant de date. |

## Application de filtres à la bibliothèque des offres {#filters}

Cliquez sur l’icône **[!UICONTROL Afficher les filtres]** ( ![Icône Afficher les filtres sur la page Offres](/help/main/assets/icons/Filter.svg)) pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source] et [!UICONTROL Type AEM].

L&#39;icône **[!UICONTROL Afficher les filtres]** permet de filtrer les offres selon les catégories suivantes :

* **[!UICONTROL Type]** : [!UICONTROL Offre HTML], [[!UICONTROL Offre de redirection]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Offre distante]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) et [[!UICONTROL Offre JSON]](/help/main/c-experiences/c-manage-content/create-json-offer.md).

* **[!UICONTROL Source]** : [!DNL Adobe Target], [!DNL Adobe Target Classic] et [!DNL Adobe Experience Manager].

* **Type AEM** : [Fragments de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) et [Fragments d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Pour plus d’informations sur les différents types de fragments, consultez la présentation sur les fragments d’expérience et les fragments de contenu d’AEM [](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

Les filtres sont persistants au niveau de la session.

## Exécution d’actions rapides {#quick-actions}

Vous pouvez effectuer les actions rapides suivantes en cliquant sur l’icône appropriée :

### Infos rapides

Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![icône Quick Info](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte pop-up, y compris l’identifiant de l’offre, le type, la date de la dernière modification de l’offre et par qui, etc. Les options disponibles dépendent du type d’offre : [!UICONTROL Offre ], [[!UICONTROL Offre JSON]](/help/main/c-experiences/c-manage-content/create-json-offer.md), [[!UICONTROL Offre de redirection]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Offre distante]](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

### Autres actions

Les actions disponibles pour [!UICONTROL Offres de code] et [!UICONTROL Offres d’image] diffèrent légèrement. Les sections suivantes comprennent davantage d’informations :

#### Options [!UICONTROL  Code Offer ]

Cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![Icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’offre pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité.

Les actions suivantes sont disponibles (en fonction de vos autorisations et du statut de l&#39;offre) :

* [!UICONTROL Modifier]
* [!UICONTROL Copier]
* [!UICONTROL Supprimer]
* [!UICONTROL Déplacer] (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur **[!UICONTROL Déplacer]** en regard de l’élément souhaité, cliquez sur le dossier souhaité, puis cliquez sur **[!UICONTROL Déplacer]**.)

Selon vos autorisations, il se peut que vous ne voyiez pas d’icônes pour toutes les options. Par exemple, un utilisateur disposant des autorisations [!UICONTROL Observateur] ne dispose pas des droits d’utilisation de l’option [!UICONTROL Copier].

Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [ Utilisation de contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

#### Options [!UICONTROL Offre Image]

Effectuez des tâches supplémentaires en pointant sur l’offre d’image ou le dossier de votre choix sur l’onglet [!UICONTROL  Offres d’image ], puis en cliquant sur l’icône de votre choix.

Les options incluent :

* [!UICONTROL Select]
* [!UICONTROL Téléchargement]
* [!UICONTROL Afficher les propriétés]
* [!UICONTROL Autres actions]
* [!UICONTROL Modifier]
* [!UICONTROL Annoter ]
* [!UICONTROL Copier]

Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [ Utilisation de contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>Les offres d’image ne font pas partie du modèle [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

## Affichage des définitions d&#39;offre {#section_6B059DD121434E6292CAB393507D010E}

Pour afficher les détails de la définition de l’offre sur une carte pop-up de la bibliothèque [!UICONTROL Offres] sans ouvrir l’offre, cliquez sur le bouton ( ![icône d’informations rapides](/help/main/assets/icons/InfoOutline.svg) ).

Les informations suivantes sont disponibles :

* [!UICONTROL Nom]
* [!UICONTROL Identifiant de l’offre]
* [!UICONTROL Type]
* [!UICONTROL Dernière modification]

Cliquez sur le lien [!UICONTROL Afficher tous les détails] pour afficher les attributs et les activités de l’offre qui font référence à une offre de code dans la carte pop-up de définition de chaque offre. Cette fonctionnalité ne s’applique pas aux offres d’image. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Les informations comprennent des détails sur les [!UICONTROL Activités actives] et [!UICONTROL Activités inactives].
