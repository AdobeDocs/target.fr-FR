---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: L’utilisation de Adobe Analytics comme source de données comportementales permet aux clients d’utiliser les données comportementales basées sur les vues et/ou les achats d’Analytics dans Adobe Recommendations.
title: Utilisation de Adobe Analytics avec Cible Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 3%

---


# Utiliser Adobe Analytics avec Recommendations

L’utilisation de [!DNL Adobe Analytics] comme source de données comportementales permet aux clients d’utiliser les données comportementales basées sur les vues et/ou les achats de [!DNL Analytics] dans les activités de recommandations [!DNL Adobe Target]. Cette fonctionnalité est particulièrement utile dans les situations où la configuration de [!DNL Target Recommendations] est nouvelle et où [!DNL Analytics] dispose de nombreuses données historiques à exploiter.

L&#39;utilisation de [!DNL Analytics] comme source de données comportementales peut constituer une source d&#39;informations riche sur le comportement des utilisateurs. Cela peut inclure des données provenant d’une source ou d’un flux tiers qui est partagé uniquement avec [!DNL Analytics].

Bien que [la création de critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md) ait lieu à Recommendations, deux boutons radio permettent de choisir la source de données à utiliser : [!UICONTROL mbox] ou [!UICONTROL Analytics].

![Boutons de source de données comportementaux](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Si ces deux boutons ne s’affichent pas dans votre compte, contactez le [service à la clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Cas d’utilisation des données Analytics dans la Cible

L&#39;utilisation de [!DNL Analytics] en tant que source de données comportementales pour les recommandations permet également de déployer des cas d&#39;utilisation spécifiques sans devoir baliser les pages d&#39;entité avec tous les paramètres d&#39;entité [!DNL Target]. Bien que cela exige la mise en place de certaines conditions préalables, la disponibilité des &quot;variables de produit&quot; est la chose la plus importante pour que cette fonctionnalité fonctionne de manière transparente. Les eVars et les props régulières ne sont pas suffisantes pour que cette poignée de main se produise automatiquement entre [!DNL Analytics] et [!DNL Target].

Vous pouvez utiliser [!DNL Analytics] comme source de données comportementales pour :

* Affichez les recommandations sur un site de vente au détail à l’intention des utilisateurs d’une page PDP, en fonction de ce que d’autres utilisateurs ont acheté à la même catégorie le mois dernier, à l’aide des données Analytics.
* Affichez le contenu sur l’écran d’accueil d’un site multimédia pour le contenu le plus populaire dans une catégorie donnée qui est actuellement en tendance, en fonction de données [!DNL Analytics].

## Mise en oeuvre dans Analytics

Les sections suivantes vous aideront à mettre en oeuvre cette fonctionnalité du côté [!DNL Analytics].

### Conditions préalables : configuration de variables de produit dans Analytics

Vous devez implémenter des variables de produit dans [!DNL Analytics] avec les attributs nécessaires pour [!DNL Target Recommendations].

Un exemple de format de flux [!DNL Target Recommendations] servira de guide pour déterminer quels attributs doivent être définis dans les variables de produit. Par la suite, ces valeurs doivent être &quot;mappées&quot; dans l&#39;interface utilisateur [!DNL Target] pour les valeurs d&#39;entité [!DNL Target] respectives.

>[!NOTE]
>
>S&#39;il s&#39;agit d&#39;un site de contenu, les éléments de contenu respectifs doivent être traités comme des &quot;produits&quot; et les attributs associés à ce contenu (par exemple : nom de l’auteur, date de publication, titre du contenu, mois de publication, etc.) doit être transmis en tant qu’attributs. La granularité du niveau de catégorie, ou type de catégorie, doit être décidée par l&#39;entreprise en fonction des besoins de cas d&#39;utilisation.

Pour plus d’informations sur la configuration des variables de produit, voir [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) dans le *Guide de mise en oeuvre d’Analytics*. Certaines notes de cette documentation nécessitent la discrétion de l’équipe qui la déploie (exemple : Catégorie). Il est toujours conseillé de consulter l&#39;Adobe avant de faire cette activité.

### Considérations

[!DNL Analytics] les données sont envoyées via un flux quotidien. Les résultats comportementaux peuvent prendre jusqu’à 24 heures pour être reflétés dans les résultats des recommandations sur votre site. Comme pour tous les paramètres de critères [!DNL Recommendations], cette source de données peut et doit être testée.

Pour une prise de décision rapide sur la source de données à utiliser, s’il y a beaucoup de données organiques générées chaque jour par les utilisateurs et qu’il n’y a pas beaucoup de dépendance à l’égard des données historiques, l’utilisation d’une mbox [!DNL Target] comme source de données comportementales peut s’avérer une bonne solution. Dans les cas où la disponibilité des données organiques récemment générées est moindre, si vous souhaitez utiliser des données [!DNL Analytics], l&#39;utilisation de [!DNL Analytics] comme source de données comportementales est une bonne solution.

### Procédure de déploiement

En supposant que toutes les conditions préalables soient réunies, l&#39;équipe [!DNL Adobe Target Recommendations] doit exécuter les tâches suivantes :

>[!IMPORTANT]
>
>Les étapes ci-dessous sont fournies à titre indicatif uniquement. Un membre de l&#39;équipe [!DNL Recommendations] doit actuellement effectuer ces étapes. [Contactez l’assistance clientèle pour en savoir plus.](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** pour acquérir votre [!DNL Target] code client.

   ![Code client](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. Achetez votre suite de rapports [!DNL Analytics].

   Utilisez la suite de rapports de votre site de production [!DNL Analytics]. Il s’agit de la suite de rapports qui suit le site sur lequel vous avez déployé [!DNL Recommendations].

1. Dans [!DNL Analytics], cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Flux de données]**.

   ![Configuration > Flux de données](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Cliquez sur **[!UICONTROL Ajouter]** pour créer un flux.

   ![Ajouter le flux](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. Renseignez les informations du flux :

   * **Nom** : Flux de produit Recs
   * **Report Suite** : Votre suite de rapports prédéterminée
   * **Courriel** : Spécifiez l’adresse appropriée d’un utilisateur administrateur.
   * **Intervalle** de flux : Sélectionner l’intervalle de votre choix
   * **Traitement** du délai : Pas de délai.
   * **Dates** de début et de fin : Alimentation continue

   ![Section d’informations sur les flux](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Renseignez les détails de la section **[!UICONTROL Destination]** :

   >[!NOTE]
   > 
   >Consultez l&#39;équipe [!DNL Adobe Analytics] avant de procéder à cette étape.

   * **Type** : FTP
   * **Host**: `xxx.yyy.com`
   * **Chemin** : Votre code  [!DNL Target] client
   * **Nom d&#39;utilisateur** : Indiquez votre nom d’utilisateur
   * **Mot de passe** : Indiquez votre mot de passe

   La capture d&#39;écran est utilisée à titre de référence uniquement. Les informations d’identification de votre déploiement seront différentes. Consultez l’équipe [!DNL Adobe Analytics] ou le service à la clientèle lors de cette étape.

   ![Section de destination](/help/c-recommendations/c-algorithms/assets/destination.png)

1. Renseignez les définitions de **[!UICONTROL Colonne de données]** :

   * **Format** de compression : Gzip
   * **Type** de groupement : Fichier unique
   * **Manifeste:** Fin du fichier

      ![Paramètres Format de compression, Type de groupement et Manifeste](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **Colonnes incluses**:

      >[!IMPORTANT]
      >
      >Les colonnes doivent être ajoutées dans le même ordre que celui indiqué ici. Sélectionnez les colonnes dans l’ordre suivant et cliquez sur **[!UICONTROL Ajouter]** pour chaque colonne.

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   ![Section des définitions de colonne de données](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

Ainsi, la configuration sur le côté [!DNL Analytics] est terminée. Il est maintenant temps de mettre en correspondance ces variables du côté [!DNL Target] pour une fourniture continue de données comportementales.

## Mise en oeuvre dans Cible

1. Dans Cible, cliquez sur **[!UICONTROL Recommendations]**, puis sur l’onglet **[!UICONTROL Flux]**.

   ![Flux](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Cliquez sur **[!UICONTROL Créer le flux]**.

1. Sélectionnez **[!UICONTROL Classifications Analytics]**, puis spécifiez la suite de rapports.

   ![Option Classifications Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Cliquez sur **[!UICONTROL Mappage]**, puis mappez les en-têtes de colonne de champ aux noms de champ [!UICONTROL Recommendations] appropriés.

   ![Section de mappage](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Questions fréquentes 

Tenez compte des questions fréquentes suivantes lorsque vous utilisez [!DNL Analytics] avec [!DNL Target] :

### Les valeurs `entity.id` et `entity.categoryId` doivent-elles être transmises dans l’appel de mbox [!DNL Target] ?

Oui, ces deux valeurs sont toujours requises. Le reste des attributs peut être transmis via un flux [!DNL Analytics], comme expliqué dans ce document.

### Puis-je utiliser des règles d’inclusion dynamique, telles que le paramètre d’entité correspond aux attributs de profil en utilisant l’approche de flux [!DNL Analytics] ?

Oui, vous pouvez. La méthode est similaire lorsque vous utilisez [!DNL Target] autonome. Dans ce cas, cependant, vous devez être attentif au facteur de timing. Les variables d’entité censées correspondre aux variables de profil dépendent de la couche de données qui peut apparaître bien plus tard sur la page.

