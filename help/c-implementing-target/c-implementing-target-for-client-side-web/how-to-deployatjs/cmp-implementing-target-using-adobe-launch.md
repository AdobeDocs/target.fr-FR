---
keywords: implémenter;implémentation;implémentation;lancement d’adobe;course;redirection;platform launch d’expérience;platform launch
description: Découvrez comment implémenter la bibliothèque Adobe [!DNL Target] at.js à l’aide d’Adobe Experience Platform Launch, la méthode préconisée pour implémenter Adobe [!DNL Target].
title: Comment mettre en oeuvre  [!DNL Target] avec Adobe Launch ?
feature: Mise en oeuvre côté serveur
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: fd7d3900f9e5d1a6c3d13fd2452de8528f8fd248
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 9%

---

# Implémentez [!DNL Target] à l’aide de [!DNL Adobe Platform Launch]

[!DNL Adobe Experience Platform Launch] est la nouvelle génération de plateforme de gestion des balises d’  [!DNL Adobe] et est la méthode préconisée pour l’implémentation de  [!DNL Adobe Target]. [!DNL Platform Launch] offre aux clients un moyen simple de déployer et gérer les balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes.

## Implémentez [!DNL Target] à l’aide de [!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Le tableau suivant répertorie les différentes sources fournissant plus d’informations sur [!DNL Platform Launch]:

| Ressource | Détails |
|--- |--- |
| [ [!DNL Target] Mise en oeuvre à l’aide du tutoriel sur l’extension  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Ce tutoriel fournit des instructions étape par étape pour mettre en oeuvre [!DNL Target] dans un site web avec [!DNL Platform Launch]. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d’un tutoriel plus vaste qui vous explique comment mettre en oeuvre [!DNL Platform Launch] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Guide de démarrage rapide pour les balises dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Informations sur le déploiement et la gestion des balises d’analyse, de marketing et de publicité nécessaires pour offrir des expériences client pertinentes. |
| [ [!DNL Target] Documentation d’Adobe Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Informations sur l’implémentation de [!DNL Target] à l’aide de [!DNL Platform Launch]. |

## Avantages de l’implémentation d’at.js à l’aide de l’extension [!DNL Target] [!DNL Platform Launch] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez [!DNL Platform Launch] pour implémenter at.js. Pour cette raison, [!DNL Adobe] recommande vivement d’utiliser [!DNL Platform Launch] plutôt qu’une mise en oeuvre manuelle d’at.js.

* **Résout  [!DNL Adobe Analytics] et condition  [!DNL Target] de concurrence :** comme l’ [!DNL Analytics] appel peut être déclenché avant l’ [!DNL Target] appel, l’ [!DNL Target] appel n’est pas associé à l’ [!DNL Analytics] appel. Ce séquencement peut entraîner des données incorrectes. À partir de la version 0.6.0, l’extension [!DNL Platform Launch] garantit que l’appel de balise [!DNL Analytics] attend la fin de l’appel [!DNL Target], réussi ou non. L’utilisation de [!DNL Platform Launch] résout l’incohérence des données que les clients peuvent rencontrer lors de l’implémentation manuelle.
* **Empêche la gestion incorrecte des offres de redirection :**  si vous avez  [!DNL Target] et  [!DNL Analytics] sur la page et qu’une offre de redirection est exécutée par  [!DNL Target], vous pouvez rencontrer une situation où le  [!DNL Analytics] dispositif de suivi déclenche une requête alors qu’il ne devrait pas (car l’utilisateur est redirigé vers une autre URL). Si vous implémentez [!DNL Target] et [!DNL Analytics] via [!DNL Platform Launch], vous ne rencontrerez pas ce problème. En utilisant [!DNL Platform Launch], [!DNL Target] demande à [!DNL Analytics] d’abandonner la demande de balise [!DNL Analytics].
