---
keywords: source de données comportementales;analytics;recommandations;critères;variables de produits
description: Découvrez comment utiliser  [!DNL Adobe Analytics] comme source de données comportementales pour utiliser les données comportementales basées sur les vues et/ou basées sur les achats de  [!DNL Analytics] dans [!DNL Target Recommendations].
title: Comment utiliser [!DNL Adobe Analytics] avec [!DNL Target Recommendations] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 1%

---

# Utilisation de [!DNL Adobe Analytics] avec [!DNL Recommendations]

L’utilisation de [!DNL Adobe Analytics] comme source de données comportementales permet aux clients d’utiliser les données comportementales basées sur les vues et/ou basées sur les achats provenant de [!DNL Analytics] dans les activités [!DNL Adobe Target] [!DNL Recommendations]. Cette fonctionnalité est particulièrement utile dans les situations où la configuration [!DNL Target Recommendations] est nouvelle et où [!DNL Analytics] contient de nombreuses données historiques à utiliser.

L’utilisation de [!DNL Analytics] comme source de données comportementales peut agir comme une source d’informations riche sur le comportement des utilisateurs. Ces informations peuvent inclure des données provenant d’une source ou d’un flux tiers qui est partagé uniquement avec [!DNL Analytics].

Lors de la [création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) dans [!DNL Recommendations], deux boutons radio permettent de choisir la source de données à utiliser : [!UICONTROL mboxes] ou [!UICONTROL Analytics]. Pour créer un critère, cliquez sur [!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]. Pour plus d’informations, voir [Création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

![Boutons de source de données comportementales](assets/behavioral-data-source.png)

>[!NOTE]
>
>Si ces deux boutons ne s’affichent pas dans votre compte, contactez l’ [assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Cas d’utilisation des données Analytics dans Target

L’utilisation de [!DNL Analytics] comme source de données comportementales pour les recommandations vous permet également de déployer des cas d’utilisation spécifiques sans avoir à baliser les pages d’entités avec tous les paramètres d’entité [!DNL Target]. Bien que cela nécessite la mise en place de certaines conditions préalables, la disponibilité des &quot;variables de produit&quot; est la chose la plus importante pour que cette fonctionnalité fonctionne de manière transparente. Les eVars et les props régulières ne sont pas suffisantes pour que cette liaison se produise automatiquement entre [!DNL Analytics] et [!DNL Target].

Vous pouvez utiliser [!DNL Analytics] comme source de données comportementales pour :

* Affichez des recommandations sur un site de vente au détail aux utilisateurs sur une page des détails d’un produit, en fonction des achats d’autres utilisateurs de la même catégorie au cours du dernier mois, à l’aide des données [!DNL Analytics].
* Affichez le contenu sur l’écran d’accueil d’un site multimédia pour le contenu le plus populaire d’une catégorie particulière qui est actuellement en tendance, en fonction des données [!DNL Analytics].

## Mise en oeuvre dans [!DNL Analytics]

Les sections suivantes vous aident à mettre en oeuvre cette fonctionnalité du côté [!DNL Analytics].

### Conditions préalables : configuration de variables de produit dans [!DNL Analytics]

Mettez en oeuvre des variables de produit dans [!DNL Analytics] avec les attributs nécessaires pour [!DNL Target Recommendations].

Un format d’exemple de flux [!DNL Target Recommendations] sert de guide sur lequel tous les attributs doivent être définis dans les variables de produit. Par la suite, ces valeurs doivent être &quot;mappées&quot; dans l’interface utilisateur [!DNL Target] pour les valeurs d’entité [!DNL Target] respectives.

>[!NOTE]
>
>S’il s’agit d’un site de contenu, les éléments de contenu respectifs doivent être traités comme des &quot;produits&quot; et les attributs associés à ce contenu doivent être transmis en tant qu’attributs. Ces attributs peuvent inclure le nom de l’auteur, la date de publication, le titre du contenu, le mois de publication, etc. La granularité des types de catégorie ou de catégorie doit être décidée par l’entreprise en fonction des besoins du cas d’utilisation.

Pour plus d’informations sur la configuration des variables de produit, voir [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) dans le guide *Mise en oeuvre d’Adobe Analytics*. Certaines notes de cette documentation requièrent la discrétion de l’équipe qui la déploie (exemple : Catégorie). Il est toujours conseillé de consulter [!DNL Adobe] avant d’effectuer cette activité.

### Considérations

Les données [!DNL Analytics] sont envoyées via un flux quotidien. Les résultats comportementaux peuvent prendre jusqu’à 24 heures pour être reflétés dans les résultats de recommandations sur votre site. Comme avec tous les paramètres de critère [!DNL Recommendations], cette source de données peut et doit être testée.

Pour une prise de décision rapide sur la source de données à utiliser, si de nombreuses données organiques sont générées chaque jour par les utilisateurs et qu’il n’est pas nécessaire de dépendre beaucoup des données historiques, l’utilisation d’une mbox [!DNL Target] comme source de données comportementales peut s’avérer adaptée. Dans les cas où la disponibilité des données organiques générées récemment est moindre, si vous souhaitez utiliser des données [!DNL Analytics], l’utilisation de [!DNL Analytics] comme source de données comportementales est une bonne option.

Il est maintenant temps de mapper ces variables du côté [!DNL Target] pour assurer un approvisionnement continu des données comportementales.

## Implémentation dans [!DNL Target]

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Recommendations]**, puis sur l’onglet **[!UICONTROL Feeds]** .

   ![Flux](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Cliquez sur **[!UICONTROL Create Feed]**.

1. Sélectionnez **[!UICONTROL Analytics Classifications]**, puis spécifiez la suite de rapports.

   ![Option de classifications Analytics](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Cliquez sur **[!UICONTROL Next]** pour passer aux paramètres **[!UICONTROL Schedule]**, puis sélectionnez une période de fréquence pour le flux :

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   Vous pouvez également sélectionner l’heure de la journée du traitement du flux.

1. Cliquez sur **[!UICONTROL Next]** pour passer aux paramètres **[!UICONTROL Mapping]**, puis mappez les en-têtes de colonne de champ aux noms de champ [!UICONTROL Recommendations] appropriés.

   ![Section de mappage](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. Cliquez sur **[!UICONTROL Save]**.

## Questions fréquentes

Tenez compte des questions fréquentes suivantes lorsque vous utilisez [!DNL Analytics] avec [!DNL Target] :

### Les valeurs `entity.id` et `entity.categoryId` doivent-elles être transmises dans l’appel de mbox [!DNL Target] ?

Oui, ces deux valeurs sont toujours requises. Le reste des attributs peut être transmis via un flux [!DNL Analytics], comme décrit dans ce document.

### Puis-je utiliser des règles d’inclusion dynamiques, telles que le paramètre d’entité, correspond aux attributs de profil en utilisant l’approche de flux [!DNL Analytics] ?

Oui, vous pouvez. La méthode est similaire lors de l’utilisation de [!DNL Target] autonome. Dans ce cas, toutefois, vous devez être attentif au facteur de minutage. Les variables d’entité censées correspondre aux variables de profil dépendent de la couche de données qui peut apparaître beaucoup plus tard sur la page.
