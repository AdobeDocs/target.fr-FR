---
description: Target collecte et utilise automatiquement une diversité de données pour composer ses algorithmes de personnalisation dans les activités Automated Personalization (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).
seo-description: Target collecte et utilise automatiquement une diversité de données pour composer ses algorithmes de personnalisation dans les activités Automated Personalization (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).
seo-title: Collecte de données pour les algorithmes de personnalisation de Target
solution: Target
title: Collecte de données pour les algorithmes de personnalisation de Target
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: tm+mt
source-git-commit: 2baa75b6020b2f9229db68667c2e19a698954231

---


# Collecte de données ![PREMIUM](/help/assets/premium.png) pour les algorithmes de personnalisation Target{#data-collection-for-the-target-personalization-algorithms}

Target collecte et utilise automatiquement une diversité de données pour composer ses algorithmes de personnalisation dans les activités Automated Personalization (AP) et de ciblage automatique (AT). Lorsqu’un visiteur entre dans l’activité l’AP ou AT, un cliché des informations est transmis à un ensemble d’« enregistrements d’entraînement » (données de visiteur sur lesquelles les algorithmes de personnalisation fonderont leur auto-apprentissage).

Pour en savoir plus sur les algorithmes de personnalisation de Target, reportez-vous à la section  [Algorithme Forêt aléatoire](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

Le tableau suivant affiche les données collectées par la personnalisation automatisée par défaut, sans que le spécialiste du marketing ait à intervenir, ainsi que la convention de dénomination utilisée pour indiquer ces attributs dans [Rapports de personnalisation](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Vous pouvez augmenter le jeu de données entrant à tout moment. Pour en savoir plus sur le chargement de données supplémentaires, reportez-vous à la section  [Chargement de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Type de données | Description | Convention de dénomination des types de données | Attributs exemples |
|--- |--- |--- |--- |
| Paramètres d’URL | Target inspecte l’URL pour extraire les paramètres d’URL. | `Custom - URL Parameter - [URL Parameter]` | Données personnalisées |
| Paramètres d’URL de référence | En règle générale, l’URL de référence est celle qui sert de référent à une page particulière ayant initialisé l’appel mbox.<br>Il est à noter que cette variable peut être affectée par l’activité des utilisateurs sur votre site, ainsi que par la mise en œuvre technique de ce dernier. | `Custom - [Referring URL Parameter] - [Parameter value]` | Données personnalisées |
| Données d’environnement et de session | Informations indiquant comment et quand l’utilisateur accède à l’activité. | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | Profil du visiteur - Début de la visite la plus récente<br>Profil du visiteur - Visites totales<br>Profil du visiteur - Durée moyenne par visiteur<br>Navigateur - Fuseau horaire<br>Navigateur - Jour de la semaine<br>Navigateur - Paramètres de langue<br>Navigateur - Type<br>Système opérateur - Version |
| Géographie | Informations sur la position du visiteur | `Geo - [geo attribute]` | Ville<br>Pays<br>Région / État<br>Code postal<br>Latitude<br> Longitude<br>ISP ou opérateur de téléphonie mobile |
| Données de périphérique et de mobile | Informations spécifiques au périphérique et au mobile. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Système d’exploitation du périphérique mobile<br>Taille d’écran du dispositif portable |

