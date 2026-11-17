---
keywords: données environnementales;données de session;données géographiques;données géographiques;données d’appareil;données mobiles;attributs;attributs de profil;algorithmes de personnalisation;algorithmes de machine learning;algorithmes de machine learning
description: Découvrez les données que [!DNL Adobe Target] collecte et utilise pour créer ses algorithmes de machine learning.
title: Quelles données sont collectées pour créer des algorithmes de machine learning ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
TQID: 'https://experienceleague.adobe.com/eXEeFKovZmtYqcIe0dNda7f0J-nWgfW5mB1Mxv9Zp6U'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '2038'
ht-degree: 48%
---
# Données utilisées par [!DNL Target] algorithmes de machine learning {#ap-data}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez quelles données [!DNL Target] collecte par défaut et quelles données personnalisées vous pouvez fournir pour créer les modèles de personnalisation des activités de **[!UICONTROL Automated Personalization]** et de **[!UICONTROL ciblage automatique]**.

>[!ENDSHADEBOX]

[!DNL Adobe Target] collecte et utilise automatiquement diverses données pour créer ses algorithmes de personnalisation dans les activités **[!UICONTROL Automated Personalization]** (AP) et **[!UICONTROL Ciblage automatique]** (AT). Lorsqu’un visiteur accède à une activité de **[!UICONTROL Automated Personalization]** ou de **[!UICONTROL ciblage automatique]**, un instantané des informations est transmis à un ensemble d’« enregistrements d’identification » (les données du visiteur sur lesquelles les algorithmes de personnalisation s’appuient).

