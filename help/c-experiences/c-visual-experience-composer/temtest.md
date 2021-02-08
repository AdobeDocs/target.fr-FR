---
keywords: tests de modèle;modèle;même expérience sur des pages similaires;test de modèles
description: Découvrez comment utiliser le compositeur d’expérience visuelle Adobe Target pour inclure la même expérience sur plusieurs pages qui sont structurées de manière similaire ou qui contiennent les mêmes éléments de modèle.
title: Puis-je inclure la même expérience sur des pages similaires ?
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 45%

---


# Inclure la même expérience sur des pages similaires

Utilisez un modèle de page dans [!DNL Adobe Target] pour fournir une structure à vos pages, ou si vos pages contiennent des éléments similaires, pour tester les variations d&#39;éléments de page structurés de manière similaire ou sur l&#39;ensemble de votre domaine.

Pour fonctionner correctement, cette fonction doit être utilisée sur les pages qui ont une structure similaire ou qui contiennent des éléments de modèle structurés de la même manière sur toutes les pages.

>[!IMPORTANT]
>
>L’utilisation de cette fonctionnalité pour modifier des éléments sur des pages dissemblables provoquera probablement des résultats inattendus.

Par exemple, vous pouvez utiliser cette fonctionnalité pour effectuer les opérations suivantes :

* Tester une barre de navigation globale en réorganisant ou supprimant des éléments
* Supprimer un élément de toutes les pages de produits qui utilisent un modèle de page spécifique
* Ajouter une bannière à toutes les pages de produits
* Modifier la disposition d’un modèle d’article

Vous pouvez spécifier les pages qui incluent les éléments de modification ou appliquer la modification sur votre site ou domaine.

1. Créez ou modifiez une activité comme décrit dans [Activités](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Pour spécifier les pages sur lesquelles l’expérience apparaîtra, dans le [!UICONTROL compositeur d’expérience visuelle] (compositeur d’expérience visuelle), cliquez sur l’icône d’engrenage, puis sélectionnez **[!UICONTROL Diffusion de page]**.

   ![Icône d’engrenage > Diffusion de page](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Cliquez sur **[!UICONTROL Ajouter une règle de modèle]**, puis spécifiez le critère des pages où vous souhaitez ajouter l’expérience.

1. Indiquez la plage de pages. La plage de pages peut être :

   * URL (Pour plus d&#39;informations sur l&#39;évaluation des URL par la Cible, consultez la [FAQ sur les Cibles et les audiences](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * Domaine
   * Chemin
   * Fragment de hachage (#) (cible de la partie d’une URL qui suit le symbole #).
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

   Par exemple, si vous sélectionnez **[!UICONTROL Domaine]** et **[!UICONTROL Est (sensible à la casse)]**, saisissez le domaine dans lequel vous souhaitez que l’expérience soit ajoutée à toutes les pages.

   Vous pouvez inclure plusieurs éléments.

   >[!IMPORTANT]
   >
   >Plusieurs éléments utilisent la logique OU, ce qui signifie qu’un seul élément de la liste rend la condition vraie.

1. Si vous le souhaitez, entrez des critères supplémentaires en cliquant sur **[!UICONTROL Ajouter la règle de modèle]** et en répétant la procédure des étapes précédentes.

   Plusieurs critères sont associés avec la logique ET. [!DNL Target] ajoute l’expérience à toutes les pages qui correspondent aux critères spécifiés.

>[!IMPORTANT]
>
> [!DNL Target] ne peut pas vérifier les pages afin de garantir qu’elles s’affichent comme prévu. Il est donc primordial de tester les pages affectées avant de les rendre publiques lorsque vous utilisez cette fonctionnalité.

## Cas d’utilisation

Examinez les cas d’utilisation suivants pour savoir comment utiliser les règles de modèle sur votre site :

### Générer la même activité sur l’ensemble du domaine

Vous pouvez envisager d’utiliser des règles de modèle pour générer la même activité sur l’ensemble de votre domaine pour les cas d’utilisation suivants :

* Pour inclure un en-tête ou un pied de page global
* Pour inclure une bannière globale (annonces COVID-19, par exemple)
* Pour inclure une promotion mondiale de la livraison gratuite

1. Créez ou modifiez une activité comme décrit dans [Activités](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Pour spécifier le domaine dans lequel l’expérience apparaîtra, dans le compositeur d’expérience visuelle, cliquez sur l’icône en forme d’engrenage, puis sélectionnez **[!UICONTROL Diffusion de page]**.

1. Cliquez sur **[!UICONTROL Ajouter la règle de modèle]** > **[!UICONTROL Domaine]**.

1. Dans la liste déroulante **[!UICONTROL Choisir évaluateur]**, sélectionnez **[!UICONTROL Contient]**, puis spécifiez le domaine.

   ![Le domaine contient](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Vidéo de formation : Compositeur visuel d’expérience (2 sur 2) (7:29) ![badge didacticiel](/help/assets/tutorial.png)

* Attribution d’un nouveau nom à une expérience et duplication d’une expérience
* Création d’une expérience de redirection
* Ciblage d’une activité sur une URL unique ou un groupe d’URL
* Création d’une activité multipage
* Prévisualisation et création d’expérience pour des sites web réactifs
* Utilisation de superposition pour mettre en avant des types d’éléments

>[!VIDEO](https://video.tv.adobe.com/v/17401)