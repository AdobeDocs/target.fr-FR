---
keywords: catalog;search
description: La recherche catalogue dans Adobe Target vous aide à localiser les produits ou le contenu dans votre catalogue.
title: Recherche catalogue dans Adobe Target
feature: catalog
uuid: e0876963-5905-4850-a615-953e435f26e9
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 96%

---


# ![Premium](/help/assets/premium.png) recherche catalogue{#catalog-search}

La recherche catalogue vous aide à localiser les produits ou le contenu dans votre catalogue.

To access catalog search, click **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

Vous pouvez affiner votre recherche en sélectionnant une option de recherche dans le menu d’options qui s’affiche lorsque vous cliquez sur la flèche vers le bas dans le champ de recherche.

![](assets/searchproductsmenu.png)

Les options de recherche disponibles sont les suivantes :

* TOUT
* Nom
* Marque
* Catégorie
* ID
* Message

L’option **[!UICONTROL TOUT]** effectue une recherche selon tous les autres critères de recherche, à l’aide de la logique OU.

Dans les résultats de recherche, cliquez sur l’**[!UICONTROL environnement]** pour indiquer l’environnement du groupe d’hôtes de production dont vous affichez le catalogue. [](/help/administrating-target/hosts.md) Vous pouvez également faire défiler les éléments des résultats de recherche afin d’afficher des miniatures et d’autres informations sur les produits.

Le nombre qui s’affiche en regard de « Produits » est le nombre de produits qui correspondent au terme de recherche, sur le total disponible dans l’environnement spécifié.

Le catalogue est automatiquement actualisé lorsque des mises à jour sont reçues via des fichiers de flux, des API ou des mises à jour de mbox. Les mises à jour sont généralement effectuées en une heure. Si des mises à jour sont en cours, l’heure de début de la mise à jour la plus récente s’affiche. Si aucune mise à jour n’est en cours, l’heure de début et de fin de la mise à jour la plus récente s’affiche.

## Création d’une collection ou d’une exclusion à l’aide de la recherche avancée

Vous pouvez créer des [collections](/help/c-recommendations/c-products/collections.md) ou des [exclusions](/help/c-recommendations/c-products/exclusions.md) à l’aide de la fonctionnalité de recherche avancée de la page de recherche catalogue ([!UICONTROL Recommandations] > [!UICONTROL Recherche catalogue] > [!UICONTROL Recherche avancée]).

![Enregistrer sous, boîte de dialogue](/help/c-recommendations/c-products/assets/save-as-dialog.png)

Après avoir créé une recherche avec « id > contient », par exemple, vous pouvez cliquer sur [!UICONTROL Enregistrer sous] > [!UICONTROL Collection ou Exclusion.]

>[!IMPORTANT]
>
>La fonctionnalité de recherche avancée n’est pas sensible à la casse ; cependant, les produits renvoyés lors de la diffusion sont basés sur une recherche sensible à la casse. Cette incohérence peut prêter à confusion. Veillez à tenir compte du respect de la casse lorsque vous créez des collections ou des exclusions sur la base de résultats obtenus à l’aide de la fonctionnalité de recherche avancée. Par exemple, si vous effectuez une recherche portant sur « Vacances », cette recherche initiale répertorie les résultats contenant « Vacances » et « vacances ». Si vous créez ensuite un catalogue avec l’intention de renvoyer les produits contenant « vacances », seuls les produits contenant « vacances » sont renvoyés. Les produits contenant « Vacances » ne sont pas renvoyés. Les exclusions sont traitées de façon similaire.
