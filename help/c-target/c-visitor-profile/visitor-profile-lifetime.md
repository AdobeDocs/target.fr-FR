---
keywords: Aperçu et référence
description: En savoir plus sur le moment où un profil de visiteur expire dans [!DNL Adobe Target].
title: Quelle est la durée de vie du profil du visiteur et puis-je l’étendre ?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 45%

---

# Durée de vie du profil du visiteur

Par défaut, un profil du visiteur dans [!DNL Adobe Target] expire après 14 jours d’inactivité pour ce visiteur. Cette durée de vie peut être prolongée.

[Contactez le service à la clientèle ou votre consultant Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour prolonger la durée de vie du profil sans frais supplémentaires. La durée de vie peut être fixée à 90 jours.

Vous n’avez pas besoin de télécharger un nouveau fichier [!DNL Platform Web SDK] ou fichier at.js si votre profil est étendu au-delà de la valeur par défaut.

La date d’expiration n’est pas réinitialisée pour les profils existants. Si un ancien visiteur ne revient pas pendant 15 jours, ce profil expire. Si un ancien visiteur revient avant que le profil initial de deux semaines n’expire, le profil est réinitialisé avec la durée de vie prolongée. Tous les nouveaux profils de visiteur sont définis avec la durée de vie de profil prolongée.

Dans le scénario suivant, supposons qu’un ou les deux sites soient implémentés avec la balise [!DNL Platform Web SDK]. Si les deux sites se trouvent sous un code client et qu’un visiteur se rend sur les deux sites, le profil est défini sur la durée de vie des profils sur le dernier site consulté. Supposons, par exemple, que la durée de vie du profil du site 1 soit de 84 jours. Le site 2 a une durée de vie de 14 jours. Si le visiteur se rend sur le site 1, puis sur le site 2, son profil expire après 14 jours d’inactivité. Si le visiteur se rend sur le site 1 après s’être rendu sur le site 2, le profil expire après 84 jours d’inactivité.
