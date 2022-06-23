---
keywords: événements personnalisés;at.js;échec de la requête; réussite de la requête;échec du rendu du contenu;réussite du rendu du contenu;bibliothèque chargée;démarrage de la requête;démarrage du rendu du contenu;aucune offre du rendu du contenu;redirection du rendu du contenu
description: Utilisation d’événements personnalisés pour l’Adobe [!DNL Target] bibliothèque JavaScript at.js à avertir lorsqu’une requête ou une offre mbox échoue ou réussit.
title: Comment utiliser les événements personnalisés at.js ?
feature: at.js
role: Developer
exl-id: 4073210b-b782-48a7-8b69-29eb5cd98fd5
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 83%

---

# événements personnalisés at.js

Informations sur `at.js custom events`, qui permet de savoir quand une requête ou une offre mbox échoue ou réussit.

Historiquement, mbox.js (désormais obsolète) ne laissait aucun autre code JavaScript qui s’exécute sur la page savoir ce qui se passait en arrière-plan. Avec l’évolution d’at.js, nous avions une opportunité unique de résoudre ce problème.

Nos clients nous ont ainsi indiqué qu’ils souhaiteraient être informés dans différentes situations, notamment lorsque :

* Une requête mbox a échoué en raison du délai d’attente, d’un code d’état erroné, d’une erreur d’analyse JSON, etc.
* Une requête mbox a réussi.
* Le rendu d’une offre a échoué en raison d’un élément mbox d’encapsulage manquant, d’un sélecteur introuvable, etc.
* Le rendu d’une offre a réussi. Des modifications ont été appliquées au modèle DOM.

Les événements prédéfinis ont une structure qui vous permet d’extraire les données requises en fonction du type d’événement.

Pour s’assurer que des événements peuvent être utilisés dans différents scénarios, les événements personnalisés ont un objet de charge utile affecté à la propriété Détail de l’objet d’événement (transféré au gestionnaire). De plus, pour éviter de transférer des chaînes comme noms d’événements, les événements sont exposés sous la forme de constantes par le biais de l’espace de noms `adobe.target.event`.

## Structure {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

| Clé | Type | Description |
|--- |--- |--- |
| type | Chaîne | Il existe plusieurs scénarios dans lesquels vous pouvez souhaiter être notifié afin de faciliter les activités de traçage, de débogage et de personnalisation de l’interaction avec at.js.<br>Chacun des événements personnalisés ci-dessous comporte deux formats : une « constante » et une « valeur de chaîne ».<ul><li>**Constantes** : précédées de `adobe.target.event.`, présentées en majuscules et contenant des traits de soulignement. Pour vous abonner à des événements personnalisés *après* le chargement d’at.js, mais *avant* que la réponse mbox n’ait été reçue, utilisez le format de la constante.</li><li>**Valeurs de chaîne** : en minuscules avec des tirets. Pour vous abonner à des événements personnalisés *avant* le chargement d’at.js, utilisez la valeur de chaîne.</li></ul>**Échec de la demande**<br> Constante : `adobe.target.event.REQUEST_FAILED`<br>Valeur de chaîne : `at-request-failed`<br>Description : Une requête de mbox a échoué en raison du délai d’attente, d’un code d’état incorrect, d’une erreur d’analyse JSON, etc.<br>**Requête Réussie**<br> Constante : `adobe.target.event.REQUEST_SUCCEEDED`<br>Valeur de chaîne : `at-request-succeeded`<br>Description : Une requête mbox a abouti.<br>**La restitution de contenu a échoué**<br> Constante : `adobe.target.event.CONTENT_RENDERING_FAILED`<br>Valeur de chaîne : `at-content-rendering-failed`<br>Description : La restitution de l’offre a échoué en raison d’un élément mbox d’encadrement manquant, d’un sélecteur introuvable, etc.<br>**La restitution de contenu a réussi**<br> Constante : `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>Valeur de chaîne : `at-content-rendering-succeeded`<br>Description : La restitution des offres a réussi. Des modifications ont été appliquées au modèle DOM.<br>**Bibliothèque chargée**<br> : Constante : `adobe.target.event.LIBRARY_LOADED`<br>Valeur de chaîne : `at-library-loaded`<br>Description : Cet événement est idéal pour effectuer le suivi lorsque at.js a été entièrement chargé. Vous pouvez utiliser cet événement pour personnaliser l’exécution globale de mbox. Vous pouvez également l’utiliser pour désactiver la mbox globale, puis écouter cet événement de manière à en différer le déclenchement.<br>**Lancement de requête**<br> Constante : `adobe.target.event.REQUEST_START`<br>Valeur de chaîne : `at-request-start`<br>Description : Cet événement est déclenché avant l’exécution d’une requête HTTP. Vous pouvez utiliser cet événement pour effectuer des mesures de performances à l’aide de l’API de temporisation de ressources.<br>**Lancement de restitution de contenu**<br> Constante : `adobe.target.event.CONTENT_RENDERING_START`<br>Valeur de chaîne : `at-content-rendering-start`<br>Description : Cet événement est déclenché avant le déclenchement du sondage du sélecteur et la restitution du contenu sur la page. Vous pouvez utiliser cet événement pour effectuer le suivi de la progression du rendu du contenu.<br>**Restitution de contenu sans offre**<br> Constante : `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>Valeur de chaîne : `at-content-rendering-no-offers`<br>Description : Cet événement est déclenché lorsqu’aucune offre n’est renvoyée.<br>**Redirection de restitution de contenu**<br> Constante : `adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>Valeur de chaîne : `at-content-rendering-redirect`<br>Description : Cet événement est déclenché lorsqu’une offre est une redirection et que Target redirige vers une autre URL. |
| mbox | Chaîne | nom de mbox |
| message | Chaîne | Contient une description explicite indiquant ce qui s’est passé, le message d’erreur, etc. |
| Suivi | Objet | Contient `sessionId` et `deviceId`. Dans certains cas, `deviceId` peut être absent si [!DNL Target] n’est pas parvenu à le récupérer dans le serveur Edge. |
| type | Chaîne | **Artefact de prise de décision sur l’appareil réussi**<br> Constante :<br>`adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`<br>Valeur de chaîne : `artifactDownloadSucceeded`<br>Description : Appelé lorsque l’artefact de prise de décision sur l’appareil est correctement téléchargé.<br>**Échec de l’artefact de prise de décision sur l’appareil**<br> Constante : `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`<br>Valeur de chaîne : `artifactDownloadFailed`<br>Description : Appelé lorsque l’artefact de prise de décision sur l’appareil n’a pas pu être téléchargé. |

## Utilisation {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```javascript
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## Vidéo de formation : Jetons de réponse et événements personnalisés at.js ![Badge du tutoriel](/help/main/assets/tutorial.png) {#section_ED304A7137DC42A4BDCD6D57C989F1FA}

Regardez la vidéo suivante pour savoir comment utiliser les jetons de réponse et les événements personnalisés at.js pour partager des informations de profil de Target avec des systèmes tiers.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
