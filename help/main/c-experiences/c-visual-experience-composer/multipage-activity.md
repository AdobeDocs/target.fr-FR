---
keywords: multi-page, test du parcours, activité multi-page
description: Découvrez comment créer une activité multipage dans Adobe [!DNL Target]. Vous pouvez ainsi créer une histoire sur plusieurs pages, avec une conception spécifique à chaque page.
title: Comment créer une activité multipage ?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
TQID: 'https://experienceleague.adobe.com/ZFqgbNp-sLF-ahG-uXKvWY0XPcxO0oZScGkpNX8hDHY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
    internal-label: Mobile experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 13%
---
# Activité multi-page {#multipage-activity}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser une activité multipage pour créer une histoire sur plusieurs pages, avec une conception spécifique à chaque page.

>[!ENDSHADEBOX]

Une activité multipage dans [!DNL Adobe Target] crée une histoire sur plusieurs pages, avec une conception spécifique à chaque page.

Par exemple, une offre de livraison gratuite avec des achats supérieurs à un certain montant peut être testée. L’offre peut apparaître sur la page de destination, sur une page de catégorie et sur certaines pages de produits, avec une taille différente et à un emplacement différent sur chaque type de page. Une offre importante peut être affichée sur la page d’accueil, puis renforcée par des offres plus petites sur d’autres pages pertinentes.

Une activité multipage peut également définir différentes dispositions pour les sites de bureau et les sites mobiles qui ne répondent pas. Si le site comporte un site mobile distinct, tel que [!DNL m.mysite.com] au lieu de [!DNL `www.mysite.com`], créez une activité multipage, ajoutez [!DNL m.mysite.com] en tant que pages distinctes, puis appliquez la modification pour appareils mobiles afin d’apporter les modifications appropriées à la version de bureau et à la version pour appareils mobiles dans la même expérience. Pour les sites mobiles réactifs, utilisez [la modification de l’expérience mobile](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

>[!NOTE]
>
>Les activités multi-page sont conçues pour des activités pour lesquelles la même offre a une apparence différente sur plusieurs pages. Si l’offre apparaît de la même manière sur toutes les pages, un [test de modèle](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages) est plus efficace.

Les règles de modèle peuvent être spécifiées pour chaque page dans le test de plusieurs pages. Par exemple, un test de plusieurs pages peut s’exécuter sur la page d’accueil et toutes les pages de catégorie en appliquant des règles de modèle à la page de catégorie du test de plusieurs pages. Voir [Inclure la même expérience sur des pages similaires](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages).

## Ajouter des pages à une activité {#add-pages}

Chaque page ajoutée à l’activité peut avoir sa propre conception de l’offre.

1. Cliquez sur l’icône **[!UICONTROL Configurer]** ( ![Icône Configurer](/help/main/assets/icons/Setting.svg) ).

1. Cliquez sur **[!UICONTROL Ajouter des pages supplémentaires]**.

   Un volet **[!UICONTROL Pages]** s’affiche à gauche de l’écran.

   ![Icône Configurer](assets/vec_edit_4.png)

1. Spécifiez les pages et définissez la page par défaut.

   Cliquez sur **[!UICONTROL Ajouter une page]** ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ) pour ajouter une page supplémentaire, spécifiez le nom de la page et l’URL, puis cliquez sur **[!UICONTROL Enregistrer]**.

1. Utilisez le [!UICONTROL compositeur d’expérience visuelle] pour concevoir l’apparence de l’offre sur chaque page.
