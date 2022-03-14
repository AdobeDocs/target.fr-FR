---
keywords: implémentation, at.js, bibliothèque JavaScript
description: Découvrez comment déployer l’Adobe [!DNL Target] Bibliothèque JavaScript at.js utilisant des balises dans Adobe Experience Platform ou sans gestionnaire de balises.
title: Comment déployer at.js ?
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 35%

---

# Déploiement d’at.js

Informations sur la manière de déployer le [!DNL Adobe Target] Bibliothèque JavaScript, at.js, utilisation de balises dans [!DNL Adobe Experience Platform] ou sans gestionnaire de balises.

Vous pouvez déployer at.js à l’aide des méthodes suivantes :

* **[Mise en oeuvre [!DNL Target] utilisation des balises dans [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**: Balises dans [!DNL Adobe Experience Platform] représente la nouvelle génération des fonctionnalités de gestion des balises de [!DNL Adobe]. Les balises offrent aux clients un moyen simple de déployer et gérer les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] est désormais une suite de technologies dédiée à la collecte de données dans [!DNL Adobe Experience Platform]. Plusieurs modifications terminologiques ont par conséquent été déployées dans la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=fr) suivant pour obtenir une référence consolidée des modifications terminologiques.

* **[Implémentation de Target sans gestionnaire de balises](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**: Vous pouvez implémenter Target sans utiliser de gestionnaire de balises (par exemple, des balises dans [!DNL Adobe Experience Platform]).
* **Mise en oeuvre de Target avec un gestionnaire de balises tiers**: [Balises dans [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] extension](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Cependant, si vous savez comment implémenter [!DNL Target] sans gestionnaire de balises, vous pouvez facilement l’implémenter avec un gestionnaire de balises tiers au lieu de coder en dur at.js dans le code du site.

   Voici deux rubriques pertinentes qui vous aideront à mettre en oeuvre [!DNL Target] avec un gestionnaire de balises tiers :

   * [Avant l’implémentation](/help/main/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Mise en oeuvre [!DNL Target] sans gestionnaire de balises](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Pour plus d’informations, consultez la documentation de votre gestionnaire de balises tiers.

Pour mettre en oeuvre [!DNL Target] lors de l’utilisation d’applications d’une seule page (SPA), voir [Implémentation d’applications d’une seule page](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).
