---
keywords: implémentation, at.js, bibliothèque JavaScript
description: Découvrez comment déployer l’Adobe [!DNL Target] Bibliothèque JavaScript at.js utilisant des balises dans Adobe Experience Platform ou sans gestionnaire de balises.
title: Comment déployer at.js ?
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 30%

---

# Déploiement d’at.js

Informations sur la manière de déployer le [!DNL Adobe Target] Bibliothèque JavaScript, at.js, utilisation de balises dans [!DNL Adobe Experience Platform] ou sans gestionnaire de balises.

Vous pouvez déployer at.js à l’aide des méthodes suivantes :

* **[Mise en oeuvre [!DNL Target] utilisation des balises dans [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/)**: Balises dans [!DNL Adobe Experience Platform] représente la nouvelle génération des fonctionnalités de gestion des balises de [!DNL Adobe]. Les balises offrent aux clients un moyen simple de déployer et gérer les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] est désormais une suite de technologies dédiée à la collecte de données dans [!DNL Adobe Experience Platform]. Plusieurs modifications terminologiques ont par conséquent été déployées dans la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=fr) suivant pour obtenir une référence consolidée des modifications terminologiques.

* **[Implémentation de Target sans gestionnaire de balises](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)**: Vous pouvez implémenter Target sans utiliser de gestionnaire de balises (par exemple, des balises dans [!DNL Adobe Experience Platform]).
* **Mise en oeuvre de Target avec un gestionnaire de balises tiers**: [Balises dans [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] extension](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/).

   Cependant, si vous savez comment implémenter [!DNL Target] sans gestionnaire de balises, vous pouvez facilement l’implémenter avec un gestionnaire de balises tiers au lieu de coder en dur at.js dans le code du site.

   Voici deux rubriques pertinentes qui vous aideront à mettre en oeuvre [!DNL Target] avec un gestionnaire de balises tiers :

   * [Avant l’implémentation](https://developer.adobe.com/target/before-implement/)
   * [ [!DNL Target] Mise en œuvre de sans gestionnaire de balises](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

   Pour plus d’informations, consultez la documentation de votre gestionnaire de balises tiers.

Pour mettre en oeuvre [!DNL Target] lors de l’utilisation d’applications d’une seule page (SPA), voir [Implémentation d’applications d’une seule page](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/).
