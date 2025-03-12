---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour,mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 911950b341d8221145eeacfa288926b0a1be434e
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 43%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 25.3.5 (11 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) en raison duquel les chemins de navigation n’étaient pas toujours affichés en bas de l’éditeur, ce qui entraînait des difficultés pour sélectionner précisément les éléments. (TGT-51844)
* Correction d’un problème qui empêchait les utilisateurs de modifier les offres dans le panneau [!UICONTROL Modifications]. (TGT-51800)
* Correction d’un problème où les actions s’affichaient incorrectement dans le panneau de gauche pour les expériences et les audiences, y compris en mode [!UICONTROL ClickTrack]. (TGT-51895)
* Correction d’un problème où les sélecteurs [!UICONTROL ClickTrack] n’étaient pas appliqués à la bonne page d’audience. (TGT-51871)

## [!DNL Target Standard/Premium] 25.3.4 (7 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème où les audiences d’activité unique n’étaient pas visibles dans le panneau [!UICONTROL Audiences], empêchant leur modification ou leur réutilisation. (TGT-51860)
* Correction d’un problème qui empêchait les clients [!DNL Target Standard] de créer des activités à l’aide des rapports [!UICONTROL Analytics for Target] (A4T). (TGT-51854)
* Correction d’un problème qui excluait les compteurs d’identifiants locaux de la payload lors des opérations de création et de modification par lots. (TGT-51867)

## [!DNL Target Standard/Premium] 25.3.2 (6 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel la copie d’une activité avec une audience d’activité unique ne permettait pas de créer une activité, utilisant par erreur l’audience de l’activité originale à la place. (TGT-51855)
* Correction d’un problème qui empêchait la modification des activités [!UICONTROL Experience Targeting] (XT) avec des audiences d’activité uniquement. (TGT-51846)
* Correction d’un problème en raison duquel le [!UICONTROL Visual Experience Composer] (VEC) n’appliquait pas correctement les modifications à une expérience lors de la première modification. (TGT-51843)
* Correction d’un problème qui déclenchait une erreur « ID » lors d’un clic sur certains éléments dans le VEC. (TGT-51814)
* Mise à jour de la gestion des erreurs dans le VEC lors de la création de l’activité. (TGT-51759)
* Correction d’un problème en raison duquel une vue manquante dans le panneau [!UICONTROL Modifications] provoquait une erreur « entrée utilisateur non valide » lors de l’enregistrement de l’activité. (TGT-51827)
* Correction d’un problème qui empêchait la création de critères de recommandation. (TGT-51834)
* Ajout d’un message de confirmation avant la redirection vers une autre URL. (TGT-51703)
* Correction de problèmes liés aux tests d’intégration de GraphQL dans les offres et les dossiers. (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1 (3 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Une audience combinée peut inclure des sous-groupes, chacun contenant plusieurs audiences. Cette version a corrigé un problème qui empêchait l’affichage des audiences de sous-groupe dans la boîte de dialogue [!UICONTROL Rules]. (TGT-51813)
* Correction d’un problème où certaines audiences d’expérience étaient remplacées par des [!UICONTROL All Visitors] lors de l’ouverture d’anciennes activités. (TGT-51812)
* Correction d’un problème qui empêchait la modification des activités avec des audiences d’activité uniquement. (TGT-51807)
* Correction d’un problème qui empêchait la modification des modifications d’en-tête de page dans l’interface utilisateur [!DNL Target] mise à jour. (TGT-51797)
* Correction d’une erreur « null » qui se produisait lors de la duplication d’une expérience, de la suppression d’une autre expérience, puis de la tentative d’enregistrement de l’activité. (TGT-51796)
* Correction d’un problème qui empêchait l’affichage des règles d’exclusion d’audience dans le panneau d’informations de l’audience lors de l’étape [!UICONTROL Targeting] de la création d’activités. (TGT-51579)
* Mise à jour des messages d&#39;erreur en coréen. (TGT-51701 et TGT-51699)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
