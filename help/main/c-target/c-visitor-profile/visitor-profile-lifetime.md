---
keywords: Aperçu et référence
description: En savoir plus sur la date d’expiration d’un profil de visiteur dans [!DNL Adobe Target].
title: Quelle est la durée de vie du profil du visiteur et puis-je l’étendre ?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 62%

---

# Durée de vie du profil du visiteur

Par défaut, un profil du visiteur dans [!DNL Adobe Target] expire après 14 jours d’inactivité pour ce visiteur. Cette durée de vie peut être prolongée.

[Contactez le service à la clientèle ou votre consultant Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour prolonger la durée de vie du profil sans frais supplémentaires. La durée de vie peut être fixée à 90 jours.

Vous n’avez pas besoin de télécharger un nouveau [!DNL Platform Web SDK] fichier ou fichier at.js si votre profil est étendu au-delà de la valeur par défaut.

La date d’expiration n’est pas réinitialisée pour les profils existants. Si un ancien visiteur ne revient pas pendant 15 jours, ce profil expire. Si un ancien visiteur revient avant que le profil initial de deux semaines n’expire, le profil est réinitialisé avec la durée de vie prolongée. Tous les nouveaux profils de visiteur sont définis avec la durée de vie de profil prolongée.
