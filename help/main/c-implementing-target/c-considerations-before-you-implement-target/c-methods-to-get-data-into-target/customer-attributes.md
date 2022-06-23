---
keywords: implémentation;implémentation;configuration;configuration;attributs du client
description: Obtenir des données dans [!DNL Target] utilisation des attributs du client.
title: Comment obtenir des données dans [!DNL Target] Utilisation des attributs du client ?
feature: Implementation
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 51%

---

# Attributs du client

Les attributs du client vous permettent de transférer les données de profil du visiteur par FTP vers le [!DNL Adobe Experience Cloud]. Une fois le chargement effectué, utilisez les données de la section [!DNL Adobe Analytics] et [!DNL Adobe Target].

Les clients Target Standard peuvent appliquer cinq attributs, les clients Target Premium peuvent appliquer 200 attributs.

## Format

Un fichier .csv contenant des Experience Cloud IDs (ECID) et des paires nom/valeur d’attributs est chargé par FTP ou manuellement dans l’interface utilisateur d’Experience Cloud.

## Exemples de cas d’utilisation

Votre logiciel de gestion de la relation client ou autre système interne stocke des informations importantes que vous voulez partager avec la solution Experience Cloud d’Adobe, notamment Target et Analytics.

## Avantages de la méthode

Le chargement des données d’un client crée une entrée de profil pour ce visiteur dans Target, même si Target ne l’a pas encore vu.

Les mêmes données sont automatiquement disponibles dans Target et Analytics.

Le chargement par FTP peut constituer une méthode d’implémentation plus simple que l’API.

## Avertissements

Les clients Target Standard peuvent appliquer cinq attributs, les clients Target Premium peuvent appliquer 200 attributs.

Les valeurs peuvent uniquement être mises à jour par le biais des attributs du client, pas sur la page.

Cette méthode requiert l’implémentation de l’Experience Cloud ID (ECID).

## Exemples de code

Vous trouverez des détails dans la section [Création d’une source d’attributs du client et transfert du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Liens vers les informations pertinentes

[Création d’une source d’attributs du client et transfert du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
