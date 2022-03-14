---
keywords: faq;questions fréquentes;analytics for target;a4T;classifications;classification;importateur de classifications;post-tnt-action;codes d’événement
description: Trouver des réponses aux questions sur les classifications et l’utilisation de [!UICONTROL Analytics pour Target] (A4T).
title: Où puis-je trouver des informations sur les classifications avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 29%

---

# FAQ sur les classifications – A4T

Cette rubrique contient des réponses aux questions fréquentes sur les classifications et l’utilisation des [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T).

## Après avoir utilisé la variable [!UICONTROL Importateur de classifications] pour télécharger des classifications, comment associer la valeur post-tnt-action à un nom d’activité ? {#section_6045DAC488B248418F430E663C38D001}

Vous pouvez télécharger les classifications correspondant à la chaîne A4T/TNT à l’aide de l’[importateur de classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) des outils d’administration. Dans la liste d’exportation, la variable est nommée « TNT ». Des noms conviviaux sont attribués aux données téléchargées pour les activités, les expériences, etc.

Ce fichier de recherche est utile pour les clients qui reçoivent [!DNL Adobe]Flux de données de parcours de navigation de . Le fichier fournit des noms conviviaux pour les colonnes `post_tnt` et `post_tnt_action`.

Pour standard [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT), le format de la chaîne TNT est le suivant :

```
activityID:experienceID:targettype|event
```

Pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités, le format de la chaîne TNT est le suivant :

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` et `algorithmId` sont des identifiants internes utilisés par [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités.
* Event = 0 correspond à une ouverture de l’expérience.
* Event = 1 correspond à une visite de l’expérience.
* Event = 2 correspond à une impression d’activité.
* Event = 3-32766 représente l’identifiant de mesure de succès d’analyse.
* Event = 32767 correspond à une conversion d’activité.
* L’événement -1 ou 65535 représente que l’utilisateur est supprimé de l’activité ou de l’expérience. Cette situation se produit souvent lorsque le visiteur effectue une conversion. Le visiteur est libéré de l’expérience et peut désormais être admissible à toute autre expérience.

Vous pouvez importer fréquemment le fichier de classification à partir de l’interface utilisateur à l’aide d’une [import de navigateur](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) ou [Importation FTP](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). Vous pouvez également demander aux services techniques un fichier que vous utiliserez comme tableau de recherche avec un flux de données de parcours.
