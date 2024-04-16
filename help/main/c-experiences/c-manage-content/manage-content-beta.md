---
keywords: contenu;ressources;gestion du contenu;offres;gérer les ressources;accès au mode de sélection;mode de sélection
description: Découvrez comment gérer les offres de code et d’image à l’aide de la bibliothèque d’offres.
title: Comment gérer les offres de code et d’image ?
feature: Experiences and Offers
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: cd8035d9e2a369b9503763474ce09c4fe2434ae9
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 17%

---

# Offres

Utilisez la variable [!UICONTROL Offers] bibliothèque dans [!DNL Adobe Target] pour gérer le contenu de votre code et de votre offre d’image.

>[!NOTE]
>
>Cet article contient des informations sur les mises à jour apportées à la variable [!DNL Target] interface utilisateur qui fait actuellement partie d’un programme bêta. La variable [!DNL Adobe Target] L’équipe active souvent de nouvelles fonctionnalités pour certains clients à des fins de test et de commentaire. Une fois la période de test terminée, ces fonctionnalités seront activées pour tous les clients à l’avenir. [!DNL Target Standard/Premium] versions et annoncées dans les notes de mise à jour.

Cliquez sur le bouton **[!UICONTROL Offers]** dans la partie supérieure de la [!DNL Target] IU pour afficher les [!UICONTROL Offers] bibliothèque .

![Bibliothèque d’offres dans Adobe Target](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

La variable [!UICONTROL Offers] La bibliothèque contient les offres qui ont été configurées via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) et les API. Les offres créées dans [!DNL Target Standard/Premium] ou d’autres solutions sont modifiables dans [!DNL Target Classic].

La bibliothèque d’offres offre un aperçu de toutes les offres de code et d’image et vous permet d’effectuer diverses actions :

| Élément | Description |
|--- |--- |
| Rail de navigation à gauche | Basculer entre les listes [!UICONTROL Code Offers] ou [!UICONTROL Image Offers]. |
| [!UICONTROL Show filters] icon<P>![Icône Afficher les filtres](/help/main/c-activities/assets/show-filters-icon.png) | Cliquez sur le bouton **[!UICONTROL Show filters]** pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source], et [!UICONTROL AEM Type]<P>Pour plus d’informations, voir [Application de filtres à la liste Offres](#filters) ci-dessous |
| Champs de recherche | Utilisez la variable **[!UICONTROL Search in]** pour trouver rapidement une offre ou pour réduire le nombre d’offres affichées dans la variable [!UICONTROL Offers] bibliothèque . Vous pouvez effectuer une recherche par [!UICONTROL Offer Name], [!UICONTROL AEM Paths], ou [!UICONTROL AEM Tags]. |
| [!UICONTROL Create Folder] | Cliquez sur Créer un dossier pour créer des dossiers dans la [!UICONTROL Offer] pour contenir des offres de code, des offres d’image, ainsi que d’autres dossiers afin de créer une structure de sous-dossiers. Pour plus d’informations, voir [Création de dossiers d’offres](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Créez une offre. Pour plus d’informations sur la création des différents types d’offres, voir : <ul><li>Offre HTML</li><li>[Offre JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Cases à cocher des opérations en bloc | Effectuez des opérations en bloc sur toutes les activités ou sur les activités sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et de l’état de l’offre), voir [Exécution d’actions rapides](#quick-actions) ci-dessous |
| [!UICONTROL Name] | Nom de chaque offre.<P>Cliquez sur le bouton **[!UICONTROL Quick Info]** icône en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte contextuelle, notamment l’identifiant, le type, la date de dernière modification de l’offre et par qui, etc.<p>Cliquez sur le bouton **[!UICONTROL More actions]** icône (points de suspension horizontaux) en regard de chaque nom d’offre pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité. Les actions suivantes sont disponibles (en fonction de vos autorisations et de l’état de l’offre) : [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete], et [!UICONTROL Move]. Pour plus d’informations sur chaque action, voir [Exécution d’actions rapides](#quick-actions) ci-dessous<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL Type] | Le type d&#39;offre : Offres HTML, [Offres de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offres distantes](/help/main/c-experiences/c-manage-content/about-remote-offers.md), et [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Affiche l’emplacement de création de l’offre : [!DNL Adobe Target], [!DNL Adobe Target Classic], et [!DNL Adobe Experience Manager]. |

## Application de filtres à la bibliothèque d’offres {#filters}

Cliquez sur le bouton **[!UICONTROL Show filters]** icône ( ![Icône Afficher les filtres sur la page Offres](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png) ) pour filtrer les offres par [!UICONTROL Type], [!UICONTROL Source], et [!UICONTROL AEM Type].

![image offer_filter](assets/offers-filter-new.png)

La variable **[!UICONTROL Show filters]** vous permet de filtrer les offres selon les catégories suivantes :

* **Type**: offre de HTML, [Offre JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), [Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

* **Source**: [!DNL Adobe Target], [!DNL Adobe Target Classic], et [!DNL Adobe Experience Manager].

* **Type d’AEM**: [Fragments de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) et [Fragments d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Pour plus d’informations sur les différents types de fragments, voir [Présentation des fragments d’expérience AEM et des fragments de contenu](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Exécution d’actions rapides {#quick-actions}

Vous pouvez effectuer les actions rapides suivantes en cliquant sur l’icône appropriée :

### Informations rapides

Cliquez sur le bouton **[!UICONTROL Quick Info]** icône en regard de chaque nom d’offre pour afficher plus d’informations sur cette offre dans une carte contextuelle, notamment l’identifiant, le type, la date de dernière modification de l’offre et par qui, etc. Les options disponibles dépendent du type d&#39;offre : Offre HTML, [Offre JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), [Offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Offre distante](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### Autres actions

Les actions disponibles pour les offres de code et pour les offres d’image diffèrent légèrement. Les sections suivantes comprennent davantage d’informations :

#### [!UICONTROL Code Offer] options

Cliquez sur le bouton **[!UICONTROL More actions]** icône (points de suspension horizontaux) en regard de chaque nom d’offre pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité. Les actions suivantes sont disponibles (en fonction de vos autorisations et de l’état de l’offre) : [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete], et [!UICONTROL Move].

![Option Autres actions dans la bibliothèque d’offres Target](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* Modifier
* Copier
* Supprimer
* Déplacer (par exemple, pour déplacer un ou plusieurs éléments dans un dossier, cliquez sur le bouton **[!UICONTROL Move]** pour l’élément de votre choix, cliquez sur le dossier de votre choix, puis sur **[!UICONTROL Drop]**.)

Selon vos autorisations, il se peut que les icônes de toutes les options ne s’affichent pas. Par exemple, un utilisateur avec [!UICONTROL Observer] Les autorisations ne disposent pas des droits permettant d’utiliser la variable [!UICONTROL Copy] .

Pour plus d’informations sur les tâches que vous pouvez effectuer sur les offres et les dossiers, voir [Utilisation du contenu de la bibliothèque de ressources](/help/main/c-experiences/c-manage-content/assets-working.md).

#### [!UICONTROL Image Offer] options

Effectuez d’autres tâches en survolant l’offre ou le dossier d’image souhaité sur la page [!UICONTROL Image Offers] puis en cliquant sur l’icône de votre choix.

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
