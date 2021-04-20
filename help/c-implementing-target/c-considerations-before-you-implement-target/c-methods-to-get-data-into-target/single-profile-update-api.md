---
keywords: implémentation ; implémentation ; configuration ; configuration ; mise à jour de profil unique
description: Récupérez des données dans la Cible à l’aide de l’API de mise à jour de profil unique.
title: Comment puis-je obtenir des données dans la Cible à l’aide de l’API de mise à jour d’un seul Profil ?
feature: Implementation
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 43%

---

# API de mise à jour de profil individuel

Presque identique à l’API de mise à jour de Profil en bloc, mais un profil visiteur est mis à jour à la fois, dans la ligne de l’appel d’API au lieu d’un fichier .csv.

## Format

Le visiteur doit être identifié à l’aide de la valeur mboxPC ou mboxThirdPartyId de Target. L’Experience Cloud ID (ECID) n’est pas pris en charge.

## Exemples de cas d’utilisation

Vous souhaitez mettre à jour la Cible en temps réel lorsqu’un visiteur effectue une action hors ligne. Les actions peuvent inclure l’accès à un centre d’appels, le financement d’un prêt, l’utilisation d’une carte de fidélité en magasin, l’accès à un kiosque, etc.

## Avantages de la méthode

Nombre d’attributs de profil illimité.

Les attributs de profil envoyés via le site peuvent être mis à jour via l’API et vice versa.

## Avertissements

Limite de 1 000 000 d’appels de l’API (1 million) par période de 24 heures.

Met à jour le profil uniquement. Ne prend pas en charge la création d’un profil pour un utilisateur que Target n’a pas encore vu.

## Exemples de code

Prise en charge des commandes GET et POST. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

## Liens vers les informations pertinentes

[Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles)
