---
keywords: implémentation ; implémentation ; configuration ; configuration ; attributs du client
description: Récupérez des données dans la Cible à l’aide d’attributs du client.
title: Comment obtenir des données dans la Cible à l’aide des attributs du client ?
feature: Mise en œuvre
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 51%

---

# Attributs du client

Les attributs du client vous permettent de transférer des données de profil de visiteur par FTP vers [!DNL Adobe Experience Cloud]. Une fois le transfert effectué, utilisez les données dans [!DNL Adobe Analytics] et [!DNL Adobe Target].

Les clients Target Standard peuvent appliquer cinq attributs, les clients Cible Premium peuvent appliquer 200 attributs.

## Format

Un fichier .csv contenant des Experience Cloud IDs (ECID) et des paires nom/valeur d’attributs est chargé par FTP ou manuellement dans l’interface utilisateur d’Experience Cloud.

## Exemples d’utilisation

Votre logiciel de gestion de la relation client ou autre système interne stocke des informations importantes que vous voulez partager avec la solution Experience Cloud d’Adobe, notamment Target et Analytics.

## Avantages de la méthode

Le chargement des données d’un client crée une entrée de profil pour ce visiteur dans Target, même si Target ne l’a pas encore vu.

Les mêmes données sont automatiquement disponibles dans Target et Analytics.

Le chargement par FTP peut constituer une méthode d’implémentation plus simple que l’API.

## Avertissements

Les clients Target Standard peuvent appliquer cinq attributs, les clients Cible Premium peuvent appliquer 200 attributs.

Les valeurs peuvent uniquement être mises à jour par le biais des attributs du client, pas sur la page.

Cette méthode requiert l’implémentation de l’Experience Cloud ID (ECID).

## Exemples de code

Vous trouverez des détails dans [Création d’une source d’attributs du client et téléchargement du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Liens vers les informations pertinentes

[Création d’une source d’attributs du client et transfert du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).