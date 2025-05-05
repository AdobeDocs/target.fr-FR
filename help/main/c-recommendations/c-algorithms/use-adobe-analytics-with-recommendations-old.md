---
keywords: source de données comportementales;analytics;recommandations;critères;variables de produit
description: Découvrez comment utiliser comme source  [!DNL Adobe Analytics]  données comportementales pour utiliser les données comportementales basées sur les vues et/ou les achats depuis [!DNL Analytics] in [!DNL Target Recommendations].
title: Comment puis-je utiliser  [!DNL Adobe Analytics]  avec  [!DNL Target Recommendations] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 1%

---

# Utilisation de [!DNL Adobe Analytics] avec [!DNL Recommendations]

L’utilisation de [!DNL Adobe Analytics] comme source de données comportementales permet aux clients d’utiliser les données comportementales basées sur les vues et/ou les achats des [!DNL Analytics] dans [!DNL Adobe Target] activités [!DNL Recommendations]. Cette fonctionnalité s’avère particulièrement utile dans les cas où la configuration du [!DNL Target Recommendations] est nouvelle et [!DNL Analytics] a beaucoup de données historiques à utiliser.

L’utilisation de [!DNL Analytics] comme source de données comportementales peut constituer une source riche d’informations sur le comportement des utilisateurs et utilisatrices. Ces informations peuvent inclure des données provenant d’une source ou d’un flux tiers partagé uniquement avec [!DNL Analytics].

Lors de la [création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) dans [!DNL Recommendations], deux boutons radio permettent de choisir la source de données à utiliser : [!UICONTROL mboxes] ou [!UICONTROL Analytics]. Pour créer un critère, cliquez sur [!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]. Pour plus d’informations, voir [Création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

![Boutons de source de données comportementaux](assets/behavioral-data-source.png)

>[!NOTE]
>
>Si ces deux boutons ne s’affichent pas dans votre compte, contactez l’[Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Cas d’utilisation des données Analytics dans Target

L’utilisation de [!DNL Analytics] comme source de données comportementales pour les recommandations vous permet également de déployer des cas d’utilisation spécifiques sans avoir à baliser les pages d’entité avec tous les paramètres d’entité [!DNL Target]. Bien que cela implique la mise en place de certaines conditions préalables, la disponibilité des « variables de produit » est la chose la plus importante pour que cette fonctionnalité fonctionne de manière transparente. Des eVars et des props régulières ne suffisent pas pour que cette liaison se produise automatiquement entre [!DNL Analytics] et [!DNL Target].

Vous pouvez utiliser [!DNL Analytics] comme source de données comportementales pour :

* Afficher des recommandations sur un site de vente au détail aux utilisateurs sur une page de détails du produit, en fonction de ce que les autres utilisateurs ont acheté à la même catégorie au cours du dernier mois, à l’aide de données [!DNL Analytics].
* Affichez le contenu sur l’écran d’accueil d’un site multimédia pour le contenu le plus populaire dans une catégorie particulière qui est actuellement en tendance, en fonction des données [!DNL Analytics].

## Mise en œuvre dans [!DNL Analytics]

Les sections suivantes vous aident à implémenter cette fonctionnalité du côté [!DNL Analytics].

### Conditions préalables : configurer des variables de produit dans [!DNL Analytics]

Implémentez des variables de produit en [!DNL Analytics] avec les attributs nécessaires à la [!DNL Target Recommendations].

Un [!DNL Target Recommendations] exemple de format de flux sert de guide sur lequel tous les attributs doivent être définis dans les variables de produit. Par la suite, ces valeurs doivent être « mappées » dans l’interface utilisateur [!DNL Target] pour les valeurs d’entité [!DNL Target] respectives.

>[!NOTE]
>
>S’il s’agit d’un site de contenu, les éléments de contenu respectifs doivent être traités comme des « produits » et les attributs associés à ce contenu doivent être transmis en tant qu’attributs. Ces attributs peuvent inclure le nom de l’auteur, la date de publication, le titre du contenu, le mois de publication, etc. La granularité du niveau de catégorie, ou des types de catégorie, doit être décidée par l’entreprise en fonction des exigences du cas d’utilisation.

Pour plus d’informations sur la configuration des variables de produit, voir [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=fr) dans le guide *Implémentation d’Adobe Analytics*. Certaines des notes de cette documentation nécessitent la discrétion de l’équipe qui la déploie (exemple : Catégorie). Il est toujours conseillé de consulter [!DNL Adobe] avant d’effectuer cette activité.

### Considérations

[!DNL Analytics] données sont envoyées via un flux quotidien. Les résultats comportementaux peuvent prendre jusqu’à 24 heures pour se refléter dans les résultats des recommandations sur votre site. Comme pour tous les paramètres de critères de [!DNL Recommendations], cette source de données peut et doit être testée.

Pour une prise de décision rapide sur la source de données à utiliser, en cas de forte quantité de données organiques générées chaque jour par les utilisateurs et de faible dépendance requise par rapport aux données historiques, l’utilisation d’une mbox [!DNL Target] comme source de données comportementales peut s’avérer pratique. En cas de disponibilité moindre des données organiques générées récemment, si vous souhaitez miser sur des données [!DNL Analytics], l’utilisation de [!DNL Analytics] comme source de données comportementales est une bonne option.

Il est maintenant temps de mapper ces variables du côté [!DNL Target] pour fournir en continu des données comportementales.

## Implémentation dans [!DNL Target]

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Recommendations]**, puis sur l&#39;onglet **[!UICONTROL Feeds]** .

   ![Flux](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Cliquez sur **[!UICONTROL Create Feed]**.

1. Sélectionnez **[!UICONTROL Analytics Classifications]**, puis spécifiez la suite de rapports.

   ![Option Classifications Analytics](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Cliquez sur **[!UICONTROL Next]** pour accéder aux paramètres de **[!UICONTROL Schedule]**, puis sélectionnez une période de fréquence pour le flux :

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   Vous pouvez également sélectionner l’heure du jour à laquelle le flux doit être traité.

1. Cliquez sur **[!UICONTROL Next]** pour accéder aux paramètres de **[!UICONTROL Mapping]**, puis mappez les en-têtes des colonnes de champs aux noms de champs de [!UICONTROL Recommendations] appropriés.

   ![Section de mappage](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. Cliquez sur **[!UICONTROL Save]**.

## Questions fréquentes

Tenez compte des questions fréquentes suivantes lorsque vous utilisez [!DNL Analytics] avec [!DNL Target] :

### Les valeurs `entity.id` et `entity.categoryId` doivent-elles être transmises dans l’appel de mbox [!DNL Target] ?

Oui, ces deux valeurs sont toujours requises. Le reste des attributs peut être transmis via un flux [!DNL Analytics], comme décrit dans ce document.

### Puis-je utiliser des règles d’inclusion dynamiques, telles que les correspondances de paramètres d’entité avec les attributs de profil à l’aide de l’approche de flux [!DNL Analytics] ?

Oui, c&#39;est possible. La méthode est similaire lors de l’utilisation de [!DNL Target] autonome. Dans ce cas, cependant, vous devez être attentif au facteur temps. Les variables d’entité qui sont censées correspondre aux variables de profil dépendent de la couche de données qui peut apparaître beaucoup plus loin sur la page.
