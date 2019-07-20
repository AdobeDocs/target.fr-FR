---
description: Adobe Target collecte et utilise automatiquement une variété de données pour créer ses algorithmes de personnalisation dans les activités de personnalisation automatisée (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).
keywords: données environnementales ; data data ; données géographiques ; données géographiques ; données de périphérique ; données mobiles ; attributs ; attributs de profil
seo-description: Adobe Target collecte et utilise automatiquement une variété de données pour créer ses algorithmes de personnalisation dans les activités de personnalisation automatisée (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).
seo-title: Collecte de données pour les algorithmes de personnalisation d'Adobe Target
solution: Target
title: Collecte de données pour les algorithmes de personnalisation de Target
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: tm+mt
source-git-commit: 156587a0375fe2dbf8c461e310b2eae04b491b57

---


# Collecte de données ![PREMIUM](/help/assets/premium.png) pour les algorithmes de personnalisation Target{#data-collection-for-the-target-personalization-algorithms}

Target collecte et utilise automatiquement une diversité de données pour composer ses algorithmes de personnalisation dans les activités Automated Personalization (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).

Pour en savoir plus sur les algorithmes de personnalisation de Target, reportez-vous à la section [Algorithme Forêt aléatoire](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

The following table shows the data collected by Automated Personalization and Auto-Target by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le chargement de données supplémentaires, reportez-vous à la section [Chargement de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Type de données | Description | Convention de dénomination des types de données | Attributs exemples |
| --- | --- | --- | --- |
| [Données de périphérique et de mobile](#device-mobile) | Informations spécifiques au périphérique et au mobile.<br>Voir « Données sur le périphérique et sur mobile » ci-dessous. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Mobile Device OS<br>Mobile Screen Size |
| [Données environnementales](#env) | Informations sur le système d'exploitation du visiteur et comment et quand le visiteur accède à l'activité. | `Browser - / Operating System] - [Attribute Name]` | Navigateur – Type |
| Segment Experience Cloud | Audiences créées dans Audience Manager ou Analytics et partagées à l'échelle d'Experience Cloud | `Custom - Experience Cloud Audience - [Audience Name]` | Données personnalisées |
| [Données géographiques](#geo) | Informations sur la position du visiteur<br>Voir « Données géographiques » ci-dessous. | `Geo - [geo attribute]` | Ville<br>Pays<br>Région / État<br>Code postal<br>Latitude<br> Longitude<br>ISP ou opérateur de téléphonie mobile |
| Attributs de profil | Scripts ou attributs de profil directement chargés dans le profil Target via l'API Update | `Custom - Visitor Profile - [attribute name]` | Données personnalisées |
| Paramètres d'URL de référence | En règle générale, l’URL de référence est celle qui sert de référent à une page particulière ayant initialisé l’appel mbox.<br>Il est à noter que cette variable peut être affectée par l’activité des utilisateurs sur votre site, ainsi que par la mise en œuvre technique de ce dernier. | `Custom - [Referring URL Parameter] - [Parameter value]` | Données personnalisées |
| Création de rapports sur les segments | Tout segment configuré dans la configuration de l'activité. | `Reporting Segment -[Segment Name]` | Données personnalisées |
| [Données de session](#session) | Informations sur le comportement du visiteur dans la session lors de l'accès à l'activité. | `Visitor Profile - [Attribute Name]` | Profil du visiteur – Début de la visite la plus récente |
| paramètres d’URL | Target inspecte l’URL pour extraire les paramètres d’URL. | `Custom - URL Parameter - [URL Parameter]` | Données personnalisées |

Les sections suivantes contiennent des informations détaillées sur les différents types de données, notamment les noms d'attributs, descriptions et exemples de valeurs.

## Device and Mobile data {#device-mobile}

| Attribute name | Description de l'attribut | Exemples de valeurs |
| --- | --- | --- |
| Mobile - Appareil - Marque | Marque du périphérique mobile utilisé par le visiteur pour accéder à l'activité. | Apple |
| Mobile - Périphérique - ereader | Indique si le périphérique est un opérateur ereader. | 0 est Faux, 1 est Vrai |
| Mobile - Périphérique - Console de jeu | Indique si le périphérique est une console de jeu. | 0 est Faux, 1 est Vrai |
| Mobile - Périphérique - Lecteur multimédia | Indique si le périphérique est un lecteur multimédia. | 0 est Faux, 1 est Vrai |
| Mobile - Périphérique - Téléphone mobile | Indique si le périphérique est un téléphone mobile. | 0 est Faux, 1 est Vrai |
| Mobile - Périphérique - Nom du modèle | Nom du modèle du périphérique mobile utilisé par le visiteur pour accéder à l'activité. | iphone XS |
| Périphérique - Zone supérieure | Indique si le périphérique est une zone supérieure. | 0 est Faux, 1 est Vrai |
| Mobile - Appareil - Tablette | Indique si le périphérique est une tablette. | 0 est Faux, 1 est Vrai |
| Mobile - Densité en pixels (ppi) | Densité en pixels du périphérique mobile utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |
| Mobile - Système d'exploitation - OSX (Android, Windows, etc.) | Indique si l'utilisateur a utilisé un OSX (ou Android, Windows, etc.) pour accéder à l'activité. | 0 est Faux, 1 est Vrai |
| Mobile - Hauteur d'écran (px) | Hauteur d'écran du périphérique mobile (en pixels) utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |
| Mobile - Largeur d'écran (px) | Largeur d'écran du périphérique mobile (en pixels) utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |

## Environmental data {#env}

| Attribute name | Description de l'attribut | Exemples de valeurs |
| --- | --- | --- |
| Navigateur – Jour de la semaine | Jour de la semaine lorsque le visiteur a accédé à l'activité. | 0 à 6.<br>(0 est dimanche) |
| Navigateur - Heure du jour | Heure du jour où le visiteur a accédé à l'activité. | 0 to 23<br>(0 is midnight) |
| Navigateur - Heure de la semaine | Heure de la semaine lorsque le visiteur a accédé à l'activité. | 0 to 168<br>(Sunday midnight is 0) |
| Navigateur – Paramètre de langue | Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l'activité. | English<br>German |
| Navigateur - Hauteur d'écran (px) | Hauteur d'écran du navigateur du périphérique (en pixels) utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |
| Navigateur - Heure de la journée | Heure du navigateur lorsque le visiteur a accédé à l'activité. | 0, 6, 12, 18<br>(0 is night, 6 is morning,<br>12 is afternoon, 18 is evening) |
| Navigateur – Fuseau horaire | Fuseau horaire du visiteur lors de l'accès à l'activité. | Pacific Time<br>Eastern Time<br>GMT |
| Navigateur – Type | Type de navigateur utilisé par le visiteur lors de l'accès à l'activité. | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| Navigateur - Jour de semaine/Week-end | État de travail lorsque le visiteur a accédé à l'activité (week-end, heures de travail ou jours de semaine gratuits). | Saturday and Sunday is weekend<br>Monday-Friday 0900 to 1800 is work time<br>Monday-Friday after 1800 until 0900 is weekday free time |
| Navigateur - Hauteur de fenêtre (px) | Hauteur de fenêtre du navigateur (en pixels) utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |
| Navigateur - Largeur de fenêtre (px) | Largeur de la fenêtre du navigateur (en pixels) utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |
| Périphérique - Hauteur d'écran | Hauteur d'écran du périphérique utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |
| Périphérique - Largeur d'écran | Largeur d'écran du périphérique utilisée par le visiteur pour accéder à l'activité. | 1, 2, 3, etc. |
| Système d’exploitation | Système d'exploitation sur le périphérique du visiteur utilisé pour accéder à l'activité. | Mac OS<br>Windows<br>Linux<br>Search Bot<br>Unknown OS |
| Système d'exploitation - Version | Version du système d'exploitation utilisée par le visiteur pour accéder à l'activité. | Windows 10<br>Mac OS 10 |
| Sources de trafic - URL de la page d'entrée de référence | Première page vue par le visiteur lors de l'accès à votre site. | `https://www.adobe.com/ecloud.html` |

## Geographical data {#geo}

| Attribute name | Description de l'attribut | Exemples de valeurs |
| --- | --- | --- |
| Géo - Ville | Ville à partir de laquelle le visiteur a accédé à l'activité. | San Francisco |
| Géo - Pays | Pays depuis lequel le visiteur a accédé à l'activité. | Allemagne |
| Géo - DMA | Zone de marketing désignée à partir de laquelle le visiteur a accédé à l'activité. | Charlottesville |
| Géo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l'activité. | 47.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| Géo - Longitude | Longitude à partir de laquelle le visiteur a accédé à l'activité. | -122.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| Géo - État/région | Etat ou région à partir duquel le visiteur a accédé à l'activité. | Utah<br>New South Wales |
| Géo - Code postal | Code postal à partir duquel le visiteur a accédé à l'activité. | 84004 |
| Mobile - Opérateur | Opérateur de téléphonie mobile utilisé par le visiteur lors de l'accès à l'activité. | Vodafone<br>T-Mobile |
| Réseau - Vitesse de connexion | Vitesse de connexion réseau du périphérique lorsque le visiteur a accédé à l'activité. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| Réseau - Nom de domaine | Nom du domaine réseau à partir duquel le visiteur a accédé à l'activité. | `nnt.net` |
| Réseau - FAI | Réseau depuis lequel le visiteur a accédé à l'activité. | nnt communications corporation |

## Session data {#session}

| Attribute name | Description de l'attribut | Exemples de valeurs |
| --- | --- | --- |
| Profil du visiteur - Valeur de la commande de durée de vie de l'activité | Indique la somme de toutes les valeurs de commande pour toutes les visites/sessions à une activité particulière. | Double |
| Profil du visiteur - Durée de vie de l'activité sur le site | Indique le temps total passé par le visiteur sur le site, à l'exclusion de la session en cours et est mis à jour à l'expiration de la session. | Double, millisecondes |
| Profil du visiteur -moyen pages vues par visite durant l'activité | Indique le nombre moyen de pages vues par session, à l'exception de la session en cours. | Double |
| Profil du visiteur – Durée moyenne par visite | Indique la durée moyenne passée par visite/session. Ceci n'inclut pas la session en cours. | Double, millisecondes |
| Profil du visiteur - Première visite | Indique l'heure de la première visite que l'utilisateur a interagi avec Target. | Double, millisecondes |
| Profil du visiteur - Heures depuis la dernière visite | Indique les heures écoulées depuis la dernière visite de cette activité particulière. | Double (uniquement nombre positif entier) 1, 2, 3, etc. |
| Profil du visiteur - Impressions de lieu/contenu | Indique le nombre d'impressions à une combinaison emplacement/contenu spécifique dans une activité particulière. | Double (uniquement nombre positif entier) 1, 2, 3, etc. |
| Profil du visiteur - Interaction de dernière cible | Indique l'heure de la dernière interaction avec Target. L'interaction survient sur chaque requête de mbox, car l'implémentation actuelle de Target met à jour le profil à chaque demande. | Double, millisecondes |
| Profil du visiteur - Pages vues avant l'activité | Indique le nombre total de pages vues (impressions), y compris la visite/session actuelle jusqu'à ce que le visiteur entre dans l'activité. | Double (uniquement nombre positif entier) 1, 2, 3, etc. |
| Profil du visiteur - Pages vues dans la visite actuelle | Indique le nombre de pages vues lors de la visite/session actuelle jusqu'à ce que le visiteur entre dans l'activité. Plus précisément, le nombre d'impressions. Ces impressions ne sont pas des pages vues réelles. Il s'agit plutôt du nombre de fois où la requête a atteint Target. Target ne peut pas distinguer les dépassements de délai ou les autres raisons pour lesquelles l'utilisateur n'a pas reçu ou consulté le contenu. | Double (uniquement nombre positif entier) |
| Profil du visiteur - Début de la visite actuelle | Indique l'heure de début de la visite/session actuelle avec Target. La visite avec Target peut être lancée sans entrer dans une activité. Tout ce qui est requis est un appel à une mbox. Un visiteur peut prendre un certain temps avant de saisir l'activité et l'instantané est pris. | Double, millisecondes |
| Profil du visiteur – Début de la visite la plus récente | Indique l'heure de début de la dernière visite/session avec Target. Cet attribut est mis à jour lorsque la session expire.<br>S'il s'agit de la première session du visiteur, elle se traduira par une `LAST_SESSION_START = 0.` | Double, millisecondes |
| Profil du visiteur - Heure depuis la visite la plus récente lors de la première saisie de l'activité | Indique la durée entre la session précédente et l'heure à laquelle l'utilisateur saisit l'activité et l'instantané est exécuté. | Double, millisecondes |
| Profil du visiteur - Heure de la visite avant de saisir l'activité | Indique la différence entre la dernière interaction avec Target et la date de début de la visite en cours. Cet attribut peut être considéré comme une durée de visite/session jusqu'à ce que l'utilisateur entre dans l'activité et que l'instantané soit exécuté.<br>Des valeurs négatives surviennent lorsque la session démarre et que la dernière heure de mise à jour est déclenchée par le même appel de mbox. Les valeurs négatives doivent être considérées comme 0 (zéro). | Double, millisecondes |
| Profil visiteur – Nombre total de visites | Indique le nombre total de visites/sessions. N'inclut pas la visite/session active. | Double (uniquement nombre positif entier) 1, 2, 3, etc. |
| Profil du visiteur - Visites totales à l'activité | Indique le nombre de visites d'une activité particulière. En l'absence de visite précédente, renvoie 0 (zéro). | Double (uniquement nombre positif entier) 1, 2, 3, etc. |
| Profil du visiteur - Visites totales à l'activité avec conversion | Indique le nombre de visites/sessions à une activité particulière en cas d'au moins une conversion durant la visite. | Double |
| Profil du visiteur - Visites à l'activité sans conversion | Nombre de visites/sessions sans conversion à une activité particulière. Cette valeur est réinitialisée à zéro après la conversion ou -1 si la conversion n'a jamais eu lieu. | Double (uniquement nombre positif entier) 1, 2, 3, etc. |
