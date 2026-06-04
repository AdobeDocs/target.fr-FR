---
keywords: Ciblage;rapports AP;rapports automated personalization;rapport de niveau activité;rapport de niveau offre;rapport des détails de l’offre;questions fréquentes
description: Découvrez comment interpréter le rapport de synthèse Automated Personalization dans Adobe Target. Vous pouvez passer aux rapports Segments automatisés et Attributs importants à partir de ce rapport.
title: Comment utiliser les rapports récapitulatifs d’Automated Personalization ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
TQID: https://experienceleague.adobe.com/Gj9Jo0NHnSxGE4BpvFbd0SudYjbkP4yrV3GFHWHNPjw
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 702
ht-degree: 21%

---

# Rapports de synthèse d’Automated Personalization

Des rapports de synthèse spécialisés sont disponibles pour les utilisateurs des activités  dans [!DNL Adobe Target].

>[!NOTE]
>
> est disponible dans le cadre de la solution [!DNL Target Premium]. Il n’est pas inclus dans [!DNL Target Standard] sans licence [Target Premium](/help/main/c-intro/intro.md#premium).

1. Cliquez sur **[!UICONTROL Activités]**, sélectionnez l’activité d’[!UICONTROL Automated Personalization] souhaitée dans la liste, puis cliquez sur l’onglet **[!UICONTROL Rapports]**.

   Si vous avez de nombreuses activités, cliquez sur l’icône Filtrer ( ![icône Filtrer](/help/main/assets/icons/Filter.svg) ) pour filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Statut], [!UICONTROL Source de création de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesures] et [!UICONTROL Activity Source].

1. (Facultatif) Cliquez sur l’icône **[!UICONTROL Télécharger]** ( ![icône Télécharger](/help/main/assets/icons/Download.svg) ) pour télécharger la vue récapitulative (par exemple, la comparaison du trafic de contrôle et du trafic ciblé), telle qu’elle est répartie par toutes les mesures de succès disponibles.

[!UICONTROL Automated Personalization] fournit les rapports suivants :

* Niveau d&#39;activité
* Niveau de l’offre
* Segments automatisés
* Attributs importants

## Rapport au niveau de l’activité {#section_6F72FC5C790B4492B3DCECBFFA971337}

Le [!UICONTROL rapport au niveau de l’activité] compare les performances agrégées de l’utilisation d’un algorithme d’[!UICONTROL Automated Personalization] au contenu diffusé de manière aléatoire (contrôle).

Les règles standard de l’interprétation des résultats des tests A/B s’appliquent toujours, notamment l’effet élévateur, la confiance, les tendances, la durée, etc. Pour plus d’informations sur l’interprétation des résultats, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Rapport au niveau de l’offre {#section_CAA6409879E349C6906E2BE8156D87A1}

Le [!UICONTROL rapport au niveau de l’offre] de l’expérience Forêt aléatoire compare les performances de chaque offre à laquelle est appliqué l’algorithme à la même offre diffusée de manière aléatoire (contrôle). Par conséquent, les offres ne doivent pas être comparées les unes aux autres dans cette vue.

Cliquez sur l’algorithme d’expérience (Forêt aléatoire ou contrôle) pour afficher le rapport [!UICONTROL &#x200B; Niveau de l’offre &#x200B;].

>[!NOTE]
>
>Une icône d’horloge indique que le modèle d’algorithme est toujours en cours de création. Une icône en forme de coche indique que l’algorithme de base a été établi.

Les offres peuvent être affichées dans des [groupes de rapports](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md) et ces groupes de rapports peuvent être réduits et développés. Cliquez sur **[!UICONTROL Contrôle]** ou **[!UICONTROL Ciblé]** dans le tableau pour afficher les informations cumulées par groupes de rapports, plutôt que par offres.

## Segments automatisés

Cliquez sur l’icône [!UICONTROL Segments automatisés]. Ce rapport montre comment différents visiteurs réagissent différemment aux offres/expériences dans votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

Pour plus d’informations, voir [&#x200B; Rapport Segments automatisés &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Attributs importants

Cliquez sur l’icône [!UICONTROL Attributs importants]. Ce rapport montre comment, dans différentes activités, les différents attributs sont plus (ou moins) importants pour la manière dont le modèle décide d’effectuer la personnalisation. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

Pour plus d’informations, voir [Rapport Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Questions fréquentes

### Pourquoi y a-t-il des différences de données entre les rapports Niveau d’activité et Niveau d’offre ?

**[!UICONTROL Rapport Niveau d’activité]** : les visites enregistrées sur le rapport [!UICONTROL Niveau d’activité] capturent le nombre de visites sur la ou les expériences de contrôle par rapport au trafic « ciblé ». Le trafic ciblé comprend un mélange de trafic d’exploration et de trafic personnalisé.

**Rapport Niveau de l’offre** : les impressions enregistrées dans le rapport [!UICONTROL Niveau de l’offre] capturent le nombre d’impressions pour chaque offre. Par conséquent, dans une activité comportant plusieurs emplacements, le nombre total de visites enregistrées dans le rapport [!UICONTROL Niveau d&#39;offre] dans tous les groupes de création de rapports est égal au multiple du nombre de visites enregistrées pour le trafic de contrôle ou ciblé dans le rapport [!UICONTROL Niveau d&#39;activité] multiplié par le nombre total d&#39;emplacements dans l&#39;activité. Les impressions de contenu par défaut se produisant aux emplacements où le contenu par défaut était une option disponible sont enregistrées dans le groupe d’offres « Contenu par défaut ». Les impressions d’offres dont l’affectation à un groupe de génération de rapports a été annulée sont enregistrées dans le groupe d’offres « Dissocié ».

>[!NOTE]
>
>Le nombre d’impressions enregistrées dans le rapport [!UICONTROL Niveau d’offre] peut ne pas être un multiple entier exact du nombre de visites enregistrées dans le rapport [!UICONTROL Niveau d’activité]. Cela est dû à des écarts mineurs qui se produisent dans la capture du trafic de données de rapport sur Internet (le taux d’écart type est inférieur à 5 %). Ainsi, le nombre d’impressions ne sera pas un multiple exact lorsque le nombre d’emplacements disponibles dans l’activité aura changé après l’activation de l’activité.
