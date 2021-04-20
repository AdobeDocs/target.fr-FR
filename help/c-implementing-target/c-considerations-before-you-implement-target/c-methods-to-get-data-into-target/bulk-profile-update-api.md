---
keywords: implémentation ; implémentation ; configuration ; configuration ; mise à jour du profil en bloc
description: Récupérez des données dans la Cible à l’aide de l’API de mise à jour de profil en masse.
title: Comment puis-je obtenir des données dans la Cible à l’aide de l’API de mise à jour du Profil en bloc ?
feature: Implementation
role: Developer
exl-id: 068658fc-7082-425a-87c1-dd0de03cdc71
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 78%

---

# API de mise à jour des profils en masse

Par le biais de l’API, envoyez un fichier .csv à [!DNL Adobe Target] avec les mises à jour du profil visiteur pour de nombreux visiteurs. Chaque profil du visiteur peut être mis à jour avec plusieurs attributs de profil internes à la page en un seul appel.

Cette option est similaire aux attributs du client avec quelques différences :

* Les attributs du client utilisent le transfert FTP, tandis que l’API de mise à jour des profils en masse de Target utilise une API HTTP POST.
* Les données d’attributs du client peuvent être partagées avec Analytics. La mise à jour des profils en masse peut uniquement être utilisée dans Target.
* Les attributs du client prennent en charge la création d’un profil pour un utilisateur que Target n’a pas encore vu. L’API de mise à jour des profils en masse met uniquement à jour les profils Target existants.
* Les attributs du client requièrent l’utilisation de l’Experience Cloud ID (ECID). L’API de mise à jour des profils en masse requiert soit l’ID TNT, soit l’ID `mbox3rdPartyId`.
* Vous ne pouvez pas envoyer les caractères suivants dans `mbox3rdPartyID` : signe plus (+) et barre oblique (/).

## Format

Le fichier .csv doit désigner chaque visiteur par son PCID ou son mboxThirdPartyId Target. L’Experience Cloud ID (ECID) n’est pas pris en charge. Tous les attributs/valeurs de profil sont créés et mis à jour via l’API. Les détails relatifs au format sont disponibles dans la documentation de l’API.

## Exemples d’utilisation

Votre logiciel de gestion de la relation client ou autre système interne stocke des données importantes sur vos visiteurs que vous souhaitez constamment mettre à jour dans Target, sans exposer les données du profil dans l’implémentation de votre page.

## Avantages de la méthode

Nombre d’attributs de profil illimité.

Les attributs de profil envoyés via le site peuvent être mis à jour via l’API et vice versa.

## Avertissements

La taille du fichier de traitement par lot doit être inférieure à 50 Mo. En outre, le nombre total de lignes ne doit pas dépasser 500 000 lignes par téléchargement.

Le nombre de lignes pouvant être téléchargées en lots ultérieurs sur une période de 24 heures est illimité. Cependant, le processus d’assimilation peut être ralenti pendant les heures ouvrables pour s’assurer que les autres processus s’exécutent efficacement.

Les [appels de mise à jour de lots V2](https://developers.adobetarget.com/api/#updating-profiles) consécutifs non espacés par des appels mbox pour le même identifiant tiers remplacent les propriétés mises à jour au premier appel de mise à jour de lots.

## Exemples de code

Voir [Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles).

### Liens vers les informations pertinentes

[Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles)
