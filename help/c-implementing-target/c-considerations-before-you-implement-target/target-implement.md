---
keywords: document.write;target;implémenter;implémenter target;dtm;at.js;mbox.js;target.js;mbox;adobe experience platform web skdk;sdk web
description: Implémentez des bibliothèques Adobe [!DNL Target] by referencing the [!DNL Target] (at.js ou mbox.js) sur vos pages web.
title: Comprendre les  [!DNL Target] bibliothèques JavaScript
feature: Mise en œuvre
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 24%

---


# Comprendre les [!DNL Target]bibliothèques JavaScript

Implémentez [!DNL Adobe Target] en référençant les bibliothèques [!DNL Adobe Target] (SDK Web Adobe Experience Platform ou at.js) sur vos pages web.

>[!NOTE]
>
>La bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js ou vers le [!UICONTROL SDK Web Adobe Experience Platform] avant le 31 mars 2021.

## Différences entre les bibliothèques JavaScript [!DNL Target] {#section_40117C78C2F84FECAC4F1BA40CC4F171}

Le tableau suivant explique les différences entre les bibliothèques JavaScript [!DNL Target] :

| Référence de bibliothèque | Description |
|--- |--- |
| SDK web Adobe Experience Platform | Le [!UICONTROL SDK Web Adobe Experience Platform] vous permet d’interagir avec les différents services de la [!DNL Experience Cloud] (y compris [!DNL Target]) par le biais d’Adobe Experience Edge Network. Si vous choisissez de migrer vers le [!DNL Adobe Experience Platform Web SDK], voir [SDK Web Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) dans le *Guide du SDK Web*. |
| at.js | at.js remplace mbox.js pour les implémentations [!DNL [!DNL Target]].<br>Autres avantages : at.js optimise les délais de chargement des pages pour les mises en œuvre web, renforce la sécurité, bloque les avertissements document.write dans Google Chrome et fournit de meilleures options d’implémentation pour les applications d’une seule page. |

## Impact d’at.js sur le délai de chargement des pages {#section_16630CD0FF0A498EB596A51381366A5A}

De nombreux clients et consultants souhaitent connaître l’impact de [!DNL at.js] sur le délai de chargement des pages, en particulier dans le contexte des nouveaux utilisateurs et des utilisateurs réguliers. Malheureusement, il est difficile de mesurer et de fournir des chiffres concrets sur l’ influence de [!DNL at.js] sur le délai de chargement des pages en raison de l’implémentation de chaque client.

Cependant, si l’API visiteur est présente sur la page, [!DNL Target] peut mieux comprendre comment [!DNL at.js] influence le délai de chargement des pages.

>[!NOTE]
>
>L’API visiteur et [!DNL at.js] ont un impact sur le délai de chargement des pages uniquement lorsque vous utilisez la mbox globale (en raison de la technique de masquage du corps). Les mboxes régionales ne sont pas impactées par l’intégration de l’API visiteur.

Les sections suivantes décrivent la séquence d’actions pour les nouveaux visiteurs et les visiteurs récurrents :

### Nouveaux visiteurs

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js est chargé, analysé et exécuté.
1. Si la création automatique de mbox globale est activée, la bibliothèque JavaScript [!DNL Target] :

   * instancie l’objet visiteur ;
   * La bibliothèque [!DNL Target] tente de récupérer les données [!UICONTROL Identifiant visiteur Experience Cloud].
   * Pour un nouveau visiteur, l’API visiteur déclenche une requête inter-domaines à `demdex.net`.
   * Une fois les données [!UICONTROL Identifiant visiteur Experience Cloud] récupérées, une requête à Target est déclenchée.

### Visiteurs récurrents

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js est chargé, analysé et exécuté.
1. Si la création automatique de mbox globale est activée, la bibliothèque JavaScript [!DNL Target] :

   * instancie l’objet visiteur ;
   * La bibliothèque [!DNL Target] tente de récupérer les données [!UICONTROL Identifiant visiteur Experience Cloud].
   * l’API visiteur récupère les données du cookies ;
   * Une fois les données [!UICONTROL Identifiant visiteur Experience Cloud] récupérées, une requête vers [!DNL Target] est déclenchée.

>[!NOTE]
>
>Pour les nouveaux visiteurs, lorsque l’API visiteur est présente, [!DNL Target] passe le fil plusieurs fois pour s’assurer que les demandes [!DNL Target] contiennent des données [!UICONTROL Identifiant visiteur Experience Cloud]. Pour les visiteurs récurrents, [!DNL Target] passe le fil à [!DNL Target] pour récupérer le contenu personnalisé.
