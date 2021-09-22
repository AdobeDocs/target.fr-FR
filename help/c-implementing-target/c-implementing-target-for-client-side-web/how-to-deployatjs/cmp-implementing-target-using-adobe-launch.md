---
keywords: implémenter;implémentation;implémentation;lancement d’adobe;course;redirection;platform launch d’expérience;platform launch;balises;adobe platform
description: Découvrez comment implémenter la bibliothèque [!DNL Adobe Target] at.js à l’aide de [!DNL Adobe Experience Platform], the preferred method to implement [!DNL Target].
title: Comment mettre en oeuvre [!DNL Target] en utilisant [!DNL Adobe Experience Platform] ?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 11%

---

# Implémentation de[!DNL Target]à l’aide d’[!DNL Adobe Experience Platform]

Les balises de [!DNL Adobe Experience Platform] représentent la nouvelle génération des fonctionnalités de gestion des balises de [!DNL Adobe]. Les balises offrent aux clients un moyen simple de déployer et gérer les balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] est désormais une suite de technologies dédiée à la collecte de données dans [!DNL Adobe Experience Platform]. Plusieurs modifications terminologiques ont par conséquent été déployées dans la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) suivant pour une référence consolidée des modifications terminologiques.

Le tableau suivant répertorie les différentes sources où vous pouvez obtenir plus d’informations :

| Ressource | Détails |
|--- |--- |
| [Ajouter  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Ce tutoriel fournit des instructions détaillées pour implémenter [!DNL Target] dans un site web avec des balises dans [!DNL Adobe Experience Platform]. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d’un tutoriel plus vaste qui vous explique comment mettre en oeuvre [!DNL Adobe Experience Platform] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Informations sur le déploiement et la gestion des balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes. |
| [ [!DNL Target] Présentation d’Adobe Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Informations sur l’implémentation de [!DNL Target] à l’aide de [!DNL Adobe Experience Platform]. |

## Avantages de l’implémentation d’at.js à l’aide de l’extension [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez des balises dans [!DNL Adobe Experience Platform] pour implémenter at.js. Pour cette raison, [!DNL Adobe] recommande vivement d’utiliser des balises dans [!DNL Adobe Experience Platform] plutôt qu’une mise en oeuvre manuelle d’at.js.

* **Résout  [!DNL Adobe Analytics] et condition  [!DNL Target] de concurrence :** comme l’ [!DNL Analytics] appel peut être déclenché avant l’ [!DNL Target] appel, l’ [!DNL Target] appel n’est pas associé à l’ [!DNL Analytics] appel. Ce séquencement peut entraîner des données incorrectes. L’extension [!DNL Target] garantit que l’appel de balise [!DNL Analytics] attend la fin de l’appel [!DNL Target], réussi ou non. L’utilisation de balises dans [!DNL Adobe Experience Platform] résout l’incohérence des données que les clients peuvent rencontrer lors de l’implémentation manuelle.

   >[!NOTE]
   >
   >Utilisez l’action [!UICONTROL Envoyer la balise] dans l’extension [!DNL Adobe Analytics] afin que l’appel [!DNL Analytics] attende l’appel [!DNL Target] . Si vous appelez directement `s.t()` ou `s.tl()` à l’aide d’un code personnalisé, les appels [!DNL Analytics] n’attendent pas la fin des appels [!DNL Target].

* **Empêche la gestion incorrecte des offres de redirection :**  si vous avez  [!DNL Target] et  [!DNL Analytics] sur la page et qu’une offre de redirection est exécutée par  [!DNL Target], vous pouvez rencontrer une situation où le  [!DNL Analytics] dispositif de suivi déclenche une requête alors qu’il ne devrait pas (car l’utilisateur est redirigé vers une autre URL). Si vous implémentez [!DNL Target] et [!DNL Analytics] par des balises dans [!DNL Adobe Experience Platform], vous ne rencontrerez pas ce problème. En utilisant des balises dans [!DNL Adobe Experience Platform], [!DNL Target] demande à [!DNL Analytics] d’abandonner la demande de balise [!DNL Analytics].
