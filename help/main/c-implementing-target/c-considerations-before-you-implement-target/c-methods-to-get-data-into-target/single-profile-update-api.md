---
keywords: implémenter;implémentation;configuration;configurer;mise à jour de profil unique
description: Obtenir des données dans [!DNL Target] à l’aide de l’API de mise à jour de profil unique.
title: Comment obtenir des données dans [!DNL Target] Utilisation de l’API de mise à jour de profil unique ?
feature: Implementation
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 44%

---

# API de mise à jour de profil individuel

Presque identique à l’API de mise à jour de profil en bloc, mais un profil du visiteur est mis à jour à la fois, en ligne dans l’appel d’API au lieu d’être associé à un fichier .csv.

## Format

Le visiteur doit être identifié à l’aide de la valeur mboxPC ou mboxThirdPartyId de Target. L’Experience Cloud ID (ECID) n’est pas pris en charge.

## Exemples de cas d’utilisation

Vous souhaitez mettre à jour Target en temps réel lorsqu’un visiteur effectue une action hors ligne. Les actions peuvent inclure l’accès à un centre d’appel, le financement d’un prêt, l’utilisation d’une carte de fidélité en magasin, l’accès à un kiosque, etc.

## Avantages de la méthode

Nombre d’attributs de profil illimité.

Les attributs de profil envoyés via le site peuvent être mis à jour via l’API et vice versa.

## Avertissements

Limite de 1 000 000 d’appels de l’API (1 million) par période de 24 heures.

Met à jour le profil uniquement. Ne prend pas en charge la création d’un profil pour un utilisateur que Target n’a pas encore vu.

## Exemples de code

Prise en charge des commandes GET et POST. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles)

