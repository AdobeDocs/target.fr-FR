---
keywords: Aperçu et référence
description: En savoir plus sur le moment où un profil visiteur arrive à expiration (par défaut, 14 jours) dans Adobe Target. La durée de vie du profil peut être prolongée en contactant le service à la clientèle Adobe.
title: Quelle est la durée de vie du Profil Visiteur et puis-je l'étendre ?
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Durée de vie du profil du visiteur{#visitor-profile-lifetime}

Par défaut, un profil de visiteur expire après 14 jours d’inactivité pour ce visiteur. Cette durée de vie peut être prolongée.

[Contactez le service à la clientèle ou votre consultant Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour prolonger la durée de vie du profil sans frais supplémentaires. La durée de vie peut être fixée à 90 jours.

La bibliothèque JavaScript de [!DNL Target] que vous utilisez ([!DNL at.js] ou [!DNL mbox.js]) détermine si vous devez télécharger un nouveau fichier :

| Bibliothèque Target | Détails |
|--- |--- |
| at.js | Il n’est pas nécessaire de télécharger un nouveau fichier at.js si votre profil est prolongé au-delà de la valeur par défaut. |
| mbox.js | Si votre profil est prolongé au-delà des 14 jours par défaut, vous devrez télécharger un nouveau fichier mbox.js une fois que votre consultant ou représentant du service à la clientèle aura changé vos paramètres. Le prolongement des cookies correspondant au changement de la durée de vie du profil est inclus dans le fichier mbox.js mis à jour. Après avoir commencé à utiliser la nouvelle bibliothèque, la durée de vie des profils des visiteurs est mise à jour. |

La date d’expiration n’est pas réinitialisée pour les profils existants. Si un ancien visiteur ne revient pas pendant 15 jours, ce profil expire. Si un ancien visiteur revient avant que le profil initial de deux semaines n’expire, le profil est réinitialisé avec la durée de vie prolongée. Tous les nouveaux profils de visiteur sont définis avec la durée de vie de profil prolongée.

Dans le scénario suivant, supposons qu’un ou les deux sites soient implémentés avec mbox.js, ce qui nécessite une mise à jour du code une fois le profil mis à jour. Si les deux sites sont sous un code client et qu’un visiteur visite les deux sites, le profil est défini sur la durée de vie des profils sur le dernier site visité. Si, par exemple, la durée de vie du profil est de 84 jours sur le site 1 et de 14 jours sur le site 2 et que le visiteur se rend sur le site 1, puis sur le site 2, son profil expire après 14 jours d’inactivité. Si le visiteur se rend sur le site 1 après s’être rendu sur le site 2, le profil expire après 84 jours d’inactivité.
