---
description: Des rapports spécialisés sont disponibles pour les utilisateurs d’Automated Personalization.
keywords: ciblage;rapports PA;rapports de personnalisation automatisée;rapport du niveau d’activité;rapport du niveau de l’offre;rapport des détails de l’offre
seo-description: Des rapports spécialisés sont disponibles pour les utilisateurs d’Automated Personalization.
seo-title: Rapports de synthèse d’Automated Personalization
solution: Target
title: Rapports de synthèse d’Automated Personalization
title-outputclass: Premium
uuid: 959b6814-9686-4741-8a79-5957e64f6209
badge: Premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Rapports de synthèse de personnalisation automatisée{#automated-personalization-summary-reports}

Des rapports spécialisés sont disponibles pour les utilisateurs d’Automated Personalization.

>[!NOTE]
>
>La personnalisation automatisée fait partie de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

1. Cliquez sur **[!UICONTROL Activités]**, sélectionnez l’activité d’[!UICONTROL Automated Personalization] souhaitée dans la liste, puis cliquez sur l’onglet ]**Rapports[!UICONTROL **.

   S’il y a de nombreuses activités, vous pouvez filtrer la liste en sélectionnant [!UICONTROL Automated Personalization] dans la liste déroulante [!UICONTROL Type].

1. (Facultatif) Cliquez sur l’icône [!UICONTROL Télécharger] pour télécharger une vue de synthèse (comparaison du trafic de contrôle et du trafic cible, par exemple) telle que ventilée selon toutes les mesures de succès disponibles.

>[!NOTE]
>
>L’icône [!UICONTROL Paramètres] n’est pas disponible pour les rapports [!UICONTROL Automated Personalization].

[!UICONTROL Automated Personalization] fournit les rapports suivants :

## Rapport au niveau de l’activité  {#section_6F72FC5C790B4492B3DCECBFFA971337}

Le [!UICONTROL rapport au niveau de l’activité] compare les performances agrégées de l’utilisation d’un algorithme d’[!UICONTROL Automated Personalization] au contenu diffusé de manière aléatoire (contrôle).

![](assets/box_plot_ap.jpg)

Les règles standard de l’interprétation des résultats des tests A/B s’appliquent toujours, notamment l’effet élévateur, la confiance, les tendances, la durée, etc. Pour plus d’informations sur l’interprétation des résultats, voir  [À propos du taux de conversion](../c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Rapport au niveau de l’offre {#section_CAA6409879E349C6906E2BE8156D87A1}

Le [!UICONTROL rapport au niveau de l’offre] de l’expérience Forêt aléatoire compare les performances de chaque offre à laquelle est appliqué l’algorithme à la même offre diffusée de manière aléatoire (contrôle). Par conséquent, les offres ne doivent pas être comparées les unes aux autres dans cette vue. Dans l’exemple ci-dessous, on peut affirmer que l’offre D présente un effet élévateur de 12,43 % lorsqu’elle est diffusée selon la logique de l’algorithme (forêt aléatoire) par rapport à une diffusion aléatoire (contrôle).

Cliquez sur l’algorithme d’expérience (forêt aléatoire ou contrôle) pour afficher le rapport au niveau de l’offre.

![](assets/ap_OfferLevelRpt.png)

Les offres peuvent être affichées dans des groupes de rapports. Ceux-ci peuvent être développés ou réduits. Sélectionnez [!UICONTROL Groupe de rapports] dans la liste déroulante pour afficher les informations cumulées par groupes de rapports plutôt que par offres.

>[!NOTE]
>
>L’icône représentant une horloge indique que le modèle d’algorithme est toujours en cours de création. L’icône en forme de coche indique que l’algorithme de base a été établi.

