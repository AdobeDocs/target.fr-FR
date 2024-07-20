---
keywords: données environnementales;données de session;données géographiques;données géographiques;données de périphérique;données mobiles;attributs;attributs de profil;algorithmes de personnalisation;algorithmes d’apprentissage automatique;algorithmes d’apprentissage automatique
description: Découvrez quelles données [!DNL Adobe Target] collecte et utilise pour créer ses algorithmes d’apprentissage automatique.
title: Quelles données sont collectées pour créer des algorithmes d’apprentissage automatique ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '1967'
ht-degree: 51%

---

# Données utilisées par les algorithmes d’apprentissage automatique [!DNL Target]

[!DNL Adobe Target] collecte et utilise automatiquement diverses données pour créer ses algorithmes de personnalisation dans les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT). Lorsqu’un visiteur entre dans une activité [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target], un instantané des informations est transmis à un ensemble d’&quot;enregistrements d’entraînement&quot; (les données de visiteur sur lesquelles les algorithmes de personnalisation apprennent).

Pour en savoir plus sur les algorithmes de personnalisation [!DNL Target], voir [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Catégories d’attributs par défaut [!DNL Target]

Le tableau suivant affiche les données collectées par les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target] par défaut, sans aucune configuration de [!DNL Target] ou d&#39;autres solutions [!DNL Adobe]. Le tableau comprend également la convention d’affectation des noms utilisée pour indiquer ces attributs dans les [rapports Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le téléchargement de données supplémentaires, voir [Chargement de données pour les  [!DNL Target] algorithmes de personnalisation](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans les rapports [!UICONTROL Insights] |
| --- | --- | --- | --- |
| Paramètres d’environnement | ENV | Informations sur l’environnement d’un utilisateur, y compris le système d’exploitation, le navigateur et l’heure du jour/jour de la semaine. | Browser - [Attribute Name]<br>Operating System - [Value] |
| Géographie | GEO | Informations sur la géographie d’un utilisateur, obtenues par le biais de la recherche d’adresses IP. | Geo - [attribut geo] |
| Appareil mobile | MOB | Informations sur l’appareil mobile d’un utilisateur. | Appareil - [attribut de périphérique]<br>Mobile - [attribut mobile] |
| [!DNL Target] segments de création de rapports | SEG | Segments de création de rapports configurés dans la création de rapports [!DNL Target]. | Segment de création de rapports -[Nom de segment] |
| Comportement de la session | SES | Informations sur le comportement des utilisateurs, telles que le nombre de pages consultées. | Profil du visiteur - [Nom d’attribut] |

## Catégories d’attributs [!DNL Target] personnalisées

