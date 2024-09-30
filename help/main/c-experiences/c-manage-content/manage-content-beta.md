---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer efficacement les offres de code et d’image à l’aide de la bibliothèque [!UICONTROL Offers]. Découvrez les bonnes pratiques et les conseils pour rationaliser votre workflow et améliorer vos projets.
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 74dbbb2f56e62c2c5595497c7ae1e264f9ffd9d4
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 8%

---

# Offres

Découvrez comment gérer efficacement les offres de code et d’image à l’aide de la bibliothèque [!UICONTROL Offers] dans [!DNL Adobe Target].

>[!NOTE]
>
>Cet article contient des informations sur les mises à jour apportées à l’interface utilisateur de [!DNL Target] qui fait actuellement partie d’un programme Beta. L’équipe [!DNL Adobe Target] active souvent de nouvelles fonctionnalités pour certains clients à des fins de test et de commentaire. Une fois la période de test terminée, ces fonctionnalités sont activées pour tous les clients dans les prochaines versions de [!DNL Target Standard/Premium] et annoncées dans les notes de mise à jour.

Pour afficher la bibliothèque [!UICONTROL Offers], cliquez sur l’onglet **[!UICONTROL Offers]** en haut de l’interface utilisateur de [!DNL Target].

![Page Offres](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

La bibliothèque [!UICONTROL Offers] contient des offres qui ont été configurées via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et des API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

La bibliothèque [!UICONTROL Offers] offre un aperçu de toutes les offres de code et d’image et vous permet d’effectuer diverses actions :

| Élément | Description |
|--- |--- |
| Rail de navigation à gauche | Basculez entre l’affichage de [!UICONTROL Code Offers] ou de [!UICONTROL Image Offers]. |
| Icône [!UICONTROL Show filters]<P>![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) | Cliquez sur l’icône **[!UICONTROL Show filters]** pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source] et [!UICONTROL AEM Type].<P>Pour plus d’informations, voir [Application de filtres à la liste Offres](#filters) ci-dessous. |
| Champs de recherche | Utilisez les champs **[!UICONTROL Search in]** pour rechercher rapidement une offre ou pour réduire le nombre d’offres affichées dans la bibliothèque [!UICONTROL Offers]. Vous pouvez effectuer des recherches par [!UICONTROL Offer Name], [!UICONTROL AEM Paths] ou [!UICONTROL AEM Tags]. |
| [!UICONTROL Create Folder] | Cliquez sur **[!UICONTROL Create Folder]** pour créer des dossiers dans la bibliothèque [!UICONTROL Offer] afin de contenir les offres de code, les offres d’image, ainsi que d’autres dossiers pour créer une structure de sous-dossiers.<P>Pour plus d’informations, voir [Création de dossiers d’offres](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Cliquez sur **[!UICONTROL Create Offer]** pour créer une offre.<P>Pour plus d’informations sur la création des différents types d’offres, voir : <ul><li>Offre HTML</li><li>[Offre JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Cases à cocher des opérations en bloc<P>![Icône Opérations en bloc](/help/main/assets/icons/Selection.svg) | Cochez les cases [!UICONTROL Bulk Operations] pour effectuer des opérations en bloc sur toutes les activités ou sur les activités sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et de l’état de l’offre), reportez-vous à la section [ Exécution d’actions rapides ](#quick-actions) ci-dessous. |
| [!UICONTROL Name] | Nom de chaque offre.<P>Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![Icône Quick Info](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte contextuelle, notamment l’identifiant de l’offre, le type, la date de la dernière modification et par qui, etc.<p>Cliquez sur l’icône **[!UICONTROL More Actions]** ( ![Icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’offre pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité. Les actions suivantes sont disponibles (selon vos autorisations et l’état de l’offre) : [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] et [!UICONTROL Move]. Pour plus d’informations sur chaque action, voir [Réaliser des actions rapides](#quick-actions) ci-dessous.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL Type] | Le type d’offre : [!UICONTROL HTML Offers], [[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) et [[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Affiche l’emplacement de création de l’offre : [!DNL Adobe Target], [!DNL Adobe Target Classic] et [!DNL Adobe Experience Manager]. |

## Application de filtres à la bibliothèque d’offres {#filters}

Cliquez sur l’icône **[!UICONTROL Show filters]** ( ![ icône Afficher les filtres sur la page Offres ](/help/main/assets/icons/Filter.svg)) pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source] et [!UICONTROL AEM Type].

L&#39;icône **[!UICONTROL Show filters]** permet de filtrer les offres selon les catégories suivantes :

* **[!UICONTROL Type]** : [!UICONTROL HTML Offer], [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) et [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md).

* **[!UICONTROL Source]** : [!DNL Adobe Target], [!DNL Adobe Target Classic] et [!DNL Adobe Experience Manager].

* **AEM Type** : [Fragments de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) et [Fragments d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Pour plus d’informations sur les différents types de fragments, consultez la [présentation des fragments d’expérience AEM et des fragments de contenu](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Exécution d’actions rapides {#quick-actions}

Vous pouvez effectuer les actions rapides suivantes en cliquant sur l’icône appropriée :

### Informations rapides

Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![Icône Quick Info](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte contextuelle, notamment l’identifiant de l’offre, le type, la date de dernière modification de l’offre et par qui, etc. Les options disponibles dépendent du type d’offre : [!UICONTROL HTML Offer], [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md), [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

### Autres actions

Les actions disponibles pour les offres de code et pour les offres d’image diffèrent légèrement. Les sections suivantes comprennent davantage d’informations :

#### [!UICONTROL Code Offer] options

Cliquez sur l’icône **[!UICONTROL More actions]** ( ![Icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’offre pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité.

Les actions suivantes sont disponibles (selon vos autorisations et l’état de l’offre) : [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] et [!UICONTROL Move].

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] (Par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur l’icône **[!UICONTROL Move]** de l’élément souhaité, cliquez sur le dossier de votre choix, puis sur **[!UICONTROL Drop]**.)

Selon vos autorisations, il se peut que les icônes de toutes les options ne s’affichent pas. Par exemple, un utilisateur disposant d’autorisations [!UICONTROL Observer] n’a pas les droits d’utiliser l’option [!UICONTROL Copy].

Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

#### [!UICONTROL Image Offer] options

Effectuez d’autres tâches en survolant l’offre ou le dossier d’image de votre choix sur l’onglet [!UICONTROL Image Offers], puis en cliquant sur l’icône de votre choix.

Les options incluent :

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu dans la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>Les offres d’images ne font pas partie du modèle [Autorisations des utilisateurs d’entreprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

## Affichage des définitions d’offre {#section_6B059DD121434E6292CAB393507D010E}

Pour afficher les détails de la définition de l’offre sur une carte contextuelle de la bibliothèque [!UICONTROL Offers] sans ouvrir l’offre, cliquez sur l’ ![icône Quick Info](/help/main/assets/icons/InfoOutline.svg) .

Les informations suivantes sont disponibles :

* [!UICONTROL Name]
* [!UICONTROL Source]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]
* [!UICONTROL Offer path]


Cliquez sur le lien [!UICONTROL View Full Details] pour afficher les attributs et activités de l’offre qui font référence à une offre de code dans la carte contextuelle de définition de chaque offre. Cette fonctionnalité ne s’applique pas aux offres d’image. Vous pouvez ainsi éviter toute répercussion sur les autres activités lorsque vous modifiez les offres. Les informations incluent des détails pour [!UICONTROL Live Activities] et [!UICONTROL Inactive Activities].
