---
keywords: implémentation;implémentation;at.js;sdk web adobe experience platform;sdk web aep
description: Découvrez comment mettre en oeuvre Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] Bibliothèque JavaScript at.js.
title: Comment mettre en oeuvre [!DNL Target] pour le Web côté client
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 47%

---

# Aperçu : implémenter [!DNL Target] pour le web côté client

Dans une implémentation côté client de [!DNL Adobe Target], [!DNL Target] fournit les expériences associées directement à une activité dans le navigateur client. Le navigateur décide de l’expérience à afficher et l’affiche. Avec une implémentation côté client, vous pouvez utiliser un éditeur WYSIWYG, le [compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou une interface non visuelle, le [compositeur d’expérience basé sur les formulaires](/help/c-experiences/form-experience-composer.md), pour créer vos expériences d’activité et de personnalisation.

Pour mettre en oeuvre [!DNL Adobe Target] côté client, vous devez utiliser l’une des bibliothèques JavaScript suivantes :

* [SDK web Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Bibliothèque JavaScript at.js de Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**Fin de vie de** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut. Adobe recommande à tous les clients de migrer vers la version la plus récente de [!DNL Adobe Experience Platform Web SDK] ou vers la bibliothèque JavaScript at.js avant cette date afin d’éviter tout problème potentiel avec leurs sites.
>
>* **SDK Web Adobe Experience Platform**: Le [!UICONTROL SDK Web Adobe Experience Platform] permet d’interagir avec les différents services de la variable [!DNL Experience Cloud] (y compris [!DNL Target]) par le biais d’Adobe Experience Edge Network. Si vous choisissez de migrer vers le [!DNL Adobe Experience Platform Web SDK], voir [Présentation du SDK Web Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) dans le *Guide du SDK Web*.
>
>* **at.js**: La bibliothèque JavaScript at.js réduit les délais de chargement des pages pour les implémentations web, renforce la sécurité et offre des options d’implémentation optimisées pour les applications d’une seule page. Si vous choisissez de migrer vers at.js, reportez-vous à la section [Fonctionnement d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) et [Adobe Target Skill Builder : Chat de développeur, migrez le fichier mbox.js Adobe Target vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).


