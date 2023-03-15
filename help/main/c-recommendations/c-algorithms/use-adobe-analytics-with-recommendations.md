---
keywords: source de données comportementales;analytics;recommandations;critères;variables de produits
description: Découvrez comment utiliser [!DNL Adobe Analytics] comme source de données comportementales pour utiliser les données comportementales basées sur les vues et/ou basées sur les achats de [!DNL Analytics] in [!DNL Target Recommendations].
title: Comment utiliser [!DNL Adobe Analytics] avec [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# Utilisation [!DNL Adobe Analytics] avec [!DNL Recommendations]

Utilisation [!DNL Adobe Analytics] car la source de données comportementales permet aux clients d’utiliser les données comportementales basées sur les vues et/ou basées sur les achats de [!DNL Analytics] in [!DNL Adobe Target] [!DNL Recommendations] activités. Cette fonctionnalité est particulièrement utile dans les cas où la fonction [!DNL Target Recommendations] la configuration est nouvelle et [!DNL Analytics] contient de nombreuses données historiques à utiliser.

Utilisation [!DNL Analytics] car la source de données comportementales peut agir comme une source d’informations riche sur le comportement des utilisateurs. Ces informations peuvent inclure des données provenant d’une source ou d’un flux tiers qui est partagé uniquement avec [!DNL Analytics].

while [création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) in [!DNL Recommendations], deux boutons radio permettent de choisir la source de données à utiliser : [!UICONTROL mbox] ou [!UICONTROL Analytics]. Pour créer un critère, cliquez sur [!UICONTROL Recommendations] > [!UICONTROL Critères] > [!UICONTROL Création de critères] > [!UICONTROL Création de critères]. Pour plus dʼinformations, consultez la section [Création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

![Boutons de source de données comportementales](assets/behavioral-data-source.png)

>[!NOTE]
>
>Si ces deux boutons ne s’affichent pas dans votre compte, contactez [Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Cas d’utilisation des données Analytics dans Target

Utilisation [!DNL Analytics] en tant que source de données comportementales pour recommendations vous permet également de déployer des cas d’utilisation spécifiques sans devoir baliser les pages d’entité avec tous les [!DNL Target] paramètres d’entité. Bien que cela nécessite la mise en place de certaines conditions préalables, la disponibilité des &quot;variables de produit&quot; est la chose la plus importante pour que cette fonctionnalité fonctionne de manière transparente. Les variables eVar et prop régulières ne sont pas suffisantes pour que cette liaison se produise automatiquement entre [!DNL Analytics] et [!DNL Target].

Vous pouvez utiliser [!DNL Analytics] comme source de données comportementales pour :

* Affichez des recommandations sur un site de vente au détail à l’intention des utilisateurs sur une page des détails d’un produit, en fonction de ce que d’autres utilisateurs ont acheté dans la même catégorie au cours du dernier mois, en utilisant [!DNL Analytics] data.
* Afficher le contenu sur l’écran d’accueil d’un site multimédia pour le contenu le plus populaire d’une catégorie particulière qui est actuellement en tendance, en fonction de [!DNL Analytics] data.

## Mise en oeuvre dans [!DNL Analytics]

Les sections suivantes vous aident à mettre en oeuvre cette fonctionnalité sur la page [!DNL Analytics] côté.

### Conditions préalables : configurer des variables de produit dans [!DNL Analytics]

Mise en oeuvre de variables de produit dans [!DNL Analytics] avec les attributs nécessaires pour [!DNL Target Recommendations].

A [!DNL Target Recommendations] l’exemple de format de flux sert de guide sur lequel tous les attributs doivent être définis dans les variables de produit. Par la suite, ces valeurs doivent être &quot;mappées&quot; dans la variable [!DNL Target] l’interface utilisateur des [!DNL Target] valeurs d’entité.

>[!NOTE]
>
>S’il s’agit d’un site de contenu, les éléments de contenu respectifs doivent être traités comme des &quot;produits&quot; et les attributs associés à ce contenu doivent être transmis en tant qu’attributs. Ces attributs peuvent inclure le nom de l’auteur, la date de publication, le titre du contenu, le mois de publication, etc. La granularité des types de catégorie ou de catégorie doit être décidée par l’entreprise en fonction des besoins du cas d’utilisation.

Pour plus d’informations sur la configuration des variables de produit, voir [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) dans le *Mise en oeuvre d’Adobe Analytics* guide. Certaines notes de cette documentation requièrent la discrétion de l’équipe qui la déploie (exemple : Catégorie). Il est toujours conseillé de consulter [!DNL Adobe] avant d’effectuer cette activité.

### Considérations

[!DNL Analytics] Les données sont envoyées via un flux quotidien. Les résultats comportementaux peuvent prendre jusqu’à 24 heures pour être reflétés dans les résultats de recommandations sur votre site. Comme pour tout [!DNL Recommendations] , cette source de données peut et doit être testée.

Pour une prise de décision rapide concernant la source de données à utiliser, si les utilisateurs génèrent de nombreuses données organiques quotidiennement et qu’ils ne dépendent pas trop des données historiques, utilisez une [!DNL Target] mbox comme source de données comportementales peut s’avérer adapté. Si vous souhaitez utiliser des données organiques moins disponibles récemment, [!DNL Analytics] data, puis l’utilisation de [!DNL Analytics] car la source de données comportementales est adaptée.

Il est maintenant temps de mapper ces variables sur [!DNL Target] côté pour l’approvisionnement continu des données comportementales.

## Mise en oeuvre dans [!DNL Target]

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Recommendations]**, puis cliquez sur le bouton **[!UICONTROL Flux]** .

   ![Flux](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Cliquez sur **[!UICONTROL Création d’un flux]**.

1. Sélectionner **[!UICONTROL Classifications Analytics]**, puis spécifiez la suite de rapports.

   ![Option Classifications Analytics](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder au **[!UICONTROL Planification]** , sélectionnez une période de fréquence pour le flux :

   * [!UICONTROL Quotidien]
   * [!UICONTROL Hebdomadaire]
   * [!UICONTROL Toutes les 2 semaines]
   * [!UICONTROL Jamais]

   Vous pouvez également sélectionner l’heure de la journée du traitement du flux.

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder au  **[!UICONTROL Mappage]** , puis associez les en-têtes de colonne de champ aux [!UICONTROL Recommendations] noms de champ.

   ![Section de mappage](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Questions fréquentes

Tenez compte des questions fréquentes suivantes lorsque vous utilisez [!DNL Analytics] avec [!DNL Target]:

### Sont les `entity.id` et `entity.categoryId` valeurs devant être transmises dans la variable [!DNL Target] appel de mbox ?

Oui, ces deux valeurs sont toujours requises. Le reste des attributs peut être transmis via un [!DNL Analytics] flux, comme décrit dans ce document.

### Puis-je utiliser des règles d’inclusion dynamiques, telles que le paramètre d’entité, correspond aux attributs de profil à l’aide de la variable [!DNL Analytics] approche du flux ?

Oui, vous pouvez. La méthode est similaire lors de l’utilisation de [!DNL Target] autonome. Dans ce cas, toutefois, vous devez être attentif au facteur de minutage. Les variables d’entité censées correspondre aux variables de profil dépendent de la couche de données qui peut apparaître beaucoup plus tard sur la page.
