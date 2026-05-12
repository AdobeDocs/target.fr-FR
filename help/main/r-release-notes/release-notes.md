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
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 42%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).


## Dernières mises à jour - 12 mai 2026

**[!DNL Adobe Target]du serveur MCP (Public Beta)**

[!DNL Adobe Target] fournit désormais un serveur MCP (Model Context Protocol) qui surfacique les opérations d’expérimentation, de personnalisation et de création de rapports directement dans toute application compatible MCP. Grâce à cette intégration, les personnes spécialisées dans le marketing et la technologie peuvent inspecter les tests A/B, analyser les rapports de performances, gérer les audiences et les offres, et prendre des mesures gouvernées, le tout à l’aide d’invites en langage naturel au lieu de parcourir plusieurs écrans d’interface utilisateur ou d’écrire des requêtes sur l’API REST [!DNL Adobe Target]. Cette fonctionnalité est actuellement disponible dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**.

Cette fonctionnalité est disponible pour tous les clients dans Public Beta.

Pour plus d’informations, voir [[!DNL Adobe Target] Serveur MCP](../c-integrating-target-with-mac/mcp/target-mcp.md).


## [!DNL Target Standard/Premium] 26.5.1 (7 mai 2026)

**Intégrations**

+++Afficher les détails

* Gestion des **[!DNL Adobe Target]dans Experimentation Accelerator.** Ajout de la prise en charge de l’affectation d’espaces de travail [!DNL Target] aux sandbox Experimentation Accelerator afin que les équipes puissent afficher les expériences de [!DNL Adobe Target] dans Experimentation Accelerator à un seul endroit. [En savoir plus](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

**Activités**

+++Afficher les détails

* **[!UICONTROL Graph View]désynchronisé du tableau et du téléchargement.** Correction d’un problème en raison duquel les rapports d’activité pouvaient afficher des mesures manquantes ou nulles dans les **[!UICONTROL Graph View]** pour certaines périodes, même si les valeurs affichées dans les rapports **[!UICONTROL Table View]** et téléchargés étaient toujours correctes. (TGT-54998)

+++

**[!UICONTROL Audiences]**

+++Afficher les détails

* **La liste d’utilisation de l’audience n’est pas entièrement rendue.** Correction d’un problème en raison duquel la section **[!UICONTROL Usage]** dans les détails de l’audience ne pouvait afficher qu’un sous-ensemble d’activités mappées même si des activités supplémentaires étaient associées à cette audience. (TGT-55094)

+++

**[!UICONTROL Administration]**

+++Afficher les détails

* **Confirmation plus claire pour l’obscurcissement de l’adresse IP du dernier octet.** Lorsque vous modifiez **[!UICONTROL Obfuscate Visitor IP addresses]** en **[!UICONTROL Last octet]** dans **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**, la boîte de dialogue de confirmation explique désormais que [!DNL Target] masque le dernier octet de l’adresse IP du visiteur. (TGT-44821)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Afficher les détails

* **Page vierge ou incomplète avec le Enhanced Experience Composer (EEC).** Correction d’un problème en raison duquel le [!UICONTROL Visual Experience Composer] ne pouvait pas charger le site dans l’éditeur lorsque **[!UICONTROL Enhanced Experience Composer]** était activé. (TGT-54576)

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
| [Notes De Mise À Jour De &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