Le tableau suivant montre les données fournies par le client collectées par les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target]. Ces données ne sont collectées que si vous les fournissez. Des noms d’attributs spécifiques et des exemples de valeurs sont spécifiques à la configuration de votre système.

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans les rapports [!UICONTROL Insights] |
| --- | --- | --- | --- |
| Paramètres de page | BOX | Paramètres de page personnalisés (&quot;paramètres mbox&quot;) transmis dans l’appel à [!DNL Target]. | Personnalisé - Paramètre de mbox - [nom du paramètre] |
| Profil [!DNL Target] | PRO | Les attributs de profil personnalisés sont directement chargés vers le profil [!DNL Target] via l’API ou le paramètre de page et les scripts de profil [!DNL Target]. | Personnalisé - Profil du visiteur - [nom d’attribut] |
| Attributs du client | CRS | Attributs du client transférés vers le profil [!DNL Target] via [[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Personnalisé - Profil du visiteur - [nom d’attribut] |
| paramètres d’URL | URL | URL et paramètres d’URL de la page actuellement consultée. | Personnalisé - Paramètre d’URL - [Paramètre d’URL] |
| URL de référence | REF | URL de référence et tous les paramètres d’URL de l’URL de référence. | Personnalisé - [Paramètre d’URL de référence] - [Valeur de paramètre] |
| [!DNL Adobe Experience Cloud] audiences partagées | AAM | Toutes les audiences partagées avec [!DNL Target] à partir d’autres solutions [!DNL Adobe Experience Cloud] (par exemple, [!DNL Adobe Audience Manager] et [!DNL Adobe Analytics], via [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Personnalisé - Audience Experience Cloud - [Nom d’audience] |
| [!DNL Adobe Experience Platform Real-time CDP] audiences | UPS | Plateforme d’audiences CDP en temps réel partagées avec [!DNL Target] via [!UICONTROL Destinations]. |  |
| [!DNL Adobe Experience Platform Real-time CDP] attributs | AEP | Attributs de plateforme CDP en temps réel partagés avec [!DNL Target] via [!UICONTROL Destinations]. |  |

## Blocage des fonctionnalités des algorithmes d’apprentissage automatique [!DNL Target]

Les fonctionnalités peuvent être bloquées dans les algorithmes d’apprentissage automatique [!DNL Target], ce qui les empêche d’être utilisées dans n’importe quel modèle ou activité [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target].

Pour plus d’informations, voir [Présentation de l’API Modèles (Liste bloquée)](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} dans le *[!DNL Adobe Target]Guide du développeur*.

## Données de périphérique et de mobile {#device-mobile}

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
| Mobile - OS - OS X ([!DNL Android], [!DNL Windows], etc.) | Indique si l’utilisateur a utilisé un appareil OSX (ou [!DNL Android], [!DNL Windows], etc.) pour accéder à l’activité. | 0 est Faux, 1 est Vrai | MOB_targeting.mobile.os[OS]<br>Par exemple, MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | Hauteur d’écran de l’appareil mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | Largeur d’écran de l’appareil mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | MOB_targeting.mobile.displayWidth |

## Données environnementales {#env}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | -- |
| Browser - Day of Week | Jour de la semaine où le visiteur a accédé à l’activité. | 0 à 6.<br>(0 est dimanche) | ENV_DayOfWeek |
| Browser - Hour of Day | Heure du jour où le visiteur a accédé à l’activité. | 0 - 23<br>(0 est minuit) | ENV_UserHour |
| Browser - Hour of Week | Heure de la semaine où le visiteur a accédé à l’activité. | 0 - 168<br>(le dimanche minuit est 0) | ENV_WeekHour |
| Browser - Language Setting | Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l’activité. | English<br>German | ENV_Language |
| Browser - Time of Day | Heure du navigateur lorsque le visiteur a accédé à l’activité. | 0, 6, 12, 18<br>(0 est la nuit, 6 est le matin,<br>12 est l’après-midi et 18 est le soir) | ENV_LocalTimePeriod |
| Browser - Timezone | Fuseau horaire du visiteur lors de l’accès à l’activité. | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | Type de navigateur utilisé par le visiteur lors de l’accès à l’activité. | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br> Autre | ENV_Browser |
| Browser - Weekday/Weekend | État de travail lorsque le visiteur a accédé à l’activité (week-end, heures de travail ou loisirs en semaine). | Samedi et dimanche sont le week-end<br>Lundi-vendredi 09 h 00 - 18 h 00 est l’heure de travail<br>Lundi au vendredi après 18 h 00 jusqu’à 9 h 00 est l’heure de la semaine libre. | ENV_UserHourType |
| Browser - Window Height (px) | Hauteur de fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_BrowserHeight |
| Browser - Window Width (px) | Largeur de la fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_BrowserWidth |
| Appareil - Hauteur d’écran (px) | Hauteur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_ScreenHeight |
| Appareil - Largeur d’écran (px) | Largeur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc., | ENV_ScreenWidth |
| Système d’exploitation | Système d’exploitation sur l’appareil du visiteur utilisé pour accéder à l’activité. | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>Search Bot<br>Système d’exploitation inconnu | ENV_OperatingSystem |
| Operating System - Version | Version du système d’exploitation utilisée par le visiteur pour accéder à l’activité. | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | Première page vue par le visiteur lors de l’accès à votre site. | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## Données géographiques {#geo}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Geo - City | Ville à partir de laquelle le visiteur a accédé à l’activité. | San Francisco | Geo_City |
| Geo - Country | Pays depuis lequel le visiteur a accédé à l’activité. | Allemagne | Geo_Country |
| Geo - DMA | Zone desservie à partir de laquelle le visiteur a accédé à l’activité. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l’activité. | 47.269<br>Arrondi à 3 décimales près (précision d’environ 100 mètres) | GEO_Latitude |
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
| Visitor Profile - First Visit | Indique l’heure de la première visite à laquelle l’utilisateur a interagi avec [!DNL Target]. | Double, millisecondes | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | Indique les heures écoulées depuis la dernière visite de cette activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Indique le nombre d’impressions à une combinaison emplacement/contenu spécifique dans une activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Profil du visiteur - Dernière interaction [!DNL Target] | Indique l’heure de la dernière interaction avec [!DNL Target]. L’interaction se produit sur chaque requête [!DNL Target], car l’implémentation actuelle de [!DNL Target] met à jour le profil sur chaque requête. | Double, millisecondes | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Indique le nombre total de pages vues (impressions), y compris la visite/session actuelle jusqu’à ce que le visiteur entre dans l’activité. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Indique le nombre de pages vues lors de la visite/session en cours jusqu’à ce que le visiteur entre dans l’activité. Plus précisément, le nombre d’impressions. Ces impressions ne sont pas des pages vues réelles, mais il s’agit du nombre de fois où la requête a atteint [!DNL Target]. [!DNL Target] ne peut pas distinguer les dépassements de délai ou toute autre raison pour laquelle l’utilisateur n’a pas reçu ou consulté le contenu. | Double (uniquement nombre entier positif) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Indique l’heure de début de la visite/session en cours avec [!DNL Target]. La visite avec [!DNL Target] peut être lancée sans entrer dans une activité. Tout ce qui est requis est un appel à toute requête [!DNL Target]. Un visiteur peut prendre un certain temps avant de saisir l’activité et l’instantané est pris. | Double, millisecondes | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Indique l’heure de début de la dernière visite/session avec [!DNL Target]. Cet attribut est mis à jour lorsque la session expire.<br>S’il s’agit de la première session du visiteur, `LAST_SESSION_START = 0.` en résulte | Double, millisecondes | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Indique la durée entre la session précédente et l’heure à laquelle l’utilisateur saisit l’activité et l’instantané est exécuté. | Double, millisecondes | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Indique la différence entre la dernière interaction avec [!DNL Target] et le début de la visite en cours. Cet attribut peut être considéré comme une durée de visite/session jusqu’à ce que l’utilisateur entre dans l’activité et que l’instantané soit pris.<br>Des valeurs négatives surviennent lorsque la session démarre et que la dernière heure de mise à jour est déclenchée par le même appel [!DNL Target]. Les valeurs négatives doivent être considérées comme 0 (zéro). | Double, millisecondes | SES_SESSION_TIME |
| Profil de visiteur – Nombre total de visites | Indique le nombre total de visites/sessions. N’inclut pas la visite/session active. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Indique le nombre de visites sur une activité particulière. En l’absence de visite précédente, renvoie 0 (zéro). | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Indique le nombre de visites/sessions sur une activité particulière en cas d’au moins une conversion durant la visite. | Double | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | Nombre de visites/sessions sans conversion sur une activité particulière. Cette valeur est réinitialisée à zéro après la conversion ou -1 si la conversion n’a jamais eu lieu. | Double (uniquement nombre entier positif) 1, 2, 3, etc. | SES_SUCCESS_RECENCY |
