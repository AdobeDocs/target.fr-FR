---
keywords: ciblage;rapports AP;rapports de personnalisation automatisée;rapport au niveau de l’activité;rapport au niveau de l’offre;rapport des détails de l’offre;faq
description: Découvrez comment interpréter le rapport de synthèse Automated Personalization dans Adobe Target. Vous pouvez passer aux rapports Segments automatisés et Attributs importants à partir de ce rapport.
title: Comment utiliser les rapports de synthèse Automated Personalization ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 12%

---

# Rapports de synthèse d’Automated Personalization

Des rapports de synthèse spécialisés sont disponibles pour les utilisateurs des activités [!UICONTROL Automated Personalization] dans [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] est disponible dans le cadre de la solution [!DNL Target Premium]. Elle n’est pas incluse dans [!DNL Target Standard] sans une [licence Target Premium](/help/main/c-intro/intro.md#premium).

1. Cliquez sur **[!UICONTROL Activities]**, cliquez sur l’activité [!UICONTROL Automated Personalization] souhaitée dans la liste, puis cliquez sur l’onglet **[!UICONTROL Reports]** .

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant [!UICONTROL Automated Personalization] dans la liste déroulante [!UICONTROL Type].

1. (Facultatif) Cliquez sur l’icône **[!UICONTROL Download]** pour télécharger la vue de synthèse (comparaison du trafic de contrôle et du trafic ciblé, par exemple) telle que ventilée selon toutes les mesures de succès disponibles.

[!UICONTROL Automated Personalization] fournit les rapports suivants :

* Niveau d’activité
* Niveau de l’offre
* Segments automatisés
* Attributs importants

## Rapport au niveau de l’activité {#section_6F72FC5C790B4492B3DCECBFFA971337}

Le rapport [!UICONTROL Activity Level] compare les performances agrégées de l’utilisation d’un algorithme [!UICONTROL Automated Personalization] au contenu diffusé de manière aléatoire (contrôle).

![Rapport au niveau de l’activité](/help/main/c-reports/assets/box_plot_ap.png)

Les règles standard de l’interprétation des résultats des tests A/B s’appliquent toujours, notamment l’effet élévateur, la confiance, les tendances, la durée, etc. Pour plus d&#39;informations sur l&#39;interprétation des résultats, voir [Calculs statistiques dans les tests A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Rapport au niveau de l’offre {#section_CAA6409879E349C6906E2BE8156D87A1}

Le rapport [!UICONTROL Offer Level] de l’expérience Forêt aléatoire compare les performances de chaque offre appliquée à l’algorithme à la même offre diffusée de manière aléatoire (contrôle). Ainsi, les offres ne doivent pas être comparées les unes aux autres dans cette vue.

Cliquez sur l’algorithme d’expérience (forêt aléatoire ou contrôle) pour afficher le rapport [!UICONTROL Offer Level].

![Rapport au niveau de l’offre dans Adobe Target](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>Une icône d’horloge indique que le modèle d’algorithme est toujours en cours de création. Une icône représentant une coche indique que l’algorithme de base a été établi.

Les offres peuvent être affichées dans les [groupes de génération de rapports](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md), et ces groupes de génération de rapports peuvent être réduits et développés. Cliquez sur **[!UICONTROL Control]** ou **[!UICONTROL Targeted]** dans le tableau pour afficher les informations cumulées par groupes de génération de rapports plutôt que par offres.

## Segments automatisés

Cliquez sur l’icône [!UICONTROL Automated Segments] . Ce rapport montre comment différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

![Icône Segments automatisés](/help/main/c-reports/assets/icon-automated-sements-ap.png)

Pour plus d’informations, voir [Rapport Segments automatisés](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Attributs importants

Cliquez sur l’icône [!UICONTROL Important Attributes] . Ce rapport montre comment, dans différentes activités, différents attributs sont plus (ou moins) importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

![Icône Attributs importants](/help/main/c-reports/assets/icon-important-attributes-ap.png)

Pour plus d’informations, voir [Rapport Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Questions fréquentes

### Pourquoi y a-t-il des différences de données entre les rapports Niveau d’activité et Niveau d’offre ?

**[!UICONTROL Activity Level]rapport** : les visites enregistrées sur le rapport [!UICONTROL Activity Level] capturent le nombre de visites sur la ou les expériences de contrôle par rapport au trafic &quot;ciblé&quot;. Le trafic ciblé comprend un mélange de trafic d’exploration et de trafic personnalisé.

**Rapport au niveau de l’offre** : les impressions enregistrées sur le rapport [!UICONTROL Offer Level] capturent le nombre d’impressions pour chaque offre. Par conséquent, dans une activité comportant plusieurs emplacements, le nombre total de visites enregistrées dans le rapport [!UICONTROL Offer Level] de tous les groupes de génération de rapports est égal au multiple du nombre de visites enregistrées pour le trafic de contrôle ou ciblé dans le rapport [!UICONTROL Activity Level] multiplié par le nombre total d’emplacements dans l’activité. Les impressions du contenu par défaut se produisant à des emplacements où le contenu par défaut était une option disponible sont enregistrées dans le groupe d’offres &quot;Contenu par défaut&quot;. Les impressions des offres qui n’ont pas été affectées à un groupe de génération de rapports sont enregistrées dans le groupe d’offres &quot;Non regroupées&quot;.

>[!NOTE]
>
>Le nombre d’impressions enregistrées sur le rapport [!UICONTROL Offer Level] peut ne pas être un nombre entier exact multiple du nombre de visites enregistrées dans le rapport [!UICONTROL Activity Level]. Cela est dû à des incohérences mineures qui se produisent dans la capture du trafic des données de rapport sur Internet (le taux d’incohérence typique est inférieur à 5 %). Ainsi, le nombre d’impressions ne sera pas un multiple exact lorsque le nombre d’emplacements disponibles dans l’activité changera une fois l’activité activée.
