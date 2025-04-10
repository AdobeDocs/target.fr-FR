---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour,mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2e3191da2ac21f51fa6e08af615659db1ccdd2d9
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 52%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 25.4.1 (2 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel les audiences d’expérience disparaissaient des activités . (TGT-52003)
* Correction d’un problème qui provoquait des éléments inattendus lors de la diffusion. (TGT-52011)
* Correction d’un problème qui empêchait les clients et clientes d’afficher l’audience dans le graphique de ciblage sur la page [!UICONTROL r] vue et lors de la modification de l’activité. (TGT-52050)
* Correction d’un problème qui empêchait les clients de réorganiser les expériences par ordre de priorité dans les activités [!UICONTROL Experience Targeting] (XT). (TGT-52054)
* Correction d’un problème qui provoquait un rendu incorrect lors de l’annulation de modifications de style de texte. (TGT-51876)
* Correction d’un problème en raison duquel, lors de la modification d’une offre de redirection, [!DNL Target] supprime également tous les sélecteurs de [!UICONTROL ClickTrack] associés à cette offre. (TGT-51936)
* Correction d’un problème en raison duquel [!DNL Target] enregistrait incorrectement le sélecteur lors de l’annulation du [!UICONTROL ClickTrack]. (TGT-51937)
* Correction d’un problème qui déclenchait une erreur de nom non valide après l’ouverture et la fermeture du sélecteur de mbox sur la page [!UICONTROL Goals & Settings] sans apporter de modifications. (TGT-51983)
* Correction d’un problème qui bloquait la modification des offres ad hoc créées dans l’interface utilisateur de [!DNL Target] héritée. (TGT-51984)
* Correction d’un problème qui bloquait les activités de modification comportant des offres ad hoc contenant du code personnalisé. (TGT-51995)
* Correction d’un problème en raison duquel les règles d’exclusion s’affichaient en tant que règles d’inclusion lors de la modification des définitions d’audience combinées. (TGT-51999)
* Correction d’un problème qui empêchait l’affichage correct du code personnalisé lors de l’édition de l’expérience. (TGT-52005)
* Correction d’un problème qui rendait l’option [!UICONTROL Insert Before] indisponible pour insérer du contenu avant la barre de navigation. (TGT-52031)
* Correction d’un problème qui empêchait la mise en surbrillance correcte de l’expérience par défaut dans les rapports. (TGT-51716)
* Correction d’un problème qui déclenchait un message `default message [Invalid optionLocalIds: xx]]` lors de la création d’une activité. (TGT-52038)

## at.js version 2.11.8 (31 mars 2025)

* Résolution d’une vulnérabilité identifiée par CodeQL dans la validation du suffixe de chaîne pour empêcher les cas Edge lors des opérations de redimensionnement et de déplacement. (TNT-51516)

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
