---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer efficacement les offres de code et d’images à l’aide de la bibliothèque [!UICONTROL Offers].
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f034aba7fe4f54b937dee0846140af140052694c
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 8%

---

# Offres

Découvrez comment gérer efficacement les offres de code et d’images à l’aide de la bibliothèque [!UICONTROL Offers] dans [!DNL Adobe Target].

Pour afficher la bibliothèque [!UICONTROL Offers], cliquez sur l’onglet **[!UICONTROL Offers]** dans la partie supérieure de l’interface utilisateur de [!DNL Target].

![Page Offres](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

La bibliothèque [!UICONTROL Offers] contient les offres qui ont été configurées via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et les API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

La bibliothèque [!UICONTROL Offers] fournit un aperçu de toutes les offres de code et d’image et vous permet d’effectuer différentes actions :

| Élément | Description |
|--- |--- |
| Rail de navigation de gauche | Basculez entre l’affichage de [!UICONTROL Code Offers] ou [!UICONTROL Image Offers]. |
| [!UICONTROL Show Folders] / [!UICONTROL Hide Folders]<P>![Icône Afficher/Masquer les filtres](/help/main/assets/icons/RailLeft.svg) | Cliquez sur l’icône **[!UICONTROL Show Folders]** ou **[!UICONTROL Hide Folders]** pour basculer entre l’affichage de la structure de dossiers de vos offres et l’affichage de votre structure de dossiers.<P>Pour plus d’informations, voir [Création de dossiers d’offres](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| Icône [!UICONTROL Show filters]<P>![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) | Cliquez sur l&#39;icône **[!UICONTROL Show filters]** pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source] et [!UICONTROL AEM Type].<P>Pour plus d’informations, voir [Appliquer des filtres à la liste Offres](#filters) ci-dessous. |
| Champs de recherche | Utilisez les champs **[!UICONTROL Search in]** pour rechercher rapidement une offre ou pour réduire le nombre d’offres affichées dans la bibliothèque de [!UICONTROL Offers]. Vous pouvez effectuer une recherche par [!UICONTROL Offer Name], [!UICONTROL AEM Paths] ou [!UICONTROL AEM Tags]. Les options de recherche sont persistantes au niveau de la session. |
| [!UICONTROL Create Folder] | Cliquez sur **[!UICONTROL Create Folder]** pour créer des dossiers dans la bibliothèque [!UICONTROL Offer] afin de contenir les offres de code, les offres d’image, ainsi que d’autres dossiers pour créer une structure de sous-dossiers.<P>Pour plus d’informations, voir [Création de dossiers d’offres](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Cliquez sur **[!UICONTROL Create Offer]** pour créer une offre.<P>Pour plus d&#39;informations sur la création des différents types d&#39;offres, voir : <ul><li>Offre HTML</li><li>[ Offre JSON ](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Cases à cocher des opérations en bloc<P>![ Icône Opérations en bloc ](/help/main/assets/icons/Rectangle.svg) | Cliquez sur les cases à cocher [!UICONTROL Bulk Operations] pour effectuer des opérations en bloc sur toutes les offres ou sur les offres sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et du statut de l’offre), consultez [Exécution d’actions rapides](#quick-actions) ci-dessous. |
| [!UICONTROL Name] | Le nom de chaque offre.<P>Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![icône d’informations rapides](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte pop-up, y compris l’identifiant de l’offre, le type, la date de dernière modification de l’offre et de qui, etc.<p>Cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’offre pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité. Les actions suivantes sont disponibles (en fonction de vos autorisations et du statut de l’offre) : [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] et [!UICONTROL Move]. Pour plus d’informations sur chaque action, consultez [Exécution d’actions rapides](#quick-actions) ci-dessous.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL Type] | Le type d’offre : [!UICONTROL HTML Offers], [[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) et [[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Indique l’emplacement de création de l’offre : [!DNL Adobe Target], [!DNL Adobe Target Classic] et [!DNL Adobe Experience Manager]. |
| [!UICONTROL Last updated] | Affiche la date et l&#39;heure de la dernière modification de l&#39;offre et la personne qui les a effectuées.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre croissant ou décroissant de date. |

## Application de filtres à la bibliothèque des offres {#filters}

Cliquez sur l’icône **[!UICONTROL Show filters]** ( ![icône Afficher les filtres sur la page Offres](/help/main/assets/icons/Filter.svg)) pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source] et [!UICONTROL AEM Type].

L&#39;icône **[!UICONTROL Show filters]** permet de filtrer les offres selon les catégories suivantes :

* **[!UICONTROL Type]** : [!UICONTROL HTML Offer], [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) et [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md).

* **[!UICONTROL Source]** : [!DNL Adobe Target], [!DNL Adobe Target Classic] et [!DNL Adobe Experience Manager].

* **Type AEM** : [Fragments de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) et [Fragments d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Pour plus d’informations sur les différents types de fragments, consultez la présentation sur les fragments d’expérience et les fragments de contenu d’AEM [](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

Les filtres sont persistants au niveau de la session.

## Exécution d’actions rapides {#quick-actions}

Vous pouvez effectuer les actions rapides suivantes en cliquant sur l’icône appropriée :

### Infos rapides

Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![icône d’informations rapides](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte pop-up, y compris l’identifiant de l’offre, le type, la date de dernière modification de l’offre et de qui, etc. Les options disponibles dépendent du type d’offre : [!UICONTROL HTML Offer], [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md), [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

### Autres actions

Les actions disponibles pour [!UICONTROL Code Offers] et pour [!UICONTROL Image Offers] diffèrent légèrement. Les sections suivantes comprennent davantage d’informations :

#### [!UICONTROL Code Offer] des options

Cliquez sur l’icône **[!UICONTROL More actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’offre pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité.

Les actions suivantes sont disponibles (en fonction de vos autorisations et du statut de l&#39;offre) :

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur **[!UICONTROL Move]** en regard de l’élément souhaité, cliquez sur le dossier souhaité, puis cliquez sur **[!UICONTROL Move]**.)

Selon vos autorisations, il se peut que vous ne voyiez pas d’icônes pour toutes les options. Par exemple, un utilisateur disposant d’autorisations [!UICONTROL Observer] ne dispose pas des droits d’utilisation de l’option [!UICONTROL Copy].

Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [ Utilisation de contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

#### [!UICONTROL Image Offer] des options

Effectuez des tâches supplémentaires en pointant sur l’offre d’image ou le dossier de votre choix sur l’onglet [!UICONTROL Image Offers] , puis en cliquant sur l’icône de votre choix.

Les options incluent :

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [ Utilisation de contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>Les offres d’image ne font pas partie du modèle [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

## Affichage des définitions d&#39;offre {#section_6B059DD121434E6292CAB393507D010E}

Pour afficher les détails de la définition de l’offre sur une carte pop-up de la bibliothèque de [!UICONTROL Offers] sans ouvrir l’offre, cliquez sur ( ![icône d’informations rapides](/help/main/assets/icons/InfoOutline.svg) ).

Les informations suivantes sont disponibles :

* [!UICONTROL Name]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]

Cliquez sur le lien [!UICONTROL View Full Details] pour afficher les attributs et les activités de l’offre qui font référence à une offre de code dans la vignette pop-up de définition de chaque offre. Cette fonctionnalité ne s’applique pas aux offres d’image. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Les informations comprennent des détails sur les [!UICONTROL Live Activities] et les [!UICONTROL Inactive Activities].