Pour en savoir plus sur les algorithmes de personnalisation [!DNL Target], consultez [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Catégories d’attributs [!DNL Target] par défaut

Le tableau suivant présente les données collectées par les activités de **[!UICONTROL ciblage automatique]** et **[!UICONTROL ciblage automatique]** par défaut, sans configuration de [!DNL Target] ou d’autres solutions [!DNL Adobe]. Le tableau inclut également la convention de nommage utilisée pour indiquer ces attributs dans les [rapports Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le chargement de données supplémentaires, consultez [Chargement de données pour les [!DNL Target] algorithmes de personnalisation](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans les rapports **[!UICONTROL Insights]** |
| --- | --- | --- | --- |
| Paramètres d’environnement | ENV | Informations sur l’environnement d’un utilisateur, notamment le système d’exploitation, le navigateur et l’heure du jour ou du jour de la semaine. | Navigateur - [Nom De L’Attribut]<br>Système D’Exploitation - [Valeur] |
| Géographie | GÉO | Informations sur la zone géographique d’un utilisateur, obtenues via la recherche d’adresses IP. | Géolocalisation - [attribut géolocalisé] |
| Appareil mobile | FOULE | Informations sur l’appareil mobile d’un utilisateur. | Appareil - [attribut d’appareil]<br>Mobile - [attribut mobile] |
| [!DNL Target] segments de reporting | SEG | Segments de reporting configurés dans le reporting [!DNL Target]. | Segment De Création De Rapports - [Nom Du Segment] |
| Comportement de la session | SES | Informations sur le comportement de l’utilisateur, telles que le nombre de pages vues. | Profil Du Visiteur - [Nom De L’Attribut] |

## Catégories d’attributs [!DNL Target] personnalisées

Le tableau suivant présente les données fournies par le client collectées par les activités de **[!UICONTROL ciblage automatique]** et **[!UICONTROL Automated Personalization]**. Ces données ne sont collectées que si vous les fournissez. Les noms d’attributs et les valeurs d’exemple spécifiques sont spécifiques à votre configuration système.

| Catégorie de données | Préfixe système | Description | Nom d’affichage dans les rapports **[!UICONTROL Insights]** |
| --- | --- | --- | --- |
| Paramètres de page | BOX | Paramètres de page personnalisés (« paramètres mbox ») transmis dans l’appel à [!DNL Target]. | Personnalisé - Paramètre de mbox - [nom du paramètre] |
| Profil [!DNL Target] | PRO | Les attributs de profil personnalisés sont directement chargés sur le profil [!DNL Target] via l’API ou le paramètre de page et les scripts de profil [!DNL Target]. | Personnalisé - Profil du visiteur - [nom de l’attribut] |
| Attributs du client | CRS | Attributs du client chargés dans le profil [!DNL Target] via le [[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Personnalisé - Profil du visiteur - [nom de l’attribut] |
| paramètres d’URL | URL | URL et tout paramètre d’URL pour la page actuellement consultée. | Personnalisé - Paramètre d’URL - [Paramètre d’URL] |
| URL de référence | RÉF | l’URL de référence et les paramètres d’URL correspondants ; | Personnalisé - [Paramètre d’URL de renvoi] - [Valeur du paramètre] |
| [!DNL Adobe Experience Cloud] audiences partagées | AAM | Toutes les audiences partagées avec [!DNL Target] à partir d&#39;autres solutions [!DNL Adobe Experience Cloud] (par exemple, [!DNL Adobe Audience Manager] et [!DNL Adobe Analytics], via [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Personnalisé - Audience Experience Cloud - [Nom De L’Audience] |
| [!DNL Adobe Experience Platform Real-time CDP] audiences | UPS | Audiences de Platform Real-time CDP partagées avec [!DNL Target] via **[!UICONTROL Destinations]**. |  |

## Blocage des fonctionnalités des algorithmes de machine learning [!DNL Target]

Les fonctionnalités peuvent être bloquées à partir des algorithmes de machine learning [!DNL Target], ce qui empêche leur utilisation dans n’importe quel modèle ou activité **[!UICONTROL Automated Personalization]** ou **[!UICONTROL Ciblage automatique]**.

Pour plus d&#39;informations, consultez [Présentation de l&#39;API Modèles (qui Place sur la liste bloquée)](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} dans le *[!DNL Adobe Target]Guide du développeur*.

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
| Browser - Day of Week | Jour de la semaine où le visiteur a accédé à l’activité. | 0 - 6.<br>(0 correspond à dimanche) | ENV_DayOfWeek |
| Browser - Hour of Day | Heure du jour où le visiteur a accédé à l’activité. | 0 - 23<br>(0 correspond à minuit) | ENV_UserHour |
| Browser - Hour of Week | Heure de la semaine où le visiteur a accédé à l’activité. | 0 - 168<br>(dimanche minuit est 0) | ENV_WeekHour |
| Browser - Language Setting | Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l’activité. | English<br>German | ENV_Language |
| Browser - Time of Day | Heure du navigateur lorsque le visiteur a accédé à l’activité. | 0, 6, 12, 18<br>(0 est la nuit, 6 est le matin,<br>12 est l’après-midi et 18 est le soir) | ENV_LocalTimePeriod |
| Browser - Timezone | Fuseau horaire du visiteur lors de l’accès à l’activité. | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | Type de navigateur utilisé par le visiteur lors de l’accès à l’activité. | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>Autre | ENV_Browser |
| Browser - Weekday/Weekend | État de travail lorsque le visiteur a accédé à l’activité (week-end, heures de travail ou loisirs en semaine). | Le samedi et le dimanche sont le week-end<br>Du lundi au vendredi 0900 - 1800 est le temps de travail<br>Du lundi au vendredi après 1800 jusqu&#39;au 0900 est le temps libre en semaine | ENV_UserHourType |
| Browser - Window Height (px) | Hauteur de fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | ENV_BrowserHeight |
| Browser - Window Width (px) | Largeur de la fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | ENV_BrowserWidth |
| Appareil - Hauteur d’écran (px) | Hauteur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | ENV_ScreenHeight |
| Appareil - Largeur d’écran (px) | Largeur d’écran de l’appareil utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. | ENV_ScreenWidth |
| Système d’exploitation | Système d’exploitation sur l’appareil du visiteur utilisé pour accéder à l’activité. | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>Robot de recherche<br>Système d&#39;exploitation inconnu | ENV_OperatingSystem |
| Operating System - Version | Version du système d’exploitation utilisée par le visiteur pour accéder à l’activité. | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | Première page vue par le visiteur lors de l’accès à votre site. | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## Données géographiques {#geo}

| Attribute name | Description de l’attribut | Exemples de valeurs | Nom du système |
| --- | --- | --- | --- |
| Geo - City | Ville à partir de laquelle le visiteur a accédé à l’activité. | San Francisco | Geo_City |
| Geo - Country | Pays depuis lequel le visiteur a accédé à l’activité. | Allemagne | Geo_Country |
| Geo - DMA | Zone desservie à partir de laquelle le visiteur a accédé à l’activité. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l’activité. | 47,269<br>Arrondi à 3 décimales (précision d&#39;environ 100 mètres) | Latitude_GÉO |
| Geo - Longitude | Longitude à partir de laquelle le visiteur a accédé à l’activité. | -122,269<br>Arrondi à 3 décimales (précision d&#39;environ 100 mètres) | GEO_Longitude |
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
| Profil du visiteur - Moyenne de pages vues par visite pendant l’activité | Indique le nombre moyen de pages vues par session, à l’exception de la session en cours. | Double | SES_REQUESTS_PER_SESSION |
| Visitor Profile - Average Time per Visit | Indique la durée moyenne passée par visite/session. Ceci n’inclut pas la session en cours. | Double, millisecondes | SES_TIME_PER_SESSION |
| Visitor Profile - First Visit | Spécifie l&#39;heure de la première visite avec laquelle l&#39;utilisateur a interagi avec [!DNL Target]. | Double, millisecondes | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | Indique les heures écoulées depuis la dernière visite de cette activité particulière. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Indique le nombre d’impressions à une combinaison emplacement/contenu spécifique dans une activité particulière. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Profil Du Visiteur - Dernière Interaction [!DNL Target] | Indique l&#39;heure de la dernière interaction avec [!DNL Target]. L’interaction se produit sur chaque requête [!DNL Target], car l’implémentation actuelle de [!DNL Target] met à jour le profil de chaque requête. | Double, millisecondes | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Indique le nombre total de pages vues (impressions), y compris la visite/session en cours jusqu’à ce que le visiteur rejoigne l’activité. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Indique le nombre de pages vues dans la visite/session en cours jusqu’à ce que le visiteur rejoigne l’activité. Plus précisément, le nombre d’impressions. Ces impressions ne sont pas de vraies pages vues, il s’agit plutôt du nombre de fois où la requête a atteint [!DNL Target]. [!DNL Target] n&#39;est pas capable de distinguer les délais d&#39;expiration ou toute autre raison pour laquelle l&#39;utilisateur n&#39;a pas reçu ou vu le contenu. | Double (uniquement nombre entier positif) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Indique l’heure à laquelle la visite/session actuelle avec [!DNL Target] a démarré. La visite avec [!DNL Target] peut être lancée sans entrer dans une activité. Il suffit d’appeler une requête [!DNL Target]. Un visiteur peut mettre un certain temps avant d’accéder à l’activité et que l’instantané soit pris. | Double, millisecondes | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Indique l’heure de début de la dernière visite/session avec [!DNL Target]. Cet attribut est mis à jour lorsque la session expire.<br>S’il s’agit de la première session pour le visiteur, `LAST_SESSION_START = 0.` est généré | Double, millisecondes | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Indique la durée entre la session précédente et l’heure à laquelle l’utilisateur saisit l’activité et l’instantané est exécuté. | Double, millisecondes | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Spécifie la différence entre la dernière interaction avec [!DNL Target] et le moment où la visite actuelle a commencé. Cet attribut peut être considéré comme une durée de visite/session jusqu’à ce que l’utilisateur entre dans l’activité et que l’instantané soit pris.<br>Les valeurs négatives se produisent lorsque le démarrage de la session et l&#39;heure de la dernière mise à jour sont déclenchés par le même appel [!DNL Target]. Les valeurs négatives doivent être considérées comme 0 (zéro). | Double, millisecondes | SES_SESSION_TIME |
| Profil du visiteur - Nombre total de visites | Indique le nombre total de visites/sessions. N’inclut pas la visite/session active. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Indique le nombre de visites sur une activité particulière. En l’absence de visite précédente, renvoie 0 (zéro). | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Indique le nombre de visites/sessions sur une activité particulière en cas d’au moins une conversion durant la visite. | Double | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | Nombre de visites/sessions sans conversion sur une activité particulière. Cette valeur est réinitialisée à zéro après la conversion ou -1 si la conversion n’a jamais eu lieu. | Double (nombre entier positif uniquement) 1, 2, 3, etc. | SES_SUCCESS_RECENCY |
