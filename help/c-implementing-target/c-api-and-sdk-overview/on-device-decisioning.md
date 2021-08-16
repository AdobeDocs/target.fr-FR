---
keywords: côté serveur;côté serveur;sdk;sdk;on-device;prise de décision;on device;ondevice;zéro latence;latence;proche de zéro;node.js
description: 'Découvrez comment utiliser la prise de décision sur l’appareil pour mettre en cache vos activités A/B et MVT sur votre serveur afin d’effectuer une prise de décision en mémoire à une latence proche de zéro. [!DNL Target] '
title: Qu’est-ce que la prise de décision sur appareil ?
feature: Mise en oeuvre côté serveur
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: fe70f357e2298f1656d713aae5fae800e6775d64
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 10%

---

# Prise de décision sur l’appareil

La prise de décision sur appareil permet de mettre en cache vos activités [!DNL Adobe Target] [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) sur votre serveur et d’effectuer une prise de décision en mémoire à une latence proche de zéro, sans bloquer les demandes réseau au [!DNL Adobe Target] réseau Edge.

Pour plus d’informations, voir [Présentation de la prise de décision sur l’appareil](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) dans la *[documentation des SDK Adobe Target](https://adobetarget-sdks.gitbook.io/docs/)*.

## Webinaire : Personalize and test at zero latency with on-device decisions from  (Personnalisation et test sans latence avec prise de décision sur l’appareil à partir d’Adobe Target ; en anglais)[!DNL Adobe Target]

Plus que jamais, les professionnels du marketing, les propriétaires et les développeurs de produits sont chargés d’optimiser l’expérience client globale sur les sites, les applications et dans toutes les situations où ils sont en contact avec leurs clients. Les multiples outils avec des silos de données et des mises en oeuvre complexes sont inadéquats.

Dans ce webinaire enregistré, [!DNL Adobe Target] experts du produit expliquent comment le déplacement des décisions d’optimisation de l’expérience critique sur l’appareil pour s’exécuter localement avec une latence proche de zéro peut ouvrir la porte à de nouveaux cas d’utilisation passionnants tout en améliorant les performances du site pour vos clients.

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## Bonnes pratiques .

Adobe recommande les bonnes pratiques suivantes lors de l’utilisation de la prise de décision sur l’appareil :

### Bonnes pratiques lorsque la méthode de prise de décision est &quot;sur appareil&quot; {#best-practices-on-device}

Lors de l’utilisation de la méthode de prise de décision &quot;sur l’appareil&quot;, l’artefact est téléchargé lorsque le visiteur charge la page web pour la première fois. Toute qualification d’activité qui doit se produire au premier chargement de page (sans cache) n’a lieu qu’après le téléchargement complet de l’artefact. Vous pouvez suivre certaines bonnes pratiques pour vous assurer que les qualifications d’activité se produisent rapidement pour un nouveau visiteur anonyme.

* Désactivez les activités compatibles &quot;On-Device&quot; qui ne sont pas destinées à être dans l’artefact.
* Si vous disposez de [!DNL Target Premium], vous pouvez utiliser [properties/workspaces](/help/administrating-target/c-user-management/property-channel/property-channel.md) pour créer différents fichiers d’artefacts pour différents espaces de travail.
* Si vos fichiers d’artefact deviennent très volumineux pour des raisons légitimes, vous pouvez utiliser la méthode de prise de décision &quot;hybride&quot;. Cette méthode vous permet de télécharger l’artefact en parallèle et tous les appels d’API [!DNL Target] passent sur le fil jusqu’à ce que l’artefact ait été téléchargé. Pour en savoir plus sur cette approche, consultez la section [Bonnes pratiques relatives au mode de prise de décision &quot;hybride&quot;](#best-practices-hybrid) ci-dessous.
* Si vous disposez d’une application d’une seule page (SPA), [!DNL Adobe] vous recommande de charger et d’initialiser at.js avant de charger le fichier JavaScript principal de votre application lors du premier chargement de la page. Cette approche lance le téléchargement de l’artefact beaucoup plus tôt, ce qui accélère le rendu de l’expérience.

### Bonnes pratiques lorsque la méthode de prise de décision est &quot;hybride&quot; {#best-practices-hybrid}

Lors de l’utilisation de la méthode de prise de décision &quot;hybride&quot;, l’artefact est téléchargé en parallèle. Tant que l’artefact n’est pas téléchargé, tout appel d’API [!DNL Target] passe par le réseau même si les &quot;emplacements&quot; sont compatibles avec l’appareil. Ce comportement est la valeur par défaut de tous les appels `getOffers()` et fournit les meilleures performances dans la plupart des situations. Si vous modifiez le comportement par défaut de `getOffers()` en définissant `decisioningMethod` sur `on-device`, suivez ces bonnes pratiques pour éviter les erreurs et garantir les meilleures performances.

* Si vous décidez d’appeler `getOffers()` avec `decisioningMethod` comme `on-device` lorsque la page se charge pour la première fois, vous devez le faire dans le gestionnaire d’événements at.js &quot;ARTIFACT_DOWNLOAD_SUCCEEDED&quot; pour éviter les erreurs. Si votre artefact est très volumineux, les &quot;emplacements&quot; utilisant cette approche ne sont rendus qu’après son téléchargement complet, ce qui peut retarder le rendu de l’expérience. [!DNL Adobe] recommande d’utiliser rarement cette approche. Suivez les bonnes pratiques pour réduire la taille de l’artefact dans la section [ Bonnes pratiques sur l’appareil](#best-practices-on-device) ci-dessus lors de l’utilisation de cette approche.

## Tutoriel : Prise de décision sur appareil

[!DNL Adobe Target] la prise de décision sur appareil active la diffusion de contenu avec une latence proche de zéro.

Cette vidéo de 7 minutes :

* Décrit la prise de décision sur l’appareil, y compris la manière dont elle se compare à d’autres méthodes de mise en oeuvre de [!DNL Target]
* Illustre comment activer la prise de décision sur l’appareil dans [!DNL Target]
* Examiner un exemple d’activité de compositeur d’après les formulaires qui a été configuré avec du contenu JSON
* Affiche un exemple de code du SDK Node.JS contenant la configuration de clé requise pour la prise de décision sur l’appareil.
* Illustre les résultats dans un navigateur

>[!VIDEO](https://video.tv.adobe.com/v/329032)

Pour visionner d’autres vidéos et tutoriels, consultez le guide [Adobe Target Tutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=fr) .

## Adobe Tech Blog - Partie 1 : Exécutez [!DNL Adobe Target] SDK NodeJS pour l’expérimentation et la personnalisation sur les plateformes de périphérie (Akamai Edge Workers).

[Cliquez ici pour accéder à la publication](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9) du blog.

## Blog Adobe Tech - Partie 2 : exécutez le SDK NodeJS [!DNL Adobe Target] pour permettre l’expérimentation et la personnalisation sur les plateformes Edge (AWS Lambda@Edge).

[Cliquez ici pour accéder à la publication](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563) du blog.