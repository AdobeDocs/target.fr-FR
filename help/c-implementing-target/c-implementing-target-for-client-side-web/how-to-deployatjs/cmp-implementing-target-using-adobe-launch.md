---
keywords: implémenter;implémentation;implémentation;lancement d’adobe;course;redirection;platform launch d’expérience;platform launch;balises;adobe platform
description: Découvrez comment implémenter la bibliothèque Adobe [!DNL Target] at.js à l’aide d’Adobe Experience Platform Launch, la méthode préconisée pour implémenter Adobe [!DNL Target].
title: Comment mettre en oeuvre  [!DNL Target] avec Adobe Launch ?
feature: Mise en oeuvre côté serveur
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: 82629fb4c543220796fc99d9c034ebb725e1a645
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---

# Implémentez [!DNL Target] à l’aide de [!DNL Adobe Experience Platform]

Les balises de [!DNL Adobe Experience Platform] représentent la nouvelle génération des fonctionnalités de gestion des balises de [!DNL Adobe]. Les balises offrent aux clients un moyen simple de déployer et gérer les balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] a été renommé suite de technologies de collecte de données dans  [!DNL Adobe Experience Platform]. Plusieurs modifications terminologiques ont par conséquent été apportées à la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) suivant pour une référence consolidée des modifications terminologiques.

Le tableau suivant répertorie les différentes sources où vous pouvez obtenir plus d’informations :

| Ressource | Détails |
|--- |--- |
| [Ajouter  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Ce tutoriel fournit des instructions détaillées pour implémenter [!DNL Target] dans un site web avec des balises dans [!DNL Adobe Experience Platform]. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d’un tutoriel plus vaste qui vous explique comment mettre en oeuvre [!DNL Adobe Experience Platform] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Informations sur le déploiement et la gestion des balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes. |
| [ [!DNL Target] Présentation d’Adobe Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Informations sur l’implémentation de [!DNL Target] à l’aide de [!DNL Adobe Experience Platform]. |

## Avantages de l’implémentation d’at.js à l’aide de l’extension [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez des balises dans [!DNL Adobe Experience Platform] pour implémenter at.js. Pour cette raison, [!DNL Adobe] recommande vivement d’utiliser des balises dans [!DNL Adobe Experience Platform] plutôt qu’une mise en oeuvre manuelle d’at.js.

* **Résout  [!DNL Adobe Analytics] et condition  [!DNL Target] de concurrence :** comme l’ [!DNL Analytics] appel peut être déclenché avant l’ [!DNL Target] appel, l’ [!DNL Target] appel n’est pas associé à l’ [!DNL Analytics] appel. Ce séquencement peut entraîner des données incorrectes. L’extension [!DNL Target] garantit que l’appel de balise [!DNL Analytics] attend la fin de l’appel [!DNL Target], réussi ou non. L’utilisation de balises dans [!DNL Adobe Experience Platform] résout l’incohérence des données que les clients peuvent rencontrer lors de l’implémentation manuelle.
* **Empêche la gestion incorrecte des offres de redirection :**  si vous avez  [!DNL Target] et  [!DNL Analytics] sur la page et qu’une offre de redirection est exécutée par  [!DNL Target], vous pouvez rencontrer une situation où le  [!DNL Analytics] dispositif de suivi déclenche une requête alors qu’il ne devrait pas (car l’utilisateur est redirigé vers une autre URL). Si vous implémentez [!DNL Target] et [!DNL Analytics] par des balises dans [!DNL Adobe Experience Platform], vous ne rencontrerez pas ce problème. En utilisant des balises dans [!DNL Adobe Experience Platform], [!DNL Target] demande à [!DNL Analytics] d’abandonner la demande de balise [!DNL Analytics].
