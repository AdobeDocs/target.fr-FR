---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: Pour utiliser Adobe Target Standard ou Cible Premium, ajoutez une ligne de code pour appeler mbox.js.
title: Implémentation de mbox.js
feature: null
translation-type: tm+mt
source-git-commit: a85a5c10c31fb0d7eb00c21ff03b2012d044de45
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 32%

---


# Implémentation de mbox.js

Pour utiliser [!DNL Adobe Target Standard] ou [!DNL Target Premium], ajoutez une ligne de code pour appeler mbox.js.

Vous pouvez utiliser l’une des deux références de bibliothèque suivantes : [!DNL Adobe Experience Platform Web SDK] ou [!DNL at.js]. [Les avantages de at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexpliquent les différences entre les bibliothèques mbox.js et at.js.

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