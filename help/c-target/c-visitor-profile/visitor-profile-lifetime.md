---
description: Par défaut, les profils de visiteur sont stockés pendant 14 jours. Cette durée de vie peut être prolongée.
keywords: Aperçu et référence
seo-description: Par défaut, les profils de visiteur sont stockés pendant 14 jours. Cette durée de vie peut être prolongée.
seo-title: Durée de vie du profil du visiteur
solution: Target
subtopic: Prise en main
title: Durée de vie du profil du visiteur
topic: Standard
uuid: 01ccda60-7e28-4d26-8d5d-1c0a022bbef0
translation-type: tm+mt
source-git-commit: 592fb6833a9bce1a4b9b5b698ee41331374a8a22

---


# Durée de vie du profil du visiteur{#visitor-profile-lifetime}

Par défaut, les profils de visiteur sont stockés pendant 14 jours. Cette durée de vie peut être prolongée.

[Contactez le service à la clientèle ou votre consultant Adobe](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour prolonger la durée de vie du profil sans frais supplémentaires. La durée de vie peut être fixée à 90 jours.

La bibliothèque JavaScript de [!DNL Target] que vous utilisez ([!DNL mbox.js] ou [!DNL at.js]) détermine si vous devez télécharger un nouveau fichier :

| Bibliothèque Target | Détails |
|--- |--- |
| at.js  | Il n’est pas nécessaire de télécharger un nouveau fichier at.js si votre profil est prolongé au-delà de la valeur par défaut. |
| mbox.js | Si votre profil est prolongé au-delà des 14 jours par défaut, vous devrez télécharger un nouveau fichier mbox.js une fois que votre consultant ou représentant du service à la clientèle aura changé vos paramètres. Le prolongement des cookies correspondant au changement de la durée de vie du profil est inclus dans le fichier mbox.js mis à jour. Après avoir commencé à utiliser la nouvelle bibliothèque, la durée de vie des profils des visiteurs est mise à jour. |

La date d’expiration n’est pas réinitialisée pour les profils existants. Si un ancien visiteur ne revient pas pendant 15 jours, ce profil expire. Si un ancien visiteur revient avant que le profil initial de deux semaines n’expire, le profil est réinitialisé avec la durée de vie prolongée. Tous les nouveaux profils de visiteur sont définis avec la durée de vie de profil prolongée.

Si vous possédez deux sites sous un code client et qu’un visiteur se rend sur les deux sites, le profil est défini sur la durée de vie des profils sur le dernier site consulté par ce visiteur. Si, par exemple, la durée de vie du profil est de 84 jours sur le site 1 et de 14 jours sur le site 2 et que le visiteur se rend sur le site 1, puis sur le site 2, son profil expire dans 14 jours. Si le visiteur se rend sur le site 1 après s’être rendu sur le site 2, le profil expire dans 84 jours.
