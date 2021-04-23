---
keywords: implémentation ; mbox ; télécharger mbox.js ; api de téléchargement ; api mbox.js
description: Découvrez l’implémentation héritée du fichier mbox.js d’Adobe Target. Migration vers le Adobe Experience Platform Web SDK (AEP Web SDK) ou vers la dernière version d’at.js.
title: Comment mettre en oeuvre  [!DNL Target] avec mbox.js ?
feature: at.js
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 47%

---

# Implémentation de mbox.js

Pour utiliser [!DNL Adobe Target Standard] ou [!DNL Target Premium], ajoutez une ligne de code pour appeler mbox.js.

Vous pouvez utiliser l’une des deux références de bibliothèque suivantes : [!DNL Adobe Experience Platform Web SDK] ou [!DNL at.js]. [Les avantages de at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexpliquent les différences entre les bibliothèques mbox.js et at.js.

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : A compter du 31 mars 2021, la bibliothèque mbox.js  [!DNL Adobe Target] ne sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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
