---
description: Informations expliquant comment déployer at.js de manière sécurisée dans un environ hors production.
title: Déploiement d’at.js dans un environnement hors production
feature: null
uuid: 7f1adc43-35b4-442c-bb06-feab60604a87
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 92%

---


# Deploy at.js to a non-production environment{#deploy-at-js-to-a-non-production-environment}

Informations sur les techniques de déploiement sécurisé d’at.js dans un environ hors production.

## Déploiement dans l’environnement de test de la gestion dynamique des balises

Si vous utilisez la gestion dynamique des balises, vous pouvez facilement enregistrer at.js dans la configuration de l’outil Adobe Target.

Une fois la bibliothèque enregistrée, utilisez l’outil DTM Switch pour la tester sur le code de production. Ainsi, les consultants pourront aussi plus facilement vous aider.

Pour en savoir plus, voir [Option 3 : Mise en œuvre manuelle de Target avec la bibliothèque JavaScript Target hébergée par la Dynamic Tag Management](https://experienceleague.adobe.com/docs/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html) dans le guide *Bonnes pratiques relatives à la mise en œuvre d’Adobe Target à l’aide de la Dynamic Tag Management*.

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