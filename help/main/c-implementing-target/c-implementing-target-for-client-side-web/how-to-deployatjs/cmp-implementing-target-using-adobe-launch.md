---
keywords: implémenter;implémentation;implémentation;adobe launch;launch;concurrence;rediriger;experience platform launch;platform launch;balises;adobe platform
description: Découvrez comment mettre en oeuvre le [!DNL Adobe Target] bibliothèque at.js à l’aide de [!DNL Adobe Experience Platform], la méthode recommandée pour implémenter [!DNL Target].
title: Comment puis-je implémenter  [!DNL Target]  avec  [!DNL Adobe Experience Platform] ?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 96%

---

# Implémentation de [!DNL Target] à l’aide d’[!DNL Adobe Experience Platform]

Les balises dans [!DNL Adobe Experience Platform] représentent la nouvelle génération de fonctionnalités de gestion des balises proposées par [!DNL Adobe]. Les balises offrent aux clients un moyen simple de déployer et gérer les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] est désormais une suite de technologies dédiée à la collecte de données dans [!DNL Adobe Experience Platform]. Plusieurs modifications terminologiques ont par conséquent été déployées dans la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=fr) suivant pour obtenir une référence consolidée des modifications terminologiques.

Le tableau suivant répertorie les différentes sources fournissant plus d’informations :

| Ressource | Détails |
|--- |--- |
| [Ajouter [!UICONTROL Adobe Target] ](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html?lang=fr#implement-solutions) | Ce tutoriel fournit des instructions détaillées relatives à l’implémentation de [!DNL Target] dans un site web avec des balises dans [!DNL Adobe Experience Platform]. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d’un tutoriel plus vaste qui vous explique comment implémenter [!DNL Adobe Experience Platform] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=fr) | Informations sur le déploiement et la gestion des balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes. |
| [Présentation de l’extension Adobe  [!DNL Target] ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=fr) | Informations sur l’implémentation de [!DNL Target] avec [!DNL Adobe Experience Platform]. |

## Avantages de l’implémentation d’at.js à l’aide de l’extension [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez les balises dans [!DNL Adobe Experience Platform] pour implémenter at.js. Pour cette raison, [!DNL Adobe] vous recommande vivement d’utiliser les balises dans [!DNL Adobe Experience Platform] plutôt qu’une implémentation manuelle d’at.js.

* **Résout la condition de concurrence [!DNL Adobe Analytics] et [!DNL Target] :** comme l’appel [!DNL Analytics] peut être déclenché avant l’appel [!DNL Target], l’appel [!DNL Target] n’est pas associé à l’appel [!DNL Analytics]. Ce séquencement peut entraîner des données incorrectes. L’extension [!DNL Target] garantit que l’appel de la balise [!DNL Analytics] attend la fin de l’appel [!DNL Target], réussi ou non. L’utilisation de balises dans [!DNL Adobe Experience Platform] résout l’incohérence des données que les clients peuvent rencontrer lors de l’implémentation manuelle.

   >[!NOTE]
   >
   >Utilisez l’action [!UICONTROL Envoyer la balise] dans l’extension [!DNL Adobe Analytics] afin que l’appel [!DNL Analytics] attende l’appel [!DNL Target]. Si vous appelez directement `s.t()` ou `s.tl()` à l’aide d’un code personnalisé, les appels [!DNL Analytics] n’attendent pas la fin des appels [!DNL Target].

* **Empêche une gestion incorrecte des offres de redirection :** si vous avez [!DNL Target] et [!DNL Analytics] sur la page et qu’une offre de redirection est en cours d’exécution par [!DNL Target], il peut arriver que le système de suivi [!DNL Analytics] déclenche une requête alors qu’il ne devrait pas (car l’utilisateur est redirigé vers une autre URL). Si vous implémentez [!DNL Target] et [!DNL Analytics] via les balises dans [!DNL Adobe Experience Platform], vous ne rencontrerez pas ce problème. À l’aide des balises dans [!DNL Adobe Experience Platform], [!DNL Target] donne l’ordre à [!DNL Analytics] d’abandonner la requête de balise [!DNL Analytics].
