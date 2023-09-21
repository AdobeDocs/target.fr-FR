---
keywords: données environnementales;données de session;données géographiques;données géographiques;données de périphérique;données mobiles;attributs;attributs de profil;algorithmes de personnalisation;algorithmes d’apprentissage automatique;algorithmes d’apprentissage automatique
description: En savoir plus sur les données [!DNL Adobe Target] collecte et utilise pour créer ses algorithmes d’apprentissage automatique.
title: Quelles données sont collectées pour créer des algorithmes d’apprentissage automatique ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '2024'
ht-degree: 56%

---

# Données utilisées par les algorithmes de machine learning de [!DNL Target]

[!DNL Adobe Target] collecte et utilise automatiquement diverses données pour créer ses algorithmes de personnalisation dans [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage automatique] (AT). Lorsqu’un visiteur entre dans une [!UICONTROL Automated Personalization] ou [!UICONTROL Ciblage automatique] activité, un instantané des informations est transmis à un ensemble d’&quot;enregistrements d’entraînement&quot; (les données du visiteur que les algorithmes de personnalisation apprennent).

Pour en savoir plus sur la variable [!DNL Target] algorithmes de personnalisation, voir [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Par défaut [!DNL Target] catégories d’attributs

Le tableau suivant affiche les données collectées par [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] activités par défaut, sans configuration de [!DNL Target] ou autre [!DNL Adobe] solutions. Le tableau comprend également la convention de dénomination utilisée pour indiquer ces attributs dans [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le chargement de données supplémentaires, reportez-vous à la section [Chargement de données pour le [!DNL Target] algorithmes de personnalisation](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans [!UICONTROL Informations] rapports |
| --- | --- | --- | --- |
| Paramètres d’environnement | ENV | Informations sur l’environnement d’un utilisateur, y compris le système d’exploitation, le navigateur et l’heure du jour/jour de la semaine. | Browser - [Nom de l’attribut]<br>Système d’exploitation - [Valeur] |
| Géographie | GEO | Informations sur la géographie d’un utilisateur, obtenues par le biais de la recherche d’adresses IP. | Geo - [attribut geo] |
| Appareil mobile | MOB | Informations sur l’appareil mobile d’un utilisateur. | Device - [attribut device]<br>Mobile - [attribut mobile] |
| [!DNL Target] segments de reporting | SEG | Segments de rapport configurés dans [!DNL Target] création de rapports. | Segment de création de rapports -[Nom du segment] |
| Comportement de la session | SES | Informations sur le comportement des utilisateurs, telles que le nombre de pages consultées. | Profil du visiteur - [Nom de l’attribut] |

## Personnalisé [!DNL Target] catégories d’attributs

Le tableau suivant présente les données fournies par le client et collectées par [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] activités. Ces données ne sont collectées que si vous les fournissez. Des noms d’attributs spécifiques et des exemples de valeurs sont spécifiques à la configuration de votre système.

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans [!UICONTROL Informations] rapports |
| --- | --- | --- | --- |
| Paramètres de page | BOX | Paramètres de page personnalisés (&quot;paramètres de mbox&quot;) transmis dans l’appel à [!DNL Target]. | Personnalisé - Paramètre de mbox - [parameter name] |
| [!DNL Target] profil | PRO | Les attributs de profil personnalisés sont directement chargés dans la variable [!DNL Target] profil via l’API ou le paramètre de page et [!DNL Target] scripts de profil. | Custom - Visitor Profile - [nom de l’attribut] |
| Attributs du client | CRS | Attributs du client transférés vers le [!DNL Target] via le [[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Custom - Visitor Profile - [nom de l’attribut] |
| paramètres d’URL | URL | URL et paramètres d’URL de la page actuellement consultée. | Custom - URL Parameter - [Paramètre d’URL] |
| URL de référence | REF | URL de référence et tous les paramètres d’URL de l’URL de référence. | Personnalisé - [Paramètre d’URL de référence] - [Valeur du paramètre] |
| [!DNL Adobe Experience Cloud] audiences partagées | AAM | Toutes les audiences partagées avec [!DNL Target] de [!DNL Adobe Experience Cloud] solutions (par exemple, [!DNL Adobe Audience Manager] et [!DNL Adobe Analytics], via le [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Personnalisé - Audience Experience Cloud - [Nom de l’audience] |
| [!DNL Adobe Experience Platform Real-time CDP] audiences | UPS | Audiences de la plateforme CDP en temps réel partagées avec [!DNL Target] via [!UICONTROL Destinations]. |  |
| [!DNL Adobe Experience Platform Real-time CDP] attributs | AEP | Attributs de la plateforme CDP en temps réel partagés avec [!DNL Target] via [!UICONTROL Destinations]. |  |

## Blocage des fonctionnalités de [!DNL Target] algorithmes d’apprentissage automatique

Les fonctionnalités peuvent être bloquées depuis [!DNL Target] algorithmes d’apprentissage automatique, qui empêchent leur utilisation dans n’importe quel [!UICONTROL Automated Personalization] ou [!UICONTROL Ciblage automatique] modèle ou activité.

Pour plus d’informations, voir [Présentation de l’API de modèles (Liste bloquée)](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} dans le *[!DNL Adobe Target]Guide du développeur*.

## Données d’appareil et de mobile {#device-mobile}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Mobile - Device - Brand | Marque de l’appareil mobile utilisé par le visiteur pour accéder à l’activité. | Apple | MOB_targeting.mobile.vendor |
| Mobile - Device - eReader | Indique si l’appareil est un eReader. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.ereader |
| Mobile - Device - Game Console | Indique si l’appareil est une console de jeu. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.gamesConsole |
| Mobile - Device - Media Player | Indique si l’appareil est un lecteur multimédia. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.mediaPlayer |
| Mobile - Device - Mobile Phone | Indique si l’appareil est un téléphone mobile. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.mobilePhone |
| Mobile - Device - Model Name | Nom du modèle de l’appareil mobile utilisé par le visiteur pour accéder à l’activité. | iPhone XS | MOB_targeting.mobile.model |
| Device - Set-Top Box | Indique si l’appareil est un décodeur. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.setTopBox |
| Mobile - Device - Tablet | Indique si l’appareil est une tablette. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.tablet |
| Mobile - Pixel Density (ppi) | Densité en pixels de l’appareil mobile utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayPpi |
| Mobile - OS - OS X ([!DNL Android], [!DNL Windows], etc.) | Indique si l’utilisateur a utilisé un OSX (ou [!DNL Android], [!DNL Windows]pour accéder à l’activité, etc. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.os[SE]<br>Par exemple, MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | Hauteur d’écran de l’appareil mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | Largeur d’écran de l’appareil mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayWidth |

## Données environnementales {#env}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | -- |
| Browser - Day of Week | Jour de la semaine où le visiteur a accédé à l’activité. | 0 – 6.<br>(0 est dimanche) | ENV_DayOfWeek |
| Browser - Hour of Day | Heure du jour où le visiteur a accédé à l’activité. | 0 à 23<br>(0 est minuit) | ENV_UserHour |
| Browser - Hour of Week | Heure de la semaine où le visiteur a accédé à l’activité. | 0 à 168<br>(Le dimanche minuit est 0) | ENV_WeekHour |
| Browser - Language Setting | Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l’activité. | English<br>German | ENV_Language |
| Browser - Time of Day | Heure du navigateur lorsque le visiteur a accédé à l’activité. | 0, 6, 12, 18<br>(0 est la nuit, 6 est le matin,<br>12 est l’après-midi et 18 est le soir) | ENV_LocalTimePeriod |
| Browser - Timezone | Fuseau horaire du visiteur lors de l’accès à l’activité. | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | Type de navigateur utilisé par le visiteur lors de l’accès à l’activité. | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>Les autres | ENV_Browser |
| Browser - Weekday/Weekend | État de travail lorsque le visiteur a accédé à l’activité (week-end, heures de travail ou loisirs en semaine). | Samedi et dimanche sont week-end<br>Lundi au vendredi 09:00 - 18:00 est le temps de travail<br>Lundi au vendredi après 18h00 jusqu’à 9h00 est l’heure de la semaine libre | ENV_UserHourType |
| Browser - Window Height (px) | Hauteur de fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_BrowserHeight |
| Browser - Window Width (px) | Largeur de la fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_BrowserWidth |
| Appareil - Hauteur d’écran (px) | Hauteur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_ScreenHeight |
| Appareil - Largeur d’écran (px) | Largeur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_ScreenWidth |
| Système d’exploitation | Système d’exploitation sur l’appareil du visiteur utilisé pour accéder à l’activité. | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>Robot de recherche<br>Système d’exploitation inconnu | ENV_OperatingSystem |
| Operating System - Version | Version du système d’exploitation utilisée par le visiteur pour accéder à l’activité. | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | Première page vue par le visiteur lors de l’accès à votre site. | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## Données géographiques {#geo}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Geo - City | Ville à partir de laquelle le visiteur a accédé à l’activité. | San Francisco | Geo_City |
| Geo - Country | Pays depuis lequel le visiteur a accédé à l’activité. | Allemagne | Geo_Country |
| Geo - DMA | Zone desservie à partir de laquelle le visiteur a accédé à l’activité. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l’activité. | 47,269<br>Arrondi à 3 décimales près (précision d’environ 100 mètres) | GEO_Latitude |
| Geo - Longitude | Longitude à partir de laquelle le visiteur a accédé à l’activité. | -122.269<br>Arrondi à 3 décimales près (précision d’environ 100 mètres) | GEO_Longitude |
| Geo - State/Region | État ou région à partir duquel le visiteur a accédé à l’activité. | Utah<br>New South Wales | GEO_State<br>GEO_Region |
| Geo - Zip Code | Code postal à partir duquel le visiteur a accédé à l’activité. | 84004 | GEO_ZipCode |
| Mobile - Carrier | Opérateur de téléphonie mobile utilisé par le visiteur lors de l’accès à l’activité. | [!DNL Vodafone]<br>[!DNL T-Mobile] | GEO_mobileCarrier |
| Network - Connection Speed | Vitesse de connexion réseau de l’appareil lorsque le visiteur a accédé à l’activité. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite | GEO_ConnectionSpeed |
| Network - Domain Name | Nom du domaine réseau à partir duquel le visiteur a accédé à l’activité. | `nnt.net` | GEO_DomainName |
| Network - ISP | Réseau depuis lequel le visiteur a accédé à l’activité. | nnt communications corporation | GEO_IspName |

## Données de session {#session}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | Indique la somme de toutes les valeurs de commande pour toutes les visites/sessions sur une activité particulière. | Double | SES_CUMULATIVE_ORDER_VALUE |
| Profil du visiteur - Durée de vie de l’activité - Temps passé sur le site | Indique le temps total passé par le visiteur sur le site, à l’exclusion de la session en cours et est mis à jour à l’expiration de la session. | Double, millisecondes | SES_TOTAL_TIME |
| Visitor Profile -Average Page Views per Visit during Activity | Indique le nombre moyen de pages vues par session, à l’exception de la session en cours. | Double | SES_REQUESTS_PER_SESSION |
| Visitor Profile - Average Time per Visit | Indique la durée moyenne passée par visite/session. Ceci n’inclut pas la session en cours. | Double, millisecondes | SES_TIME_PER_SESSION |
| Visitor Profile - First Visit | Indique l’heure de la première visite où l’utilisateur a interagi avec [!DNL Target]. | Double, millisecondes | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | Indique les heures écoulées depuis la dernière visite de cette activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Indique le nombre d’impressions à une combinaison emplacement/contenu spécifique dans une activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Profil du visiteur - Dernier [!DNL Target] Interaction | Indique l’heure de la dernière interaction avec [!DNL Target]. L’interaction se produit à chaque [!DNL Target] , car l’implémentation actuelle de [!DNL Target] met à jour le profil à chaque requête. | Double, millisecondes | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Indique le nombre total de pages vues (impressions), y compris la visite/session actuelle jusqu’à ce que le visiteur entre dans l’activité. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Indique le nombre de pages vues lors de la visite/session en cours jusqu’à ce que le visiteur entre dans l’activité. Plus précisément, le nombre d’impressions. Ces impressions ne sont pas des pages vues réelles. Il s’agit plutôt du nombre de fois où la requête a atteint [!DNL Target]. [!DNL Target] ne peut pas distinguer les dépassements de délai ou toute autre raison pour laquelle l’utilisateur n’a pas reçu ou consulté le contenu. | Double (uniquement nombre entier positif) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Indique l’heure à laquelle la visite/session en cours avec [!DNL Target] démarrée. La visite avec [!DNL Target] peut être lancée sans entrer dans une activité. Tout ce qui est requis est un appel à n’importe quel [!DNL Target] requête. Un visiteur peut prendre un certain temps avant de saisir l’activité et l’instantané est pris. | Double, millisecondes | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Indique l’heure de la dernière visite/session avec [!DNL Target] démarrée. Cet attribut est mis à jour lorsque la session expire.<br>S’il s’agit de la première session du visiteur, cela entraîne `LAST_SESSION_START = 0.` | Double, millisecondes | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Indique la durée entre la session précédente et l’heure à laquelle l’utilisateur saisit l’activité et l’instantané est exécuté. | Double, millisecondes | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Spécifie la différence entre la dernière interaction avec [!DNL Target] et au début de la visite actuelle. Cet attribut peut être considéré comme une durée de visite/session jusqu’à ce que l’utilisateur entre dans l’activité et que l’instantané soit pris.<br>Des valeurs négatives surviennent lorsque la session démarre et que la dernière heure de mise à jour est déclenchée par le même [!DNL Target] appelez . Les valeurs négatives doivent être considérées comme 0 (zéro). | Double, millisecondes | SES_SESSION_TIME |
| Profil de visiteur – Nombre total de visites | Indique le nombre total de visites/sessions. N’inclut pas la visite/session active. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Indique le nombre de visites sur une activité particulière. En l’absence de visite précédente, renvoie 0 (zéro). | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Indique le nombre de visites/sessions sur une activité particulière en cas d’au moins une conversion durant la visite. | Double | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | Nombre de visites/sessions sans conversion sur une activité particulière. Cette valeur est réinitialisée à zéro après la conversion ou -1 si la conversion n’a jamais eu lieu. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_SUCCESS_RECENCY |
