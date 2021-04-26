---
keywords: implémentation ; bibliothèque javascript ; js ; atjs ; prise de décision sur périphérique ; prise de décision sur périphérique ; at.js ; on-device ; on-device ; résolution des problèmes ; dépannage
description: Découvrez comment résoudre les problèmes de prise de décision sur périphérique avec la bibliothèque at.js.
title: Comment résoudre les problèmes de prise de décision sur le périphérique avec la bibliothèque JavaScript at.js ?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: a73525a7c2096235d583f54865fcdcbc4b36e7c0
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Dépannage de la prise de décision sur périphérique pour at.js

Suivez les étapes ci-après pour résoudre les problèmes de prise de décision sur périphérique en Adobe Target avec la bibliothèque JavaScript at.js :

1. Activation du journal de la console pour at.js
1. Vérifiez le téléchargement de l’artefact de règle dans l’onglet Réseau de votre navigateur.
1. Vérification du téléchargement d’artefact de règle à l’aide de événements personnalisés at.js

Les sections suivantes décrivent chaque étape de manière plus détaillée :

## Étape 1 : Activation du journal de la console pour at.js

L’ajout du paramètre d’URL `mboxDebug=1` permet à at.js d’imprimer des messages dans la console de votre navigateur.

Tous les messages contiennent un préfixe &quot;AT:&quot; pour un aperçu pratique. Pour vous assurer qu’un artefact a bien été chargé, votre journal de console doit contenir des messages similaires à ceux-ci :

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

L’illustration suivante présente ces messages dans le journal de la console :

![Journal de la console avec des messages d&#39;artefact](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## Étape 2 : Vérifiez le téléchargement de l’artefact de règle dans l’onglet Réseau de votre navigateur.

Ouvrez l’onglet Réseau de votre navigateur.

Par exemple, pour ouvrir DevTools dans Google Chrome :

1. Appuyez sur Ctrl+Maj+J (Windows) ou Commande+Option+J (Mac).
1. Accédez à l&#39;onglet Réseau.
1. Vous pouvez filtrer vos appels par mot-clé &quot;règles.json&quot; pour vous assurer que seul le fichier de règles d’artefact s’affiche.

   En outre, vous pouvez filtrer par &quot;/diffusion|rules.json/&quot; pour afficher tous les appels [!DNL Target] et artefact rule.json.

   ![Onglet Réseau dans Google Chrome](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## Étape 3 : Vérification du téléchargement d’artefact de règle à l’aide de événements personnalisés at.js

La bibliothèque at.js distribue deux nouveaux événements personnalisés pour prendre en charge la prise de décision sur le périphérique.

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

Vous pouvez vous abonner pour écouter ces événements personnalisés dans votre application afin de passer à l’action en cas de succès ou d’échec du téléchargement du fichier de règles d’artefact.

L’exemple suivant montre un exemple de code qui écoute les événements de succès et d’échec du téléchargement d’artefact :

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
