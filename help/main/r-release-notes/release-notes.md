---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3d8da94a52046e70a89dc24d7923f743bee5c458
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 83%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 22.9.1 (version échelonnée : 13 - 15 septembre 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **13 septembre** : région Europe, Moyen-Orient et Afrique (EMEA)
* **14 septembre** : région des Amériques
* **15 septembre** : région Asie-Pacifique (APAC)

Cette version comprend les améliorations et correctifs suivants :

* Ajout d’une option [!UICONTROL interdomaines] lors du téléchargement d’at.js 2.10.0 (et versions ultérieures) pour autoriser ou désactiver la définition des cookies tiers. (TGT-43674)
* Notifications mises à jour dans le [!DNL Target] Interface utilisateur pour informer les clients si l’importation de [!DNL Recommendations] les flux échouent. (TGT-35811)
* Correction d’un problème en raison duquel [!UICONTROL Offres de décision] ne fonctionnait pas correctement dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC). (TGT-43866)
* Correction d’un problème en raison duquel un message d’erreur s’affichait lors de la sélection de l’objectif de conversion [!UICONTROL Clic sur un élément] pendant la création d’une activité de [!UICONTROL test multivarié] (MVT). (TGT-43842)
* Correction d’un problème en raison duquel la variable [!UICONTROL Impressions] ne s’affichait pas dans le fichier de rapport CSV téléchargé pour les activités de [!UICONTROL ciblage automatique] (AP). (TGT-43780)
* Correction d’un problème qui empêchait les clients de modifier les offres de HTML/JSON après avoir dupliqué des expériences lors de l’utilisation de la variable [!UICONTROL Compositeur d’expérience d’après les formulaires]. (TGT-43633)
* Correction d’un problème en raison duquel les clients ne pouvait pas copier une activité de [!UICONTROL Test A/B] d’un espace de travail non par défaut vers un autre espace de travail non par défaut. (TGT-41910)
* Correction d’un problème pour s’assurer que les clients peuvent afficher correctement les utilisations de [!DNL Recommendations] objets (conceptions, critères, collections, etc.) dans [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) activités qui contiennent des recommandations et qui suppriment également les objets de critère qui ne sont plus utilisés depuis [!DNL Target] Interface utilisateur et [!DNL Recommendations] back-end. (TGT-42331)
* Correction d’un problème qui entraînait l’affichage d’une alerte de délai d’expiration réseau dans la variable [!DNL Target] IU lors de la récupération des paramètres. (TGT-43737)
* Mise à jour de l’interface utilisateur pour garantir que certaines actions de glisser-déposer sont accessibles par le clavier. (TGT-42969)
* Mise à jour de l’interface utilisateur pour garantir que les chaînes de texte sont correctement localisées.

## at.js version 2.10.0 (13 septembre 2022)

* Ajout d’une option [!UICONTROL interdomaines] lors du téléchargement d’at.js 2.10.0 (et versions ultérieures) pour autoriser ou désactiver la définition des cookies tiers. (TGT-43674)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/main/r-release-notes/target-release-notes.md). |
