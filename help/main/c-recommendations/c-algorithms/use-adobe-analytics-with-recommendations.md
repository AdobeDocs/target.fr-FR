---
keywords: source de données comportementales;analytics;recommandations;critères;variables de produit
description: Découvrez comment utiliser [!DNL Adobe Analytics] comme source de données comportementales dans [!DNL Target Recommendations].
title: Utiliser Adobe Analytics avec Recommandations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
TQID: 'https://experienceleague.adobe.com/2ryixOT-YoKjDlMbqs8g2DJElNVmlCUFhbdZzpfSnNs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 374d176c5c40826d958a8b87d220422466433690
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 1%
---
# Utiliser [!DNL Adobe Analytics] avec [!DNL Recommendations] {#use-analytics-with-recommendations}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser [!DNL Adobe Analytics] comme source de données comportementales dans les activités [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

L’utilisation de [!DNL Adobe Analytics] comme source de données comportementales permet aux activités [!DNL Adobe Target Recommendations] d’utiliser les données comportementales basées sur les vues et les achats de [!DNL Analytics]. Cela s’avère utile lorsque la configuration [!DNL Target Recommendations] est nouvelle et que [!DNL Analytics] contient de nombreuses données historiques à utiliser. Les données peuvent également inclure des informations provenant d&#39;une source ou d&#39;un flux tiers partagé uniquement avec [!DNL Analytics].

La source de données est sélectionnée avec l’option **[!UICONTROL Source de données comportementales]** lors de la [création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) dans [!DNL Recommendations] : **[!UICONTROL Adobe Target]** ou **[!UICONTROL Analytics]**.

>[!NOTE]
>
>Si ces deux options ne s&#39;affichent pas dans le compte, contactez l&#39;[Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Cas d’utilisation des données [!DNL Analytics] dans [!DNL Target] {#use-cases}

L’utilisation de [!DNL Analytics] comme source de données comportementales permet également de déployer des cas d’utilisation spécifiques sans baliser les pages d’entité avec tous les paramètres d’entité [!DNL Target]. Cela requiert certaines conditions préalables et la disponibilité des « variables de produit » est la plus importante. Les eVars et les props régulières ne suffisent pas pour que [!DNL Analytics] et [!DNL Target] échangent automatiquement ces données.

[!DNL Analytics] peut être utilisé comme source de données comportementales pour :

* Afficher des recommandations sur un site de vente au détail aux utilisateurs sur une page de détails du produit, en fonction de ce que les autres utilisateurs ont acheté dans la même catégorie au cours du dernier mois, à l&#39;aide de données [!DNL Analytics].
* Affichez le contenu sur l’écran d’accueil d’un site multimédia pour le contenu le plus populaire dans une catégorie particulière qui est actuellement en tendance, en fonction des données [!DNL Analytics].

## Implémentation dans [!DNL Analytics]

### Conditions préalables : configurer les variables de produit dans [!DNL Analytics] {#prerequisites}

Implémentez des variables de produit dans [!DNL Analytics] avec les attributs requis pour [!DNL Target Recommendations]. Un exemple de format de flux [!DNL Target Recommendations] indique les attributs qui doivent être définis dans les variables de produit. Ces valeurs doivent ensuite être « mappées » dans l’interface utilisateur [!DNL Target] aux valeurs d’entité [!DNL Target] respectives.

>[!NOTE]
>
>S’il s’agit d’un site de contenu, les éléments de contenu respectifs doivent être traités comme des « produits » et les attributs associés de ce contenu doivent être transmis en tant qu’attributs. Ces attributs peuvent inclure le nom de l’auteur, la date de publication, le titre du contenu, le mois de publication, etc. L’entreprise doit décider de la granularité du niveau de catégorie, ou des types de catégorie, en fonction des exigences du cas d’utilisation.

Pour plus d’informations sur la configuration des variables de produit, voir [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) dans le guide *Implémentation d’Adobe Analytics*. Certaines des notes de cette documentation, par exemple celle sur la catégorie, nécessitent le jugement de l’équipe qui la déploie. Il est recommandé de consulter [!DNL Adobe] avant cette activité.

### Considérations {#considerations}

Les données [!DNL Analytics] sont envoyées via un flux quotidien. Les résultats comportementaux peuvent prendre jusqu’à 24 heures pour se refléter dans les résultats des recommandations sur le site. Comme pour tous les paramètres de critère [!DNL Recommendations], cette source de données doit être testée.

Pour choisir une source de données :

* Une mbox [!DNL Target] convient parfaitement lorsque de nombreuses données organiques sont générées chaque jour par les utilisateurs et qu’une faible dépendance aux données historiques est requise.
* [!DNL Analytics] convient lorsque moins de données organiques ont été générées récemment et que les données [!DNL Analytics] doivent être utilisées.

Les valeurs `entity.id` et `entity.categoryId` doivent toujours être transmises dans l’appel de mbox [!DNL Target]. Les autres attributs peuvent être transmis par un flux [!DNL Analytics], comme décrit sur cette page.

Les règles d’inclusion dynamique, telles que la correspondance d’un paramètre d’entité à un attribut de profil, peuvent être utilisées avec l’approche de flux [!DNL Analytics]. La méthode est similaire à l’utilisation de [!DNL Target] en mode autonome, mais le timing doit être pris en compte : les variables d’entité qui sont censées correspondre aux variables de profil dépendent de la couche de données, qui peut apparaître beaucoup plus tard sur la page.

## Implémentation dans [!DNL Target] {#implement-target}

Les variables de produit sont mappées dans [!DNL Target] pour fournir un approvisionnement continu de données comportementales.

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Recommendations]**, puis sur l’onglet **[!UICONTROL Flux]**.

1. Cliquez Sur **[!UICONTROL Créer Un Flux]**.

   ![Page de flux avec le bouton Créer un flux en surbrillance](../assets/feeds_1.png)

1. Sélectionnez **[!UICONTROL Classifications Analytics]**, puis spécifiez la suite de rapports.

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder aux paramètres **[!UICONTROL Planification]**, puis sélectionnez une fréquence pour le flux : **[!UICONTROL Quotidienne]**, **[!UICONTROL Hebdomadaire]**, **[!UICONTROL Toutes les 2 semaines]** ou **[!UICONTROL Jamais]**. Vous pouvez également sélectionner l’heure de la journée à laquelle le flux doit être traité.

   ![Étape Planifier de la boîte de dialogue Créer un flux avec les options Fréquence Quotidienne, Hebdomadaire, Toutes les 2 semaines et Jamais, et le champ Heure de la journée](../assets/feeds_3.png)

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder aux paramètres **[!UICONTROL Mappage]**, puis mappez les en-têtes des colonnes de champs aux noms de champs **[!UICONTROL Recommendations]** appropriés.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour plus d’informations sur la création d’un flux, voir [Créer un flux](/help/main/c-recommendations/c-products/feeds.md#steps).
