---
keywords: Real-time Customer Data Platform;rtcdp;personnalisation;audiences aep;audiences adobe experience platform;attributs de profil
description: Découvrez comment utiliser l’intégration  [!DNL Target]/[!DNL Real-Time Customer Data Platform]  (RTCDP) pour fournir des données client plus riches et une personnalisation avec plus d’impact.
title: Comment intégrer  [!DNL Target]  à  [!DNL Real-Time Customer Data Platform] ?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 4104b6cb67347205c0143c9dea46dd483a8266ce
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 71%

---

# Intégrer à [!DNL Real-Time Customer Data Platform]

[!DNL Real-Time Customer Data Platform] (RTCDP), qui repose sur [!DNL Adobe Experience Platform], aide les entreprises à rassembler des données connues et anonymes provenant de plusieurs sources d’entreprise. RTCDP vous permet de créer des profils clients afin d’offrir des expériences personnalisées à votre clientèle sur l’ensemble des canaux et appareils en temps réel.

Pour plus d’informations sur RTCDP, consultez la présentation de [Real-Time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr){target=_blank}.

## Fonctionnalités principales

Les principales fonctionnalités sont les suivantes :

* Intégration directe de [!DNL Target] à Real-Time CDP/[!DNL Adobe Experience Platform] sur Edge (suppression de la dépendance aux [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations Card] de la gouvernance et de l’application des politiques
* Segments Real-time CDP et attributs de profil partagés

## Scénarios d’implémentation

Les sections suivantes indiquent le type de cas d’utilisation de la personnalisation (session suivante ou même page) disponible lors de l’utilisation de différentes méthodes d’implémentation :

### Implémentation d’at.js

| Solutions | Cas d’utilisation activé |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) et [!DNL Target]</li><li>[!DNL RTCDP] (Premium ou Ultimate) et [!DNL Target]</li><li>[!DNL RTCDP] (tout SKU), [!DNL AAM] et [!DNL Target]</li></ul> | Personnalisation de la prochaine session |

### Implémentation du [!DNL Adobe Experience Platform Web SDK] ou de l’[!DNL Experience Platform Server-Side API]

| Solutions | Cas d’utilisation activé |
| --- | --- |
| <ul><li>[!DNL RTCDP] (tout SKU) et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><li>Personnalisation de la même page via Edge</li><li>Application de la gouvernance lors du partage de segments</li></ul> |
| <ul><li>[!DNL RTCDP] (tout SKU), [!DNL AAM] et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><ul><li>Segments [!DNL AAM]</li><li>Segments tiers via [!DNL AAM]</li></ul><li>Personnalisation de la même page via Edge</li><ul><li>Segments [!DNL RTCDP]</li><li>Application de la gouvernance lors du partage de segments</li></ul> |

### Combinaison d’implémentation [!UICONTROL at.js] et [!DNL Platform Web SDK]

