---
keywords: implémentation;implémentation;at.js;sdk web adobe experience platform;sdk web aep
description: Découvrez comment mettre en oeuvre Adobe [!DNL Target] pour le Web côté client à l’aide du SDK Web Adobe Experience Platform (SDK Web AEP) ou de la variable [!DNL Target] Bibliothèque JavaScript at.js.
title: Comment mettre en oeuvre [!DNL Target] pour le Web côté client
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 27%

---

# Aperçu : implémenter [!DNL Target] pour le web côté client

Dans une implémentation côté client de [!DNL Adobe Target], [!DNL Target] fournit les expériences associées directement à une activité dans le navigateur client. Le navigateur décide de l’expérience à afficher et l’affiche. Avec une implémentation côté client, vous pouvez utiliser un éditeur WYSIWYG, le [compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou une interface non visuelle, le [compositeur d’expérience basé sur les formulaires](/help/main/c-experiences/form-experience-composer.md), pour créer vos expériences d’activité et de personnalisation.

Pour mettre en oeuvre [!DNL Adobe Target] côté client, vous devez utiliser l’une des bibliothèques JavaScript suivantes :

* [SDK web Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)

   Le [!UICONTROL SDK Web Adobe Experience Platform] permet d’interagir avec les différents services de la variable [!DNL Experience Cloud] (y compris [!DNL Target]) par le biais d’Adobe Experience Edge Network. Si vous choisissez de migrer vers le [!DNL Adobe Experience Platform Web SDK], voir [Présentation du SDK Web Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} dans la variable *Guide du SDK Web*.

* [Bibliothèque JavaScript at.js de Target](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)

   La bibliothèque JavaScript at.js réduit les délais de chargement des pages pour les implémentations web, renforce la sécurité et offre des options d’implémentation optimisées pour les applications d’une seule page. Si vous choisissez de migrer vers at.js, reportez-vous à la section [Fonctionnement d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/){target=_blank} et [Adobe Target Skill Builder : Chat de développeur, migrez le fichier mbox.js Adobe Target vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true){target=_blank}.



