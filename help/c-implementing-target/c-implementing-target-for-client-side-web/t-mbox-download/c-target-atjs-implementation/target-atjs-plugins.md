---
description: Informations sur les modules externes at.js pris en charge et non pris en charge.
keywords: plugins at.js, plugins pris en charge, plugins non pris en charge; Ttmeta ; ttmeta ; Mboxtrack
seo-description: Informations sur les modules externes at. js pris en charge et non pris en charge pour Adobe Target.
seo-title: Modules externes at. js pour Adobe Target
solution: Target
title: Modules externes at.js
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: 6908038449c9f172fcd509ca9c0616bee5a7674f

---


# at.js plug-ins{#at-js-plug-ins}

Informations sur les modules externes at.js pris en charge et non pris en charge.

De nombreux utilisateurs ont créé des modules externes personnalisés et des modules externes de réponse pour [!DNL mbox.js]. Il est possible que les modules externes personnalisés ne soient pas pris en charge par [!DNL at.js] sans mise à jour.

Si vous utilisez un module externe qui n’est pas répertorié dans cette rubrique et si vous souhaitez connaître son état, contactez votre gestionnaire de compte.

Voici l’état actuel de certains modules externes utilisés par bon nombre de clients avec [!DNL at.js]:

| Module externe | Détails |
|--- |--- |
| mboxTrack | Non pris en charge.<br>Ceci est remplacé par la fonction [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md). Mettez à jour vos modules externes pour appliquer la nouvelle fonction.<br>Voir la page [intégrations](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md). |
| Persistent Profile Backup Plugin | Non pris en charge.<br>Ce module externe a été abandonné lorsque la durée de vie du profil Target a été prolongée de deux semaines à 90 jours. Vérifiez la date d’expiration du cookie de mbox pour déterminer le paramètre de durée de vie du profil de votre compte.<br>Si vous souhaitez prolonger la durée de vie du profil à 90 jours, contactez le service à la clientèle. |
| ttMeta | Non pris en charge.<br>Au lieu de ce plug-in, utilisez [des jetons de réponse](/help/administrating-target/response-tokens.md). |