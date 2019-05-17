---
description: Si vous utilisez un modèle de page afin de fournir une structure à vos pages, ou si vos pages contiennent des éléments similaires, cette fonctionnalité permet de tester des variations dans des éléments de page structurés de manière similaire.
keywords: tests de modèle;modèle;même expérience sur des pages similaires;test de modèles
seo-description: Si vous utilisez un modèle de page afin de fournir une structure à vos pages, ou si vos pages contiennent des éléments similaires, cette fonctionnalité permet de tester des variations dans des éléments de page structurés de manière similaire.
seo-title: Inclure la même expérience sur des pages similaires
solution: Target
title: Inclure la même expérience sur des pages similaires
topic: Premium
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Inclure la même expérience sur des pages similaires{#include-the-same-experience-on-similar-pages}

Si vous utilisez un modèle de page afin de fournir une structure à vos pages, ou si vos pages contiennent des éléments similaires, cette fonctionnalité permet de tester des variations dans des éléments de page structurés de manière similaire.

Pour fonctionner correctement, cette fonctionnalité doit être utilisée sur des pages ayant une structure très similaire ou contenir des éléments de modèle qui sont structurés de manière identique sur toutes les pages.

>[!IMPORTANT]
>
>L’utilisation de cette fonctionnalité pour modifier des éléments sur des pages dissemblables provoquera probablement des résultats inattendus.

Par exemple, vous pouvez utiliser cette fonctionnalité pour effectuer les opérations suivantes :

* Tester une barre de navigation globale en réorganisant ou supprimant des éléments
* Supprimer un élément de toutes les pages de produits qui utilisent un modèle de page spécifique
* Ajouter une bannière à toutes les pages de produits
* Modifier la disposition d’un modèle d’article

La vidéo de démonstration suivante contient des informations sur l’utilisation d’un modèle :

Vous pouvez spécifier les pages qui incluent les éléments de modification, ou appliquer la modification sur l’ensemble du site.

1. Créez une activité comme décrite dans [Activités](../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).
1. Pour spécifier les pages dans lesquelles l&#39;expérience s&#39;affiche, cliquez sur l&#39;icône d&#39;engrenage dans le compositeur d&#39;expérience visuelle, puis sélectionnez **[!UICONTROL Diffusion de page]**.
1. Cliquez sur **[!UICONTROL Ajouter une règle de modèle]**, puis spécifiez les critères des pages auxquelles vous voulez ajouter l&#39;expérience.

1. Indiquez la plage de pages. La plage de pages peut être :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#) (ciblez la partie d’une URL après le symbole #.)
   * Requête
   * Paramètre

1. Sélectionnez un opérateur.

   L’opérateur indique comment les éléments après l’opérateur sont associés à la plage de pages. Les opérateurs disponibles sont :

   * Contient
   * Ne contient pas
   * Is (sensible à la casse)
   * N’est pas
   * Commence par
   * Se termine par

1. Saisissez les chaînes qui définissent l’emplacement d’ajout de l’expérience, par exemple le domaine ou les chaînes contenues dans le nom de la page.

   Par exemple, si vous sélectionnez **[!UICONTROL Domaine]** et **[!UICONTROL Est (sensible à la casse)]**, entrez le domaine dans lequel vous souhaitez que l&#39;expérience soit ajoutée à toutes les pages.

   Vous pouvez inclure plusieurs éléments.

   >[!IMPORTANT]
   >
   >De nombreux éléments utilisent la `OR`logique, ce qui signifie que n’importe quel élément de la liste rend la condition « true ».

1. Si vous le souhaitez, saisissez des critères supplémentaires en cliquant sur **[!UICONTROL Ajouter une règle]** de modèle et en répétant la procédure à suivre à l&#39;étape précédente.

   Plusieurs critères sont associés avec la logique ET. Adobe Target ajoute l’expérience à toutes les pages qui correspondent aux critères spécifiés.

>[!IMPORTANT]
>
> Target ne peut pas vérifier les pages afin de garantir qu’elles s’affichent comme prévu. Il est donc primordial de tester les pages affectées avant de les rendre publiques lorsque vous utilisez cette fonctionnalité.

## Vidéo de formation : compositeur d’expérience visuelle (2 de 2) (7 min 29)

* Attribution d’un nouveau nom à une expérience et duplication d’une expérience
* Création d’une expérience de redirection
* Ciblage d’une activité sur une URL unique ou un groupe d’URL
* Création d’une activité multipage
* Prévisualisation et création d’expérience pour des sites web réactifs
* Utilisation de superposition pour mettre en avant des types d’éléments

>[!VIDEO](https://video.tv.adobe.com/v/17401)