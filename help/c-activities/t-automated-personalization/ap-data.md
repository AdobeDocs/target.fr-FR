---
description: Target collecte et utilise automatiquement une diversité de données pour composer ses algorithmes de personnalisation dans les activités Automated Personalization (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).
seo-description: Adobe Target collecte et utilise automatiquement une variété de données pour créer ses algorithmes de personnalisation dans les activités de personnalisation automatisée (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).
seo-title: Collecte de données pour les algorithmes de personnalisation d'Adobe Target
solution: Target
title: Collecte de données pour les algorithmes de personnalisation de Target
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: tm+mt
source-git-commit: 59a838b5cca86c7f67fa62494dc30eb64a3e70c2

---


# Collecte de données ![PREMIUM](/help/assets/premium.png) pour les algorithmes de personnalisation Target{#data-collection-for-the-target-personalization-algorithms}

Target collecte et utilise automatiquement une diversité de données pour composer ses algorithmes de personnalisation dans les activités Automated Personalization (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).

Pour en savoir plus sur les algorithmes de personnalisation de Target, reportez-vous à la section [Algorithme Forêt aléatoire](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

Le tableau suivant affiche les données collectées par la personnalisation automatisée par défaut, sans que le spécialiste du marketing ait à intervenir, ainsi que la convention de dénomination utilisée pour indiquer ces attributs dans [Rapports de personnalisation](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le chargement de données supplémentaires, reportez-vous à la section [Chargement de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Type de données | Description | Convention de dénomination des types de données | Attributs exemples |
| --- | --- | --- | --- |
| Paramètres d’URL | Target inspecte l’URL pour extraire les paramètres d’URL. | `Custom - URL Parameter - [URL Parameter]` | Données personnalisées |
| Paramètres d’URL de référence | En règle générale, l’URL de référence est celle qui sert de référent à une page particulière ayant initialisé l’appel mbox.<br>Il est à noter que cette variable peut être affectée par l’activité des utilisateurs sur votre site, ainsi que par la mise en œuvre technique de ce dernier. | `Custom - [Referring URL Parameter] - [Parameter value]` | Données personnalisées |
| Données d’environnement et de session | Informations indiquant comment et quand l’utilisateur accède à l’activité. | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | Profil du visiteur - Début de la visite la plus récente<br>Profil du visiteur - Visites totales<br>Profil du visiteur - Durée moyenne par visiteur<br>Navigateur - Fuseau horaire<br>Navigateur - Jour de la semaine<br>Navigateur - Paramètres de langue<br>Navigateur - Type<br>Système opérateur - Version |
| Géographie | Informations sur la position du visiteur | `Geo - [geo attribute]` | Ville<br>Pays<br>Région / État<br>Code postal<br>Latitude<br> Longitude<br>ISP ou opérateur de téléphonie mobile |
| Données de périphérique et de mobile | Informations spécifiques au périphérique et au mobile. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Système d’exploitation du périphérique mobile<br>Taille d’écran du dispositif portable |

Les sections suivantes contiennent des informations détaillées sur les différents types de données, notamment les noms d&#39;attributs, descriptions et exemples de valeurs.

Notez que certaines valeurs sont arrondies à l&#39;entier ou à l&#39;heure le plus proche.

## Données environnementales et de session

| Attribute name | Description de l&#39;attribut | Exemples de valeurs |
| --- | --- | --- |
| Navigateur – Jour de la semaine | Jour de la semaine lorsque le visiteur a accédé à l&#39;activité. | 0 à 6.<br>(0 est dimanche) |
| Navigateur - Heure du jour | Heure du jour où le visiteur a accédé à l&#39;activité. | 0 à 23 |
| Navigateur - Heure de la semaine | Heure de la semaine lorsque le visiteur a accédé à l&#39;activité. | 0 à 168<br>(le dimanche minuit est 0) |
| Navigateur – Paramètre de langue | Langue spécifiée dans le navigateur du visiteur utilisé pour accéder à l&#39;activité. | Englishallemand<br> |
| Navigateur - Hauteur d&#39;écran (px) | Hauteur d&#39;écran du navigateur du périphérique (en pixels) utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |
| Navigateur - Heure de la journée | Heure du navigateur lorsque le visiteur a accédé à l&#39;activité. | 0, 6, 12, 18<br>(0 est nuit, 6 is morning, 12 is afteris 12 is evening is evening) |
| Navigateur – Fuseau horaire | Fuseau horaire du visiteur lors de l&#39;accès à l&#39;activité. | Pacifique timeeastern<br>timegmt<br> |
| Navigateur – Type | Type de navigateur utilisé par le visiteur lors de l&#39;accès à l&#39;activité. | Chromefirefoxinternet<br><br>Explorer 10<br>safariother<br> |
| Navigateur - Jour de semaine/Week-end | État de travail (week-end, heures de travail ou heure de semaine libre) lorsque le visiteur a accédé à l&#39;activité. | Samedi et dimanche is weekendmonday<br>allant du vendredi 0900 à 1800, il s&#39;agit du mois de timemonday<br>jusqu&#39;au vendredi après 1800 jusqu&#39;à ce que 0900 soit un temps de semaine gratuit |
| Navigateur - Hauteur de fenêtre (px) | Hauteur de fenêtre du navigateur (en pixels) utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |
| Navigateur - Largeur de fenêtre (px) | Largeur de la fenêtre du navigateur (en pixels) utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |
| Périphérique - Hauteur d&#39;écran | Hauteur d&#39;écran du périphérique utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |
| Périphérique - Largeur d&#39;écran | Largeur d&#39;écran du périphérique utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |
| Mobile &gt; Densité en pixels (ppi) | Densité en pixels du périphérique mobile utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |
| Système d’exploitation | Système d&#39;exploitation utilisé par le périphérique du visiteur pour accéder à l&#39;activité. | Mac oswindows<br>10<br>linuxsearch<br>botunknown<br>OS |
| Système d&#39;exploitation - Version | Version du système d&#39;exploitation utilisée par le visiteur pour accéder à l&#39;activité. | Windows 10<br>Mac OS 10 |
| Sources de trafic - URL de la page d&#39;entrée de référence | Première page vue par le visiteur lors de l&#39;accès à votre site. | `https://www.adobe.com/experience-cloud.html` |

## Données géographiques

| Attribute name | Description de l&#39;attribut | Exemples de valeurs |
| --- | --- | --- |
| Géo - Ville | Ville à partir de laquelle le visiteur a accédé à l&#39;activité. | San Francisco |
| Géo - Pays | Pays depuis lequel le visiteur a accédé à l&#39;activité. | Allemagne |
| Géo - DMA | Zone de marketing désignée à partir de laquelle le visiteur a accédé à l&#39;activité. | Charlottesville |
| Géo - Latitude | Latitude à partir de laquelle le visiteur a accédé à l&#39;activité. | 47.269<br>Arrondi à 3 décimales (précision environ 100 mètres) |
| Géo - Longitude | Longitude à partir de laquelle le visiteur a accédé à l&#39;activité. | -122.269<br>Arrondi à 3 décimales (précision environ 100 mètres) |
| Géo - État/région | Etat ou région à partir duquel le visiteur a accédé à l&#39;activité. | Utahnew<br>South Wales |
| Géo - Code postal | Code postal à partir duquel le visiteur a accédé à l&#39;activité. | 84004 |
| Mobile - Opérateur | Opérateur de téléphonie mobile utilisé par le visiteur lors de l&#39;accès à l&#39;activité. | Vodafonet<br>-Mobile |
| Réseau - Vitesse de connexion | Vitesse de connexion réseau lorsque le visiteur a accédé à l&#39;activité. | Broadbandcabledslmobilewirelesssatellite<br><br><br><br><br> |
| Réseau - Nom de domaine | Nom du domaine réseau à partir duquel le visiteur a accédé à l&#39;activité. | `nnt.net` |
| Réseau - FAI | Réseau depuis lequel le visiteur a accédé à l&#39;activité. | nnt communications corporation |

## Données mobiles

| Attribute name | Description de l&#39;attribut | Exemples de valeurs |
| --- | --- | --- |
| Mobile - Appareil - Marque | Marque du périphérique mobile utilisée par le visiteur pour accéder à l&#39;activité. | Apple |
| Mobile - Périphérique - Nom du modèle | Nom du modèle du périphérique mobile utilisé par le visiteur pour accéder à l&#39;activité. | iphone XS |
| Mobile - Système d&#39;exploitation - OSX | Indique si l&#39;utilisateur a utilisé un périphérique OSX pour accéder à l&#39;activité. | 0 est Faux, 1 est Vrai |
| Mobile - Hauteur d&#39;écran (px) | Hauteur d&#39;écran du périphérique mobile (en pixels) utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |
| Mobile - Largeur d&#39;écran (px) | Largeur d&#39;écran du périphérique mobile (en pixels) utilisée par le visiteur pour accéder à l&#39;activité. | 1, 2, 3, etc. |