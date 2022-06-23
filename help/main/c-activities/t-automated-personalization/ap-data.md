---
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes;personalization algorithms;machine-learning algorithms;machine learning algorithms
description: Découvrez quel Adobe de données [!DNL Target] collecte et utilise pour créer ses algorithmes d’apprentissage automatique.
title: Quelles données sont collectées pour créer des algorithmes d’apprentissage automatique ?
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2062'
ht-degree: 53%

---

# ![PREMIUM](/help/main/assets/premium.png) Données utilisées par [!DNL Target] algorithmes d’apprentissage automatique

[!DNL Adobe Target] automatically collects and uses a variety of data to build its personalization algorithms in [!UICONTROL Automated Personalization] (AP) and [!UICONTROL Auto-Target] (AT) activities. When a visitor enters an AP or AT activity, a snapshot of information is passed to a set of &quot;training records&quot; (the visitor data that the personalization algorithms will learn on).

Pour en savoir plus sur la variable [!DNL Target] algorithmes de personnalisation, voir [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Par défaut [!DNL Adobe Target] catégories d’attributs

Le tableau suivant affiche les données collectées par [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] activités par défaut, sans configuration de [!DNL Target] ou autre [!DNL Adobe] les solutions, ainsi que la convention d’affectation des noms utilisée pour indiquer ces attributs dans [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le chargement de données supplémentaires, reportez-vous à la section [Chargement de données pour le [!DNL Target] algorithmes de personnalisation](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans [!UICONTROL Insights] rapports |
| --- | --- | --- | --- |
| Paramètres d’environnement | ENV | Informations sur l’environnement d’un utilisateur, y compris le système d’exploitation, le navigateur et l’heure du jour/jour de la semaine. | Browser - [Nom de l’attribut]<br>Système d’exploitation - [Valeur] |
| Géographie | GEO | Informations sur la géographie d’un utilisateur, obtenues par le biais de la recherche d’adresses IP. | Geo - [attribut geo] |
| Appareil mobile | MOB | Informations sur l’appareil mobile d’un utilisateur. | Device - [device attribute]<br>Mobile - [mobile attribute] |
| Target reporting segments | SEG | Segments de création de rapports configurés dans [!DNL Target] création de rapports. | Reporting Segment -[Segment Name] |
| Comportement de session | SES | Information about user behavior, such as number of pages viewed. | Visitor Profile - [Attribute Name] |

## Catégories d’attributs Adobe Target personnalisées

Le tableau suivant présente les données fournies par le client et collectées par [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] activités. This data is collected only if you provide it. Des noms d’attributs spécifiques et des exemples de valeurs seront spécifiques à la configuration de votre système.

| Catégorie de données | System prefix | Description | Nom d’affichage dans [!UICONTROL Insights] rapports |
| --- | --- | --- | --- |
| Paramètres de page | BOX | Paramètres de page personnalisés (&quot;paramètres de mbox&quot;) transmis dans l’appel à [!DNL Target]. | Personnalisé - Paramètre de mbox - [parameter name] |
| [!DNL Target] profil | PRO | Custom profile attributes directly uploaded to the [!DNL Target] profile via API or page parameter and [!DNL Target] profile scripts. | Custom - Visitor Profile - [attribute name] |
| Attributs du client | CRS | Customer Attributes uploaded to the [!DNL Target] profile via the [Adobe Experience Cloud Customer Attributes Service](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Custom - Visitor Profile - [attribute name] |
| paramètres d’URL | URL | URL et paramètres d’URL de la page actuellement consultée. | Personnalisé - Paramètre d’URL - [Paramètre d’URL] |
| URL de référence | REF | Referring URL and any URL parameters for the referring URL. | Custom - [Referring URL Parameter] - [Parameter value] |
| Audiences partagées Adobe Experience Cloud | AAM | Toutes les audiences partagées avec [!DNL Target] de [!DNL Adobe Experience Cloud] solutions (par exemple, [!DNL Adobe Audience Manager] et [!DNL Adobe Analytics], via le [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Custom - Experience Cloud Audience - [Audience Name] |
| Audiences RTCDP Adobe Experience Platform | UPS | AEP RTCDP Audiences shared with [!DNL Target] via Destinations. |  |

## Blocking features from [!DNL Target] machine-learning algorithms

Les fonctionnalités peuvent être bloquées depuis [!DNL Target] algorithmes d’apprentissage automatique, qui empêchent leur utilisation dans n’importe quel [!UICONTROL Ciblage automatique] ou [!UICONTROL Automated Personalization] modèle ou activité.

Pour bloquer une catégorie de fonctionnalités de [!DNL Target] algorithmes d’apprentissage automatique, contactez [Assistance clientèle Adobe](/help/main/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) et spécifiez les catégories de fonctionnalités que vous souhaitez bloquer à l’aide du ou des préfixes système fournis ci-dessus.

Pour bloquer une ou plusieurs fonctionnalités spécifiques de [!DNL Target] algorithmes d’apprentissage automatique, contactez [Assistance clientèle Adobe](/help/main/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) et spécifiez les noms de fonctionnalités spécifiques qui doivent être bloqués, à l’aide des noms système fournis ci-dessous. Les sections suivantes contiennent des informations détaillées sur les différents types de données, notamment les noms d’attributs, descriptions et exemples de valeurs.

## Données de périphérique et de mobile {#device-mobile}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Mobile - Device - Brand | Marque du périphérique mobile utilisé par le visiteur pour accéder à l’activité. | Apple | MOB_targeting.mobile.vendor |
| Mobile - Device - eReader | Indique si le périphérique est un eReader. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.ereader |
| Mobile - Device - Game Console | Indique si le périphérique est une console de jeu. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.gamesConsole |
| Mobile - Device - Media Player | Indique si le périphérique est un lecteur multimédia. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.mediaPlayer |
| Mobile - Device - Mobile Phone | Indique si le périphérique est un téléphone mobile. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.mobilePhone |
| Mobile - Device - Model Name | Nom du modèle du périphérique mobile utilisé par le visiteur pour accéder à l’activité. | iPhone XS | MOB_targeting.mobile.model |
| Device - Set-Top Box | Indique si le périphérique est un décodeur. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.setTopBox |
| Mobile - Device - Tablet | Indique si le périphérique est une tablette. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.tablet |
| Mobile - Pixel Density (ppi) | Densité en pixels du périphérique mobile utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayPpi |
| Mobile - Système d’exploitation - OSX (Android, Windows, etc.) | Indique si l’utilisateur a utilisé un OSX (ou Android, Windows, etc.) pour accéder à l’activité. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.os[SE]<br>Par exemple, MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | Hauteur d’écran du périphérique mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | Largeur d’écran du périphérique mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayWidth |

## Données environnementales {#env}

|Attribute name|Attribute description|Sample values|System name|
| --- | --- | --- | -- |
|Browser - Day of Week|The day of the week when the visitor accessed the activity.|0 à 6.<br>(0 est dimanche)|ENV_DayOfWeek| |Browser - Hour of Day|Heure de la journée à laquelle le visiteur a accédé à l’activité.|0 à 23<br>(0 est minuit)|ENV_UserHour| |Navigateur - Heure de la semaine|Heure de la semaine à laquelle le visiteur a accédé à l’activité.|0 à 168<br>(Le dimanche minuit est 0)|ENV_WeekHour| |Navigateur - Paramètre de langue|Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l’activité.|Anglais<br>Allemand|ENV_Language| |Navigateur - Heure de la journée|Heure du navigateur à laquelle le visiteur a accédé à l’activité.|0, 6, 12, 18<br>(0 est la nuit, 6 est le matin,<br>12 est l’après-midi, 18 est le soir)|ENV_LocalTimePeriod| |Navigateur - Fuseau horaire|Fuseau horaire du visiteur lors de l’accès à l’activité.|Heure du Pacifique<br>Heure de l’Est<br>GMT|ENV_BrowserTimezoneOffsetMinutes| |Navigateur - Type|Type de navigateur utilisé par le visiteur lors de l’accès à l’activité.|Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Autre|ENV_Browser| |Navigateur - Jour ouvrable/week-end|État du travail lorsque le visiteur a accédé à l’activité (week-end, heures de travail ou jour de semaine libre).|Le samedi et le dimanche sont week-end<br>Lundi au vendredi 09:00 à 18:00 est l&#39;heure du travail<br>Lundi au vendredi après 18 h 00 jusqu&#39;à 9 h 00 est le jour de la semaine libre|ENV_UserHourType| |Navigateur - Hauteur de la fenêtre (px)|Hauteur de la fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité.|1, 2, 3, etc.|ENV_BrowserHeight| |Navigateur - Largeur de la fenêtre (px)|Largeur de la fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité.|1, 2, 3, etc.|ENV_BrowserWidth| |Appareil - Hauteur d’écran (px)|Hauteur d’écran du périphérique utilisé par le visiteur pour accéder à l’activité.|1, 2, 3, etc.|ENV_ScreenHeight| |Appareil - Largeur d’écran (px)|Largeur d’écran du périphérique utilisé par le visiteur pour accéder à l’activité.|1, 2, 3, etc.|ENV_ScreenWidth| |Système d’exploitation|Système d’exploitation sur le périphérique du visiteur utilisé pour accéder à l’activité.|Mac OS<br>Windows<br>Linux<br>Robot de recherche<br>Système d’exploitation inconnu|ENV_OperatingSystem| |Système d’exploitation - Version|Version du système d’exploitation utilisée par le visiteur pour accéder à l’activité.|Windows 10<br>Mac OS 10|ENV_OperatingSystemVersion| |Sources de trafic - URL de page d’entrée de référence|Première page vue par le visiteur lors de l’accès à votre site.|`https://www.adobe.com/ecloud.html`|ENV_Referrer|

## Données géographiques {#geo}

| Nom de l’attribut | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Geo - City | Ville à partir de laquelle le visiteur a accédé à l’activité. | San Francisco | Geo_City |
| Geo - Country | Pays depuis lequel le visiteur a accédé à l’activité. | Allemagne | Geo_Country |
| Geo - DMA | Zone desservie à partir de laquelle le visiteur a accédé à l’activité. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l’activité. | 47.269<br>Arrondi à 3 décimales près (précision d’environ 100mètres) | GEO_Latitude |
| Geo - Longitude | Longitude à partir de laquelle le visiteur a accédé à l’activité. | -122.269<br>Arrondi à 3 décimales près (précision d’environ 100 mètres) | GEO_Longitude |
| Geo - State/Region | État ou région à partir duquel le visiteur a accédé à l’activité. | Utah<br>New South Wales | GEO_State<br>GEO_Region |
| Geo - Zip Code | Code postal à partir duquel le visiteur a accédé à l’activité. | 84004 | GEO_ZipCode |
| Mobile - Carrier | Opérateur de téléphonie mobile utilisé par le visiteur lors de l’accès à l’activité. | Vodafone<br>T-Mobile | GEO_mobileCarrier |
| Network - Connection Speed | Vitesse de connexion réseau du périphérique lorsque le visiteur a accédé à l’activité. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite | GEO_ConnectionSpeed |
| Network - Domain Name | Nom du domaine réseau à partir duquel le visiteur a accédé à l’activité. | `nnt.net` | GEO_DomainName |
| Network - ISP | Réseau depuis lequel le visiteur a accédé à l’activité. | nnt communications corporation | GEO_IspName |

## Données de session {#session}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | Indique la somme de toutes les valeurs de commande pour toutes les visites/sessions sur une activité particulière. | Double | SES_CUMULATIVE_ORDER_VALUE |
| Visitor Profile - Activity Lifetime Time on Site | Indique le temps total passé par le visiteur sur le site, à l’exclusion de la session en cours et est mis à jour à l’expiration de la session. | Double, millisecondes | SES_TOTAL_TIME |
| Visitor Profile -Average Page Views per Visit during Activity | Indique le nombre moyen de pages vues par session, à l’exception de la session en cours. | Double | SES_REQUESTS_PER_SESSION |
| Visitor Profile - Average Time per Visit | Indique la durée moyenne passée par visite/session. Ceci n’inclut pas la session en cours. | Double, millisecondes | SES_TIME_PER_SESSION |
| Visitor Profile - First Visit | Indique l’heure de la première visite où l’utilisateur a interagi avec [!DNL Target]. | Double, millisecondes | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | Indique les heures écoulées depuis la dernière visite de cette activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Indique le nombre d’impressions à une combinaison emplacement/contenu spécifique dans une activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Profil du visiteur - Dernier [!DNL Target] Interaction | Indique l’heure de la dernière interaction avec [!DNL Target]. L’interaction se produit à chaque [!DNL Target] , car l’implémentation actuelle de [!DNL Target] met à jour le profil à chaque requête. | Double, millisecondes | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Indique le nombre total de pages vues (impressions), y compris la visite/session actuelle jusqu’à ce que le visiteur entre dans l’activité. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Indique le nombre de pages vues lors de la visite/session actuelle jusqu’à ce que le visiteur entre dans l’activité. Plus précisément, le nombre d’impressions. Ces impressions ne sont pas des pages vues réelles. Il s’agit plutôt du nombre de fois où la requête a atteint Target. Target ne peut pas distinguer les dépassements de délai ou les autres raisons pour lesquelles l’utilisateur n’a pas reçu ou consulté le contenu. | Double (uniquement nombre entier positif) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Indique l’heure de début de la visite/session actuelle avec Target. La visite avec Target peut être lancée sans entrer dans une activité. All that is required is a call to any [!DNL Target] request. Un visiteur peut prendre un certain temps avant de saisir l’activité et l’instantané est pris. | Double, millisecondes | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Indique l’heure de la dernière visite/session avec [!DNL Target] démarrée. Cet attribut est mis à jour lorsque la session expire.<br>S’il s’agit de la première session du visiteur, elle se traduira par une `LAST_SESSION_START = 0.` | Double, millisecondes | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Indique la durée entre la session précédente et l’heure à laquelle l’utilisateur saisit l’activité et l’instantané est exécuté. | Double, millisecondes | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Specifies the difference between the last interaction with [!DNL Target] and when the current visit started. Cet attribut peut être considéré comme une durée de visite/session jusqu’à ce que l’utilisateur entre dans l’activité et que l’instantané soit pris.<br>[!DNL Target]Des valeurs négatives surviennent lorsque la session démarre et que la dernière heure de mise à jour est déclenchée par le même appel de Les valeurs négatives doivent être considérées comme 0 (zéro). | Double, millisecondes | SES_SESSION_TIME |
| Profil de visiteur – Nombre total de visites | Indique le nombre total de visites/sessions. N’inclut pas la visite/session active. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Indique le nombre de visites sur une activité particulière. En l’absence de visite précédente, renvoie 0 (zéro). | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Indique le nombre de visites/sessions sur une activité particulière en cas d’au moins une conversion durant la visite. | Double | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | Nombre de visites/sessions sans conversion sur une activité particulière. Cette valeur est réinitialisée à zéro après la conversion ou -1 si la conversion n’a jamais eu lieu. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_SUCCESS_RECENCY |