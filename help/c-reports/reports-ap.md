---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Comment utiliser les rapports de synthèse Automated Personalization ?
title: Rapports de synthèse d’Automated Personalization
feature: Reports
translation-type: tm+mt
source-git-commit: a34c6830b0e30017ae54ef1bf47407d390935d29
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 44%

---


# ![PREMIUM](/help/assets/premium.png) Rapports de synthèse de personnalisation automatisée

Des rapports spécialisés sont disponibles pour les utilisateurs d&#39;activités [!UICONTROL Automated Personalization] dans [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL La personnalisation automatisée] fait partie de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une licence [Target Premium](/help/c-intro/intro.md#premium).

1. Cliquez sur **[!UICONTROL Activités]**, sélectionnez l’activité d’[!UICONTROL Automated Personalization] souhaitée dans la liste, puis cliquez sur l’onglet **** Rapports.

   S’il y a de nombreuses activités, vous pouvez filtrer la liste en sélectionnant [!UICONTROL Automated Personalization] dans la liste déroulante [!UICONTROL Type].

1. (Facultatif) Cliquez sur l’icône **[!UICONTROL Télécharger]** pour télécharger une vue de synthèse (comparaison du trafic de contrôle et du trafic cible, par exemple) telle que ventilée selon toutes les mesures de succès disponibles.

[!UICONTROL Automated Personalization] fournit les rapports suivants :

* Niveau d&#39;Activité
* Niveau d&#39;Offre
* Segments automatisés
* Attributs importants

## Rapport au niveau de l’activité {#section_6F72FC5C790B4492B3DCECBFFA971337}

Le [!UICONTROL rapport au niveau de l’activité] compare les performances agrégées de l’utilisation d’un algorithme d’[!UICONTROL Automated Personalization] au contenu diffusé de manière aléatoire (contrôle).

![Rapport au niveau de l’activité](/help/c-reports/assets/box_plot_ap.png)

Les règles standard de l’interprétation des résultats des tests A/B s’appliquent toujours, notamment l’effet élévateur, la confiance, les tendances, la durée, etc. Pour plus d’informations sur l’interprétation des résultats, voir [À propos du taux de conversion](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Rapport au niveau de l’offre {#section_CAA6409879E349C6906E2BE8156D87A1}

Le [!UICONTROL rapport au niveau de l’offre] de l’expérience Forêt aléatoire compare les performances de chaque offre à laquelle est appliqué l’algorithme à la même offre diffusée de manière aléatoire (contrôle). Par conséquent, les offres ne doivent pas être comparées les unes aux autres dans cette vue.

Cliquez sur l’algorithme d’expérience (forêt aléatoire ou contrôle) pour vue du rapport [!UICONTROL Niveau d’Offre].

![](assets/ap_OfferLevelRpt.png)

Les offres peuvent être affichées dans des groupes de rapports. Ceux-ci peuvent être développés ou réduits. Sélectionnez [!UICONTROL Groupe de rapports] dans la liste déroulante pour afficher les informations cumulées par groupes de rapports plutôt que par offres.

>[!NOTE]
>
>L’icône représentant une horloge indique que le modèle d’algorithme est toujours en cours de création. L’icône en forme de coche indique que l’algorithme de base a été établi.

## Segments automatisés

Cliquez sur l&#39;icône [!UICONTROL Segments automatisés]. Ce rapport montre comment les différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

![Icône Segments automatisés](/help/c-reports/assets/icon-automated-sements-ap.png)

Pour plus d’informations, voir [rapport Segments automatisés](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Attributs importants

Cliquez sur l&#39;icône [!UICONTROL Attributs importants]. Ce rapport montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

![Icône des attributs importants](/help/c-reports/assets/icon-important-attributes-ap.png)

Pour plus d’informations, voir [Rapport Attributs importants](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Questions fréquentes 

### Existe-t-il des différences entre les données des rapports Niveau d’Activité et Niveau d’Offre ?

**[!UICONTROL Activité ] Levelreport** : Les visites enregistrées sur le rapport  [!UICONTROL Niveau de l’] Activité capturent le nombre de visites dans la ou les expériences de contrôle par rapport à trafic &quot;ciblé&quot;. Le trafic ciblé comprend un mélange de trafic d’exploration et de trafic personnalisé.

**Rapport** au niveau de l&#39;Offre : Les impressions enregistrées sur le rapport  [!UICONTROL Niveau de l’] Offre capturent le nombre d’impressions pour chaque offre. Par conséquent, dans une activité comportant plusieurs emplacements, le nombre total de visites enregistrées dans le rapport [!UICONTROL Niveau d&#39;Offre] de tous les groupes de Rapports est égal au multiple du nombre de visites enregistrées pour le trafic de contrôle ou de ciblage dans le rapport [!UICONTROL Niveau d&#39;Activité] multiplié par le nombre total d&#39;emplacements dans l&#39;activité. Les impressions du contenu par défaut se produisant à des emplacements où le contenu par défaut était une option disponible sont enregistrées dans le groupe d’offres &quot;Contenu par défaut&quot;. Les impressions d’offres qui n’ont pas été attribuées à un groupe de rapports sont enregistrées dans le groupe d’offres &quot;Non regroupées&quot;.

>[!NOTE]

Le nombre d&#39;impressions enregistrées sur le rapport [!UICONTROL Niveau d&#39;Offre] ne peut pas être un multiple entier exact du nombre de visites enregistrées dans le rapport [!UICONTROL Niveau d&#39;Activité]. Ceci est dû à des incohérences mineures survenant dans la capture du trafic de données de rapports sur Internet (le taux d&#39;incohérence typique est inférieur à 5 %). Ainsi, le nombre d’impressions ne sera pas un multiple exact lorsque le nombre d’emplacements disponibles dans l’activité a changé après l’activation de l’activité.
