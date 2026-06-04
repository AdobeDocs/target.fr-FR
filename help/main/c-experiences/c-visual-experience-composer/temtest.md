---
keywords: tests de modèle;modèle;même expérience sur des pages similaires;test de modèles
description: Découvrez comment utiliser le compositeur  [!DNL Target] ’expérience visuelle (VEC) d’Adobe pour inclure la même expérience sur plusieurs pages structurées de manière similaire ou contenant les mêmes éléments de modèle.
title: Puis-je inclure la même expérience sur des pages similaires ?
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 564
ht-degree: 23%

---

# Inclure la même expérience sur des pages similaires

Utilisez un modèle de page dans [!DNL Adobe Target] pour fournir une structure à vos pages, ou si vos pages contiennent des éléments similaires, pour tester des variations dans des éléments de page à structure similaire ou sur l’ensemble de votre domaine.

Pour fonctionner correctement, cette fonction doit être utilisée sur des pages ayant une structure similaire ou contenant des éléments de modèle structurés de la même manière sur toutes les pages.

>[!IMPORTANT]
>
>L’utilisation de cette fonctionnalité pour modifier des éléments sur des pages différentes entraîne probablement des résultats inattendus.

Par exemple, vous pouvez utiliser cette fonctionnalité pour effectuer les opérations suivantes :

* Tester une barre de navigation globale en réorganisant ou supprimant des éléments
* Supprimer un élément de toutes les pages de produits qui utilisent un modèle de page spécifique
* Ajouter une bannière à toutes les pages de produits
* Modifier la disposition du modèle d’article

Vous pouvez spécifier des pages qui incluent les éléments de modification ou appliquer la modification à l’ensemble de votre site ou domaine.

1. Créez ou modifiez une activité comme décrit dans [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Pour spécifier les pages où l’expérience s’affiche, dans le [!UICONTROL compositeur d’expérience visuelle] (VEC), cliquez sur l’icône [!UICONTROL Configurer] ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ), puis sélectionnez **[!UICONTROL Diffusion de page]**.

1. Cliquez sur **[!UICONTROL Ajouter une règle]**, puis spécifiez les critères des pages auxquelles vous souhaitez ajouter l’expérience.

1. Indiquez la plage de pages. La plage de pages peut être :

   * [!UICONTROL URL] (pour plus d’informations sur la façon dont [!DNL Target] évalue les URL, voir [FAQ sur les cibles et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * [!UICONTROL Domaine]
   * [!UICONTROL Chemin]
   * [!UICONTROL Fragment de hachage (#)] (ciblez la partie d’une URL qui suit le symbole #.)
   * [!UICONTROL Requête]
   * [!UICONTROL Personnalisé]

1. Sélectionnez un opérateur.

   L’opérateur indique comment les éléments après l’opérateur sont associés à la plage de pages. Les opérateurs disponibles sont les suivants :

   * [!UICONTROL Contient]
   * [!UICONTROL Ne contient pas]
   * [!UICONTROL Est (sensible à la casse)]
   * [!UICONTROL n’est pas]
   * [!UICONTROL Commence par]
   * [!UICONTROL Se termine par]

1. Saisissez les chaînes qui définissent l’emplacement d’ajout de l’expérience, par exemple le domaine ou les chaînes contenues dans le nom de la page.

   Par exemple, si vous sélectionnez **[!UICONTROL Domaine]** et **[!UICONTROL Est (sensible à la casse)]**, saisissez le domaine dans lequel vous souhaitez que l’expérience soit ajoutée à toutes les pages.

   Vous pouvez inclure plusieurs éléments.

   >[!IMPORTANT]
   >
   >Plusieurs éléments utilisent la logique OR, ce qui signifie que tout élément unique de la liste rend la condition vraie.

1. Si vous le souhaitez, saisissez des critères supplémentaires en cliquant sur **[!UICONTROL Ajouter une règle]** et en répétant la procédure des étapes précédentes.

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

1. Pour spécifier le domaine dans lequel l’expérience s’affiche, dans le [!UICONTROL compositeur d’expérience visuelle] cliquez sur l’icône [!UICONTROL Configurer] ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ), puis sélectionnez **[!UICONTROL Diffusion de page]**.

1. Cliquez sur **[!UICONTROL Ajouter une règle]** > **[!UICONTROL Domaine]**.

1. Dans la liste déroulante **[!UICONTROL Choisir l’évaluateur]**, sélectionnez **[!UICONTROL Contient]**, puis spécifiez le domaine.
