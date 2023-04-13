---
keywords: Real-time Customer Data Platform;rtcdp;personnalisation;audiences aep;audiences adobe experience platform;attributs de profil
description: Découvrez comment utiliser l’intégration  [!DNL Target]/[!DNL Real-Time Customer Data Platform]  (RTCDP) pour fournir des données client plus riches et une personnalisation avec plus d’impact.
title: Comment intégrer  [!DNL Target]  à  [!DNL Real-Time Customer Data Platform] ?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 08422323607f7238a7cf9bac5b863032ce734662
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 8%

---

# Intégrer dans [!DNL Real-Time Customer Data Platform]

Basé sur [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP) aide les entreprises à rassembler des données connues et anonymes provenant de plusieurs sources d’entreprise. La plateforme RTCDP vous permet de créer des profils client qui peuvent être utilisés pour offrir des expériences client personnalisées sur tous les canaux et appareils en temps réel.

Pour plus d’informations sur RTCDP, voir [Présentation de Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr){target=_blank}.

## Fonctionnalités clés

Les principales fonctionnalités sont les suivantes :

* Direct [!DNL Target] intégration à Real-Time CDP/[!DNL Adobe Experience Platform] sur l’Edge (suppression de la dépendance sur [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations Card] avec gouvernance et application des politiques
* Segments CDP en temps réel et attributs de profil partagés

## Scénarios de mise en oeuvre

Les sections suivantes indiquent le type de cas d’utilisation de la personnalisation (session suivante ou même page) disponible lors de l’utilisation de différentes méthodes de mise en oeuvre :

### Implémentation d’at.js

| Solutions | Cas d’utilisation activé |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) et [!DNL Target]</li><li>[!DNL RTCDP] (Premium ou Ultimate) et [!DNL Target]</li><li>[!DNL RTCDP] (toute SKU), [!DNL AAM], et [!DNL Target]</li></ul> | Personnalisation de la prochaine session |

### [!DNL Adobe Experience Platform Web SDK] ou [!DNL Experience Platform Server-Side API] implémentation

| Solutions | Cas d’utilisation activé |
| --- | --- |
| <ul><li>[!DNL RTCDP] (tout SKU) et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><li>Personnalisation de la même page via Edge</li><li>Gouvernance appliquée lors du partage de segments</li></ul> |
| <ul><li>[!DNL RTCDP] (toute SKU), [!DNL AAM], et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><ul><li>[!DNL AAM] segments</li><li>Segments tiers via [!DNL AAM]</li></ul><li>Personnalisation de la même page via Edge</li><ul><li>[!DNL RTCDP] segments</li><li>Gouvernance appliquée lors du partage de segments</li></ul> |

### Mix of [!UICONTROL at.js] et [!DNL Platform Web SDK] implémentation

