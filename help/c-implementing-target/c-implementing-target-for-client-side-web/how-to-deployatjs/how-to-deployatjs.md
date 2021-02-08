---
keywords: implémentation, at.js, bibliothèque JavaScript
description: Découvrez comment déployer la bibliothèque JavaScript Adobe Target at.js à l’aide de Adobe Experience Platform Launch ou sans gestionnaire de balises.
title: Comment déployer at.js ?
feature: Implement Server-side
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 49%

---


# Déploiement d’at.js

Informations expliquant comment déployer la bibliothèque JavaScript d’Adobe Target, at.js, avec Adobe Launch, sans gestionnaire de balises, ou avec Adobe Dynamic Tag Management (DTM).

Vous pouvez déployer at.js à l’aide des méthodes suivantes :

* **[Implémentation de Target avec Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)** : Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.
* **[Implémentation de Target sans gestionnaire de balises](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)** : vous pouvez implémenter Target sans utiliser de gestionnaire de balises (Adobe Launch ou Dynamic Tag Management).
* **[Mise en oeuvre de la Cible à l’aide de la gestion](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md)** dynamique des balises : Vous pouvez mettre en oeuvre la Cible à l’aide de la gestion dynamique des balises (DTM) Adobe, le gestionnaire de balises hérité du Adobe. Adobe Launch est la dernière méthode en date, préconisée pour la mise en œuvre de Target et de la bibliothèque at.js. Désormais, utilisez Launch pour implémenter Target.
* **Mettez en oeuvre la Cible à l’aide d’un gestionnaire** de balises tiers :  [Adobe ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) Launchis est la méthode privilégiée pour mettre en oeuvre la Cible ; toutefois, vous pouvez également implémenter la Cible à l’aide d’un gestionnaire de balises tiers, tel que Tealium, Ensighten, Google Tag, etc. Pour une liste des avantages de l’utilisation du lancement, voir [Avantages de l’implémentation d’at.js à l’aide de l’extension de lancement de Cible](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Cependant, si vous savez comment implémenter la Cible sans gestionnaire de balises, vous pouvez facilement l’implémenter avec un gestionnaire de balises tiers au lieu de coder en dur at.js dans le code du site.

   Voici deux rubriques pertinentes qui vous aideront à mettre en oeuvre la Cible avec un gestionnaire de balises tiers :

   * [Avant l’implémentation](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Mise en œuvre de Target sans gestionnaire de balises](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Pour plus d’informations, consultez la documentation de votre gestionnaire de balises tiers.

Pour implémenter Target lors de l’utilisation d’applications monopage, consultez la section [Implémentation d’application monopage](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).