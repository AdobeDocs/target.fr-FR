---
keywords: tests de modèle;modèle;même expérience sur des pages similaires;test de modèles
description: Découvrez comment utiliser le compositeur  [!DNL Target] ’expérience visuelle (VEC) d’Adobe pour inclure la même expérience sur plusieurs pages structurées de manière similaire ou contenant les mêmes éléments de modèle.
title: Puis-je inclure la même expérience sur des pages similaires ?
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 34%

---

# Inclure la même expérience sur des pages similaires

Utilisez un modèle de page dans [!DNL Adobe Target] pour fournir une structure à vos pages, ou si vos pages contiennent des éléments similaires, pour tester des variations dans des éléments de page à structure similaire ou sur l’ensemble de votre domaine.

Pour fonctionner correctement, cette fonction doit être utilisée sur des pages ayant une structure similaire ou contenant des éléments de modèle structurés de la même manière sur toutes les pages.

>[!IMPORTANT]
>
>L’utilisation de cette fonctionnalité pour modifier des éléments sur des pages dissemblables provoquera probablement des résultats inattendus.

Par exemple, vous pouvez utiliser cette fonctionnalité pour effectuer les opérations suivantes :

* Tester une barre de navigation globale en réorganisant ou supprimant des éléments
* Supprimer un élément de toutes les pages de produits qui utilisent un modèle de page spécifique
* Ajouter une bannière à toutes les pages de produits
* Modifier la disposition d’un modèle d’article

Vous pouvez spécifier des pages qui incluent les éléments de modification ou appliquer la modification à l’ensemble de votre site ou domaine.

1. Créez ou modifiez une activité comme décrit dans [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Pour spécifier les pages où l’expérience apparaîtra, dans le [!UICONTROL Visual Experience Composer] (VEC), cliquez sur l’icône d’engrenage, puis sélectionnez **[!UICONTROL Page Delivery]**.

   ![Icône Engrenage > Diffusion de page](/help/main/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Cliquez sur **[!UICONTROL Add Template Rule]**, puis spécifiez les critères des pages auxquelles vous souhaitez ajouter l’expérience.

1. Indiquez la plage de pages. La plage de pages peut être :

   * URL (pour plus d’informations sur la manière dont Target évalue les URL, voir [FAQ sur les cibles et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * Domaine
   * Chemin
   * Fragment de hachage (#) (cible la partie d’une URL qui suit le symbole #).
   * Requête
   * Paramètre

1. Sélectionnez un opérateur.

   L’opérateur indique comment les éléments après l’opérateur sont associés à la plage de pages. Les opérateurs disponibles sont les suivants :

   * Contient
   * Ne contient pas
   * Est (sensible à la casse)
   * N’est pas
   * Commence par
   * Se termine par

1. Saisissez les chaînes qui définissent l’emplacement d’ajout de l’expérience, par exemple le domaine ou les chaînes contenues dans le nom de la page.

   Par exemple, si vous sélectionnez **[!UICONTROL Domain]** et **[!UICONTROL Is (case sensitive)]**, saisissez le domaine dans lequel vous souhaitez que l’expérience soit ajoutée à toutes les pages.

   Vous pouvez inclure plusieurs éléments.

   >[!IMPORTANT]
   >
   >Plusieurs éléments utilisent la logique OR, ce qui signifie que tout élément unique de la liste rend la condition vraie.

1. Si vous le souhaitez, saisissez des critères supplémentaires en cliquant sur **[!UICONTROL Add Template Rule]** et en répétant la procédure des étapes précédentes.

   Plusieurs critères sont associés avec la logique ET. [!DNL Target] ajoute l’expérience à toutes les pages qui correspondent aux critères spécifiés.

>[!IMPORTANT]
>
> [!DNL Target] ne pouvez pas vérifier les pages pour vous assurer qu’elles s’affichent comme prévu. Il est donc toujours important d’utiliser cette fonctionnalité pour tester les pages affectées avant de les rendre publiques.

## Cas d’utilisation

Consultez les cas d’utilisation suivants pour savoir comment utiliser les règles de modèle sur votre site :

### Rendu de la même activité sur l’ensemble du domaine

Vous pouvez envisager d’utiliser des règles de modèle pour effectuer le rendu de la même activité sur l’ensemble de votre domaine pour les cas d’utilisation suivants :

* Pour inclure un en-tête ou un pied de page global
* Pour inclure une bannière globale (par exemple, les annonces COVID-19)
* Pour inclure une promotion de livraison gratuite internationale

1. Créez ou modifiez une activité comme décrit dans [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Pour spécifier le domaine dans lequel l’expérience apparaîtra, dans le compositeur d’expérience visuelle, cliquez sur l’icône en forme d’engrenage, puis sélectionnez **[!UICONTROL Page Delivery]**.

1. Cliquez sur **[!UICONTROL Add Template Rule]** > **[!UICONTROL Domain]**.

1. Dans la liste déroulante **[!UICONTROL Choose evaluator]** , sélectionnez **[!UICONTROL Contains]**, puis spécifiez le domaine.

   ![Le domaine contient](/help/main/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Vidéo de formation : Compositeur d’expérience visuelle (2 de 2) (7:29) ![Badge de tutoriel](/help/main/assets/tutorial.png)

* Attribution d’un nouveau nom à une expérience et duplication d’une expérience
* Création d’une expérience de redirection
* Ciblage d’une activité sur une URL unique ou un groupe d’URL
* Création d’une activité multipage
* Prévisualisation et création d’expérience pour des sites web réactifs
* Utilisation de superposition pour mettre en avant des types d’éléments

>[!VIDEO](https://video.tv.adobe.com/v/30142?captions=fre_fr)
