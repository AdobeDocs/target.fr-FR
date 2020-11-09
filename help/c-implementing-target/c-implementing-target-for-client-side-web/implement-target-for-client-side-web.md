---
description: Informations sur l’implémentation d’Adobe Target pour le web côté client.
title: Implémentation d’Adobe Target pour le web côté client
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 100%

---


# Aperçu : implémentation de Target pour le web côté client

Dans une implémentation côté client de [!DNL Adobe Target], [!DNL Target] fournit les expériences associées directement à une activité dans le navigateur client. Le navigateur décide de l’expérience à afficher et l’affiche. Avec une implémentation côté client, vous pouvez utiliser un éditeur WYSIWYG, le [compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou une interface non visuelle, le [compositeur d’expérience basé sur les formulaires](/help/c-experiences/form-experience-composer.md), pour créer vos expériences d’activité et de personnalisation.

Pour implémenter [!DNL Adobe Target] côté client, vous devez utiliser la bibliothèque [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) ou mbox.js.

>[!NOTE]
>
>La bibliothèque mbox.js n’est plus développée. Tous les clients doivent [déployer at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) ou [migrer de mbox.js vers at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).
