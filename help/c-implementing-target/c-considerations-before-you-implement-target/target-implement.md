---
keywords: document.write;cible;implémenter;mettre en oeuvre la cible;dtm;gestion dynamique des balises;at.js;mbox.js;cible.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: Mettez en oeuvre des bibliothèques d’Adobe [!DNL Target] by referencing the [!DNL Target] (at.js ou mbox.js) sur vos pages Web.
title: Comprendre les  [!DNL Target] bibliothèques JavaScript
feature: Mise en œuvre
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 23%

---


# Comprendre les [!DNL Target]bibliothèques JavaScript

Implémentez [!DNL Adobe Target] en référençant les bibliothèques [!DNL Adobe Target] (Adobe Experience Platform Web SDK ou at.js) sur vos pages Web.

>[!NOTE]
>
>La bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js ou vers le [!UICONTROL SDK Web de Adobe Experience Platform] avant le 31 mars 2021. Pour plus d’informations, voir [Migration vers at.js à partir de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA) ou [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

## Différences entre les bibliothèques JavaScript [!DNL Target] {#section_40117C78C2F84FECAC4F1BA40CC4F171}

Le tableau suivant explique les différences entre les bibliothèques JavaScript [!DNL Target] :

| Référence de bibliothèque | Description |
|--- |--- |
| Adobe Experience Platform Web SDK | Le [!UICONTROL Adobe Experience Platform Web SDK] vous permet d’interagir avec les différents services de [!DNL Experience Cloud] (y compris [!DNL Target]) via le réseau Adobe Experience Edge Network. Si vous choisissez de migrer vers [!DNL Adobe Experience Platform Web SDK], consultez [Qu’est-ce que le SDK Web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) dans le *Guide du SDK Web*. |
| at.js | at.js remplace mbox.js pour les implémentations [ ! DNL [!DNL Target]].<br>Autres avantages : at.js optimise les délais de chargement des pages pour les mises en œuvre web, renforce la sécurité, bloque les avertissements document.write dans Google Chrome et fournit de meilleures options d’implémentation pour les applications d’une seule page.<br>Pour plus d’informations, consultez [Implémentation de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md). |

## Impact d’at.js sur le temps de chargement de page {#section_16630CD0FF0A498EB596A51381366A5A}

De nombreux clients et consultants veulent connaître l’impact de [!DNL at.js] sur le temps de chargement des pages, en particulier dans le contexte des utilisateurs nouveaux ou récurrents. Malheureusement, il est difficile de mesurer et de fournir des chiffres concrets sur la façon dont [!DNL at.js] influence le temps de chargement de page en raison de l&#39;implémentation de chaque client.

Cependant, si l&#39;API du Visiteur est présente sur la page, [!DNL Target] peut mieux comprendre comment [!DNL at.js] influence le temps de chargement de page.

>[!NOTE]
>
>L’API du Visiteur et [!DNL at.js] ont un impact sur le temps de chargement des pages uniquement lorsque vous utilisez la mbox globale (en raison de la technique de masquage du corps). Les mboxes régionales ne sont pas impactées par l’intégration de l’API visiteur.

Les sections suivantes décrivent la séquence d’actions pour les nouveaux visiteurs et les visiteurs récurrents :

### Nouveaux visiteurs

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js est chargé, analysé et exécuté.
1. Si la création automatique de mbox globale est activée, la bibliothèque JavaScript [!DNL Target] :

   * instancie l’objet visiteur ;
   * La bibliothèque [!DNL Target] tente de récupérer les données [!UICONTROL ID de Visiteur Experience Cloud].
   * Pour un nouveau visiteur, l’API du Visiteur déclenche une requête interdomaines à `demdex.net`.
   * Une fois les données [!UICONTROL ID de Visiteur Experience Cloud] récupérées, une demande de Cible est déclenchée.

### Visiteurs récurrents

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js est chargé, analysé et exécuté.
1. Si la création automatique de mbox globale est activée, la bibliothèque JavaScript [!DNL Target] :

   * instancie l’objet visiteur ;
   * La bibliothèque [!DNL Target] tente de récupérer les données [!UICONTROL ID de Visiteur Experience Cloud].
   * l’API visiteur récupère les données du cookies ;
   * Une fois les données [!UICONTROL ID de Visiteur Experience Cloud] récupérées, une requête à [!DNL Target] est déclenchée.

>[!NOTE]
>
>Pour les nouveaux visiteurs, lorsque l’API du Visiteur est présente, [!DNL Target] passe le fil plusieurs fois afin de s’assurer que les requêtes [!DNL Target] contiennent des données [!UICONTROL ID de Visiteur Experience Cloud]. Pour les visiteurs de retour, [!DNL Target] passe le fil à [!DNL Target] uniquement pour récupérer le contenu personnalisé.
