---
keywords: implémentation, at.js, bibliothèque JavaScript
description: Découvrez comment déployer la bibliothèque JavaScript Adobe [!DNL Target] at.js à l’aide de Adobe Experience Platform Launch ou sans gestionnaire de balises.
title: Comment déployer at.js ?
feature: Mise en oeuvre côté serveur
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 32%

---

# Déploiement d’at.js

Informations sur la manière de déployer la bibliothèque JavaScript Adobe Target, at.js, à l’aide de Adobe Experience Platform Launch ou sans gestionnaire de balises.

Vous pouvez déployer at.js à l’aide des méthodes suivantes :

* **[ [!DNL Target] Implémentation de avec [!DNL Platform Launch]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)** : Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.
* **[Mise en oeuvre de la Cible sans gestionnaire](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)** de balises : Vous pouvez implémenter la Cible sans utiliser de gestionnaire de balises ([!DNL Platform Launch]).
* **Mettez en oeuvre la Cible à l’aide d’un gestionnaire** de balises tiers :  [Adobe ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) Launchis est la méthode privilégiée pour mettre en oeuvre la Cible ; toutefois, vous pouvez également implémenter la Cible à l’aide d’un gestionnaire de balises tiers, tel que Tealium, Ensighten, Google Tag, etc. Pour une liste des avantages de l’utilisation du lancement, voir [Avantages de l’implémentation d’at.js à l’aide de l’extension de lancement de Cible](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Cependant, si vous savez comment implémenter [!DNL Target] sans gestionnaire de balises, vous pouvez facilement implémenter avec un gestionnaire de balises tiers au lieu de coder en dur at.js dans le code du site.

   Voici deux rubriques pertinentes qui vous aideront à mettre en oeuvre la Cible avec un gestionnaire de balises tiers :

   * [Avant l’implémentation](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Implémentation de Target sans gestionnaire de balises](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Pour plus d’informations, consultez la documentation de votre gestionnaire de balises tiers.

Pour implémenter Target lors de l’utilisation d’applications monopage, consultez la section [Implémentation d’application monopage](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).