| Solutions | Cas d’utilisation activé |
| --- | --- |
| <ul><li>[!DNL RTCDP] (tout SKU) et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><ul><li>Pour toutes les pages avec [!UICONTROL at.js]</li></ul><li>Personnalisation de la même page</li><ul><li>Pour toutes les pages avec [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (toute SKU), [!DNL AAM], et [!DNL Target]</li></ul> | <ul><li>Personnalisation de la prochaine session</li><ul><li>Pour toutes les pages avec [!UICONTROL at.js]</li><li>[!DNL AAM] segments</li><li>Segments tiers via [!DNL AAM]</li></ul> |

## Temps d’évaluation des segments

Le tableau suivant indique le temps d’évaluation des segments pour les événements provenant de différents scénarios d’implémentation :

| Scénario | Segment Edge (évaluation en millisecondes) | Segment de diffusion en continu (évaluation par minute) | Évaluation de segments par lots |
| --- | --- | --- | --- |
| Événements/données provenant de [!DNL Adobe Experience Platform] SDK | Oui | Oui | S.O. |
| Événements de [!UICONTROL at.js] | Non | Oui | S.O. |
| Événements de [!DNL Target Mobile] SDK | Non | Oui | S.O. |
| Événements de chargement par lots | Non | Non | Oui |
| Événements des données hors ligne (flux) | Non | Oui | Oui |

## Utilisation d’audiences provenant de [!DNL Adobe Experience Platform] {#aep}

Utilisation [audiences](/help/main/c-target/c-audiences/audiences.md) créé dans [!DNL Adobe Experience Platform] fournir des données client plus riches qui mènent à une personnalisation plus impactée. Le [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr){target=_blank} (RTCDP), basé sur [!DNL Adobe Experience Platform], aide les entreprises à rassembler des données connues et anonymes provenant de plusieurs sources d’entreprise. Ce processus vous permet de créer des profils client qui peuvent être utilisés pour offrir des expériences client personnalisées sur tous les canaux et appareils en temps réel.

En se connectant [!DNL Target] au [!DNL Real-Time Customer Data Platform], les clients peuvent enrichir leur personnalisation web. Cette intégration vous permet de déverrouiller de nouveaux segments qui étaient auparavant inaccessibles pour [!DNL Target] pour activer la personnalisation en temps réel en millisecondes sur la première page de la visite web d’un client. Utilisation des audiences et des attributs de profil créés dans [!DNL Adobe Experience Platform] vous permet d’étendre les points de données disponibles pour une personnalisation plus riche.

Cette intégration permet de déverrouiller les cas d’utilisation clés avec Real-Time CDP :

* Personnalisation Même page / Accès suivant
* Personnalisation des nouveaux utilisateurs / utilisateurs inconnus

## Partage des attributs de profil Real-Time CDP avec [!DNL Target] {#rtcdp-profile-attributes}

Les attributs de profil Real-Time CDP peuvent être partagés avec [!DNL Target] à utiliser dans les offres de HTML et [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Limites et considérations des fonctionnalités des attributs de profil Real-Time CDP

>[!NOTE]
>
>La fonction Attributs de profil Real-Time CDP est disponible en version bêta pour les offres de HTML et [Offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

Tenez compte des points suivants :

* Les attributs d’une offre donnée doivent provenir du même [!UICONTROL Experience Platform] sandbox. (En d’autres termes, une offre ne peut pas contenir d’attributs provenant de différents [!UICONTROL Experience Platform] environnements de test.)
* Les attributs d’une offre donnée peuvent provenir de différentes sources ; en d’autres termes, [!DNL Target] et la variable [!UICONTROL Experience Platform] profile. (En d’autres termes, vous pouvez combiner des attributs d’où ils proviennent [!DNL Target] ou de [!UICONTROL Experience Platform] profile.)
* Lors de la définition d’une offre, vous pouvez attribuer des valeurs par défaut pour [!UICONTROL Attributs de profil Real-Time CDP], au cas où l’attribut n’a pas de valeur explicite. Par exemple, si une stratégie de consentement ou de gouvernance bloque l’attribut utilisé dans le service de personnalisation, la valeur par défaut peut être utilisée à la place.

### Exemple de cas d’utilisation JSON

En tant que marketeur en ligne, vous souhaitez que le profil AEP/unifié partage des valeurs d’attribut avec [!DNL Target] pour fournir une personnalisation en temps réel. En utilisant [!UICONTROL Attributs de profil Real-Time CDP], vous pouvez afficher la valeur de la variable [!UICONTROL Experience Platform] dans un [!DNL Target] offre utilisant le remplacement de jeton. Vous pouvez, par exemple, personnaliser en fonction de la couleur préférée d’un client à l’aide de `${aep.profile.favoriteColor}`, ou leur niveau de fidélité et leur valeur de point de fidélité à l’aide des jetons `${aep.loyalty.tier}` et `${aep.loyalty.points}`.

Pour créer une offre JSON afin de partager des attributs de profil AEP/unifié avec [!DNL Target]:

1. while [création d’une offre JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), de la fonction **[!UICONTROL Sélection d’une source]** list, select **[!UICONTROL Adobe Experience Platform]**.
1. Dans la **[!UICONTROL Sélection d’un nom d’environnement de test de profil]** sélectionnez l’environnement de test de votre choix.
1. Dans la **[!UICONTROL Sélection d’un attribut de profil]** sélectionnez les attributs souhaités.
1. (Facultatif) Dans le **[!UICONTROL Insérer une valeur par défaut]** sélectionnez les valeurs de votre choix.
1. Cliquez sur **[!UICONTROL Ajouter]**.

L’illustration suivante montre que deux attributs de profil : `loyalty.tier` et `loyalty.points` ont été ajoutés à l’offre JSON.

![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Liens vers plus d’informations

Pour plus d’informations, voir les rubriques suivantes :

* [Notes de mise à jour des destinations](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} dans le *Notes de mise à jour de Adobe Experience Platform*
* [Configuration des destinations de personnalisation pour la personnalisation de la même page et de la page suivante](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} dans le *Présentation des destinations* guide.
* [Connexion Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} dans le *Présentation des destinations* guide
* [Attributs de mappage](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=en#map-attributes){target=_blank} dans le *Présentation des destinations* guide.

## Vidéos et billets de blog

Les vidéos et articles de blog suivants fournissent des informations supplémentaires sur la personnalisation améliorée avec Target et la plateforme RTCDP :

### Vidéo : Personnalisation de l’accès suivant avec Real-Time CDP et [!DNL Adobe Target]{#RTCDP}

Découvrez comment personnaliser lors de l’accès suivant avec [!DNL Real-Time Customer Data Platform] et [!DNL Adobe Target]. Le [!DNL Adobe Target] destination dans [!DNL Real-Time CDP] vous permet d’utiliser des [!DNL Experience Platform] segments dans [!DNL Adobe Target] pour une même personnalisation de page et une personnalisation de page suivante avec prise en charge de la gouvernance et de la confidentialité.

Pour plus d’informations, voir [Personnalisation de l’accès suivant avec Real-Time CDP et Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} dans le *Tutorials de plateforme* guide.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### [!DNL Adobe Target] blog et vidéo : Personnalisation améliorée de la même page

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] et [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