| Solutions | Cas d’utilisation activé |
| --- | --- |
| <ul><li>[!DNL RTCDP] (tout SKU) et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><ul><li>Pour toutes les pages avec [!UICONTROL at.js]</li></ul><li>Personnalisation de la même page</li><ul><li>Pour toutes les pages avec [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (tout SKU), [!DNL AAM] et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><ul><li>Pour toutes les pages avec [!UICONTROL at.js]</li><li>Segments [!DNL AAM]</li><li>Segments tiers via [!DNL AAM]</li></ul> |

## Temps d’évaluation des segments

Le tableau suivant indique le temps d’évaluation des segments pour les événements provenant de différents scénarios d’implémentation :

| Scénario | Segment Edge (évaluation en millisecondes) | Segment de streaming (évaluation en minutes) | Évaluation de segments par lots |
| --- | --- | --- | --- |
| Événements/données des SDK [!DNL Adobe Experience Platform] | Oui | Oui | S.O. |
| Événements de [!UICONTROL at.js] | Non | Oui | S.O. |
| Événements des SDK [!DNL Target Mobile] | Non | Oui | S.O. |
| Événements des téléchargements par lots | Non | Non | Oui |
| Événements des données hors ligne (flux) | Non | Oui | Oui |

## Utiliser des audiences d’[!DNL Adobe Experience Platform] {#aep}

Les [audiences](/help/main/c-target/c-audiences/audiences.md) créées dans [!DNL Adobe Experience Platform] fournissent des données clientes plus riches et permettent d’offrir une personnalisation plus poussée. [Real-Time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr){target=_blank} (RTCDP), qui repose sur [!DNL Adobe Experience Platform], aide les entreprises à rassembler des données connues et anonymes provenant de plusieurs sources d’entreprise. Ce processus vous permet de créer des profils clients afin d’offrir des expériences personnalisées à votre clientèle sur l’ensemble des canaux et appareils en temps réel.

En associant [!DNL Target] à [!DNL Real-Time Customer Data Platform], nos clientes et clients peuvent offrir une personnalisation web plus poussée. Cette intégration vous permet de déverrouiller de nouveaux segments, inaccessibles autrefois pour [!DNL Target], afin d’activer la personnalisation en temps réel en millisecondes sur la première page de la visite d’un client ou d’une cliente sur le web. Utilisez les audiences et les attributs de profil créés dans [!DNL Adobe Experience Platform] pour étendre les points de données disponibles pour une personnalisation plus riche.

L’intégration permet de déverrouiller les cas d’utilisation clés suivants avec Real-Time CDP :

* Personnalisation de la même page / de l’accès suivant
* Personnalisation des nouveaux utilisateurs et utilisatrices / utilisateurs et utilisatrices inconnus

## Partager des attributs de profil Real-Time CDP avec [!DNL Target] {#rtcdp-profile-attributes}

Les attributs de profil Real-Time CDP peuvent être transmis à [!DNL Target] pour être utilisés dans les offres HTML et les [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Limites et considérations de la fonctionnalité Attributs de profil Real-Time CDP {#limitations}

Tenez compte des points suivants :

* Les attributs d’une offre donnée doivent provenir du même sandbox [!UICONTROL Experience Platform]. (En d’autres termes, une offre ne peut pas contenir d’attributs provenant de différents sandbox [!UICONTROL Experience Platform].)
* Les attributs d’une offre donnée peuvent provenir de différentes sources, à savoir du profil [!DNL Target] et du profil [!UICONTROL Experience Platform]. (En d’autres termes, vous pouvez combiner des attributs provenant de l’[!DNL Target] ou du profil [!UICONTROL Experience Platform].)
* Lors de la définition d’une offre, vous pouvez attribuer des valeurs par défaut à [!UICONTROL Real-Time CDP Profile Attributes], au cas où l’attribut n’a pas de valeur explicite. Par exemple, si une politique de consentement ou de gouvernance bloque l’utilisation de l’attribut dans le service de personnalisation, la valeur par défaut peut être utilisée à la place.
* [!DNL Target] prend uniquement en charge le type de données « chaîne » pour [!DNL Adobe Experience Platform] attributs de profil à utiliser dans les offres. Les attributs de type « Map » et « Array » ne sont pas encore pris en charge.

### Exemple de cas d’utilisation JSON

En tant que personne travaillant dans le marketing en ligne, vous souhaitez que le profil AEP/unifié transmette les valeurs d’attribut à [!DNL Target] pour fournir une personnalisation en temps réel. En utilisant [!UICONTROL Real-Time CDP Profile Attributes], vous pouvez afficher la valeur de l’attribut [!UICONTROL Experience Platform] dans une offre [!DNL Target] à l’aide du remplacement de jeton. Vous pouvez, par exemple, personnaliser votre offre en fonction de la couleur préférée d’un client ou d’une cliente à l’aide de `${aep.profile.favoriteColor}`, ou de son niveau de fidélité et de la valeur de ses points de fidélité à l’aide des jetons `${aep.loyalty.tier}` et `${aep.loyalty.points}`.

Pour créer une offre JSON afin de partager des attributs de profil AEP/unifié avec [!DNL Target], procédez comme suit :

1. Lors de la [création d’une offre JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), dans la liste **[!UICONTROL Select a source]**, sélectionnez **[!UICONTROL Adobe Experience Platform]**.
1. Dans la liste **[!UICONTROL Select a profile sandbox name]**, sélectionnez le sandbox de votre choix.
1. Dans la liste **[!UICONTROL Select a profile attribute]**, sélectionnez les attributs souhaités.
1. (Facultatif) Dans la liste **[!UICONTROL Insert a default value]**, sélectionnez les valeurs souhaitées.
1. Cliquez sur **[!UICONTROL Add]**.

L’illustration suivante montre l’ajout des deux attributs de profil `loyalty.tier` et `loyalty.points` à l’offre JSON.

![Image d’attribut partagé d’offre json d’AEP](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Liens vers plus d’informations

Pour plus d’informations, voir les rubriques suivantes :

* [Notes de mise à jour des destinations](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=fr#destinations){target=_blank} dans les notes de mise à jour de *Adobe Experience Platform*
* [Configurer des destinations de personnalisation pour la personnalisation de la même page et de la page suivante](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr){target=_blank} dans le guide *Présentation des destinations*.
* [Connexion Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html?lang=fr){target=_blank} dans le guide *Présentation des destinations*
* [Attributs de mappage](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=fr#map-attributes){target=_blank} dans le guide *Présentation des destinations* .
* [Activer les audiences vers des destinations de personnalisation Edge](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.html?lang=fr){target=_blank} dans le guide *Vue d’ensemble des destinations*.
* [Personnalisation de la même page et de la page suivante via les destinations  [!DNL Adobe Target]  et Custom Personalization](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=fr#same-next-page-personalization){target=_blank} sous « Questions fréquentes » dans le guide *Vue d’ensemble des destinations*.

## Vidéos et articles de blog {#videos-blogs}

Consultez les vidéos et articles de blog suivants pour en savoir plus sur la personnalisation améliorée à l’aide de Target et de la plateforme RTCDP :

### Vidéo : personnalisation de l’accès suivant avec Real-Time CDP et [!DNL Adobe Target]{#RTCDP}

Découvrez comment personnaliser l’accès suivant avec [!DNL Real-Time Customer Data Platform] et [!DNL Adobe Target]. La destination [!DNL Adobe Target] dans [!DNL Real-Time CDP] permet d’utiliser des segments [!DNL Experience Platform] dans [!DNL Adobe Target] afin d’offrir une personnalisation de la même page et de la page suivante, avec prise en charge de la gouvernance et de la confidentialité.

Pour plus d’informations, consultez [Personnalisation de l’accès suivant avec Real-Time CDP et Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=fr){target=_blank} dans le guide *Tutoriels Platform*.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Vidéo : configurer la destination [!DNL Adobe Target] dans [!DNL Real-Time Customer Data Platform]

Découvrez comment configurer la destination [!DNL Adobe Target] dans [!DNL Real-Time Customer Data Platform] pour commencer à envoyer des segments et des attributs de profil à partir de [!DNL Real-Time CDP] vers [!DNL Target].

>[!VIDEO](https://video.tv.adobe.com/v/3449795/?learn=on&captions=fre_fr)

### Vidéo : activer les segments et les attributs de profil

Découvrez comment activer les segments et les attributs de profil à partir de [!DNL Adobe Real-Time Customer Data Platform] vers [!DNL Adobe Target] pour afficher du contenu personnalisé en temps réel sur vos sites web, applications mobiles et autres propriétés numériques.

>[!VIDEO](https://video.tv.adobe.com/v/3447357/?learn=on&captions=fre_fr)

### Vidéo : utiliser les segments [!DNL Real-Time CDP] dans [!DNL Target]

Découvrez comment utiliser les segments [!DNL Real-Time Customer Data Platform] dans [!DNL Adobe Target] pour offrir des expériences personnalisées sur votre site web et vos applications mobiles.

>[!VIDEO](https://video.tv.adobe.com/v/3446829/?learn=on&captions=fre_fr)

### Vidéo : utiliser les attributs de profil [!DNL Real-Time CDP] dans [!DNL Adobe Target]

Découvrez comment utiliser les attributs de profil [!DNL Adobe Real-Time Customer Data Platform] dans [!DNL Adobe Target] pour offrir des expériences personnalisées sur votre site web et vos applications mobiles.

>[!VIDEO](https://video.tv.adobe.com/v/3451895/?learn=on&captions=fre_fr)

### Blog et vidéo [!DNL Adobe Target] : personnalisation améliorée de la même page

[[!DNL Adobe] annonce le Personalization amélioré de la même page avec [!DNL Adobe Target] et [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
