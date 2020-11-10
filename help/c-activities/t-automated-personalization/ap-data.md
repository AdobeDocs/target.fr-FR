---
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes
description: Adobe Target collecte et utilise automatiquement une diversité de données pour composer ses algorithmes de personnalisation dans les activités Automated Personalization (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).
title: Collecte de données pour les algorithmes de personnalisation d’Adobe Target
feature: ap
translation-type: tm+mt
source-git-commit: 2b31d26bab2f2b702947c907c1d6966e5d0f20e3
workflow-type: tm+mt
source-wordcount: '1754'
ht-degree: 92%

---


# Collecte de données ![PREMIUM](/help/assets/premium.png) pour les algorithmes de personnalisation Target

[!DNL Adobe Target] collecte et utilise automatiquement diverses données pour créer ses algorithmes de personnalisation dans les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Cible] (AT). Lorsqu’un visiteur entre dans une activité AP ou AT, un instantané des informations est transmis à un ensemble d’&quot;enregistrements de formation&quot; (les données du visiteur sur lesquelles les algorithmes de personnalisation apprendront).

Pour en savoir plus sur les algorithmes de personnalisation de Target, reportez-vous à la section [Algorithme Forêt aléatoire](/help/c-activities/t-automated-personalization/algo-random-forest.md).

