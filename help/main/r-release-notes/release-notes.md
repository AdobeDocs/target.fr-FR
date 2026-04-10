---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e2230782005110914dbf108a865463d1faaa62cc
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 56%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.4.3 (vendredi 9 avril 2026)

**Activités**

+++Afficher les détails

* **Emplacement manquant dans certaines activités.** Correction d’un problème en raison duquel **[!UICONTROL Location]** manquait dans certaines activités. (TGT-54951)

* **Ordre des colonnes des mesures de rapports.** L’interface [!DNL Target] mise à jour permet de réorganiser les mesures de rapports sans effacer la sélection complète et ajouter à nouveau des mesures dans l’ordre. Auparavant, les utilisateurs devaient désélectionner toutes les mesures et les sélectionner à nouveau dans l’ordre souhaité, ce qui prenait du temps lorsque de nombreuses mesures étaient activées et lors de l’ajustement du positionnement des colonnes pour limiter le défilement horizontal. (TGT-53044)

+++

<!--
**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## [!DNL Target Standard/Premium] 26.4.2 (mercredi 7 avril 2026)

**Activités**

+++Afficher les détails

* **Le code personnalisé est conservé lorsqu’il est appliqué à des vues supplémentaires.** Correction d’un problème en raison duquel le code personnalisé appliqué à un **[!UICONTROL View]** pouvait être supprimé lors de l’ajout ou de l’enregistrement de code personnalisé pour un autre **[!UICONTROL View]** du même **[!UICONTROL Activity]**. (TGT-53933)
+++

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes De Mise À Jour De &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
