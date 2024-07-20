---
keywords: faq;questions fréquentes;analytics for target;a4T;classifications;classification;importateur de classifications;post-tnt-action;codes d’événement
description: Trouvez des réponses aux questions sur les classifications et l’utilisation de [!UICONTROL Analytics for Target] (A4T).
title: Où puis-je trouver des informations sur les classifications avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 24%

---

# FAQ sur les classifications – A4T

Cette rubrique contient des réponses aux questions fréquentes sur les classifications et l’utilisation de [!DNL Analytics] comme source des rapports pour [!DNL Target] (A4T).

## Après avoir téléchargé les classifications à l’aide de [!UICONTROL Classifications Importer], comment associer la valeur post-tnt-action à un nom d’activité ? {#section_6045DAC488B248418F430E663C38D001}

+++Réponse
Vous pouvez télécharger les classifications pour la chaîne A4T/TNT à partir des outils d’administration [Importateur de classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html). La variable est appelée &quot;TNT&quot; dans la liste d’exportation. Des noms conviviaux sont attribués aux données téléchargées pour les activités, les expériences, etc.

Ce fichier de recherche est utile pour les clients qui reçoivent le flux de données de parcours de navigation de [!DNL Adobe]. Le fichier fournit des noms conviviaux pour les colonnes `post_tnt` et `post_tnt_action`.

Pour les activités [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] standard (XT), le format de la chaîne TNT est le suivant :

```
activityID:experienceID:targettype|event
```

Pour les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target], le format de la chaîne TNT est :

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` et `algorithmId` sont des identifiants internes utilisés par les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].
* Event = 0 correspond à une ouverture de l’expérience.
* Event = 1 correspond à une visite de l’expérience.
* Event = 2 correspond à une impression d’activité.
* Event = 3-32766 représente l’identifiant de mesure de succès d’analyse.
* Event = 32767 correspond à une conversion d’activité.
* L’événement -1 ou 65535 représente que l’utilisateur est supprimé de l’activité ou de l’expérience. Cette situation se produit souvent lorsque le visiteur effectue une conversion. Le visiteur est libéré de l’expérience et peut désormais être admissible à toute autre expérience.

Vous pouvez importer fréquemment le fichier de classification à partir de l’interface utilisateur à l’aide d’un [import de navigateur](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) ou d’un [import FTP](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). Vous pouvez également demander aux services techniques un fichier que vous utiliserez comme tableau de recherche avec un flux de données de parcours.

+++
