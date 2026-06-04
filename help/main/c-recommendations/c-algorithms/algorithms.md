---
keywords: recommendations;activité recommendations;critères;algorithme;clé de recommandation;clé personnalisée;secteur vertical;vente au détail;commerce électronique;génération de pistes;b2b;services financiers;médias;publication
description: Découvrez comment utiliser les critères dans  [!DNL Target] [!DNL Recommendations].
title: Comment utiliser les critères dans Recommendations  [!DNL Target]  ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 657
ht-degree: 7%

---

# [!UICONTROL Critères]

[!UICONTROL Critères] dans [!DNL Adobe Target] [!DNL Recommendations] sont des règles qui déterminent quels produits ou contenus recommander selon un ensemble prédéterminé de comportements de visiteurs. Les critères peuvent être basés sur des tendances populaires, les comportements actuel et passé d’un visiteur ou des produits et contenus similaires. Vous pouvez tester plusieurs types de recommandations les uns par rapport aux autres en ajoutant plusieurs critères.

Les sections suivantes en disent plus sur les clés de critère et la logique de recommandation que vous pouvez utiliser pour chaque clé. Cliquez sur les liens pour obtenir des informations plus détaillées.

## Secteur industriel vertical {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Lors de la création d’un critère, vous sélectionnez un secteur vertical en fonction des objectifs de votre activité Recommendations .

| Secteur industriel vertical | Objectif |
|--- |--- |
| [!UICONTROL Vente Au Détail/E-Commerce] | Conversion entraînant un achat |
| [!UICONTROL Génération de piste/B2B/Services financiers] | Conversion sans achat |
| [!UICONTROL Média/Publication] | Engagement |

Les autres options de critères changent en fonction du secteur vertical que vous sélectionnez. Vous pouvez définir le secteur industriel vertical par défaut sur la page **[!UICONTROL Administration] > [!UICONTROL Recommandations]** ou spécifier le secteur industriel vertical pour chaque critère.

## Type d’algorithme {#section_885B3BB1B43048A88A8926F6B76FC482}

Le type d’algorithme que vous sélectionnez détermine les algorithmes disponibles.

Le tableau suivant explique les différents types d’algorithmes et les algorithmes associés.

| Type d’algorithme | Quand l’utiliser | Algorithmes disponibles |
| --- | --- | --- |
| [!UICONTROL Basé sur le panier] | Faites des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>[!UICONTROL Les personnes qui les ont consultés l’ont également consulté]</li><li>[!UICONTROL Les Personnes Qui Les Ont Consultés Ont Également Acheté]</li><li>[!UICONTROL Les personnes qui ont acheté ces produits ont également acheté]</li></ul>Pour plus d’informations, voir [Basé sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) dans *Baser la recommandation sur une clé de recommandation*. |
| [!UICONTROL Basé sur la popularité] | Faites des recommandations en fonction de la popularité globale d’un élément sur votre site ou en fonction de la popularité des éléments dans la catégorie, la marque, le genre préféré ou le plus consulté d’un utilisateur, etc. | <ul><li>[!UICONTROL Les plus consultés sur le site]</li><li>[!UICONTROL Les plus consultés par catégorie]</li><li>[!UICONTROL Éléments les plus consultés par attribut d’élément]</li><li>[!UICONTROL Meilleurs vendeurs sur le site]</li><li>[!UICONTROL Meilleurs vendeurs par catégorie]</li><li>[!UICONTROL Meilleurs vendeurs par attribut d&#39;article]</li><li>[!UICONTROL En tête par mesure Analytics]</li></ul> |
| [!UICONTROL Basé sur un élément] | Faites des recommandations basées sur la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>[!UICONTROL Les personnes qui ont consulté ceci ont consulté cela]</li><li>[!UICONTROL Les personnes qui ont consulté ceci ont acheté cela]</li><li>[!UICONTROL Les personnes qui ont acheté ceci ont acheté cela]</li><li>[!UICONTROL Éléments avec des attributs similaires]</li></ul> |
| [!UICONTROL Basé sur l’utilisateur] | Faites des recommandations basées sur le comportement de l’utilisateur. | <ul><li>[!UICONTROL Éléments récemment consultés]</li><li>[!UICONTROL Recommandé]</li></ul> |
| [!UICONTROL Critères personnalisés] | Faites des recommandations basées sur un fichier personnalisé que vous téléchargez. | <ul><li>Algorithme personnalisé</li></ul> |

Pour plus d’informations sur chaque algorithme, voir [Baser la recommandation sur une clé de recommandation](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Utilisation d’une clé de recommandation personnalisée {#custom-key}

Vous pouvez également baser les recommandations sur la valeur d’un attribut de profil personnalisé.

>[!NOTE]
>
>Les paramètres de profil personnalisés peuvent être transmis à [!DNL Target] par le biais de JavaScript, de l’API ou des intégrations. Pour plus d’informations sur les attributs de profil personnalisés, voir [Profils des visiteurs](/help/main/c-target/c-visitor-profile/visitor-profile.md).

Supposons, par exemple, que vous souhaitiez afficher des séquences recommandées en fonction de la dernière séquence ajoutée par un utilisateur à la file d’attente.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer des critères]**.

1. Renseignez les informations de la [section Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Dans la section [Algorithme recommandé](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), sélectionnez **[!UICONTROL Basé sur un élément]** dans la liste **[!UICONTROL Type d’algorithme]**.

1. Sélectionnez **[!UICONTROL Personnes qui ont consulté ceci ou cela]** dans la liste **[!UICONTROL Algorithme]**.

1. Sélectionnez votre attribut de profil personnalisé dans la liste **[!UICONTROL Clé de recommandation]** (par exemple, [!UICONTROL Dernier affichage ajouté à la liste de contrôle]).

## Affichage des informations sur les critères {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Vous pouvez afficher les détails des critères en cliquant sur les critères souhaités dans la colonne [!UICONTROL Nom].

Les sections **[!UICONTROL Attributs]** et Détails vous permettent d’afficher des informations générales sur les critères sélectionnés, y compris ses [!UICONTROL Nom], [!UICONTROL Description], [!UICONTROL Secteur vertical], [!UICONTROL Types de page], [!UICONTROL Recommandation Key], [!UICONTROL Recommandation Logic], [!UICONTROL Algorithm ID] et les informations sur la dernière modification (date et auteur de la modification de l’algorithme).

La section **[!UICONTROL Utilisation]** vous permet de consulter une liste d’activités qui font référence aux critères sélectionnés.

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Utilisation des algorithmes] est actuellement prise en charge pour les activités [!DNL Recommendations] uniquement. Cette fonctionnalité n’est actuellement pas prise en charge pour les activités [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique] et [!UICONTROL Ciblage d’expérience] (XT) qui incluent [recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).
