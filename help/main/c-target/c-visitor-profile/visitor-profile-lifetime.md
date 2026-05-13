---
keywords: Aperçu et référence
description: En savoir plus sur le moment auquel un profil de visiteur expire dans  [!DNL Adobe Target].
title: Quelle est la durée de vie du profil du visiteur et puis-je la prolonger ?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
TQID: https://experienceleague.adobe.com/yMfacKgQthOmpfhFiuO-jGGPWZh5VrliOSi0TQ-uis0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 62%

---

# Durée de vie du profil du visiteur

Par défaut, un profil de visiteur dans [!DNL Adobe Target] expire après 14 jours d’inactivité pour ce visiteur. Cette durée de vie peut être prolongée.

[Contactez le service à la clientèle ou votre consultant Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour prolonger la durée de vie du profil sans frais supplémentaires. La durée de vie peut être fixée à 90 jours.

Vous n’avez pas besoin de télécharger un nouveau fichier [!DNL Platform Web SDK] ou at.js si votre profil est étendu au-delà de la valeur par défaut.

La date d’expiration n’est pas réinitialisée pour les profils existants. Si un ancien visiteur ne revient pas pendant 15 jours, ce profil expire. Si un ancien visiteur revient avant que le profil initial de deux semaines n’expire, le profil est réinitialisé avec la durée de vie prolongée. Tous les nouveaux profils de visiteur sont définis avec la durée de vie de profil prolongée.
