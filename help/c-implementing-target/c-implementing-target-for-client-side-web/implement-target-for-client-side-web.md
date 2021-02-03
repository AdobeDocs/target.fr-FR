---
keywords: implémenter ; implémentation ; at.js ; adobe experience platform web sdk ; aep web sdk
description: Informations relatives à l’implémentation d’Adobe Target pour le Web côté client à l’aide d’at.js.
title: Mise en oeuvre d'Adobe Target pour le Web côté client
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 18%

---


# Aperçu : implémentation de Target pour le web côté client

Dans une implémentation côté client de [!DNL Adobe Target], [!DNL Target] fournit les expériences associées directement à une activité dans le navigateur client. Le navigateur décide de l’expérience à afficher et l’affiche. Avec une implémentation côté client, vous pouvez utiliser un éditeur WYSIWYG, le [compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou une interface non visuelle, le [compositeur d’expérience basé sur les formulaires](/help/c-experiences/form-experience-composer.md), pour créer vos expériences d’activité et de personnalisation.

Pour implémenter [!DNL Adobe Target] côté client, vous devez utiliser l’une des bibliothèques JavaScript suivantes :

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Bibliothèque JavaScript at.js cible](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut. Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites.
>
>* **Adobe Experience Platform Web SDK** : Le  [!UICONTROL Adobe Experience Platform Web ] SDK vous permet d’interagir avec les différents services du  [!DNL Experience Cloud] (y compris  [!DNL Target]) via Adobe Experience Edge Network. Si vous choisissez de migrer vers [!DNL Adobe Experience Platform Web SDK], consultez [Qu’est-ce que le SDK Web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) dans le *Guide du SDK Web*.
   >
   >
* **at.js** : La bibliothèque JavaScript at.js offre de nombreux avantages par rapport à mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page. Si vous choisissez de migrer vers at.js, voir [Fonctionnement d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) et [Adobe Target Skill Builder : Chat de développeur, mbox.js Adobe Target est migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Bien que mbox.js soit actuellement pris en charge (jusqu’au 31 mars 2021), nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. En déplaçant tous les clients vers le [!UICONTROL Adobe Experience Platform Web SDK] ou at.js, nos ingénieurs et notre personnel d&#39;assistance pourront vous fournir de nouvelles fonctionnalités et offre le support que vous attendez de l&#39;Adobe.
