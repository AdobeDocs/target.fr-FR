---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ[!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’[!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’[!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: 'https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: c5abb976-5170-45d6-bcac-66d15d10a4d4
    internal-label: Release notes
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ece061af0f50ec45e07b9710d355a9c91731578e
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 42%
---
# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 26.10.2 (15 octobre 2026)

**[!UICONTROL Activités]**

+++Afficher les détails

* **Paramètres d’objectif incorrects affichés dans la Présentation de l’activité**. Correction d’un problème en raison duquel les paramètres d’objectif affichés sur la page **[!UICONTROL Aperçu]** d’une activité étaient incorrects. Par exemple, `https://` a été ajouté à l’URL de la page et la condition **[!UICONTROL URL contains]** n’a pas été affichée, même si la configuration de l’objectif réel était correcte. (TGT-56326)

+++

**[!UICONTROL Recommandations]**

+++Afficher les détails

* **Recommandations de sauvegarde affichées après la mise à jour d’une promotion dans une activité dynamique**. Correction d’un problème en raison duquel la modification d’une promotion dans une activité Live [!DNL Recommendations] entraînait la création par les [!DNL Target] de nouvelles promotions et de nouvelles unités de recommandation même si leur définition n’avait pas changé. (TGT-56369)

+++

**[!UICONTROL Rapports]**

+++Afficher les détails

* **Préréglages de création de rapports supprimés après deux semaines**. Correction d’un problème en raison duquel les paramètres prédéfinis de création de rapports enregistrés pour une activité étaient automatiquement supprimés après environ deux semaines. (TGT-56374)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* **Ajout de la prise en charge de Safari à[!DNL Adobe Target]**. [!DNL Target] est désormais pris en charge dans le navigateur [!DNL Safari]. Notez que le compositeur d’expérience visuelle et le [!DNL Enhanced Experience Composer] ne sont pas pris en charge dans [!DNL Safari]. Par conséquent, un recouvrement apparaît désormais dans le [!DNL VEC] pour informer les utilisateurs qu’ils doivent passer à [!DNL Chrome] pour utiliser l’éditeur. (TGT-55853)
  [En savoir plus](../c-experiences/c-visual-experience-composer/visual-experience-composer.md#browser-requirements)
+++


## [!DNL Target Standard/Premium] 26.10.1 (13 octobre 2026)

**[!UICONTROL Analytics for Target]**

+++Afficher les détails

* **La création de rapports A4T échoue avec une erreur « Un problème est survenu »**. Correction d’un problème en raison duquel les activités [!DNL A4T] utilisant une suite de rapports nouvellement ajoutée affichaient une erreur « Un problème est survenu » dans le rapport [!DNL Target] au lieu des résultats. Cliquer sur **[!UICONTROL Afficher dans Analytics]** affichait également un message « Suite de rapports incompatible » avec des informations de classification de [!DNL Analytics for Target] manquantes. (TGT-56389)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* HTML brute affichée à la place du nom de l’offre pour les [!DNL Experience Fragments] diffusés via une mbox **.** Correction d’un problème en raison duquel le panneau **[!UICONTROL Modifications]** affichait l’HTML/le code brut au lieu du nom de l’offre lorsqu’une [!DNL Experience Fragment] était diffusée via une mbox. (TGT-56241)

+++

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
| [Notes De Mise À Jour D’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
