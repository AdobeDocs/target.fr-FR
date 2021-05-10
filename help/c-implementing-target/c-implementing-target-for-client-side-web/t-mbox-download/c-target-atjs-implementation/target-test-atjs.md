---
keywords: at.js ; non-production ; non-production ; déploiement
description: Découvrez l’implémentation héritée du fichier mbox.js d’Adobe Target. Migration vers le Adobe Experience Platform Web SDK (AEP Web SDK) ou vers la dernière version d’at.js.
title: Comment déployer at.js sur un Environnement hors production ?
feature: 'at.js '
role: Developer
exl-id: 607b2b5b-bb2a-4443-abc0-452b421fc009
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 80%

---

# Déploiement d’at.js sur un environnement hors production

Informations sur les techniques de déploiement sécurisé d’at.js dans un environ hors production.

## Utilisation de l’extension Requestly de Chrome pour le mappage sur un autre fichier

>[!NOTE]
>
>En plus des informations suivantes, vous pouvez utiliser l’[extension de navigateur Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) pour Google Chrome.

L’extension Chrome gratuite [Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) permet de rediriger les demandes vers une autre URL.

Vous déployez at.js vers une URL, puis utilisez Requestly pour mapper l’URL actuelle du fichier mbox.js sur la nouvelle URL du fichier at.js. Ensuite, chaque fois que le site web tente de charger mbox.js, il charge at.js à la place. Cette approche permet aussi à Adobe de vous aider plus facilement.

## Déploiement dans un environnement de développement, de test ou d’AQ

Si vous hébergez mbox.js dans le code base et si vous pouvez facilement mettre à jour vos environnements de code, déployez at.js sur l’un de vos environnements inférieurs.

Pour qu’Adobe puisse vous offrir une assistance optimale, déployez le fichier sur un environnement accessible par Adobe.

## Utilisation de Charles ou Fiddler pour mapper sur un fichier local

[Charles Web Debugging Proxy](https://www.charlesproxy.com/) est une application disponible pour Mac et Windows. Sa fonctionnalité Map Local permet de mapper le chargement du fichier mbox.js de production sur une copie locale du fichier at.js. Vous pouvez télécharger gratuitement une version d’essai pour Mac et Windows.

[Fiddler](https://www.telerik.com/fiddler) est un outil similaire pour Windows qui peut être téléchargé gratuitement.

## Déploiement dans un autre environnement de gestionnaire de balises

Si vous utilisez un autre gestionnaire de balises, il propose certainement un moyen de déployer at.js en toute sécurité sans impact sur le trafic de production.
