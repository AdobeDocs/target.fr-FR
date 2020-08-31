---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: L’utilisation de Adobe Analytics comme source de données comportementales permet aux clients d’utiliser les données comportementales basées sur les vues et/ou les achats d’Analytics dans Adobe Recommendations.
title: Utilisation de Adobe Analytics avec Cible Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 9bf30d6397fefdc85e51e2bd431ba163b10f6c09
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 1%

---


# Utiliser Adobe Analytics avec Recommendations

L’utilisation [!DNL Adobe Analytics] en tant que source de données comportementales permet aux clients d’utiliser les données comportementales basées sur les vues et/ou les achats provenant [!DNL Analytics] des activités [!DNL Adobe Target] de recommandations. Cette fonctionnalité est particulièrement utile dans les situations où la [!DNL Target Recommendations] configuration est nouvelle et [!DNL Analytics] dispose de nombreuses données historiques à exploiter.

L’utilisation [!DNL Analytics] de la source de données comportementales peut constituer une source d’informations riche sur le comportement des utilisateurs. Cela peut inclure des données provenant d’une source ou d’un flux tiers qui est partagé uniquement avec [!DNL Analytics].

Lors de la [création de critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md) dans Recommendations, deux boutons radio permettent de choisir la source de données à utiliser : [!UICONTROL mbox] ou [!UICONTROL Analytics].

![Boutons de source de données comportementaux](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Si ces deux boutons ne s’affichent pas dans votre compte, contactez le service à la [clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Cas d’utilisation

L’utilisation [!DNL Analytics] en tant que source de données comportementales pour les recommandations permet également de déployer des cas d’utilisation spécifiques sans devoir baliser les pages d’entité avec tous les paramètres [!DNL Target] d’entité. Bien que cela exige la mise en place de certaines conditions préalables, la disponibilité des &quot;variables de produit&quot; est la chose la plus importante pour que cette fonctionnalité fonctionne de manière transparente. Les variables eVar et Props régulières ne sont pas suffisantes pour que cette poignée de main se produise automatiquement entre [!DNL Analytics] et [!DNL Target].

Vous pouvez utiliser [!DNL Analytics] comme source de données comportementales pour :

* Affichez les recommandations sur un site de vente au détail à l’intention des utilisateurs d’une page PDP, en fonction de ce que d’autres utilisateurs ont acheté à la même catégorie le mois dernier, à l’aide des données Analytics.
* Affichez le contenu sur l’écran d’accueil d’un site multimédia pour le contenu le plus populaire dans une catégorie donnée qui est actuellement en tendance, en fonction des [!DNL Analytics] données.

## Mise en oeuvre dans Analytics

Les sections suivantes vous aideront à mettre en oeuvre cette fonctionnalité sur le [!DNL Analytics] côté.

### Conditions préalables : variables de produit dans Analytics

Vous devez implémenter des variables de produit dans [!DNL Analytics] les attributs nécessaires pour [!DNL Target Recommendations].

Un [!DNL Target Recommendations] exemple de format de flux servira de guide sur lequel tous les attributs doivent être définis dans les variables de produit. Par la suite, ces valeurs doivent être &quot;mappées&quot; dans l’ [!DNL Target] interface utilisateur pour les valeurs [!DNL Target] d’entité respectives.

>[!NOTE]
>
>S&#39;il s&#39;agit d&#39;un site de contenu, les éléments de contenu respectifs doivent être traités comme des &quot;produits&quot; et les attributs associés à ce contenu (par exemple : nom de l’auteur, date de publication, titre du contenu, mois de publication, etc.) doit être transmis en tant qu’attributs. La granularité du niveau de catégorie, ou type de catégorie, doit être décidée par l&#39;entreprise en fonction des besoins de cas d&#39;utilisation.

Pour plus d’informations sur la configuration des variables de produit, voir [products](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/products.html) dans le Guide *de mise en oeuvre d’* Analytics. Certaines notes de cette documentation nécessitent la discrétion de l’équipe qui la déploie (exemple : Catégorie). Il est toujours conseillé de consulter l&#39;Adobe avant de faire cette activité.

### Considérations

[!DNL Analytics] les données sont envoyées via un flux quotidien. Les résultats comportementaux peuvent prendre jusqu’à 24 heures pour être reflétés dans les résultats des recommandations sur votre site. Comme pour tous les paramètres [!DNL Recommendations] de critères, cette source de données peut et doit être testée.

Pour une prise de décision rapide sur la source de données à utiliser, s’il y a beaucoup de données organiques générées chaque jour par les utilisateurs et qu’il n’y a pas beaucoup de dépendance à l’égard des données historiques, l’utilisation d’une [!DNL Target] mbox comme source de données comportementales peut s’avérer une bonne solution. Dans les cas où la disponibilité des données organiques récemment générées est moindre, si vous voulez sauvegarder sur [!DNL Analytics] des données, l&#39;utilisation [!DNL Analytics] comme source de données comportementales est une bonne solution.

### Contactez le service à la clientèle pour que le flux de données soit créé pour vous.

En supposant que toutes les conditions préalables requises soient en place, contactez le service à la [clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’un flux de données soit créé pour vous.

## Mise en oeuvre dans Cible

1. Dans Cible, cliquez sur **[!UICONTROL Recommendations]**, puis sur l’onglet **[!UICONTROL Flux]** .

   ![Flux](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Cliquez sur **[!UICONTROL Créer un flux]**.

1. Sélectionnez Classifications **** Analytics, puis spécifiez la suite de rapports.

   ![Option Classifications Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Cliquez sur **[!UICONTROL Mappage]**, puis mappez les en-têtes de colonne de champ aux noms de champ [!UICONTROL Recommendations] appropriés.

   ![Section de mappage](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Questions fréquentes 

Tenez compte des questions fréquentes suivantes comme vous l&#39;utilisez [!DNL Analytics] avec [!DNL Target]:

### Les valeurs `entity.id` et `entity.categoryId` les valeurs doivent-elles être transmises dans l’appel de [!DNL Target] mbox ?

Oui, ces deux valeurs sont toujours requises. Le reste des attributs peut être transmis via un [!DNL Analytics] flux, comme expliqué dans ce document.

### Puis-je utiliser des règles d’inclusion dynamiques, telles que le paramètre d’entité correspond à des attributs de profil en utilisant l’approche de [!DNL Analytics] flux ?

Oui, vous pouvez. La méthode est similaire lors de l’utilisation de la méthode [!DNL Target] autonome. Dans ce cas, cependant, vous devez être attentif au facteur de timing. Les variables d’entité censées correspondre aux variables de profil dépendent de la couche de données qui peut apparaître bien plus tard sur la page.

