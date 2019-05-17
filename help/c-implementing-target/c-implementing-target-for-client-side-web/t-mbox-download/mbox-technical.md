---
description: Informations permettant à votre personnel technique de comprendre l’implémentation de mbox.js et son impact sur votre site.
keywords: implémentation;mbox.js;bibliothèque de manipulation dans le dom;target.js;compositeur d’expérience visuelle;iframe;sites angulaires;applications de page seule;appli de page seule;APS
seo-description: Informations permettant à votre personnel technique de comprendre l’implémentation de mbox.js et son impact sur votre site.
seo-title: Fonctionnement de mbox.js
solution: Target
subtopic: Prise en main
title: Fonctionnement de mbox.js
topic: Standard
uuid: 5529d620-4a33-479c-871f-18dcd59abb07
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Fonctionnement de mbox.js{#what-mbox-js-does}

Informations permettant à votre personnel technique de comprendre l’implémentation de mbox.js et son impact sur votre site.

Target Standard requiert le fichier [!DNL mbox.js] version 58 ou ultérieure. Pour obtenir des instructions concernant le téléchargement et la mise à jour [!DNL mbox.js], voir [Implémentation Mbox.](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420)

Pour Target Standard, [!DNL mbox.js] appelle un autre fichier JavaScript, [!DNL target.js]. Le fichier [!DNL Target.js] est hébergé et automatiquement mis à jour par Adobe. Aucune intervention de votre part n’est nécessaire pour mettre à jour le fichier [!DNL target.js] et il n’existe aucune personnalisation spécifique au client.

Le fichier [!DNL Target.js] crée une mbox appelée `target-global-mbox` dans la section `<head>` de votre page.

Le fichier [!DNL Target.js] est appelé à partir du fichier [!DNL mbox.js] par une ligne de code JavaScript ajoutée au champ [!UICONTROL Extra JavaScript] du fichier [!DNL mbox.js]. Le seul moyen de désactiver le fichier [!DNL target.js] consiste à ne pas inclure cette ligne de code, ce qui désactive également [!DNL Target].

[!DNL Target.js] a deux fonctions dans [!DNL Target] :

* Manipulation du modèle DOM
* Activation des éléments visuels du [!UICONTROL compositeur d’expérience visuelle]

## Manipulation du modèle DOM {#section_169F8D4C077948DCB4F891ABBB03FF63}

Le fichier [!DNL Target.js] contrôle la bibliothèque de manipulation du modèle DOM utilisée par Target Standard. Pour afficher le contenu d’un site web, le fichier [!DNL target.js] référence le fichier [!DNL sizzle.js] (version1.10.8-pre). Le fichier [!DNL Sizzle.js] active les sélecteurs d’éléments HTML. En dehors de [!DNL sizzle.js], seul du code JavaScript natif est utilisé. Aucun code jquery n’est requis.

En outre, le fragment de code suivant est utilisé pour interroger le modèle DOM :

`https://github.com/dperini/ContentLoaded`

## Fichier target.js et compositeur d’expérience visuelle {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

Lorsque vous utilisez le [!UICONTROL compositeur d’expérience visuelle] pour configurer l’expérience d’une activité, votre page web est ouverte dans un iFrame. Lorsque l’iFrame est chargé, Target Standard envoie un appel d’API `postMessage` HTML5. Le fichier [!DNL Target.js] détecte les appels `postMessage` et inclut les bibliothèques JavaScript suivantes sur le site web :

* Pour générer des vignettes : [!DNL https://html2canvas.hertzen.com/]
* Pour une requête interdomaines : [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css], utilisé pour envoyer des messages entre les iFrames. Ces scripts permettent à Adobe d’envoyer des données entre les pages.

## Points à prendre en compte pour les sites angulaires et les applications d’une seule page  {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Si vous implémentez Target dans un site angulaire ou une application d’une seule page, vous devez utiliser la bibliothèque at.js à la place de mbox.js.

Pour plus d’informations, voir [Implémentation d’at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).
