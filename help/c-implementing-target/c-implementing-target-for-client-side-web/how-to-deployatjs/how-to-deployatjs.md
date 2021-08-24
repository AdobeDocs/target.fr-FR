---
keywords: implémentation, at.js, bibliothèque JavaScript
description: Découvrez comment déployer la bibliothèque JavaScript at.js Adobe [!DNL Target] à l’aide de balises dans Adobe Experience Platform ou sans gestionnaire de balises.
title: Comment déployer at.js ?
feature: Mise en oeuvre côté serveur
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%

---

# Déploiement d’at.js

Informations sur le déploiement de la bibliothèque JavaScript [!DNL Adobe Target] at.js à l’aide de balises dans [!DNL Adobe Experience Platform] ou sans gestionnaire de balises.

Vous pouvez déployer at.js à l’aide des méthodes suivantes :

* **[ [!DNL Target] Mise en oeuvre de balises dans [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)** : Les balises dans  [!DNL Adobe Experience Platform] représentent la nouvelle génération des fonctionnalités de gestion des balises de  [!DNL Adobe]. Les balises offrent aux clients un moyen simple de déployer et gérer les balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes.

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] a été renommé suite de technologies de collecte de données dans  [!DNL Adobe Experience Platform]. Plusieurs modifications terminologiques ont par conséquent été apportées à la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) suivant pour une référence consolidée des modifications terminologiques.

* **[Implémentation de Target sans gestionnaire](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)** de balises : Vous pouvez implémenter Target sans utiliser de gestionnaire de balises (par exemple, des balises dans  [!DNL Adobe Experience Platform]).
* **Implémentation de Target à l’aide d’un gestionnaire** de balises tiers :  [La méthode  [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) inis des balises est la méthode préférée pour implémenter Target. toutefois, vous pouvez également implémenter Target à l’aide d’un gestionnaire de balises tiers, notamment Tealium, Ensighten et Google Tag. Pour obtenir la liste des avantages de l’utilisation de Launch, voir [Avantages de l’implémentation d’at.js à l’aide de  [!DNL Adobe Target] extension](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Cependant, si vous savez comment implémenter [!DNL Target] sans gestionnaire de balises, vous pouvez facilement l’implémenter avec un gestionnaire de balises tiers au lieu du codage en dur d’at.js dans le code du site.

   Voici deux rubriques pertinentes qui vous aideront à mettre en oeuvre [!DNL Target] avec un gestionnaire de balises tiers :

   * [Avant l’implémentation](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Implémentation [!DNL Target] sans gestionnaire de balises](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Pour plus d’informations, consultez la documentation de votre gestionnaire de balises tiers.

Pour implémenter [!DNL Target] lors de l’utilisation d’applications d’une seule page (SPA), voir [Implémentation d’applications d’une seule page](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).