The following table shows the data collected by [!UICONTROL Automated Personalization] and [!UICONTROL Auto-Target] by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le chargement de données supplémentaires, reportez-vous à la section [Chargement de données pour les algorithmes de personnalisation de Target](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Type de données | Description | Convention de dénomination des types de données | Attributs exemples |
| --- | --- | --- | --- |
| [Données de périphérique et de mobile](#device-mobile) | Informations spécifiques au périphérique et au mobile.<br>Voir « Données sur le périphérique et sur mobile » ci-dessous. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Système d’exploitation d’un appareil mobile<br>Taille de l’écran mobile |
| [Données environnementales](#env) | Informations sur le système d’exploitation du visiteur et comment et quand le visiteur accède à l’activité. | `Browser - / Operating System] - [Attribute Name]` | Browser - Type |
| Segment Experience Cloud | Audiences créées dans Audience Manager ou Analytics et partagées dans Experience Cloud | `Custom - Experience Cloud Audience - [Audience Name]` | Données personnalisées |
| [Données géographiques](#geo) | Informations sur la position du visiteur<br>Voir « Données géographiques » ci-dessous. | `Geo - [geo attribute]` | Ville<br>Pays<br>Région / État<br>Code postal<br>Latitude<br>Longitude<br>ISP ou opérateur de téléphonie mobile |
| Attributs de profil | Scripts ou attributs de profil directement chargés dans le profil Target via l’API Update | `Custom - Visitor Profile - [attribute name]` | Données personnalisées |
| Paramètres d’URL de référence | En général, l’URL de référence est l’URL qui fait référence à une page particulière qui a déclenché l’appel de Cible.<br>Il est à noter que cette variable peut être affectée par l’activité des utilisateurs sur votre site, ainsi que par la mise en œuvre technique de ce dernier. | `Custom - [Referring URL Parameter] - [Parameter value]` | Données personnalisées |
| Création de rapports sur les segments | Tout segment configuré dans la configuration de l’activité. | `Reporting Segment -[Segment Name]` | Données personnalisées |
| [Données de session](#session) | Informations sur le comportement du visiteur dans la session lors de l’accès à l’activité. | `Visitor Profile - [Attribute Name]` | Visitor Profile - Start of Most Recent Visit |
| paramètres d’URL | Target inspecte l’URL pour extraire les paramètres d’URL. | `Custom - URL Parameter - [URL Parameter]` | Données personnalisées |

Les sections suivantes contiennent des informations détaillées sur les différents types de données, notamment les noms d’attributs, descriptions et exemples de valeurs.

## Données de périphérique et de mobile {#device-mobile}

| Attribute name | Description de l’attribut | Exemples de valeurs |
| --- | --- | --- |
| Mobile - Device - Brand | Marque du périphérique mobile utilisé par le visiteur pour accéder à l’activité. | Apple |
| Mobile - Device - eReader | Indique si le périphérique est un eReader. | 0 est Faux, 1 est Vrai |
| Mobile - Device - Game Console | Indique si le périphérique est une console de jeu. | 0 est Faux, 1 est Vrai |
| Mobile - Device - Media Player | Indique si le périphérique est un lecteur multimédia. | 0 est Faux, 1 est Vrai |
| Mobile - Device - Mobile Phone | Indique si le périphérique est un téléphone mobile. | 0 est Faux, 1 est Vrai |
| Mobile - Device - Model Name | Nom du modèle du périphérique mobile utilisé par le visiteur pour accéder à l’activité. | iPhone XS |
| Device - Set-Top Box | Indique si le périphérique est un décodeur. | 0 est Faux, 1 est Vrai |
| Mobile - Device - Tablet | Indique si le périphérique est une tablette. | 0 est Faux, 1 est Vrai |
| Mobile - Pixel Density (ppi) | Densité en pixels du périphérique mobile utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |
| Mobile - Système d’exploitation - OSX (Android, Windows, etc.) | Indique si l’utilisateur a utilisé un OSX (ou Android, Windows, etc.) pour accéder à l’activité. | 0 est Faux, 1 est Vrai |
| Mobile - Screen Height (px) | Hauteur d’écran du périphérique mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |
| Mobile - Screen Width (px) | Largeur d’écran du périphérique mobile (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |

## Données environnementales {#env}

| Attribute name | Description de l’attribut | Exemples de valeurs |
| --- | --- | --- |
| Browser - Day of Week | Jour de la semaine où le visiteur a accédé à l’activité. | 0 à 6.<br>(0 est dimanche) |
| Browser - Hour of Day | Heure du jour où le visiteur a accédé à l’activité. | 0 à 23<br>(0 est minuit) |
| Browser - Hour of Week | Heure de la semaine où le visiteur a accédé à l’activité. | 0 à 168<br>(le dimanche minuit est 0) |
| Browser - Language Setting | Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l’activité. | English<br>German |
| Browser - Screen Height (px) | Hauteur d’écran du navigateur du périphérique (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |
| Browser - Time of Day | Heure du navigateur lorsque le visiteur a accédé à l’activité. | 0, 6, 12, 18<br>(0 est la nuit, 6 est le matin,<br>12 est l’après-midi et 18 est le soir) |
| Browser - Timezone | Fuseau horaire du visiteur lors de l’accès à l’activité. | Pacific Time<br>Eastern Time<br>GMT |
| Browser - Type | Type de navigateur utilisé par le visiteur lors de l’accès à l’activité. | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| Browser - Weekday/Weekend | État de travail lorsque le visiteur a accédé à l’activité (week-end, heures de travail ou loisirs en semaine). | Samedi et dimanche constituent le week-end<br>Lundi-vendredi 09h00 à 18h00 constitue le temps de travail<br>Lundi au vendredi après 18h00 jusqu’à 9h00 constitue les loisirs en semaine. |
| Browser - Window Height (px) | Hauteur de fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |
| Browser - Window Width (px) | Largeur de la fenêtre du navigateur (en pixels) utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |
| Device - Screen Height | Hauteur d’écran du périphérique utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |
| Device - Screen Width | Largeur d’écran du périphérique utilisé par le visiteur pour accéder à l’activité. | 1, 2, 3, etc. |
| Système d’exploitation | Système d’exploitation sur le périphérique du visiteur utilisé pour accéder à l’activité. | Mac OS<br>Windows<br>Linux<br>Search Bot<br>OS Unknown |
| Operating System - Version | Version du système d’exploitation utilisée par le visiteur pour accéder à l’activité. | Windows 10<br>Mac OS 10 |
| Traffic Sources - Referring Landing Page URL | Première page vue par le visiteur lors de l’accès à votre site. | `https://www.adobe.com/ecloud.html` |

## Données géographiques {#geo}

| Attribute name | Description de l’attribut | Exemples de valeurs |
| --- | --- | --- |
| Geo - City | Ville à partir de laquelle le visiteur a accédé à l’activité. | San Francisco |
| Geo - Country | Pays depuis lequel le visiteur a accédé à l’activité. | Allemagne |
| Geo - DMA | Zone desservie à partir de laquelle le visiteur a accédé à l’activité. | Charlottesville |
| Geo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l’activité. | 47.269<br>Arrondi à 3 décimales près (précision d’environ 100mètres) |
| Geo - Longitude | Longitude à partir de laquelle le visiteur a accédé à l’activité. | -122.269<br>Arrondi à 3 décimales près (précision d’environ 100 mètres) |
| Geo - State/Region | État ou région à partir duquel le visiteur a accédé à l’activité. | Utah<br>New South Wales |
| Geo - Zip Code | Code postal à partir duquel le visiteur a accédé à l’activité. | 84004 |
| Mobile - Carrier | Opérateur de téléphonie mobile utilisé par le visiteur lors de l’accès à l’activité. | Vodafone<br>T-Mobile |
| Network - Connection Speed | Vitesse de connexion réseau du périphérique lorsque le visiteur a accédé à l’activité. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| Network - Domain Name | Nom du domaine réseau à partir duquel le visiteur a accédé à l’activité. | `nnt.net` |
| Network - ISP | Réseau depuis lequel le visiteur a accédé à l’activité. | nnt communications corporation |

## Données de session {#session}

| Attribute name | Description de l’attribut | Exemples de valeurs |
| --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | Indique la somme de toutes les valeurs de commande pour toutes les visites/sessions sur une activité particulière. | Double |
| Visitor Profile - Activity Lifetime Time on Site | Indique le temps total passé par le visiteur sur le site, à l’exclusion de la session en cours et est mis à jour à l’expiration de la session. | Double, millisecondes |
| Visitor Profile -Average Page Views per Visit during Activity | Indique le nombre moyen de pages vues par session, à l’exception de la session en cours. | Double |
| Visitor Profile - Average Time per Visit | Indique la durée moyenne passée par visite/session. Ceci n’inclut pas la session en cours. | Double, millisecondes |
| Visitor Profile - First Visit | Indique l’heure de la première visite où l’utilisateur a interagi avec Target. | Double, millisecondes |
| Visitor Profile - Hours since Last Visit | Indique les heures écoulées depuis la dernière visite de cette activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. |
| Visitor Profile - Impressions of Location/Content | Indique le nombre d’impressions à une combinaison emplacement/contenu spécifique dans une activité particulière. | Double (uniquement nombre entier positif) 1, 2, 3, etc. |
| Visitor Profile - Last Target Interaction | Indique l’heure de la dernière interaction avec Target. Interaction happens on every [!DNL Target] request because the current implementation of [!DNL Target] updates the profile on each request. | Double, millisecondes |
| Visitor Profile - Pages Seen Before Activity | Indique le nombre total de pages vues (impressions), y compris la visite/session actuelle jusqu’à ce que le visiteur entre dans l’activité. | Double (uniquement nombre entier positif) 1, 2, 3, etc. |
| Visitor Profile - Page Views in Current Visit | Indique le nombre de pages vues lors de la visite/session actuelle jusqu’à ce que le visiteur entre dans l’activité. Plus précisément, le nombre d’impressions. Ces impressions ne sont pas des pages vues réelles. Il s’agit plutôt du nombre de fois où la requête a atteint Target. Target ne peut pas distinguer les dépassements de délai ou les autres raisons pour lesquelles l’utilisateur n’a pas reçu ou consulté le contenu. | Double (uniquement nombre entier positif) |
| Visitor Profile - Start of Current Visit | Indique l’heure de début de la visite/session actuelle avec Target. La visite avec Target peut être lancée sans entrer dans une activité. All that is required is a call to any [!DNL Target] request. Un visiteur peut prendre un certain temps avant de saisir l’activité et l’instantané est pris. | Double, millisecondes |
| Visitor Profile - Start of Most Recent Visit | Indique l’heure de début de la dernière visite/session avec Target. Cet attribut est mis à jour lorsque la session expire.<br>S’il s’agit de la première session du visiteur, elle se traduira par une `LAST_SESSION_START = 0.` | Double, millisecondes |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Indique la durée entre la session précédente et l’heure à laquelle l’utilisateur saisit l’activité et l’instantané est exécuté. | Double, millisecondes |
| Visitor Profile - Time in Visit Before Enter Activity | Indique la différence entre la dernière interaction avec Target et la date de début de la visite en cours. Cet attribut peut être considéré comme une durée de visite/session jusqu’à ce que l’utilisateur entre dans l’activité et que l’instantané soit pris.<br>[!DNL Target]Des valeurs négatives surviennent lorsque la session démarre et que la dernière heure de mise à jour est déclenchée par le même appel de Les valeurs négatives doivent être considérées comme 0 (zéro). | Double, millisecondes |
| Profil de visiteur – Nombre total de visites | Indique le nombre total de visites/sessions. N’inclut pas la visite/session active. | Double (uniquement nombre entier positif) 1, 2, 3, etc. |
| Visitor Profile - Total Visits to Activity | Indique le nombre de visites sur une activité particulière. En l’absence de visite précédente, renvoie 0 (zéro). | Double (uniquement nombre entier positif) 1, 2, 3, etc. |
| Visitor Profile - Total Visits to Activity with Conversion | Indique le nombre de visites/sessions sur une activité particulière en cas d’au moins une conversion durant la visite. | Double |
| Visitor Profile - Visits to Activity with No Conversion | Nombre de visites/sessions sans conversion sur une activité particulière. Cette valeur est réinitialisée à zéro après la conversion ou -1 si la conversion n’a jamais eu lieu. | Double (uniquement nombre entier positif) 1, 2, 3, etc. |
