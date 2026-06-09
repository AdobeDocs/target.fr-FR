---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 391653c7a45a48c311c6a6cff358bd077f8c47b7
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 41%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 26.6.1 (4 juin 2026)

**Activités**

+++Afficher les détails

* **URL d’activité incomplète dans [!UICONTROL Présentation de l’activité].** Correction d’un problème en raison duquel le [!UICONTROL Aperçu de l’activité] n’affichait pas l’URL complète d’une activité. (TGT-54029)

* **Format de date non localisé dans les rapports d’activité.** Correction d’un problème en raison duquel le format de date n’était pas localisé dans l’onglet **[!UICONTROL Rapports]** lorsque vous choisissiez une option **X derniers jours** dans la liste déroulante **[!UICONTROL Période prédéfinie]**. (TGT-51637)

* **Impossible d’enregistrer l’activité basée sur un formulaire avec certains caractères GB18030 dans [!UICONTROL Location].** Correction d’un problème en raison duquel vous ne pouviez pas enregistrer une activité basée sur des formulaires lorsque le champ **[!UICONTROL Emplacement]** contenait des caractères GB18030 spécifiques. (TGT-46980)

+++

**[!UICONTROL Audiences]**

+++Afficher les détails

* **Calendrier non localisé dans le flux Créer une audience pour le chinois simplifié et traditionnel.** Correction d’un problème en raison duquel le calendrier dans les champs **[!UICONTROL Début]** et **[!UICONTROL Fin]** des attributs **[!UICONTROL Période]** n’était pas localisé dans les paramètres régionaux Chinois simplifié (CHS) et Chinois traditionnel (CHT) pendant le flux Créer une audience. (TGT-50619)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* **Infobulles non localisées dans le créateur d’activités mis à jour.** Correction de problèmes de localisation en raison desquels les infobulles d’informations **[!UICONTROL Améliorations]** et **[!UICONTROL Contenu]** n’étaient pas localisées dans le créateur d’activités [!UICONTROL Compositeur d’expérience visuelle] mis à jour. (TGT-53721)

* **Non localisé [!UICONTROL Tous les visiteurs] dans [!UICONTROL Audiences d’expérience].** Correction d’un problème en raison duquel la chaîne **[!UICONTROL Tous les visiteurs]** dans **[!UICONTROL Audiences d’expérience]** dans le rail de gauche n’était pas localisée dans le [!UICONTROL Compositeur d’expérience visuelle]. (TGT-50086)

+++

**[!UICONTROL Rapports]**

+++Afficher les détails

* **Format de date non localisé dans la fenêtre [!UICONTROL Créer un paramètre prédéfini].** Correction d’un problème en raison duquel le format de date dans le champ **[!UICONTROL Période]** de la fenêtre **[!UICONTROL Créer un paramètre prédéfini]** n’était pas localisé. (TGT-49239)

+++

**Localisation**

+++Afficher les détails

* **GB18030 caractères affichés dans plusieurs zones.** Correction de problèmes en raison desquels certains caractères de zone d’utilisation privée s’affichaient incorrectement en tant que lettres dans les **[!UICONTROL Audience]** IU, **[!UICONTROL Administration]** > **[!UICONTROL Propriétés]**, configuration de fenêtre d’affichage mobile et notifications toast. (TGT-49622, TGT-49623, TGT-49624 ET TGT-49625)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour et une documentation détaillées via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

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
