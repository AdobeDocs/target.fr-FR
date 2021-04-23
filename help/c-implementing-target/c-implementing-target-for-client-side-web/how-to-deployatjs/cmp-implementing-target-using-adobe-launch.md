---
keywords: implémentation ; implémentation ; implémentation ; lancement adobe ; lancement ; course ; redirection ; platform launch d’expérience
description: Découvrez comment implémenter la bibliothèque Adobe [!DNL Target] at.js à l’aide de Adobe Experience Platform Launch, la méthode préférée pour implémenter Adobe [!DNL Target].
title: Comment mettre en oeuvre  [!DNL Target] à l’aide du lancement d’Adobe ?
feature: Mise en oeuvre côté serveur
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 75%

---

# Mise en oeuvre de [!DNL Target] à l’aide du lancement d’Adobe

L’Adobe Experience Platform Launch est la plateforme de gestion des balises de la prochaine génération issue de l’Adobe. Il s’agit de la méthode préférée pour implémenter Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

## Mise en oeuvre de [!DNL Target] à l’aide du lancement d’Adobe {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

Le tableau suivant répertorie les différentes sources fournissant plus d’informations sur Launch :

| Ressource | Détails |
|--- |--- |
| [Mise en oeuvre de la Cible à l’aide du didacticiel de l’extension Adobe Target](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Ce tutoriel contient des instructions étape par étape pour l’implémentation d’Adobe Target dans un site Web avec Launch. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d’un tutoriel plus important qui explique comment mettre en œuvre Adobe Launch, ainsi que les autres solutions Adobe Experience Cloud. |
| [Documentation Adobe Launch](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html) | Informations sur le déploiement et la gestion de l’ensemble des balises d’analyse, de marketing et de publicité nécessaires pour alimenter les expériences client pertinentes. |
| [Documentation de l’extension Adobe Target](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Informations sur la mise en œuvre de Target à l’aide de Launch. |

## Avantages de l’implémentation d’at.js à l’aide de l’[!DNL Target] extension de lancement {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez Adobe Launch pour mettre at.js en œuvre. Pour cette raison, nous vous conseillons vivement d’utiliser Adobe Launch plutôt que DTM ou une mise en œuvre manuelle d’at.js.

* **Résout la condition de concurrence Analytics et Target :** Comme l’appel Analytics peut être déclenché avant l’appel Target, l’appel Target n’est pas associé à l’appel Analytics. Cela peut entraîner des données incorrectes. À partir de 0.6.0, l’extension Target Launch assure que l’appel de la balise Analytics attend la fin de l’appel Target, réussi ou non. Cela devrait résoudre le problème d’incohérence de données que les clients ont pu rencontrer.
* **Empêche une gestion incorrecte des offres de redirection :** Si vous disposez de Target et d’Analytics sur la page et qu’une offre de redirection est en cours d’exécution par Target, il peut arriver que le système de suivi d’Analytics déclenche une requête alors qu’il ne devrait pas (car l’utilisateur est redirigé vers une autre URL). Si vous implémentez Target et Analytics via Launch, vous ne rencontrerez pas ce problème. Avec Launch, Target demande à Analytics d’abandonner la demande de balise Analytics.
