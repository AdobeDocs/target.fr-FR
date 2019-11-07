---
keywords: implémentation;mbox;télécharger mbox.js;télécharger api;api mbox.js
description: Pour utiliser Target Standard ou Target Premium, ajoutez une ligne de code afin d’appeler mbox.js.
title: Implémentation de mbox.js
subtopic: Prise en main
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Implémentation de mbox.js{#mbox-js-implementation}

Pour utiliser Target Standard ou Target Premium, ajoutez une ligne de code afin d’appeler mbox.js.

Vous pouvez utiliser l’une des deux références de bibliothèque suivantes : [!DNL mbox.js] ou [!DNL at.js]. [Avantages d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) présente les différences entre les deux bibliothèques.

>[!NOTE]
>
>La bibliothèque mbox.js est toujours prise en charge, mais il n’y aura plus aucune mise à jour des fonctionnalités. Tous les clients doivent migrer vers at.js. Pour plus d’informations, voir [Migration vers at.js depuis mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

L’unique référence à [!DNL mbox.js] sur chaque page offre les bibliothèques nécessaires à toutes vos activités. [!DNL mbox.js] appelle [!DNL Target] depuis chaque page qui référence le fichier [!DNL mbox.js]. Cela permet à [!DNL Target] de :

* fournir des activités Target ;
* suivre les clics ;
* suivre la plupart des mesures de succès.

>[!TIP]
>
>Pour simplifier l’implémentation, vous pouvez référencer [!DNL mbox.js] dans l’en-tête global.

Vous n’avez ainsi pas à conserver différentes versions spécifiques à une activité du fichier.

1. Référencez [!DNL mbox.js] dans la section `<head>` de chaque page de votre site.

   `<script src="/ *`répertoire`*/ *`scripts`*/mbox.js"></script>`

   Où ` *`scripts`*/ *`répertoire`*` est le répertoire dans lequel vous avez enregistré votre fichier [!DNL mbox.js] après son téléchargement. 
Si votre page contient déjà des mbox d’une implémentation héritée, celles-ci peuvent être utilisées dans la nouvelle interface. Le fichier [!DNL mbox.js] mis à jour reste requis ; toutefois, il est possible de sélectionner ces mbox pour des activités et de les modifier à l’aide du [!UICONTROL compositeur d’expérience visuelle].