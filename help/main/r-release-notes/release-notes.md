---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e3a22ef34bc78b03b71c75968d2271b9a634a0cd
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 46%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.5.1 (7 mai 2026)

**Intégrations**

+++Afficher les détails

* Gestion des **[!DNL Adobe Target]dans Experimentation Accelerator.** Ajout de la prise en charge de l’affectation d’espaces de travail [!DNL Target] aux sandbox Experimentation Accelerator afin que les équipes puissent afficher les expériences de [!DNL Adobe Target] dans Experimentation Accelerator à un seul endroit. [En savoir plus](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

## [!DNL Target Standard/Premium] 26.4.4 (28 avril 2026)

**Activités**

+++Afficher les détails

* **Erreur avec le filtre Audience dans les rapports.** Correction d’un problème en raison duquel la modification du filtre d’audience dans **[!UICONTROL Goals & Settings]** provoquait une erreur dans la section Création de rapports de l’interface utilisateur de [!DNL Target]. (TGT-55006)

* **Trier les activités par priorité.** Ajout du tri par priorité dans la liste des activités à l’aide de l’en-tête de colonne **[!UICONTROL Priority]**, avec un ordre croissant et décroissant cohérent avec les autres colonnes triables. (TGT-54948)

* **Les propriétés d’activité supplémentaires ne sont pas conservées après l’enregistrement.** Correction d’un problème en raison duquel certaines sélections de **[!UICONTROL Properties]** ne persistaient pas après l’enregistrement et la réouverture d’une activité. (TGT-53889)

+++

**Localisation**

+++Afficher les détails

* **Libellés japonais pour les opérateurs de règle [!UICONTROL Page Delivery].** Correction de chaînes illisibles ou corrompues pour les libellés d’opérateur de règle de diffusion de page dans l’interface utilisateur japonaise. (TGT-53097)

+++

**API**

+++Afficher les détails

* **Prise en charge de l’API Reporting [!DNL GraphQL] pour `segmentId`.** Ajout de `segmentId` à l’API Reporting [!DNL GraphQL]. (TGT-55021)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Afficher les détails

* **Modifications affichées sur une expérience incorrecte dans l’éditeur.** Correction d’un problème en raison duquel une suppression ou une autre modification pouvait apparaître sur la mauvaise expérience après le passage d’une expérience à l’autre dans le [!UICONTROL Visual Experience Composer]. (TGT-54955)

* **Modifications supprimées lors de la suppression de l’insertion HTML.** Correction d’un problème en raison duquel la suppression du bloc de **[!UICONTROL HTML]** supplémentaire ajouté avec **[!UICONTROL Insert before]** ou **[!UICONTROL Insert after]** supprimait également une modification liée qui n’avait pas de sélecteur CSS. (TGT-54530)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)




**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

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
| [Notes De Mise À Jour De ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
