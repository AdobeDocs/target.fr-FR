---
keywords: modules externes at.js;modules externes pris en charge;modules externes non pris en charge;ttMeta;ttmeta;mboxTrack
description: Découvrez l’implémentation héritée du fichier mbox.js d’Adobe Target. Migration vers le Adobe Experience Platform Web SDK (AEP Web SDK) ou vers la dernière version d’at.js.
title: Quels modules externes hérités ne sont pas pris en charge dans Cible at.js ?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 82%

---


# Modules externes at.js

Informations sur les modules externes at.js pris en charge et non pris en charge dans Adobe Target.

De nombreux utilisateurs ont créé des modules externes personnalisés et des modules externes de réponse pour [!DNL mbox.js]. Il est possible que les modules externes personnalisés ne soient pas pris en charge par [!DNL at.js] sans mise à jour.

Si vous utilisez un module externe qui n’est pas répertorié dans cette rubrique et si vous souhaitez connaître son état, contactez votre gestionnaire de compte.

Voici l’état actuel de certains modules externes utilisés par bon nombre de clients avec [!DNL at.js]:

| Module externe | Détails |
|--- |--- |
| mboxTrack | Non pris en charge.<br>Ceci est remplacé par la fonction [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md). Mettez à jour vos modules externes pour appliquer la nouvelle fonction.<br>Voir la page [intégrations](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md). |
| Persistent Profile Backup Plugin | Non pris en charge.<br>Ce module externe a été abandonné lorsque la durée de vie du profil Target a été prolongée de deux semaines à 90 jours. Vérifiez la date d’expiration du cookie de mbox pour déterminer le paramètre de durée de vie du profil de votre compte.<br>Si vous souhaitez prolonger la durée de vie du profil à 90 jours, contactez le service à la clientèle. |
| ttMeta | Les anciens modules externes SiteCatalyst doivent être désactivés et remplacés par [Adobe Analytics en tant que source de création de rapports pour Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Le module externe ttMeta doit être désactivé et remplacé par [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). |