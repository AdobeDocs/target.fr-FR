---
description: Cette rubrique contient des réponses aux questions fréquentes sur l’intégration héritée de SiteCatalyst à Test&Target et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).
keywords: faq;questions fréquentes;analytics pour target;a4T;classifications;classification;importateur de classifications;post-tnt-action
seo-description: Cette rubrique contient des réponses aux questions fréquentes sur l’intégration héritée de SiteCatalyst à Test&Target et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).
seo-title: FAQ sur les classifications – A4T
solution: Target
title: FAQ sur les classifications – A4T
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# FAQ sur les classifications - A4T{#classifications-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur l’intégration héritée de SiteCatalyst à Test&amp;Target et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Après avoir téléchargé des classifications à l’aide de l’importateur de classifications, comment associer la valeur post-tnt-action à un nom d’activité ?{#section_6045DAC488B248418F430E663C38D001}

Vous pouvez télécharger les classifications correspondant à la chaîne A4T/TNT à l’aide de l’[importateur de classifications](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) des outils d’administration. Dans la liste d’exportation, la variable est nommée « TNT ». Des noms conviviaux sont attribués aux données téléchargées pour les activités, les expériences, etc.

Ce fichier de recherche s’avère pratique pour les clients qui reçoivent un flux de données de parcours d’Adobe. Le fichier fournit des noms conviviaux pour les colonnes `post_tnt` et `post_tnt_action`.

Le format de chaîne de la variable TNT est `activityID:experienceID:targettype|event`.

* targettype = toujours 0 pour A4T.
* Event = 0 correspond à une ouverture de l’expérience.
* Event = 1 correspond à une visite de l’expérience.
* Event = 2 correspond à une impression d’activité.
* Event = 32767 correspond à une conversion d’activité.

Téléchargez régulièrement le fichier de classifications depuis l’interface par [exportation navigateur](https://marketing.adobe.com/resources/help/en_US/reference/browser_export.html) ou [exportation FTP](https://marketing.adobe.com/resources/help/en_US/reference/ftp_export.html). Vous pouvez également demander aux services techniques un fichier que vous utiliserez comme tableau de recherche avec un flux de données de parcours.
