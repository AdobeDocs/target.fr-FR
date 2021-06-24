---
keywords: implémentation;mbox.js;bibliothèque de manipulation dans le dom;target.js;compositeur d’expérience visuelle;iframe;sites angulaires;applications de page seule;appli de page seule;APS
description: Découvrez l’implémentation héritée de mbox.js d’Adobe Target. Migrez vers le SDK Web Adobe Experience Platform (SDK Web AEP) ou vers la dernière version d’at.js.
title: Que fait la bibliothèque [!DNL Target] mbox.js ?
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 78%

---

# Fonctionnement de mbox.js

Informations permettant à votre personnel technique de comprendre l’implémentation de mbox.js et son impact sur votre site.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel sur vos sites. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Manipulation du modèle DOM {#section_169F8D4C077948DCB4F891ABBB03FF63}

Le fichier [!DNL Target.js] contrôle la bibliothèque de manipulation du modèle DOM utilisée par Target Standard. Pour afficher le contenu d’un site web, le fichier [!DNL target.js] référence le fichier [!DNL sizzle.js] (version1.10.8-pre). Le fichier [!DNL Sizzle.js] active les sélecteurs d’éléments HTML. En dehors de [!DNL sizzle.js], seul du code JavaScript natif est utilisé. Aucun code jquery n’est requis.

En outre, le fragment de code suivant est utilisé pour interroger le modèle DOM :
`https://github.com/dperini/ContentLoaded`

## Fichier target.js et compositeur d’expérience visuelle {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

Lorsque vous utilisez le [!UICONTROL compositeur d’expérience visuelle] pour configurer l’expérience d’une activité, votre page web est ouverte dans un iFrame. Lorsque l’iFrame est chargé, Target Standard envoie un appel d’API `postMessage` HTML5. Le fichier [!DNL Target.js] détecte les appels `postMessage` et inclut les bibliothèques JavaScript suivantes sur le site web :

* Pour générer des vignettes : [!DNL https://html2canvas.hertzen.com/]
* Pour une requête interdomaines : [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css], utilisé pour envoyer des messages entre les iFrames. Ces scripts permettent à Adobe d’envoyer des données entre les pages.

## Points à prendre en compte pour les sites angulaires et les applications d’une seule page {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Si vous implémentez Target dans un site angulaire ou une application d’une seule page, vous devez utiliser la bibliothèque at.js à la place de mbox.js.
