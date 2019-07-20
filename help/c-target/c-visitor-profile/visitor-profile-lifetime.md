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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Durée de vie du profil du visiteur{#visitor-profile-lifetime}

Par défaut, un profil du visiteur expire après 14 jours d'inactivité pour ce visiteur. Cette durée de vie peut être prolongée.

[Contactez le service à la clientèle ou votre consultant Adobe](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour prolonger la durée de vie du profil sans frais supplémentaires. La durée de vie peut être fixée à 90 jours.

La bibliothèque JavaScript de [!DNL Target] que vous utilisez ([!DNL at.js] ou [!DNL mbox.js]) détermine si vous devez télécharger un nouveau fichier :

| Bibliothèque Target | Détails |
|--- |--- |
| at.js | Il n’est pas nécessaire de télécharger un nouveau fichier at.js si votre profil est prolongé au-delà de la valeur par défaut. |
| mbox.js | Si votre profil est prolongé au-delà des 14 jours par défaut, vous devrez télécharger un nouveau fichier mbox.js une fois que votre consultant ou représentant du service à la clientèle aura changé vos paramètres. Le prolongement des cookies correspondant au changement de la durée de vie du profil est inclus dans le fichier mbox.js mis à jour. Après avoir commencé à utiliser la nouvelle bibliothèque, la durée de vie des profils des visiteurs est mise à jour. |

La date d’expiration n’est pas réinitialisée pour les profils existants. Si un ancien visiteur ne revient pas pendant 15 jours, ce profil expire. Si un ancien visiteur revient avant que le profil initial de deux semaines n’expire, le profil est réinitialisé avec la durée de vie prolongée. Tous les nouveaux profils de visiteur sont définis avec la durée de vie de profil prolongée.

Si vous possédez deux sites sous un code client et qu’un visiteur se rend sur les deux sites, le profil est défini sur la durée de vie des profils sur le dernier site consulté par ce visiteur. Si, par exemple, le site 1 dispose d'une durée de vie de 84 jours et que le site 2 comporte une durée de vie de 14 jours, et que le visiteur visite le site 1 puis le site 2, le profil du visiteur expirera dans 14 jours d'inactivité. Si le visiteur consulte le site 1 après avoir visité le site 2, le profil expirera dans 84 jours d'inactivité.
