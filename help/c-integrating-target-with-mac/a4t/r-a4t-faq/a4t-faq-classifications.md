---
keywords: faq;questions fréquentes;analytics pour target;a4T;classifications;classification;importateur de classifications;post-tnt-action
description: Trouvez des réponses aux questions sur les classifications et l’utilisation d’Analytics pour la Cible (A4T). A4T vous permet d’utiliser le rapports Analytics pour les activités de Cible.
title: Où puis-je trouver des informations sur les classifications avec A4T ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 55%

---


# FAQ sur les classifications - A4T{#classifications-a-t-faq}

Cette rubrique contient des réponses aux questions fréquemment posées au sujet des classifications et utilise [!DNL Analytics] comme source de rapports pour [!DNL Target] (A4T).

## Après avoir téléchargé des classifications à l’aide de l’importateur de classifications, comment associer la valeur post-tnt-action à un nom d’activité ?{#section_6045DAC488B248418F430E663C38D001}

Vous pouvez télécharger les classifications correspondant à la chaîne A4T/TNT à l’aide de l’[importateur de classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) des outils d’administration. Dans la liste d’exportation, la variable est nommée « TNT ». Des noms conviviaux sont attribués aux données téléchargées pour les activités, les expériences, etc.

Ce fichier de recherche s’avère pratique pour les clients qui reçoivent un flux de données de parcours d’Adobe. Le fichier fournit des noms conviviaux pour les colonnes `post_tnt` et `post_tnt_action`.

Le format de chaîne de la variable TNT est `activityID:experienceID:targettype|event`.

* targettype = 0 (contrôle/aléatoire) ou 1 (ciblé) pour les activités [!UICONTROL Affectation automatique] et [!UICONTROL Cible automatique].
* Event = 0 correspond à une ouverture de l’expérience.
* Event = 1 correspond à une visite de l’expérience.
* Event = 2 correspond à une impression d’activité.
* Événement = 3-32766 représente l’identifiant de mesure de réussite d’analyse.
* Event = 32767 correspond à une conversion d’activité.

Vous pouvez importer fréquemment le fichier de classification à partir de l’interface utilisateur à l’aide d’une importation [navigateur](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) ou d’une importation [FTP](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). Vous pouvez également demander aux services techniques un fichier que vous utiliserez comme tableau de recherche avec un flux de données de parcours.
