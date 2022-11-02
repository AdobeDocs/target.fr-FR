---
keywords: ciblage;rapports AP;rapports de personnalisation automatisée;rapport au niveau de l’activité;rapport au niveau de l’offre;rapport des détails de l’offre;faq
description: Découvrez comment interpréter le rapport de synthèse Automated Personalization dans Adobe Target. Vous pouvez passer aux rapports Segments automatisés et Attributs importants à partir de ce rapport.
title: Comment utiliser les rapports de synthèse Automated Personalization ?
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: e591ced47eb3a0622b57796cef1f3bd9199a980c
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 34%

---

# ![PREMIUM](/help/main/assets/premium.png) Rapports de synthèse de personnalisation automatisée

Des rapports de synthèse spécialisés sont disponibles pour les utilisateurs de [!UICONTROL Automated Personalization] activités dans [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL La personnalisation automatisée] fait partie de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une licence [Target Premium](/help/main/c-intro/intro.md#premium).

1. Cliquez sur **[!UICONTROL Activités]**, sélectionnez l’activité d’[!UICONTROL Automated Personalization] souhaitée dans la liste, puis cliquez sur l’onglet **** Rapports.

   S’il y a de nombreuses activités, vous pouvez filtrer la liste en sélectionnant [!UICONTROL Automated Personalization] dans la liste déroulante [!UICONTROL Type].

1. (Facultatif) Cliquez sur l’icône **[!UICONTROL Télécharger]** pour télécharger une vue de synthèse (comparaison du trafic de contrôle et du trafic cible, par exemple) telle que ventilée selon toutes les mesures de succès disponibles.

[!UICONTROL Automated Personalization] fournit les rapports suivants :

* Niveau d’activité
* Niveau de l’offre
* Segments automatisés
* Attributs importants

## Rapport au niveau de l’activité {#section_6F72FC5C790B4492B3DCECBFFA971337}

Le [!UICONTROL rapport au niveau de l’activité] compare les performances agrégées de l’utilisation d’un algorithme d’[!UICONTROL Automated Personalization] au contenu diffusé de manière aléatoire (contrôle).

![Rapport au niveau de l’activité](/help/main/c-reports/assets/box_plot_ap.png)

Les règles standard de l’interprétation des résultats des tests A/B s’appliquent toujours, notamment l’effet élévateur, la confiance, les tendances, la durée, etc. Pour plus d’informations sur l’interprétation des résultats, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Rapport au niveau de l’offre {#section_CAA6409879E349C6906E2BE8156D87A1}

Le [!UICONTROL rapport au niveau de l’offre] de l’expérience Forêt aléatoire compare les performances de chaque offre à laquelle est appliqué l’algorithme à la même offre diffusée de manière aléatoire (contrôle). Par conséquent, les offres ne doivent pas être comparées les unes aux autres dans cette vue.

Cliquez sur l’algorithme de l’expérience (forêt aléatoire ou contrôle) pour afficher la variable [!UICONTROL Niveau de l’offre] rapport.

![Rapport au niveau de l’offre dans Adobe Target](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>Une icône d’horloge indique que le modèle d’algorithme est toujours en cours de création. Une icône représentant une coche indique que l’algorithme de base a été établi.

Les offres peuvent être affichées dans [groupes de génération de rapports](/help/main/c-reports/personalization-reports/offer-reporting-groups-in-automated-personalization.md), et ces groupes de génération de rapports peuvent être réduits et développés. Cliquez sur **[!UICONTROL Contrôle]** ou **[!UICONTROL Ciblés]** dans le tableau pour afficher les informations cumulées par groupes de génération de rapports plutôt que par offres.

## Segments automatisés

Cliquez sur le bouton [!UICONTROL Segments automatisés] icône . Ce rapport montre comment différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

![Icône Segments automatisés](/help/main/c-reports/assets/icon-automated-sements-ap.png)

Pour plus d’informations, voir [Rapport Segments automatisés](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Attributs importants

Cliquez sur le bouton [!UICONTROL Attributs importants] icône . Ce rapport montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

![Icône Attributs importants](/help/main/c-reports/assets/icon-important-attributes-ap.png)

Pour plus d’informations, voir [Rapport Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Questions fréquentes 

### Pourquoi y a-t-il des différences de données entre les rapports Niveau d’activité et Niveau d’offre ?

**[!UICONTROL Niveau d’activité] rapport**: Visites enregistrées dans la variable [!UICONTROL Niveau d’activité] capture le nombre de visites par rapport à l’expérience ou aux expériences de contrôle. trafic &quot;ciblé&quot;. Le trafic ciblé comprend un mélange de trafic d’exploration et de trafic personnalisé.

**Rapport au niveau de l’offre**: Impressions enregistrées sur le [!UICONTROL Niveau de l’offre] capture le nombre d’impressions pour chaque offre. Par conséquent, dans une activité comportant plusieurs emplacements, le nombre total de visites enregistrées dans la variable [!UICONTROL Niveau de l’offre] Le rapport de tous les groupes de génération de rapports est égal au multiple du nombre de visites enregistrées pour le trafic de contrôle ou le trafic ciblé dans la variable [!UICONTROL Niveau d’activité] multiplie par le nombre total d’emplacements dans l’activité. Les impressions du contenu par défaut se produisant à des emplacements où le contenu par défaut était une option disponible sont enregistrées dans le groupe d’offres &quot;Contenu par défaut&quot;. Les impressions des offres qui n’ont pas été affectées à un groupe de génération de rapports sont enregistrées dans le groupe d’offres &quot;Non regroupées&quot;.

>[!NOTE]
>
>Le nombre d’impressions enregistrées sur la variable [!UICONTROL Niveau de l’offre] Le rapport peut ne pas être un multiple entier exact du nombre de visites enregistrées dans la variable [!UICONTROL Niveau d’activité] rapport. Cela est dû à des incohérences mineures qui se produisent dans la capture du trafic des données de rapport sur Internet (le taux d’incohérence typique est inférieur à 5 %). Ainsi, le nombre d’impressions ne sera pas un multiple exact lorsque le nombre d’emplacements disponibles dans l’activité changera une fois l’activité activée.
