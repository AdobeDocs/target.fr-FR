---
keywords: données environnementales;données de session;données géographiques;données géographiques;données d’appareil;données mobiles;attributs;attributs de profil;algorithmes de personnalisation;algorithmes de machine learning;algorithmes de machine learning
description: Découvrez les données  [!DNL Adobe Target]  et utilisées pour créer ses algorithmes de machine learning.
title: Quelles données sont collectées pour créer des algorithmes de machine learning ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: fe6a7addd3854c430798fc339741c9ae6a4efc7d
workflow-type: tm+mt
source-wordcount: '1958'
ht-degree: 51%

---

# Données utilisées par [!DNL Target] algorithmes de machine learning de

[!DNL Adobe Target] collecte et utilise automatiquement diverses données pour créer ses algorithmes de personnalisation dans les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT). Lorsqu’un visiteur ou une visiteuse accède à une activité de [!UICONTROL Automated Personalization] ou de [!UICONTROL Auto-Target], un instantané des informations est transmis à un ensemble d’« enregistrements d’identification » (les données de visiteur sur lesquelles les algorithmes de personnalisation s’appuient).

Pour en savoir plus sur les algorithmes de personnalisation [!DNL Target], voir [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Catégories d’attributs de [!DNL Target] par défaut

Le tableau suivant présente les données collectées par [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target] les activités par défaut, sans aucune configuration de [!DNL Target] ou d’autres solutions de [!DNL Adobe]. Le tableau inclut également la convention de nommage utilisée pour indiquer ces attributs dans les [rapports Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le téléchargement de données supplémentaires, consultez [Téléchargement de données pour les algorithmes  [!DNL Target]  personnalisation](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans les rapports [!UICONTROL Insights] |
| --- | --- | --- | --- |
| Paramètres d’environnement | ENV | Informations sur l’environnement d’un utilisateur, notamment le système d’exploitation, le navigateur et l’heure du jour ou du jour de la semaine. | Navigateur - [Nom D’Attribut]<br>Système D’Exploitation - [Valeur] |
| Géographie | GÉO | Informations sur la zone géographique d’un utilisateur, obtenues via la recherche d’adresses IP. | Géo - [attribut géographique] |
| Appareil mobile | FOULE | Informations sur l’appareil mobile d’un utilisateur. | Appareil - [attribut d’appareil]<br>mobile - [attribut mobile] |
| [!DNL Target] des segments de reporting | SEG | Segments de reporting configurés dans les rapports [!DNL Target]. | Segment de création de rapports -[Nom du segment] |
| Comportement de la session | SES | Informations sur le comportement de l’utilisateur, telles que le nombre de pages vues. | Profil du visiteur - [Nom de l’attribut] |

## Catégories d’attributs de [!DNL Target] personnalisées

Le tableau suivant présente les données fournies par le client collectées par les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target]. Ces données ne sont collectées que si vous les fournissez. Les noms d’attributs et les valeurs d’exemple spécifiques sont spécifiques à votre configuration système.

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans les rapports [!UICONTROL Insights] |
| --- | --- | --- | --- |
| Paramètres de page | BOX | Paramètres de page personnalisés (« paramètres mbox ») transmis dans l’appel à [!DNL Target]. | Personnalisé - Paramètre de mbox - [nom du paramètre] |
| profil [!DNL Target] | PRO | Les attributs de profil personnalisés sont directement chargés vers le profil [!DNL Target] via l’API ou le paramètre de page, ainsi que des scripts de profil [!DNL Target]. | Personnalisé - Profil du visiteur - [nom de l’attribut] |
| Attributs du client | CRS | Attributs du client chargés dans le profil [!DNL Target] via l’[[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Personnalisé - Profil du visiteur - [nom de l’attribut] |
| paramètres d’URL | URL | URL et tout paramètre d’URL pour la page actuellement consultée. | Personnalisé - Paramètre d’URL - [Paramètre d’URL] |
| URL de référence | RÉF | l’URL de référence et les paramètres d’URL correspondants ; | Personnalisé - [Paramètre d’URL de référence] - [Valeur du paramètre] |
| [!DNL Adobe Experience Cloud] des audiences partagées | AAM | Toutes les audiences partagées avec des [!DNL Target] d’autres solutions [!DNL Adobe Experience Cloud] (par exemple, [!DNL Adobe Audience Manager] et [!DNL Adobe Analytics], via l’[[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank} ). | Personnalisé - Audience Experience Cloud - [Nom de l’audience] |
| [!DNL Adobe Experience Platform Real-time CDP] des audiences | UPS | Audiences de Platform Real-time CDP partagées avec [!DNL Target] via [!UICONTROL Destinations]. |  |


## Blocage des fonctionnalités des algorithmes de machine learning [!DNL Target]

Les fonctionnalités peuvent être bloquées à partir [!DNL Target] algorithmes de machine learning , qui empêchent leur utilisation dans n’importe quel modèle ou activité [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target].

Placer sur la liste bloquée Pour plus d’informations, consultez [Présentation de l’API Modèles (pour en savoir plus)](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} dans le Guide du développeur *[!DNL Adobe Target].*.

## Appareil et données mobiles {#device-mobile}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Mobile - Device - Brand | Marque de l’appareil mobile utilisé par le visiteur pour accéder à l’activité. | Apple | MOB_targeting.mobile.provider |
| Mobile - Device - eReader | Indique si l’appareil est un eReader. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.reader |
| Mobile - Device - Game Console | Indique si l’appareil est une console de jeu. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.gamesConsole |
| Mobile - Device - Media Player | Indique si l’appareil est un lecteur multimédia. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.mediaPlayer |
| Mobile - Device - Mobile Phone | Indique si l’appareil est un téléphone mobile. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.mobilePhone |
| Mobile - Device - Model Name | Nom du modèle de l’appareil mobile utilisé par le visiteur pour accéder à l’activité. | iPhone XS | MOB_targeting.mobile.model |
| Device - Set-Top Box | Indique si l’appareil est un décodeur. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.setTopBox |
| Mobile - Device - Tablet | Indique si l’appareil est une tablette. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.tablet |
| Mobile - Pixel Density (ppi) | Densité en pixels de l’appareil mobile utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayPpi |
| Mobile - OS - OS X ([!DNL Android], [!DNL Windows], etc.) | Indique si l’utilisateur a utilisé un appareil OSX (ou [!DNL Android], [!DNL Windows], etc.) pour accéder à l’activité. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.os[OS]<br>Par exemple, MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | Hauteur d’écran de l’appareil mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | Largeur d’écran de l’appareil mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayWidth |

## Données environnementales {#env}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | -- |
| Browser - Day of Week | Jour de la semaine où le visiteur a accédé à l’activité. | 0 - 6.<br>(0 est dimanche) | ENV_DayOfWeek |
| Browser - Hour of Day | Heure du jour où le visiteur a accédé à l’activité. | 0 - 23<br>(0 est minuit) | ENV_UserHour |
| Browser - Hour of Week | Heure de la semaine où le visiteur a accédé à l’activité. | 0 - 168<br>(dimanche minuit est 0) | ENV_WeekHour |
| Browser - Language Setting | Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l’activité. | English<br>German | ENV_Language |
| Browser - Time of Day | Heure du navigateur lorsque le visiteur a accédé à l’activité. | 0, 6, 12, 18<br>(0 est la nuit, 6 est le matin,<br>12 est l’après-midi et 18 est le soir) | ENV_LocalTimePeriod |
| Browser - Timezone | Fuseau horaire du visiteur lors de l’accès à l’activité. | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | Type de navigateur utilisé par le visiteur lors de l’accès à l’activité. | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>Autres frais | ENV_Browser |
| Browser - Weekday/Weekend | État de travail lorsque le visiteur a accédé à l’activité (week-end, heures de travail ou loisirs en semaine). | Samedi et dimanche sont week<br>lundi-vendredi 0900 - 1800 est le temps de travail<br>lundi-vendredi après 1800 jusqu&#39;à 0900 est le temps libre en semaine | ENV_UserHourType |
| Browser - Window Height (px) | Hauteur de fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_BrowserHeight |
| Browser - Window Width (px) | Largeur de la fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_BrowserWidth |
| Appareil - Hauteur d’écran (px) | Hauteur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_ScreenHeight |
| Appareil - Largeur d’écran (px) | Largeur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_ScreenWidth |
| Système d’exploitation | Système d’exploitation sur l’appareil du visiteur utilisé pour accéder à l’activité. | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>Rechercher un robot<br>Système d’exploitation inconnu | ENV_OperatingSystem |
| Operating System - Version | Version du système d’exploitation utilisée par le visiteur pour accéder à l’activité. | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | Première page vue par le visiteur lors de l’accès à votre site. | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## Données géographiques {#geo}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Geo - City | Ville à partir de laquelle le visiteur a accédé à l’activité. | San Francisco | Geo_City |
| Geo - Country | Pays depuis lequel le visiteur a accédé à l’activité. | Allemagne | Geo_Country |
| Geo - DMA | Zone desservie à partir de laquelle le visiteur a accédé à l’activité. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l’activité. | 47,269<br>arrondi à la 3e décimale (précision d&#39;environ 100 mètres) | Latitude_GÉO |
| Geo - Longitude | Longitude à partir de laquelle le visiteur a accédé à l’activité. | -122,269<br>arrondi à la 3e décimale (précision d&#39;environ 100 mètres) | GEO_Longitude |
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
| Visitor Profile - First Visit | Indique l’heure de la première visite à laquelle l’utilisateur a interagi avec [!DNL Target]. | Double, millisecondes | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | Indique les heures écoulées depuis la dernière visite de cette activité particulière. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Indique le nombre d’impressions à une combinaison emplacement/contenu spécifique dans une activité particulière. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Profil du visiteur - Dernière interaction [!DNL Target] | Spécifie l&#39;heure de la dernière interaction avec [!DNL Target]. L’interaction se produit sur chaque requête [!DNL Target], car l’implémentation actuelle de [!DNL Target] met à jour le profil de chaque requête. | Double, millisecondes | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Indique le nombre total de pages vues (impressions), y compris la visite/session en cours jusqu’à ce que le visiteur rejoigne l’activité. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Indique le nombre de pages vues dans la visite/session en cours jusqu’à ce que le visiteur rejoigne l’activité. Plus précisément, le nombre d’impressions. Ces impressions ne sont pas de vraies pages vues, il s’agit plutôt du nombre de fois où la requête a été [!DNL Target]. [!DNL Target] n’est pas en mesure de distinguer les délais d’expiration ou toute autre raison pour laquelle l’utilisateur ou l’utilisatrice n’a pas reçu ou vu le contenu. | Double (uniquement nombre entier positif) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Indique l’heure de début de la visite/session en cours avec [!DNL Target]. La visite avec [!DNL Target] peut être initiée sans entrer dans une activité. Il suffit d’appeler une requête [!DNL Target]. Un visiteur peut mettre un certain temps avant d’accéder à l’activité et que l’instantané soit pris. | Double, millisecondes | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Indique l’heure de début de la dernière visite/session avec [!DNL Target]. Cet attribut est mis à jour lorsque la session expire.<br>S’il s’agit de la première session pour le visiteur, cela entraîne des `LAST_SESSION_START = 0.` | Double, millisecondes | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Indique la durée entre la session précédente et l’heure à laquelle l’utilisateur saisit l’activité et l’instantané est exécuté. | Double, millisecondes | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Spécifie la différence entre la dernière interaction avec [!DNL Target] et le moment où la visite actuelle a commencé. Cet attribut peut être considéré comme une durée de visite/session jusqu’à ce que l’utilisateur entre dans l’activité et que l’instantané soit pris.<br>Les valeurs négatives se produisent lorsque le démarrage de la session et l’heure de la dernière mise à jour sont déclenchés par le même appel [!DNL Target]. Les valeurs négatives doivent être considérées comme 0 (zéro). | Double, millisecondes | SES_SESSION_TIME |
| Profil de visiteur – Nombre total de visites | Indique le nombre total de visites/sessions. N’inclut pas la visite/session active. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Indique le nombre de visites sur une activité particulière. En l’absence de visite précédente, renvoie 0 (zéro). | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Indique le nombre de visites/sessions sur une activité particulière en cas d’au moins une conversion durant la visite. | Double | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | Nombre de visites/sessions sans conversion sur une activité particulière. Cette valeur est réinitialisée à zéro après la conversion ou -1 si la conversion n’a jamais eu lieu. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_SUCCESS_RECENCY |
