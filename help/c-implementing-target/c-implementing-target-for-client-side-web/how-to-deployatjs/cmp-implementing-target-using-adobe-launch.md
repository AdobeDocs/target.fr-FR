---
keywords: implémentation ; implémentation ; implémentation ; lancement adobe ; lancement ; course ; redirection ; platform launch d’expérience ; platform launch
description: Découvrez comment implémenter la bibliothèque Adobe [!DNL Target] at.js à l’aide de Adobe Experience Platform Launch, la méthode préférée pour implémenter Adobe [!DNL Target].
title: Comment mettre en oeuvre  [!DNL Target] à l’aide du lancement d’Adobe ?
feature: Mise en oeuvre côté serveur
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a69737f49a52cde703627f91d4b97609c1796ee6
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 10%

---

# Implémentez [!DNL Target] en utilisant [!DNL Adobe Platform Launch]

[!DNL Adobe Experience Platform Launch] est la plateforme de gestion des balises de la prochaine génération  [!DNL Adobe] et est la méthode préférée pour implémenter  [!DNL Adobe Target]. [!DNL Platform Launch] permet aux clients de déployer et de gérer de manière simple les balises d’analyse, de marketing et de publicité nécessaires pour générer des expériences client pertinentes.

## Implémenter [!DNL Target] en utilisant [!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Le tableau suivant répertorie les différentes sources fournissant plus d’informations sur [!DNL Platform Launch]:

| Ressource | Détails |
|--- |--- |
| [ [!DNL Target] Mise en oeuvre à l’aide du didacticiel  [!UICONTROL Adobe Target Extension]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Ce didacticiel fournit des instructions détaillées pour implémenter [!DNL Target] dans un site Web avec [!DNL Platform Launch]. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d&#39;un didacticiel plus volumineux qui vous montre comment implémenter [!DNL Platform Launch] et d&#39;autres solutions [!DNL Adobe Experience Cloud]. |
| [[!DNL Adobe Platform Launch] Documentation](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html#get-started) | Informations relatives au déploiement et à la gestion des balises d’analyse, de marketing et de publicité nécessaires pour générer des expériences client pertinentes. |
| [Documentation  [!DNL Target] d’AdobeExtension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Informations sur l&#39;implémentation de [!DNL Target] à l&#39;aide de [!DNL Platform Launch]. |

## Avantages de l’implémentation d’at.js à l’aide de l’extension [!DNL Target] [!DNL Platform Launch] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez [!DNL Platform Launch] pour implémenter at.js. Pour cette raison, [!DNL Adobe] suggère fortement d’utiliser [!DNL Platform Launch] plutôt qu’une implémentation manuelle d’at.js.

* **Résout  [!DNL Adobe Analytics] et condition  [!DNL Target] de concurrence :** Comme l’ [!DNL Analytics] appel peut être déclenché avant l’ [!DNL Target] appel, l’ [!DNL Target] appel n’est pas assemblé à l’ [!DNL Analytics] appel. Ce séquencement peut conduire à des données incorrectes. À partir de 0.6.0, l&#39;extension [!DNL Platform Launch] garantit que l&#39;appel de balise [!DNL Analytics] attend jusqu&#39;à ce que l&#39;appel [!DNL Target] se termine, avec succès ou non. L’utilisation de [!DNL Platform Launch] résout l’incohérence des données que les clients peuvent rencontrer lors de l’implémentation manuelle.
* **Empêche la gestion incorrecte des offres de redirection :** Si vous avez  [!DNL Target] et  [!DNL Analytics] sur la page et qu’une offre de redirection est exécutée par  [!DNL Target], vous pouvez rencontrer une situation dans laquelle le  [!DNL Analytics] suivi déclenche une requête alors qu’elle ne le devrait pas (car l’utilisateur est redirigé vers une autre URL). Si vous implémentez [!DNL Target] et [!DNL Analytics] par [!DNL Platform Launch], ce problème ne se produira pas. En utilisant [!DNL Platform Launch], [!DNL Target] demande à [!DNL Analytics] d&#39;abandonner la demande de balise [!DNL Analytics].
