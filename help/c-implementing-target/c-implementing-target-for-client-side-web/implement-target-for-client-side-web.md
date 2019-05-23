---
description: Informations sur l'implémentation de Target pour le web côté client.
seo-description: Informations sur l'implémentation d'Adobe Target pour le web côté client.
seo-title: Mise en œuvre d'Adobe Target pour le web client
solution: Target
title: 'Aperçu : implémentation de Target pour le web côté client'
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: 0d5aa4d1f46bc64b0c88ee1ca0298cb09238f7e1

---


# Aperçu : implémenter Target pour le web client

Dans une mise en œuvre côté client de [!DNL Adobe Target], [!DNL Target] fournit les expériences associées directement à une activité dans le navigateur client. Le navigateur décide de l&#39;expérience à afficher et l&#39;affiche. Avec une mise en œuvre côté client, vous pouvez utiliser un éditeur WYSIWYG, le [compositeur](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) d&#39;expérience visuelle ou une interface non visuelle, le compositeur d&#39;expérience [d&#39;après les formulaires](/help/c-experiences/form-experience-composer.md), pour créer vos expériences d&#39;activité et de personnalisation.

Pour implémenter [!DNL Adobe Target] le côté client, vous devez utiliser la bibliothèque [at. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) ou mbox. js.

>[!NOTE]
>
>La bibliothèque mbox.js n’est plus développée. Tous les clients [doivent déployer at. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) ou [migrer de mbox. js vers at. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).
